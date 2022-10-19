# Artificial-Intelligence-Recognition-and-Interpretation-of-Atrial-fibrillation-Normal-Abnormal-ECG

Atrial fibrillation 

There are different types of arrhythmias and the most common one is atrial fibrillation (AF), 
which is an irregular and often very fast heart rhythm, which can result in blood clots in the heart. When you are suffering from AF  ,
it raises your chances of having a stroke, having heart failure, or even having other heart-related problems.
A person with atrial fibrillation experiences chaotic and irregular beats in the top chamber of their heart (the atria), 
which are out of rhythm with the lower chambers of the heart (the ventricles) when they are suffering from atrial fibrillation.
There are many people who suffer from AF who don't have any symptoms of the disease at all. Palpitations, shortness of breath,
and weakness are just a few of the side effects that may accompany AF.

![image](https://user-images.githubusercontent.com/109984804/196691194-2a9e16a3-f52f-4f1f-892b-c8b13883d16f.png)
There are two types of atrial fibrillation, intermittent and continuous. Although it is rare for AF to be fatal, 
it is still an important medical disease that needs to be treated as soon as possible in order to prevent strokes 
The arrhythmia (AF) causes a blood clot which can eventually lead to a stroke or heart failure, since this condition can cause a blood clot to form.


A common cardiac arrhythmia, atrial fibrillation (AF), is characterized by irregular or rapid heartbeats. 
It is estimated that 12.1 million(Colilla et al., 2013) additional AF patients will be diagnosed in the U.S. by 2050, and that the related costs will total USD 6–26 billion(Kim et al., 2011).
It is important and beneficial to detect AF early and accurately for a number of reasons, including both the social cost of healthcare and the quality of life.
AF can also cause heart failure and other heart diseases(Gillis et al., 2013), as well as thrombosis, which can lead to stroke. 
People with AF are five times more likely to suffer a stroke than individuals without it.
An electrocardiogram (ECG) is visually inspected in the clinical environment to detect AF.
Using Holter monitors (ambulatory ECG devices), cardiologists examine ECG recordings for about 24 hours. 
It can be a tedious and time-consuming process to examine large amounts of ECG recordings manually. 
It is also difficult to inspect an ECG with accurate and consistent accuracy and consistency due to its time and frequency components. 
There is insufficient evidence to support the claim that primary care practitioners can accurately detect AF(Mant et al., 2007) based on their routine manual inspections. 
Hence, it is necessary for clinicians to receive extensive training to detect AF effectively if they are going to detect hidden patterns of AF.



ARCHITECTURE OF MODELS

![image](https://user-images.githubusercontent.com/109984804/196692456-23400a60-f5f7-4a45-8c84-0bd4a1f5e4ef.png)

Data Description 
The dataset, which consists of 8528 records, 
contains a series of recordings of ECGs that are recorded at a frequency of 300 Hz, with a range of 2700 points to 18300 points in length.
These records are labelled with 4 classes: normal sinus rhythm (N, 5154 records), atrial fibrillation (A, 771 records),
alternative rhythm (O, 2557 records) and noise (P, 46 records).Before feature extraction, we
pre-process raw data to get the following five kind of data. AliveCor is the device that has picked up all the readings, and
the test set contains a total of 3,658 ECG recordings in the same length as those taken by AliveCor.
It should be noted that the test set will remain confidential for the purpose of scoring during the length of the Challenge and probably for some time afterwards.
It will be unavailable to the public during the whole Challenge period.

![image](https://user-images.githubusercontent.com/109984804/196693059-314525c8-3466-406e-99ea-1b9c3e0fcf97.png)

![image](https://user-images.githubusercontent.com/109984804/196693116-fb63f75c-af4e-4f4c-8fe7-062f7f9bdfb2.png)
Red mark highlight noise removal

ECG time series processing for deep learning algorithms
1. Zero padding to extend sequences
Convolutional neural networks require input data to be of the same size.
However, because the recording lengths that varied between 3s and 20s in the data set, ECGs were padded with zeros to create sequences of consistent lengths.
![image](https://user-images.githubusercontent.com/109984804/196693778-470ee7d1-edd2-4a17-a0db-69cdd6f7f1fb.png)

2. Time series conversion into spectrograms
Electrocardiograms are representations of the periodic cardiac cycle. They contain useful information both in the time and the frequency domain. 
We can extract frequency information by applying a Fourier transform and normalizing the frequency contributions to obtain the power spectrum of the ECG shown above.

To preserve both time and frequeny content of the signal, we can combine the PDS and the time series.
A spectrogram returns the time-dependent fourier transform for a sequence computed using a sliding window. 
This form of the Fourier transform, also known as the short-time Fourier transform (STFT), has numerous applications in speech, sonar, and radar processing.
The spectrogram of a sequence is the magnitude of the time-dependent Fourier transform versus time.
To optimize the dynamic range of frequency, it is also useful to apply a logarithmic transform.
In fact, other reports showed that the logarithmic transform considerably increases the classification accuracy.
Here is an illustration of the effect of the logarithmic transform.

![image](https://user-images.githubusercontent.com/109984804/196694252-953c26e1-4870-4c7f-926b-4a6bcefce9c4.png)


3. Overfitting can be reduced through data augmentation
Data augmentation is a technique that entails adding slightly modified versions of existing data or creating a synthetic data based on existing data in order to increase 
the amount of data that can be examined. 
There is also something called oversampling in data analysis, which plays an important role in reducing overfitting when training a machine learning model. 
This procedure acts as a regularize and helps reduce overfitting.

![image](https://user-images.githubusercontent.com/109984804/196696752-d4c82a93-df87-4fce-b56c-4b466a5cafa8.png)

![image](https://user-images.githubusercontent.com/109984804/196696819-55681017-e0d1-4763-850c-1adb81ad7867.png)

Results

![image](https://user-images.githubusercontent.com/109984804/196696946-41ad3c83-f902-4c49-a552-4d656de9ce71.png)

![image](https://user-images.githubusercontent.com/109984804/196696988-c2bde1e9-9ede-43ab-bc21-990edbcbba7a.png)


SL no	Accuracy	Validation  	Depth 	Blocks 	Epoch
1	    80.94    	78.06	          2	    6	      500
2   	75.56	    71.38	          4	    6	      500
3    	77.81   	76.88         	6	    6	      700








