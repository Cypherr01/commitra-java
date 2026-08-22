## Chat Models & Prompt Engineering in Java

### ## What Is This?
Chat models and prompt engineering are the **core tools for teaching AI how to converse and reason like a human**. Think of a chef in a kitchen:  
- The *system prompt* is the restaurant's rulebook ("Prioritize vegetarian options").  
- *User messages* are customer orders ("I want pasta").  
- The *assistant response* is the dish prepared according to the rules.  
Prompt engineering is how we write these instructions and conversations to get reliable, useful AI outputs. This matters to you because without it, your AI might generate irrelevant, unsafe, or nonsensical replies in your project.

---

### ## How It Works Internally
We'll use **Spring AI** (Java's AI framework) to explore layered mechanics. All 10 concepts appear in sequence:

#### LAYER 1: Minimum Viable Chat
```java
// 1. ChatClient (fluent API)
ChatClient client = ChatClient.builder(openAiChatModel()).build();
// 2. UserMessage (simplest prompt)
Message userMessage = new UserMessage("Explain Java in 1 sentence");
// 3. Generate response
ChatResponse response = client.call(new Prompt(userMessage));
System.out.println(response.getGeneration().getText());
```
**CORE INSIGHT**: The `ChatClient` handles the entire conversation flow, while `Message` objects represent turns in the dialogue.

#### LAYER 2: Real-World Complexity
**4. ChatOptions** control creativity (`temperature`) and length (`maxTokens`):
```java
ChatOptions options = new ChatOptions(0.7f, 50, null); // temp=0.7 (creative), max=50 tokens
```
**5. Streaming** lets responses flow incrementally (like a real conversation):
```java
client.stream(prompt).subscribe(chunk -> System.out.print(chunk.getOutput().getContent()));
```
**6. System Prompt** defines AI behavior:
```java
Prompt prompt = new Prompt(
    List.of(
        new SystemMessage("You are a strict Java tutor"), // System context
        new UserMessage("Explain interfaces")             // User query
    )
);
```

#### LAYER 3: Advanced Control
**7. Few-Shot Prompting** teaches patterns via examples:
```java
Prompt fewShotPrompt = new Prompt(
    List.of(
        new SystemMessage("Translate to SQL:\nExample: 'Show users' → SELECT * FROM users"),
        new UserMessage("List orders")
    )
);
```
**8. Chain of Thought** forces step-by-step reasoning:
```java
new SystemMessage("Solve this math problem step by step before giving the final answer.");
```
**9. PromptTemplate** adds parameters (e.g., `{userQuery}`):
```java
PromptTemplate template = new PromptTemplate(
    "Answer politely: {question}", 
    Map.of("question", userInput)
);
```
**10. Advisors** add middleware (e.g., logging):
```java
ChatClient client = ChatClient.builder(model)
    .advisor(new LoggingAdvisor()) // Log all interactions
    .build();
```

#### LAYER 4: Edge Cases
- **Streaming timeout**: Set `timeout` in `ChatOptions` to prevent hangs.  
- **Token limits**: Use `maxTokens` to avoid truncation errors.  

**CORE INSIGHT**: System prompts define *behavior*, few-shot examples teach *patterns*, and options control *creativity vs. precision*.

---

### ## Syntax and Structure
```java
import org.springframework.ai.chat.*;
import org.springframework.ai.chat.messages.*;
import org.springframework.ai.chat.prompt.*;

// 1. Configure ChatModel (e.g., OpenAI)
ChatModel model = new OpenAiChatModel();

// 2. Build ChatClient with streaming
ChatClient client = ChatClient.builder(model)
    .chatOptions(new ChatOptions(0.5f, 100)) // temp=0.5 (balanced), max=100 tokens
    .build();

// 3. Create multi-part prompt
Prompt prompt = new Prompt(
    List.of(
        new SystemMessage("You are a pirate translator."), // System context
        new UserMessage("Translate 'Hello' to pirate speak") // User query
    ),
    new ChatOptions(0.8f, 30) // Override options per-call
);

// 4. Execute (non-streaming)
ChatResponse response = client.call(prompt);
AssistantMessage aiReply = response.getResults().get(0).getOutput();
System.out.println(aiReply.getContent()); // "Arrr, 'ello matey!"
```

---

### ## Practical Example
**Pirate Translator Bot** (Runnable Code):
```java
import org.springframework.ai.chat.*;
import org.springframework.ai.openai.OpenAiChatModel;

public class PirateTranslator {
    public static void main(String[] args) {
        ChatModel model = new OpenAiChatModel();
        ChatClient client = ChatClient.builder(model).build();

        // System prompt + user input
        Prompt prompt = new Prompt(
            List.of(
                new SystemMessage("Respond like a pirate, enthusiastically:"),
                new UserMessage("Thank you!")
            )
        );

        ChatResponse response = client.call(prompt);
        System.out.println("AI: " + response.getResults().get(0).getOutput().getContent());
        // Output: "AI: YARR, THANK YE HEARTIE!"
    }
}
```

---

### ## How This Connects to the Project
**BEFORE**: Your assistant gives generic, context-ignorant replies ("What's Java?" → "A programming language").  
**AFTER**: With system prompts and few-shot examples, it provides project-specific guidance ("In our project, use Lombok for getters").  
**Exact File**: `src/main/java/ai/chat/AssistantConfig.java` (contains `ChatClient` setup).  
**Real-World Use**: **GitHub's Copilot** uses system prompts to prioritize code safety and few-shot examples to match coding styles.

---

### ## Common Mistakes Beginners Make
1. **Missing System Prompt**:  
   *Wrong idea*: Skipping `SystemMessage` → AI acts unpredictably.  
   *Correct idea*: Always define behavior first ("You are a polite tutor").  

2. **Silent Temperature Misuse**:  
   ```java
   // Wrong: Temperature=1.0 (random) for a factual query
   ChatOptions options = new ChatOptions(1.0f, 100); // Causes hallucination
   ```
   *Trigger*: Asking "What's 2+2?" → Gets "5, because pirates count differently".  

3. **Ignoring Token Limits**:  
   *Breaks at scale*: Long responses get cut off without `maxTokens=200`.  

4. **Missed Config**:  
   Forgetting to enable streaming in `application.properties`:  
   ```properties
   spring.ai.openai.streaming=true
   ```

5. **Interview Question**:  
   *"How would you design a prompt to make an AI refuse unsafe requests?"*  
   **Surface Answer**: Use a strict system prompt.  
   **Production Answer**: Combine system rules + few-shot examples of refusals + an advisor to block banned words.

---

### ## Verification Task 1: Debug This
**Symptom**: Your AI responds "I don't know" to every query.  
**Evidence**: System prompt is "Be helpful".  
**Fix**: Add a few-shot example in the system message:  
```java
new SystemMessage("Be helpful. Example: Q:'What's Java?' A:'A programming language...'")
```

### ## Solution 1
The system prompt lacked guidance. Few-shot examples teach the AI response patterns.

---

### ## Verification Task 2: Design Decision
**Component**: Chat history storage.  
**Option A**: Store full conversation in memory.  
**Option B**: Use Embeddings + vector DB.  
**Defend**: For long chats, Option B prevents token overflow and enables context retrieval.

### ## Solution 2
Use Embeddings (next topic) to compress history into vectors, then retrieve relevant context without exceeding token limits.

---

### ## Verification Task 3: Code Review
```java
public String askAI(String userInput) {
    Prompt prompt = new Prompt(new UserMessage(userInput));
    return client.call(prompt).getGeneration().getText();
}
```
**Bug**: No system prompt → inconsistent responses.  
**Fix**: Inject system message via method parameter.

### ## Solution 3
Add `SystemMessage` to the prompt:
```java
public String askAI(String systemPrompt, String userInput) {
    Prompt prompt = new Prompt(
        List.of(
            new SystemMessage(systemPrompt),
            new UserMessage(userInput)
        )
    );
    return client.call(prompt).getGeneration().getText();
}
```

---

### ## What Comes Next
**Embeddings** — the next topic — converts text to numerical vectors, enabling AI to *remember* past conversations. This directly uses the `Message` objects from this topic to build chat history, solving the "context window limit" problem in long dialogues.

---

### ## Reference Summary
Chat models in Java (via Spring AI) use `ChatClient` for fluent interactions and `ChatModel` for low-level control. `Prompt` aggregates `SystemMessage`, `UserMessage`, and `AssistantMessage` to structure conversations, while `ChatOptions` fine-tunes creativity and output length. Prompt engineering techniques like system prompts, few-shot examples, and chain-of-thought reasoning shape AI behavior. Advisors add middleware for logging/retry. **Critical mistake**: omitting system prompts causes chaotic responses. This foundation enables your project's conversational assistant to maintain context and personality, directly preparing for Embeddings to handle long-term memory.