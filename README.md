# RAG for Psychological Applications
### Description
This project leverages Retrieval-Augmented Generation (RAG) to answer psychological questions and classify mental disorders based on renowned DSM-5 book. By combining the power of large language models with domain-specific datasets, the model provides accurate and relevant responses to specialized queries in the field of psychology.
#Usage
To use the project, follow these steps:

Run each cell in the notebook file sequentially till the cell with questions then there you can ask your question from the the RAG. by editing the prompt written for the LLM you can recieve different answers.

The model will process the input and provide responses based on the combined data from the large language model and the domain-specific dataset.
## Pipeline Architecture and Models
The proposed pipeline architecture is as follows:

1. **Input**: The user provides a scenario in Persian as input to the system, referred to as the Question.
2. **Translation to English**: The user’s scenario or question is translated from Persian to English using the OpenAI API with the mini-O-4GPT model.
3. **Retrieval**: The user’s question is compared with indexed vectors of document chunks in the database. The relevant chunks are retrieved using the Database Vector with the Similarity Score criterion, extracting and returning the top 5 chunks related to the question.
4. **Response Generation**: The Phi-3-mini-128k-instruct model from Microsoft is used as the LLM to generate the output.
5. **Translation to Persian**: The generated English response is translated back to Persian using the OpenAI API with the mini-O-4GPT model.

### Encoder Models
Two different encoder models were used to convert data chunks into vector embeddings:

1. gte-small
2. all-MiniLM-L6-v2

### Retrieval and Reranker Models
Two different methods were used for retrieval based on our vector databases:

- **Classification Method**: Uses a custom-built vector database to extract the closest chunks to the user’s question based on keywords and descriptions of sub-disorders, generating the output with the LLM.
- **RAG Method**: Uses the DSM-5 book vector database to find the closest chunks to the user’s question, generating responses based on the book and the LLM’s generative power.

For ranking the retrieved chunks based on their similarity to the user’s question, the colbertv2.0 model was used as the reranker.

### Generation Models
Several models were tested for the generation phase, with the best performance in terms of feasibility and accuracy being the Phi-3-mini-128k-instruct model from Microsoft. Smaller LLMs like Phi-3 were preferred over larger models like Llama-8B due to GPU constraints and their good performance. Models like bloom-3b, opt-2.7b, and Phi-3-mini-128k-instruct were used, with the latter performing the best.

### Contact
For any questions or inquiries, please contact the project maintainers:
Seyed Mohammadreza Hosseini: smr.hosseini@ce.sharif.edu
Amirhossein Alishahi: a.h.alishahi.cs@gmail.com
Amir Mohammad Ezzati: iamirezzati@gmail.com
Morteza Shahrabi Farahani: morteza.shahrabii@gmail.com
Vahid Moghimi: Vahidmoghimi@rocketmail.com
Farhan Saravand: farhansaravand@gmail.com
