# DSTA Today-I-Learned AI 2023
<p align="justify"> 
  This GitHub repository contains the source code for my implementation of the advanced tier of Defence Science & Technology Agency (DSTA) 2023 Brainhack Decode the Future Artificial Intelligence (AI) Challenge - Today-I-Learned (TIL) AI. In this challenge, participants were required to propose machine-learning solutions for two different domains - Computer Vision and Speech Recognition. The challenge was held using Zindi's platform for 2 weeks.
</p>

## Computer Vision
### Problem
<p align="justify"> 
  In the computer vision domain, we were tasked to develop two computer vision models - an object detection model and a re-identification model. For objection detection, we were given a training dataset consisting of images of various plushies. Each image contained one or more plushies and the bounding box coordinates of each plushie present were provided. The goal was to identify all plushies in each test image and use relevant methods to extract these plushies into individual crops. At the same time, each test image came along with a cropped query plushie. After identifying and cropping all the plushies in a given test image, we were required to compare each identified plushie with the query plushie and classify whether it is the query plushie. The evaluation was based on the error metric Man Average Precision @ Intersection over Union Threshold 0.5.
</p>

### Proposed Solution
<p align="justify"> 
  For object detection, as it is paramount to identify all plushies, I used <a href="https://github.com/ultralytics/ultralytics">YOLOv8x</a>, which is the most accurate model among the YOLOv8 models. The YOLOv8x model was loaded with the publicly available pre-trained checkpoint and finetuned further on the plushie training dataset. The finetuned YOLOv8x model was then used to identify the plushies in the test dataset. In order to perform re-identification, I extracted the image features of the identified plushies and used the extracted features to do a pairwise comparison with the query plushie's feature. A simple two-layer neural network was trained to do the pairwise comparison and provide a probability for whether an identified plushie is the same as the provided query plushie. To further improve the accuracy of classification, I turned to ensemble learning where I attempted to use various feature extractors including <a href="https://huggingface.co/microsoft/resnet-50">ResNet50</a>, <a href="https://huggingface.co/docs/timm/models/se-resnet">SeResNet152</a>, and <a href="https://huggingface.co/google/vit-base-patch16-224-in21k">Vision Transformer</a>. Due to the lack of time, I was unable to attempt finetuning the feature extractors with the provided training dataset. Out of 31 teams that participated in the computer vision challenge, my solution achieved 8th place in the public leaderboard and 9th place in the private leaderboard.
</p>

## Speech Recognition
### Problem
<p align="justify"> 
  As for speech recognition, we were tasked to develop a model to perform speech-to-text transcription. We were provided with a training dataset consisting of speech audio clips with utterances of a few seconds per clip and their corresponding transcription to train the model. A separate test dataset was used to evaluate our model based on the Word Error Rate metric. 
</p>

### Proposed Solution
<p align="justify"> 
  In order to tackle the problem of speech recognition, I finetuned <a href="https://huggingface.co/facebook/wav2vec2-large-960h-lv60-self ">Facebook's Wave2Vec2-Large</a> model using the provided training dataset. I managed to only finetune one model since it was expensive time-wise to finetune a large transformer-based model. In order to further improve the transcription quality without any other finetuning, I tried using other available pre-trained automatic speech recognition models including <a href="https://huggingface.co/facebook/hubert-xlarge-ls960-ft">HuBERT-xLarge</a> and <a href="https://huggingface.co/facebook/hubert-large-ls960-ft">HuBERT-Large</a>. By comparing the number of spelling errors for a given transcription made by each model, I was able to identify which model's prediction is the best prediction for a given audio clip, which helped to lower the word error rate. Out of 36 teams that participated in the speech recognition challenge, my solution achieved 12th place in both the public leaderboard and the private leaderboard.
</p>
