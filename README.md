# WhatsLLaMA
Project for the `Essentials in NLP` Blockweek at UZH with the subtitle: Exploring Strategies for Enhancing Swiss German Performance: Prompt Engineering and Fine-tuning Techniques

## Overview
This project aims to enhance the performance of Large Language Models (LLMs) in generating Swiss German text. Swiss German is not a single language but a collection of dialects, each characterized by different uses of words and grammar. The challenges of this language diversity, along with the lack of easily accessible training data, make it difficult for LLMs, such as GPT-4 or LLaMA2, to generate dialect-specific Swiss German text. This project seeks to enhance the generation of text in my specific dialect, and evaluate the feasibility of imitating my Swiss German writing style using fine-tuning and prompt engineering methods. 

## Dataset

The dataset for this project comprises my personal WhatsApp chats. The data set has 453,948 messages from personal chats and two group chats and is structured in the ALPACA format. Owing to privacy concerns, this dataset will not be released. 

## Model Enhancement

Two techniques are used to enhance the language models in producing Swiss German text:

### Fine-tuning

Fine-tuning is a method through which the model is adjusted to perform a specific task more accurately. In this process, the weights, or parameters of the model, are adjusted based on a targeted dataset. The model used for fine-tuning in this project is LLaMA2.

### Prompt Engineering

Prompt engineering is a technique used to guide model outputs in a desired direction. It's a less resource-intensive option than fine-tuning, as it doesn't involve changes to the model's weights. The prompt created for this project guides the model to continue the conversation as me. For this task, the GPT-4 model is used. 

## Evaluation

The evaluation was conducted in a quantitative manner, by asking friends(n=13) of the author to rank the output of multiple models according to their likelihood that they were written by the author. The five models in below table were prompted to continue four conversations that were not in the training set.
| Model                           | Description                                                         |
|---------------------------------|---------------------------------------------------------------------|
| gpt4-no-data                    | ChatGPT with a prompt to only respond in Swiss German. (Zero-Shot)               |
| gpt4-prompt-data                | ChatGPT with a prompt that has some examples of my dialet (Few-Shot)  |
| Llama-2-7b-chat-hf-whatsllama   | Fine-tuned Llama-2-7b-chat-hf on my messages                        |
| Llama-2-7b-german-assistant-v3  | Fine-tuned Llama-2-7b-chat-hf on German language                    |
| Llama-2-german-whatsllama       | Fine-tuned Llama-2-7b-german-assistant-v3 on my messages            |

### Conclusion
The evaluation demonstrated that no model was able to deceive the participants over all questions. In the feedback provided the participants mentioned that often the models were producing to long sentences, while the author uses a "minimal" word style. The GPT-4 model, despite being showed
only a relatively small sample of the author’s messages, outperformed others. It showcased a good understanding of the message context. Although the vast difference in parameters of GPT-4 compared to the 7B should be mentioned.
Attempts to further fine-tune an already German-specific llama model to enhance performance did not yield positive results in our scenario. While the model’s responses often mirrored the author’s vocabulary, a consistent understanding of the input was lacking



![evalution-summary](https://github.com/theoliver7/uzh-essentials-nlp/assets/10463395/99dc59a4-916d-4496-98be-12e97ab8f15e)


## Future Work

There is potential for further work in this area. Improvements could be made to the dataset, there is the possibility of exploring larger models and running the models against known benchmarks to gain further insight into their performance.
