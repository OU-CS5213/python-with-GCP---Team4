# Python with GCP  
## Authors:Deepika Mettu, Sanoj Doddapaneni, Divya Sudha Jonnakuti, Prudhvik Yarlagadda 

*Description*  
 - In this project, we need to use the repository [cloud-nebulous-serverless](https://github.com/googlecodelabs/cloud-nebulous-serverless) and implement 3 fractals from the website - https://tashfeen.org where we need to take 2 different resolutions low and high from the fractals and display it in a public HTML page using *Cloud Function* and *Cloud Run*.  

### Cloud Function -
Firstly, we need to enable the following API's  *Cloud Shell, Cloud Build and Cloud Function*.

After enabling the required APIs, we enable the cloud shell by providing necessary authorization when prompted. Once the cloud shell is active, we clone the [cloud-nebulous-serverless] repository (https://github.com/googlecodelabs/cloud-nebulous-serverless) using "git clone https://github.com/googlecodelabs/cloud-nebulous-serverless"
command to implement the changes to the code.  

Therefore, to implement the three fractals as described in the project, we first need to take screenshots of the three fractals (High and Low resolution) and upload these images to the Cloud Storage by creating a bucket.  

To create a bucket, we navigate to [Cloud Storage](https://console.cloud.google.com/storage) in the Google Cloud Project and click on CREATE BUCKET.  
This will prompt us to provide unique name to the bucket. Once we provide the name to the bucket, We expand the section Choose how to control access toobjects and choose the option Fine-grained and click CREATE.It will take a moment to create the bucket. After creating the bucket, we upload the six images (Low and High resolution) of 3 fractals in the bucket. We change the access of these images to  "allusers" to make the images public. Similarly, repeat it on all six image files uploaded to the bucket.  
The bucket will then generate public URLs accordingly as below -  
[Harter-Heighway Dragon Low Resolution](https://storage.googleapis.com/team-4/FirstImage.png)  
[Harter-Heighway Dragon High Resolution](https://storage.googleapis.com/team-4/SecondImage.png)  
[Koch Snowflake Low Resolution](https://storage.googleapis.com/team-4/ThirdImage.png)  
[Koch Snowflake High Resolution](https://storage.googleapis.com/team-4/FourthImage.png)  
[Tree Brach Fractal Low Resolution](https://storage.googleapis.com/team-4/FifthImage.png)  
[Tree Brach Fractal High Resolution](https://storage.googleapis.com/team-4/SixthImage.png)  
