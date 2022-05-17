## BERT, which stands for Bidirectional Encoder Representations from Transformers.  

---

There are two existing strategies for applying pre-trained language representations to downstream tasks: feature-based and fine-tuning. 

The feature-based approach, such as ELMo (Peters et al., 2018a), uses task-specific architectures that include the pre-trained representations as additional features. 

The fine-tuning approach, such as the Generative Pre-trained Transformer (OpenAI GPT) (Radford et al., 2018), introduces minimal task-specific parameters, and is trained on the downstream tasks by simply fine-tuning all pretrained parameters.   



## Bert = Transformer + Bidirectional 

**B**idirectional **E**ncoder Representations from **T**ransformers.  



![image-20220517114519938](C:\Users\12630\Desktop\essay_reading\assest\image-20220517114519938.png)



### Two steps in our framework: pre-training and fine-tuning.   

- pre-training:

To make BERT handle a variety of down-stream tasks, our input representation is able to unambiguously represent both a single sentence and a pair of sentences (e.g., < Question, Answer >) in one token sequence.  

method : WordPiece embeddings  

![image-20220517115229903](C:\Users\12630\Desktop\essay_reading\assest\image-20220517115229903.png)

Task #1: Masked LM  

Task #2: Next Sentence Prediction (NSP)  

details in essay 3.1 3.2



- fine-tuning:

For each task, we simply plug in the taskspecific inputs and outputs into BERT and finetune all the parameters end-to-end. 



At the input, sentence A and sentence B from pre-trainingare analogous to 

(1) sentence pairs in paraphrasing

(2) hypothesis-premise pairs in entailment

(3) question-passage pairs in question answering 

(4) a degenerate text-? pair in text classification or sequence tagging. 



At the output, the token representations are fed into an output layer for tokenlevel tasks, such as sequence tagging or question answering, and the [CLS] representation is fed into an output layer for classification, such as entailment or sentiment analysis.  



## Conclusion

Major contribution is further generalizing these findings to **deep bidirectional architecture**s, allowing the same pre-trained model to successfully tackle a broad set of NLP tasks.  