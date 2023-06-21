**Environment Used**
Google Colab

**Importing Zipped File into Google Colab**
Just unzip the folder and open the relevant notebook using Google Colab. 

**Relevant Notebooks**
ASR_Train.ipynb: For finetuning "facebook/wav2vec2-large-960h-lv60-self" on TIL23 ASR train dataset
ASR_Test.ipynb: Doing ASR Inference using finetuned model from ASR_Train.ipynb and ensembling with pretrained model facebook/wav2vec2-large-960h-lv60-self, facebook/hubert-xlarge-ls960-ft, facebook/hubert-large-ls960-ft

**Open Sourced Pretrained Model Used**
facebook/wav2vec2-large-960h-lv60-self: https://huggingface.co/facebook/wav2vec2-large-960h-lv60-self 
facebook/hubert-xlarge-ls960-ft: https://huggingface.co/facebook/hubert-xlarge-ls960-ft 
facebook/hubert-large-ls960-ft: https://huggingface.co/facebook/hubert-large-ls960-ft 

**Model Checkpoints**
model.bin: finetuned wav2vec2 checkpoint obtained from ASR_Train.ipynb.

**Submission CSV**
submission.csv: Results are from ensembling in ASR_Test.ipynb