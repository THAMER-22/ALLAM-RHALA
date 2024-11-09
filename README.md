# ALLAM && Rahala

The Nexta Allam is an advanced conversational system designed to provide seamless audio-based interaction. It takes an audio message as input, processes it through multiple steps, and returns a spoken response. Here's a step-by-step breakdown of how the Allam Pipeline works:

##### Audio-to-Text Conversion: 
The pipeline begins by converting the user's audio input into text. This is achieved using state-of-the-art automatic speech recognition (ASR) technology, which transcribes spoken language with high accuracy.
##### Language Processing with an LLM: 
Once transcribed, the text is passed to a large language model (LLM) that interprets the message and generates a relevant response. The LLM leverages extensive training data to understand context, answer questions, and engage in natural dialogue.
##### Embedding-based Processing: 
At certain stages, the pipeline also utilizes embeddings, which are vector representations of language data. Embeddings help the system grasp deeper meanings, detect similar phrases, or connect related concepts, enhancing the relevance and accuracy of responses.
##### Text-to-Audio Conversion: 
Finally, the generated text response is converted back into an audio format using text-to-speech (TTS) technology, allowing the system to respond verbally.

The Allam Pipeline thus offers an end-to-end solution for voice interactions, combining ASR, embeddings, LLM-based natural language processing, and TTS to create an intuitive, voice-driven experience.

### Requirements

```
pip install -r requirement.txt
```

### Allam Input/output Details.
* Input: Input will come from front end in the form of audio message. Sample input audio [message](https://github.com/Nexta-sa/ALLAM/blob/main/sample/WhatsApp%20Audio%202024-11-04%20at%202.24.58%20AM.mp4).
* Output: The Nexta ALLAM code will take input audio message and save output audio file. Sample output audio [file](https://github.com/Nexta-sa/ALLAM/blob/main/sample/llm_output_speech.mp3). This audio message will be send back to front end.

### Allam Input/Output Path Settings.
* Input: You can set input file [here](https://github.com/Nexta-sa/ALLAM/blob/main/src/allam.py#L35)
* Output: You can set output file [here](https://github.com/Nexta-sa/ALLAM/blob/main/src/allam.py#L35)

### Allam Code Details.
* src/allam.py: Main file where we can set input audio and output audio paths. It also contain main function of entire process.
* src/utils.py: File contains all the helpfull functions for our Nexta ALLAM pipeline.
* src/prompt_document.py: In this file we can change system prompt easily and also we can add more documnets if we want.

### Command to run the Allam pipeline
```
python src/allam.py
```

### Rahaala Input/output Details.
* Input: Input will come from front end in the form of text.
* Output: The Nexta rahaala code will reply in text.

### Rahaala Input/Output Path Settings.
* Input: You can set input text [here](https://github.com/Nexta-sa/ALLAM/blob/rahaala/src/rahaala.py#L30)
* Output: You can take output text [here](https://github.com/Nexta-sa/ALLAM/blob/rahaala/src/rahaala.py#L32)

### Rahaala Code Details.
* src/rahaala.py: Main file where we can send questions and get answer. It also contain main function of entire process.
* src/helper_rahaala.py: File contains all the helpfull functions for our Nexta Rahaala pipeline.
* src/rahaala_prompt.py: In this file we can change system prompt easily and also we can add more documnets if we want.

### Command to run the Rahaala pipeline
```
python src/rahaala.py
```
### Command to run the recomendation pipeline 
```
python src/AlUla_activities.py
```
