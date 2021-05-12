**Brain CT image classification through CNN deep learning to diagnose brain cancer**

School of Communication, Hong Kong Baptist University

April 20, 2021

**Abstract**

Brain tumor is a brain tonic disease. Due to the unresectable nature of normal brain tissue and the characteristics of extensive infiltration of malignant tumors into the skull, it is extremely difficult to remove a large area completely. Therefore, intervention and treatment are necessary in its diagnosis. At present, AI is increasingly used as a medical tool, so machine learning can build models through the learning of existing diagnoses and serve new diagnostic problems. Existing data show that the results of multiple experiments show that the diagnosis speed and accuracy of AI recognition are better than that of doctors&#39; teams. Therefore, we focus on solving brain tumor diagnosis problems with machine learning methods. This research takes medical diagnosis as the main research field and starts with brain tumor CT image diagnosis. It is hoped to use AI and machine learning in image processing to establish a model to achieve the goal of inputting brain CT images and outputting diagnosis results to improve and Strengthen the efficiency and accuracy of doctor&#39;s diagnosis. This project uses CNN neural network as the basis for supervised learning to build a model. Through the brain CT image data training model, the original data is divided into three parts: 1500 confirmed (Yes), 1500 healthy (No) and 1500 to be diagnosed (Pred). After cutting and supplementing operations to ensure image quality, 1800 sheets are used as the training set and 600 sheets as the test set for model training and adjustment. At the same time, a standardized layer is added to the training process. After adjusting the number of layers and epoch, an 11-layer image classification model is finally trained. Subsequently, the confusion matrix was used to evaluate the model, and the accuracy and recall were both close to 0.77. Finally, the accuracy of the observation model was 77%, which performed well. Finally, the data to be diagnosed is input into the model, and the results are obtained. It can be observed that the model has a good classification of the results of the image and can achieve the diagnostic effect. Therefore, the model established by this project has practical significance and practical effectiveness.

**Introduction**

This project takes CT image diagnosis of brain tumors as a research problem and uses convolutional neural networks to build machine learning models to achieve faster and more effective diagnosis goals. This part mainly introduces the project, including the research background, application methods, and novelty.

Brain tumors are a large number of abnormal cells that grow in the brain. However, the unresectable nature of normal brain tissues and the extensive infiltration of malignant tumors into the skull make it extremely difficult to remove them completely. Therefore, how to reduce brain damage, protect the central function of the brain, and eliminate tumors to the greatest extent is still the research direction and goal of today&#39;s oncologists. Brain tumors can usually spread rapidly through surrounding tissues, and the 5-year survival rate for high-grade gliomas is 15%. In 2016 alone, there were 330,000 cases of brain cancer and 227,000 related details worldwide. Early detection is essential to improve the prognosis of patients, and machine learning is a powerful medical tool that can create and train artificial intelligence to successfully identify brain tumors in a precise manner.

On the other hand, a new study by the University of Texas Southwest showed that artificial intelligence can identify specific gene mutations in glioma tumors by examining 3D images of the brain, with an accuracy rate of over 97%. This technique has the potential to eliminate the common practice of pre-treatment surgery, which is collecting and analyzing glioma samples to select the appropriate treatment. In China, according to Xinhua News Agency, China&#39;s artificial intelligence system is more accurate and faster to diagnose brain tumors and other diseases than a team of top Chinese doctors. Artificial intelligence correctly diagnosed 87% of the 225 cases in just 15 minutes, and a team of 15 senior physicians accurately diagnosed 66% of the cases. When predicting cases of cerebral hematoma expansion, AI wins again: 83% of cases have corrected predictions, while doctors only reach 63%.

Therefore, the use of artificial intelligence for brain cancer detection has important practical significance. It can more accurately diagnose brain cancer, increase the cure rate, reduce the workload of doctors, and help them continuously improve their skills.

In order to solve the problem of image diagnosis, this study uses brain CT images as a data set to establish a machine learning model and uses supervised learning and CNN methods to deal with image recognition problems. This study uses the existing image data for model training, divides the diagnosed CT image data into three parts: confirmed diagnosis, health and to be predicted, and divides the training set and the test set. At the same time, preprocess the image data, visualize some image features, and unify all image sizes. Through image input, through the middle part of the filter (with a set of fixed weight neurons), different filters will get different output data, such as CT color depth, contour, etc. The brain CT is used to diagnose features to extract specific information about the image, so as to achieve the ultimate goal of classification.

The novelty of this project is mainly reflected in three aspects: data usage, machine learning algorithms and applications. The first is data use. This project uses image processing as the field. The input data is brain CT image data that has been diagnosed and classified. The clearly labeled training set and test set make the model established by the supervised learning method more reliable. At the same time, the image data to be inspected can serve for model inspection and evaluation.

On the other hand, the model is built using the CNN (Convolutional Neural Network) method. Because brain supplement CT imaging is based on shadows and contours, this project uses CNN as a targeted method based on this feature to extract features and learn, Get the model. At the same time, standardization operations are performed before the convolutional layer to improve the accuracy of the model.

Third, from the perspective of practical application, it is a very cutting-edge research field and a very practical method to apply image classification processing to medical diagnosis. At the same time, because the current diagnosis of brain tumors is still based on the manual observation of CT images, there is a misdiagnosis the problem of missed diagnosis still exists. The project&#39;s introduction of machine learning into brain tumor diagnosis can significantly improve the efficiency and accuracy of diagnosis.

**Methodology**

**Experimental Study**

After determining the method to be used and analyzing the specific model and application, start the experiment. This part is mainly divided into the experiment process, the evaluation method and the analysis of the experiment result.

The data set for building the model for machine learning is the diagnosed brain supplement CT data set, with a total of 100 sheets, divided into three parts: confirmed (Yes), healthy (No) and to be diagnosed (Pred). Among them, 1500 pieces of confirmed data, 1500 pieces of health data, and 60 pieces to be diagnosed. The size of the image is quite different, so it is necessary to perform cropping and re-prevent the file to establish a new directional structure.

First, create the required Directory structure, the new dataset contains three folders, we are going to create three separate folders, respectivelyTRAIN, TEST, and VAL, and each of these folders will have two folders:NO: Folder containing negative samples (no brain tumor),YES: Folder containing positive sample (brain tumor is present).

Then proceed to image cropping, first create the required function, we load resized images as np. arrays to workspace, and then create the function to prints and plots the confusion matrix. Normalization can be applied by setting &#39;normalize=True&#39;.

Next, in order to first observe the images in the dataset and perform cropping processing, we visualize the images by creating a gridplot for desired number of images (n) from the specified set. After observing the data, you can clearly find that the images in different sets are quite different, so the quality of the data is higher, and the next image cropping and model building can be carried out.

Because the existing image size is different. But the model we are going to build can only accept images with a size of (224 \* 224 \* 3) as input. To successfully build the model, the image size must be adjusted. But blindly resizing the image will cause serious distortion of the image. Therefore, we will first crop the image and then resize it to minimize the distortion problem. We use the OpenCV library to find contours in the image to complete the cropping, so that they can be used as input data to serve the model.

As shown in the figure, find the extreme point on the image and crop a rectangle from it. Then threshold the image, perform a series of erosions and dilations to remove any small regions of noise. Find the contour in the threshold image, then grab the largest contour, and then find the limit point. Cut all the images in the required folder according to the above operation, and then save the new image into the folder again. Finally, adjust the size of the image to 224\*224\*3 without serious deformation and distortion. In order to increase the number of training samples we have; data expansion is performed to complete the data processing part.

After the data is completed, the model is built. First, in order to make the model training faster and improve the gradient and avoid the problem of gradient disappearance, we use normalization methods to pull the input value distribution of any neuron in each layer of neural network back to the mean value. The standard normal distribution with 0 and variance 1 forces the increasingly skewed distribution back to a more standard distribution, so that the activation input value can fall in an area where the nonlinear function is more sensitive to the input. Then we build the model and start training. The training set is 1800 images, all of which are processed into diagnosed (Yes) and healthy (No), set the number of layers to 6, epoch to 20, train the model, and the final result is the accuracy rate 69%, it can be found that the accuracy of the model is not very high.

Then we adjusted the model parameters, added 3 normalization layers, increased the number of layers to 11, and set the epoch to 15. After training, the model accuracy rate reaches 82%, and the model effect is better at this time.

In order to observe the effect of the model and adjust the model to an ideal state, the training process is visualized for observation. At the same time, we visualize and observe the implementation of each data set, and we can see that the model training effect is better. It can be seen from the figure that the accuracy of the model is gradually increasing, and the loss is decreasing, indicating that the model is converging and the effect is good.

In order to specifically evaluate the performance of the model, we use the confusion matrix, which is a table that is often used to describe the performance of a classification model (or &quot;classifier&quot;) on a set of test data for which the true values ​​are known. It allows the Visualization of the performance of an algorithm. And through the accuracy and recall measuring the performance of the model, it can be seen that the accuracy score is 0.77, and the recall score is also close to 0.77. Specifically, in the data set marked as healthy (No), the accuracy is 0.73, the recall is 0.85, and the f1-score is 0.79. In the data marked as confirmed (Yes), the accuracy is 0.82 and the recall is 0.68. The f1-score is 0.74, which shows that the model performs well.

Analyzing the experimental results, in the 600-sheet test set, there are 448 image diagnosis results that are the same as the actual diagnosis results, and the accuracy rate is over 74%.

After the model is built and evaluated, it can be observed that the model performs well, so the CT image of the brain to be diagnosed is input into the model to solve this problem. We input 60 images and output the diagnosis results. It can be seen that the output results are better. The following figure is an example. The image that is diagnosed as healthy is obviously in the normal brain state, and the brain image that is diagnosed as the diagnosis is clearly visible. There are large shadows. Observing all the input images, it can be seen that the diagnosis result is relatively accurate, and the diagnosis of the 60 images is completed within one minute, which greatly improves the diagnosis efficiency. At the same time, the use of visual means to visually display the diagnosis results can improve the effect of medical diagnosis, assist doctors in optimizing the diagnosis process, complete early screening on the basis of improved efficiency, and increase the cure rate of brain cancer.

**Conclusion**

This project uses convolutional neural networks for model building and supervised learning methods, and solves the problem of CT image diagnosis of brain cancer through machine learning. Use the marked CT images of the brain for training and testing, and after evaluation, it is observed that the model works well, and then the actual problem is solved.

In terms of methods, this project uses CNN neural network to deal with image classification problems, and at the same time debugs when training the data set, adjusts the number of layers and epoch to retrain the model, and adds a standardized layer. At the same time, during the experiment, the distribution of the input value of any neuron in each layer of neural network was pulled back to a standard normal distribution with a mean of 0 and a variance of 1, and the increasingly skewed distribution was forced back to a more standard distribution.

From the experimental results, the model can output more accurate results after inputting the patient&#39;s brain CT image, and at the same time, it takes a shorter time, improves the efficiency, and greatly improves the medical diagnosis and cure rate. At the same time, the method, model establishment and experimental process of this project are independently built and completed. The added standard layer can make the activation input value fall in the area where the nonlinear function is more sensitive to the input, so that the accuracy of the model is more stable.

In summary, this project uses machine learning to process image classification problems with CNN neural network to solve medical diagnosis problems. Finally, the model has a good performance, and the actual application also outputs more reliable results. It can be concluded that this model has In practical significance, this model solves the problem of brain CT image diagnosis to be diagnosed, and completes an attempt and application of AI in the medical diagnosis and treatment of brain cancer.

**Reference**
