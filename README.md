important note: Since the images I use as a data set were given to me by the company, I cannot share them publicly.

Folder content:
BeeVision.jpynb: The python code that performs all the steps. Please do not run all cells from start to finish. There are cells that add additional functions independent of the process or work in opposition to each other. In order to be able to use google GPUs during the training phase, I preferred to work in Google Colab instead of working locally.
random_train_626_coco.json: json file containing the labels of the train dataset in coco format
validation_random_coco.json: Json file containing the validation or test dataset's labels in coco format
training_random_images: File containing 626 photos used in the Train phase
validation_random_images: File containing 50 photos used during validation or testing
model_weights_14epoch_626_0172.pth: The parameters of the model I am training. You can load these parameters into the model with the cells I put in the Python code. No training required. Can be put directly to the test
arial.ttf: The font file required for the class name to appear in the output photos
21568.jpeg and 21577.jpeg: 2 sample photos that can be used for testing.

Label:
Using the tools available online, I manually labeled 626 of the photos in the dataset and created a total of 23 classes. I had some problems with training because I had not created a custom dataset before and I was inexperienced with labels. I think I am not creating the dataset optimally. I got the labels from the tool I used in coco format and uploaded the photos and labels to the dataloader on the code.
Training:
After determining the parameters such as batch size, epoch number, momentum, training can be done. During the epoch, the average training loss is calculated after each batch and printed as output. At the end of each epoch, validation loss is calculated using the validation dataset and printed as output. In this way, Overfitting becomes preventable.
Before the train phase, the model can be given pre-made parameters and a pretrained model can be retrained. After training, model parameters can be saved for later use.

Test:
Accuracy can be measured using the dataset I created for the test. While measuring this value, the intersection of the ground truth box and the area of the box predicted by the model is taken, and an accuracy value is obtained by dividing the intersection area by the junction area. I get an accuracy value of approximately 77 percent with the model I train. Using the last cell in the code, a photo can be given to the model as an input and the labeled version of the photo can be seen as output.
