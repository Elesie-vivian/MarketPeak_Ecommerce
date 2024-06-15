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

**2	   Stage and Commit the Template to git**. I add my website files to git and set the git global configurations with my user name and email 
to track when modifications are made on the files using the following commands on my terminal. 
Also, proceeded to make my first commit with a clear and descriptive message.

     git add .
     git config --global user.name 
     git config --global user.email 
     git commit -m "Initial commit with basic e-commerce site structure"

![alt text](<Images/git add capstone pic.PNG>)


![alt text](<Images/git config and commit capstone on cloud pic.PNG>)


**2.1	Push the code to GitHub Repository**. This is where I have a record of my files in a remote location to ensure I can track or restore history if needed.
First, I log into my GitHub account and create a  new repository named MarketPeak_Ecommerce.
Then I proceeded to link my local repository to GitHub. This is done in my local terminal, I added the remote repository URL to my local repository configuration.

git remote add origin https://github.com/your-git-username/MarketPeak_Ecommerce.git


![alt text](<Images/capstone cloud git remote add origin.PNG>)

**2.2	Pushed my Code**. I pushed my commits from my local main branch to GitHub thereby making collaboration possible. This I did with Command

    git push -u origin main

Here, I encountered some challenges,The above command returned an error output.
Recall that the remote repository I created on GitHub was not initialized with a README, gitignore or licence.
hence to successfully create a new repository on the command line I needed to run the commands as shown below singly as copied from my remote repository.

![alt text](<Images/repo command.jpg>)

After that, I ran the git push -u origin    command to push my code to GitHub. 

![alt text](<Images/pic vs code push.PNG>)