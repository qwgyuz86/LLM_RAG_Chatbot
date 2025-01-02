# Multilingual_LLM_RAG_Chatbot

## Chatbot Technical Details:

#### Model: llama3-8b-chinese-chat-ollama-q4(8B parameters)
#### Dataset: Hugging Face Hub "MakTek/Customer_support_faqs_dataset"
#### Embedding: Hugging Face Hub "hkunlp/instructor-large"
#### Vector Database: Chroma
#### Retrieval Search Type: Maximal Marginal Relevance (MMR)
#### Language Supported: Multilingual, support most major languages
#### Device: CUDA GPU
#### Prompt:
LLM is told that it is a customer representative from ABC-company and to use chat history and RAG context to answer questions.
If it does not know the answer, it is told to say it does not know and tell user to contact human service
#### Memory:
Chat memory is fed into the input so that the chatbot is aware of the context of the conversation.
However, as the chat history gets long, it becomes confused. It is a limitation of this simple demo.
#### Temperature: 0.1
The chatbot is not encouraged to be creative but use factual answers provided in retrieval results.

#### Good Testing Question Example:
- Who is this?
    - The answer should show the role assigned in prompt is working.
- How do I go to Mars?
    - The answer should show that when asked about things it doesn't know or irrelevant, it knows it should refer users to human service.
- Start the inquiry with: Can I talk to someone? Followed by next query: When can I do that?
    - This question pair should show that the chatbot has memory and it can understand what it means by "that".
- Other typical customer support questions:
    - Can I request a refund? （or in chinese： 我可以申請退款嗎？）
    - How do I track my order? （or in chinese： 怎樣查找我的訂單？）
    - Or feel free to enter questions in French, Japanese, Spanish etc...
