# Conversational-Memory-in-LLMS

This repository explores the concept of conversational memory within Language Models (LLMs). Conversational memory refers to the ability of a model to retain and utilize information from previous interactions during a conversation.

In this research, we use LangChain and OpenAI's GPT-3 model as a case study to demonstrate different conversational memory techniques. The primary focus is on understanding how various memory strategies can enhance the conversational capabilities of language models.

## Installation

You can install the required packages by running the following command:

#### pip install -qU langchain openai tiktoken

## Setting Up OpenAI API

To use OpenAI's GPT-3 model, you will need to set up your API key. Run the following code and enter your API key when prompted:

#### from getpass import getpass

#### OPENAI_API_KEY = getpass()

## Conversational Memory Techniques

### ConversationBufferMemory

The ConversationBufferMemory keeps a buffer of previous conversation excerpts as part of the context in the prompt.

### ConversationSummaryMemory

The ConversationSummaryMemory keeps the previous pieces of conversation in a summarized form, where summarization is performed by an LLM.

### ConversationBufferWindowMemory

The ConversationBufferWindowMemory retains a few of the last interactions in memory but intentionally drops the oldest ones, acting as short-term memory. You can control the window size with the 'k' parameter.

### ConversationKnowledgeGraphMemory

The ConversationKnowledgeGraphMemory creates a knowledge graph of all entities mentioned in the interactions, along with their semantic relationships.

## Memory Analysis

You can analyze the conversation memory length for each memory type using Tiktoken:

import tiktoken

tokenizer = tiktoken.encoding_for_model('text-davinci-003')
print(
    f'Buffer memory conversation length: {len(tokenizer.encode(conversation_buf.memory.buffer))}\n'
    f'Summary memory conversation length: {len(tokenizer.encode(conversation_sum.memory.buffer))}\n'
    f'Buffer window memory conversation length: {len(tokenizer.encode(bufw_history))}\n'
     )

## Conclusion

This research demonstrates the importance of conversational memory techniques in enhancing the capabilities of Language Models. Different memory types can be employed to improve a model's ability to recall and utilize context during a conversation. Understanding and utilizing these memory techniques can lead to more meaningful and coherent interactions with language models.

## Credits

### LangChain
### OpenAI
### Tiktoken

## Contact

If you have any questions or suggestions, please feel free to contact us via email or open an issue on this repository.

### Enjoy your research on conversational memory in LLMS!





