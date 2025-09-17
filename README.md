# langchain-tutorial
test change
## A. Tutorials
### [Tool calling](https://python.langchain.com/docs/concepts/tool_calling/)
- 
## B. How-to guides
## C. Conceptual guide
1. Chat models
- Large Language Models (LLMs) are advanced machine learning models that excel in a wide range of language-related tasks such as text generation, translation, summarization, question answering, and more, without needing task-specific fine tuning for every scenario.
- LangChain provides a consistent interface for working with chat models from different providers
  - Integrations with many chat model providers.
  - Use either LangChain's messages format or OpenAI format.
  - Standard tool calling API.
  - Standard API for structuring outputs.
  - etc
- **Key methods**
  - *invoke*: It takes a list of messages as input and returns a list of messages as output.
  - *stream*: Stream the output of a chat model as it is generated.
  - *batch*: Batch multiple requests to a chat model for more efficient processing.
  - *bind_tools*: Bind a tool to a chat model for use in the model's execution context.
  - *with_structured_output*: A wrapper around the invoke method for models that natively support structured output.

2. Messages
- Messages are the unit of communication in chat models. They are used to represent the input and output of a chat model, as well as any additional context or metadata that may be associated with a conversation.
- Each message has a role (e.g., "user", "assistant") and content (e.g., text, multimodal data) with additional metadata that varies depending on the chat model provider.
- A message consists the following pieces of information:
  - *Role*: The role of the message (e.g., "user", "assistant").
  - *Content*: The content of the message (e.g., text, multimodal data).
  - Additional metadata: id, name, token usage, etc.

**Role**

Roles are used to distinguish between different types of messages in a conversation and help the chat model understand how to respond to a given sequence of messages.

|Role|Description|
|--|--|
|system|Used to tell the chat model how to behave and provide additional context. Not supported by all chat model providers.|
|user|Represents input from a user interacting with the model, usually in the form of text or other interactive input.|
|assistant|Represents a response from the model, which can include text or a request to invoke tools.|
|tool|A message used to pass the results of a tool invocation back to the model after external data or processing has been retrieved. Used with chat models that support tool calling.|
|fuction|This is a legacy role, corresponding to OpenAI's legacy function-calling API. tool role should be used instead.|
