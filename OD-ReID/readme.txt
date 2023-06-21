**Environment Used**
Google Colab

**Importing Zipped File into Google Colab**
Just unzip the folder and open the relevant notebook using Google Colab. 

**Relevant Notebooks**
Object_Detection.ipynb: For training Yolov8x model and making prediction of bounding boxes on test set
Training_Neural_Network_Classifier.ipynb: For training simple neural networks on ResNet/SENet/Vision Transformer features 
Reidentification.ipynb: For making prediction on the class (suspect/non-suspect) using the neural networks trained in Training_Neural_Network_Classifier.ipynb

**Open Sourced Pretrained Model Used**
RESNet50: https://huggingface.co/microsoft/resnet-50
SENet: https://huggingface.co/docs/timm/models/se-resnet
Vision Transformer: https://huggingface.co/google/vit-base-patch16-224-in21k

**Model Checkpoints**
resnet_best.pt: 2 layer neural network (12288 - 2048 - 1) trained to classify suspect/non-suspect based on RESNet features 
senet_best.pt: 2 layer neural network (12288 - 2048 - 1) trained to classify suspect/non-suspect based on SENet features 
vit_best.pt: 2 layer neural network (4608 - 2048 - 1) trained to classify suspect/non-suspect based on Vision Transformer features 
combined.pt: 2 layer neural network (29184 - 1024 - 1) trained to classify suspect/non-suspect based on RESNet, SENet, Vision Transformer features

**Submission CSV**
submission_combined2.csv: Results are from just the combined.pt neural network. 