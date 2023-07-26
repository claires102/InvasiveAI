# The Leafproject uses resnet-18 re-trained model and imagenet to classify healthy and unhealthy leaf images. 

# Purpose
Powdery mildew is a common yet deadly disease among many different plants that causes leaves to turn yellow and eventually die off. The least-toxic fungicides used to treat this must be applied as soon as the first sign of disease is spotted. Classifying healthy and unhealthy leaves affected by the powdery mildew using images will help in detecting the presence of this disease.

# Running the program
1. Login to the nano
2. In the jetson-inference/python/training/classification/data directory, download the dataset (wget https://download947.mediafire.com/uxnqx1yjsj6g6B0IhkPaBkliaUMSjD-M5IzHts-dNlaxHSTBoi3hHfFeqwt2Mn0O8iA6xMZZg2saFrmvkzDRgWMB2GcHeDwSpt8VvqGpX7fHCegsf8HKl9l-GY2-5edefGzAdBSN39-kdUuW9Oa1gfWUlbsYauS6JHVvCN9mv0QS7Nk/3xpk93kw9kaxzr0/myproject.zip) and unzip the file
3. From the jetson-inference folder, run ./docker/run.sh
4. In the jetson-inference/python/training/classification directory, run python3 train.py --model-dir=models/myproject data/myproject to re-train the network
5. Run python3 onnx_export.py --model-dir=models/myproject
6. Exit the docker container
7. Set the NET and DATASET variables
8. Use imagenet.py --model=$NET/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=$DATASET/labels.txt $DATASET/test/healthy/leavest1.jpg healthy.jpg
9. View output image

# Required Libraries
resnet-18

imagenet
