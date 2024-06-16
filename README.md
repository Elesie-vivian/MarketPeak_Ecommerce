# CAPSTONE PROJECT-INTRODUCTION TO CLOUD COMPUTING

## E-COMMERCE PLATFORM DEPLOYMENT WITH GIT, LINUX AND AWS.

### Introduction

This project involves developing an e-commerce website for a new online marketplace named “MarketPeak”.
This online platform will feature product listings, a shopping cart and User authentication.
The objective is to utilize Git for version control, develop the platform in a linux environment and deploy it on an AWS EC2 instance. 
We find a suitable template on tooplate or any other free template page to kickstart the deployment.

#### Step 1

**Implement version control with Git**

**1.1	Initialize Git Repository** First, I created a folder on my local computer called capstone-Project-Cloud, on my git bash terminal I opened the folder and then proceeded to make a directory “MarketPeak_Ecommerce”, cd into it and then initialized Git.

           Mkdir MarketPeak_Ecommerce
           Cd MarketPeak_Ecommerce
           git init
![alt text](<Images/git init.PNG>)

Note: I executed the above commands one at a time as seen in the image above.

**1.2	Obtain and Prepare the E-commerce website Template**. Here I used a pre-existing e-commerce website template that is ready to use and required minimal adjustments. This I downloaded from (Tooplate)[https://www.tooplate.com/].

**1.3	Prepare the website template**. Extract the downloaded website template. I extract into my project directory MarketPeak_Ecommerce on my local computer. 

![alt text](<Images/extact 2.PNG>)

**1.4	Customize the Template**. I made word edits to the source file to reflect MarketPeak_Ecommerce products and services. 
This includes adding Product Listings, a Shopping Cart and User Authentication on the web page .

![alt text](<Images/index editing on web page.PNG>)

**1.5	   Stage and Commit the Template to git**. I add my website files to git and set the git global configurations with my user name and email 
to track when modifications are made on the files using the following commands on my terminal. 
Also, proceeded to make my first commit with a clear and descriptive message.

     git add .
     git config --global user.name 
     git config --global user.email 
     git commit -m "Initial commit with basic e-commerce site structure"

![alt text](<Images/git add capstone pic.PNG>)


![alt text](<Images/git config and commit capstone on cloud pic.PNG>)


**1.6	Push the code to GitHub Repository**. This is where I have a record of my files in a remote location to ensure I can track or restore history if needed.
First, I log into my GitHub account and create a  new repository named MarketPeak_Ecommerce.
Then I proceeded to link my local repository to GitHub. This is done in my local terminal, I added the remote repository URL to my local repository configuration.

git remote add origin https://github.com/your-git-username/MarketPeak_Ecommerce.git


![alt text](<Images/capstone cloud git remote add origin.PNG>)

**1.7	Pushed my Code**. I pushed my commits from my local main branch to GitHub thereby making collaboration possible. This I did with Command

    git push -u origin main

Here, I encountered some challenges,the above command returned an error output.
Recall that the remote repository I created on GitHub was not initialized with a README, gitignore or licence.
hence to successfully create a new repository on the command line I needed to run the commands as shown below singly as copied from my remote repository.

![alt text](<Images/git push error.PNG>)


![alt text](<Images/repo command.jpg>)


After that, I ran git push --set upstream origin    command to push my code to GitHub. 

![alt text](<Images/pic vs code push.PNG>)


### Step 2

**AWS DEPLOYMENT**


**2.1  EC2 Instance Setup**
Here, I deployed “MarketPeak_Ecommerce”platform to AWS EC2 instance.
I set up and launched an AWS EC2 instance using Amazon linux AMI, after which I connected to the instance using 
SSH.

![alt text](<Images/ec2 instance cloud.PNG>)

**2.2   Cloning the repository on the linux server**. To clone the repository, I used the HTTPS method.
 This involved clicking the code button on MarketPeak_Ecommerce repository in GitHub and selecting HTTPS to generate the HTTPS URL.

git clone https://github.com/Elesie-vivian/MarketPeak_Ecommerce.git

Here, I had to install git on my linux terminal  after which I was able to clone successfully.
I installed git using command

sudo yum install git 


![alt text](<Images/Git installed.PNG>)

![alt text](<Images/git clone.PNG>)


### Step 3

**INSTALLING WEB SERVER ON EC2**
This section involves installing Apache web server (httpd). 
This is a widely used server that serves HTML files and content over the internet.
With Apache installed on my Linux EC2, I can effectively host “MarketPeak_Ecommerce” site.  

**3.1 Install Apache (httpd)**. I install Apache with the following command

     sudo yum update -y
     sudo yum install httpd -y
     sudo systemctl start httpd
     sudo systemctl enable httpd

![alt text](<Images/Apache installed for cloud.PNG>)

 **3.2   Configure httpd for website**. Here, I cleared the default httpd web directory and copied MarketPeak_Ecommerce website files into it.

     sudo rm -rf /var/www/html/*
     sudo cp -r ~/MarketPeak_Ecommerce/* /var/www/html/

     Then I reload Apache(httpd) so as to apply changes with command

     sudo systemctl reload httpd

 **3.3	Access website from Browser**. With the above configurations and website files in place, time to access MarketPeak_Ecommerce from the web browser.
 Before I access the site , I edited my inbound rules on my AWS EC2 security  groups to allow HTTP and HTTPS ports 80 and 443.

 Note: Testing the website on the Broswer returned Apache Test Page instead of MarketPeak_Ecommerce site. 
 Therefore had to go back to my linux terminal to resolve this troubleshoot.
 Another look at the configurations required re-imputing the default httpd web directory commands as seen below:
 
     sudo rm -rf /var/www/html/*
     sudo cp -r ~/MarketPeak_Ecommerce/* /var/www/html/

![alt text](<Images/Trouble shoots.PNG>)

 After which I could access MarketPeak_Ecommerce website.


 ![alt text](<Images/MarketPeak web page1.PNG>)

 ![alt text](<Images/MarketPeak web page.PNG>)

 ### Step 4

 ## CONTINUOUS INTEGRATION AND DEPLOYMENT WORKFLOW

 To maintains smooth workflow for deployment in the platform it should to incorporate new changes in a development, utilize version control with Git and deploy updates to the server.

 **4.1	Developing new features and fixes**.
 Here I created a Development Branch to isolate new features and fixes using command:

      git branch development
      git checkout development

 ![alt text](<Images/New branch.PNG>) 

 **4.2  Implement changes**. 
 I added a new(service) feature in the product; by including delivery in Product listing section.

 **4.3	Version Control with Git**. I staged the changes and prepare them for commit with a descriptive message about the changes.

     git add .
     git commit -m "Add new features or fix bugs"


 ![alt text](<Images/New feature Git.PNG>)

 I then pushed the changes to GitHub to ensure collaboration and version tracking.

   git push origin development

 ![alt text](<Images/git push Dev.PNG>)

 **4.4	Pull Request and Merging to the main branch**. I created a Pull Request on GitHub in order to merge the development branch into the main branch.
 Reviewed the changes and then proceeded to merge the Pull request, incorporating the new features into MarketPeak _Ecommerce codebase.

 ![alt text](<Images/Pull request & merge.PNG>)

  git checkout main
  git merge development


![alt text](<Images/git merge cli.PNG>)

 Next, I pushed the merged changes to GitHub, (this is the local main branch now containing the updates being pushed to the remote repository on GitHub).
 First, I pulled the files to my local repository in order to update my local repository before proceeding to push to GitHub.

     git pull origin main
     git push origin main

 
![alt text](<Images/git pull&push.PNG>)


### Step 5
## Deploying Updates to the Production Server

**5.1 Pull the latest changes on the Server**. I SSH into my AWS EC2 instance where the production website is hosted.
Then navigate into the website’s directory,(MarketPeak_Ecommerce) and pull the latest changes from the main branch.

   git pull origin main

   ![alt text](<Images/git Pull linux.PNG>)

**5.2 Restarting the web server and Testing the Changes**. I restarted the web server in order to apply the changes, before that I also cleared the default directory configuration for httpd and applied that of MarketPeak_Ecommerce.

    sudo rm -rf /var/www/html/*
    sudo cp -r ~/MarketPeak_Ecommerce/* /var/www/html/

Reloading httpd with the command

    sudo systemctl reload httpd

![alt text](<Images/cli reload.PNG>)


**5.3 Testing the new changes**Accessing the website, I open a web browser and navigate to the Public IP of my EC2 instance to test if the new features work as expected

![alt text](<Images/New fixes pic 2.PNG>)

The entire project encapsulates a stable and up-to-date process for an e-commerce platform.









 

 


 
    


