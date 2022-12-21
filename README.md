### Pre-Trained Chatbot TensorFlow.js Model

![Example output of the code](https://github.com/nadidebeyza/nlp-chatbot-tensorflowjs/blob/main/demo/1.png "Example output of the code")

**The Tools Used**

In our project, we used the Tensorflow library. Tensorflow has a pre-trained model called “qna” which gives answers to questions of a given text. The model has trained with SQuAD (Stanford Question Answering Dataset) dataset which contains articles from Wikipedia and question-answer pairs with them. It also uses BERT transformers.

We used npm to import the Tensorflow qna model. With the code below, we load the model.

    answersOutput = document.getElementById('answer');
    inputText = document.getElementById('input-text');
    questionText = document.getElementById('question');
    model = await qna.load();
  
With model.findAnswers, we give questions and content as input parameters and get answers to these questions with a confidence level. We then display answers on the box.

     model.findAnswers(questionText.value, inputText.value).then((answers) => {
       const ans = answers.map((answer) => `${answer.text}`);
       const conf = answers.map((answer) => `(confidence: ${answer.score})`);
       const ans_conf = answers.map((answer) => `${answer.text} (confidence: ${answer.score})`);        
       colect.push(ans_conf)
        
       const answersList = answers.map((answer) => `<li>${answer.text} (confidence: ${answer.score})</li>`)
         .join('<br>');
          
The user can upload a text file into the interface.

After uploading the file, the user can ask a question about the given paragraph. Then the bot will return the answers with the highest matching scores. The user can also download the chat archive as a .json file and download all possible answers as a .txt file including lower accuracy.

![Example output of the code](https://github.com/nadidebeyza/nlp-chatbot-tensorflowjs/blob/main/demo/2.png "Example output of the code")

![Example output of the code](https://github.com/nadidebeyza/nlp-chatbot-tensorflowjs/blob/main/demo/3.png "Example output of the code")

![Example output of the code](https://github.com/nadidebeyza/nlp-chatbot-tensorflowjs/blob/main/demo/4.png "Example output of the code")

![Example output of the code](https://github.com/nadidebeyza/nlp-chatbot-tensorflowjs/blob/main/demo/5.png "Example output of the code")

![Example output of the code](https://github.com/nadidebeyza/nlp-chatbot-tensorflowjs/blob/main/demo/6.png "Example output of the code")

**References**

- “@tensorflow-models/qna” NPMJS,
https://www.npmjs.com/package/@tensorflow-models/qna?activeTab=readme
(accessed Dec. 18, 2022).
- Aditya Malte, P. R. (2019) Evolution of Transfer Learning in Natural Language
Processing. Retrieved from researchgate.net:
- Question Answering Chatbot for Troubleshooting Queries based on Transfer Learning.25th International Conference on Knowledge-Based and Intelligent Information & Engineering Systems, Alcatel-Lucent Enterprise, ALE International, 32, avenue Kleber 92700 Colombes, Paris
- Transformer models used for text-based question answering systems, Khalid Nassiri1Moulay Akhloufi, 29 July 2022
- Ruder, S. (2019) Neural Transfer Learning for Natural Language Processing, Sebastian Ruder February 2019, NATIONAL UNIVERSITY OF IRELAND, GALWAY
