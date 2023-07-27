# The Leafproject 
This project uses resnet-18 re-trained model and imagenet to classify healthy and unhealthy leaf images. 
Powdery mildew is a common yet deadly disease among many different plants that causes leaves to turn yellow and eventually die off. The least-toxic fungicides used to treat this must be applied as soon as the first sign of disease is spotted. Classifying healthy and unhealthy leaves affected by the powdery mildew using images will help in detecting the presence of this disease.

# The Algorithm
The algorithm uses a datset to re-train the resnet-18 network. It is trained by being given the categories in the labels.txt file and shown the images of healthy and unhealthy leaves in the dataset. It is then shown a series of new images, which it then classifies as healthy or unhealthy.

# Running the program
1. Connect to the Jetson Nano
2. In the jetson-inference/python/training/classification/data directory, download the dataset (wget https://download937.mediafire.com/pb320kx27jtg7bJV2H0QTLhwf-aCu445WpEQ9w8VlpVkwZwWssnqs-VdeSJWapwSg_UWwGjLP1xNtfTNbADUbFZDEyQcHNxZZtS8QbWEsSf7dP7Axoe17XQ46pTetRDfJ_kilHu9bOOjfPwhZh8oLyx3AG8HbzBRSbUTwkh2k_YaEzg/xglmp6tgfcgaitt/myproject.zip) and unzip the file
3. From the jetson-inference folder, run ./docker/run.sh
4. In the jetson-inference/python/training/classification directory, run python3 train.py --model-dir=models/myproject data/myproject to re-train the network
5. Run python3 onnx_export.py --model-dir=models/myproject
6. Exit the docker container
7. Set the NET and DATASET variables
8. Use imagenet.py --model=$NET/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=$DATASET/labels.txt $DATASET/test/healthy/leavest1.jpg healthy.jpg
9. View output image

Required 
1. resnet-18
2. imagenet

# Video Demonstration
Here is the link to my video: https://youtu.be/N0RhOzZREXc
