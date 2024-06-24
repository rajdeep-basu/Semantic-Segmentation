<h1>Pneumonia Detection Deep Neural Network Model</h1>
<h2>Aim: </h2>
The aim of this project is to understand and implement semantic segmentation on a comparitively simple dataset. This knowledge and neural network can be used for transfer learning for much more complex semantic segmentation tasks like analysis seismic activity, medical imaging, self driving car optics, etc. The network architechture used in this project is called a U-Net. More on this network will be shown below.

<h2>About Semantic Segmentation: </h2>
Semantic segmentation is a computer vision task that involves classifying each pixel in an image into a specific category or class. Unlike object detection, which identifies and classifies objects as bounding boxes, semantic segmentation assigns a label to every pixel, effectively delineating the precise shape and boundary of each object in the image. This technique is crucial in applications requiring detailed image understanding, such as autonomous driving, medical imaging, and scene parsing. These results can be achieved through complex combinations of Convolutional Layers, Dense Layers, and Transpose Layers. Read below to get the details of these.

<h2>Step-by-step procedure: </h2>
<h3>Dataset: </h3>
The dataset used for this project is the Pets dataset from <a href="https://www.robots.ox.ac.uk/">Oxford IIIT website.</a> This dataset contains images of pet dogs and cats. These images are categorized by breeds and there are about 200 examples per category. Moreover, the dataset can be directly downloaded by using the tensorflow_datasets library. More information on the dataset can be found on the official site: <a href="https://www.robots.ox.ac.uk/~vgg/data/pets/">Pets Dataset</a>

<h3>Data Preprocessing: </h3>


<h3>Convolutional Neural Networks: </h3>
A Convolutional Neural Network (CNN) is a type of deep learning algorithm specifically designed for processing and analyzing visual data. CNNs are widely used in image recognition, computer vision, and various other tasks involving visual inputs due to their ability to automatically and adaptively learn spatial hierarchies of features from images. These networks are comprising of convolutional layers as the main computational units. The main advantage of such layers is that they greatly reduce the number of parameters to be trained while efficiently capturing image features. 
You can view the following animation to get an idea on how convolutional layers work.
<p><img src="./Convolutional_Layer.gif"/></p>

<h3>Unet Architecture: </h3>

<p><img src="./CNN.png"></p>

<h3>Model Performance: </h3>
<p><img src="./Performance_Graphs.png"</p>
The above graph shows the different model performance parameter graphs that I have plotted using matplotlib. Below are the descriptions of each performance parameter.
<ol>
  <li>Training Loss vs Validation Loss: </li>
  From this curve, it can be seen that the training and cross-validation losses converge quite well. There are some osscilations here and there but the end results seem very promising. We can see that overall, as the number of epochs increases, the overall losses decrease.
  <li>Training AUC vs Cross-Validation AUC: </li>
  The AUC score clearly shows how, as the learning steps increased the score increased rapidly, then flatlined at the top. This is very good results.
  <li>Confusion Matrix: </li>
  Confusion matrix was one of the more important metrics specially in this application as I had to keep a close eye on the recall of this algorithm. In the end it can be seen that the network was able to achieve a high recall system.
  <li>Region Of Convergence: </li>
  Finally, this curve shows us how better our neural network is compared to an algorithm that gets correct predictions 50% of the time (Randomly flagging positives). The general rule is the ROC should be kept as close to the top left corner as possible. As this approaches the middle, the performance gets worse.
</ol>
<h2>Conclusion: </h2>
In a use case like Pneumonia Detection, it can be disastrous to a patient if the number of False Negatives (Has Pneumonia but was not detected), is high. However, it is not as big of an issue if the number of False Positives (Doesn't have Pneumonia but was still flagged positive) is slightly high. From the above metrics, it can be seen that the Neural Network was able to achieve that result quite promisingly. The False Negative rate is extremely low (0.51%) and the False Positive Rate is not very high (11.47%).
