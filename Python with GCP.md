---
marp: true
size: 16:9
theme : uncover
paginate: true
---
<style>
{
  font-size: 22px
}
</style>

# Python with GCP

###### Authors: Team 4
Deepika Mettu
Sanoj Doddapaneni
Divya Sudha Jonnakuti
Prudhvik Yarlagadda

---

# Description

In this project, we need to use the repository cloud-nebulous-serverless and implement 3 fractals from the website -  
```https://tashfeen.org```  
Here we need to take 2 different resolutions low and high from the fractals and display it in a public HTML page using **Cloud Function** and **Cloud Run**.  

We need to enable the following API's Cloud Shell, Cloud Build, Cloud Run and Cloud Function.
---

# Cloud Function 

We enable the cloud shell by providing necessary authorization when prompted.  
Once the cloud shell is active, we clone the cloud-nebulous-serverless repository using the command below -  
```git clone https://github.com/googlecodelabs/cloud-nebulous-serverless``` 

---
Now, we run the command below to change the directory to the python directory -  
```_cd cloud-nebulous-serverless/cloud/python_```  
After we are in the correct directory, which has the python code and templates, we run the command below as references to build and deploy the cloud function -  
```gcloud functions deploy translate --runtime python39 --trigger-http --allow-unauthenticated```

---

We have successfully deployed a cloud function for the repository cloud-nebulous-serverless.  
The command will run the code for the translation given in the repository.


---

# Upload Images in cloud storage bucket

Now, to implement the three fractals as described in the project, we first need to take screenshots of the three fractals (High and Low resolution) and upload these images to the Cloud Storage by creating a bucket.  

To create a bucket -   
 - Navigate to Cloud Storage in the Google Cloud Project
 - Click on CREATE BUCKET which will prompt us to provide unique name to the bucket
 - Once we provide the name to the bucket, expand the section Choose how to control access to objects 
 - Choose the option Fine-grained and click CREATE.

---
It will take a moment to create the bucket.

After creating the bucket -  
 - Click on the bucket name and click on UPLOAD FILES
 - upload the six images (Low and High resolution) of 3 fractals in the bucket
 - We change the access of these images to "allusers" to make the images public
 - Now you can copy the public URL in of the Images in the bucket
---
The bucket will then generate public URLs accordingly as below -
```https://storage.googleapis.com/team-4/FirstImage.png```
```https://storage.googleapis.com/team-4/SecondImage.png```
```https://storage.googleapis.com/team-4/ThirdImage.png```
```https://storage.googleapis.com/team-4/FourthImage.png```
```https://storage.googleapis.com/team-4/FifthImage.png```
```https://storage.googleapis.com/team-4/SixthImage.png```

---
Now, In Cloud Function - 
 - Select the Cloud Function **translate** 
 - Modify the index.html file in the source to include the public link of the images
 - Click DEPLOY (It takes a few minutes to complete the deployment)
 - Click on TRIGGERS tab in Cloud Function, and we will find the public link below -  
```https://us-central1-root-gist-347714.cloudfunctions.net/translate```

The above page will show the links to access the images of the fractals on the web.

---

# Cloud Run 
To deploy Cloud Run function - 
 - Open Cloud Shell and close the repository
 - Edit and save the index.html file to include the public URLs of the Images
 - Run the command - ```_gcloud run deploys translate --source. --allow-unauthenticated --platform managed_.```

This will take a while to run and might ask you for time-zone selection if not defaulted.  
When the deployment is complete, we get the Service URL as below -  
```https://translate-62lns32szq-uc.a.run.app```

---

# Links: 
Cloud Function Website:  
```https://us-central1-root-gist-347714.cloudfunctions.net/translate```
Cloud Run Website:  
```https://translate-62lns32szq-uc.a.run.app```






 
