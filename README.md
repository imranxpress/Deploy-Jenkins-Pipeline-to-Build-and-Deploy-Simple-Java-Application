# Deploy-Jenkins-Pipeline-to-Build-and-Deploy-Simple-Java-Application



## Table of Contents

    1. Goal
    2. Pre-Requisites
    3. Server Configuration
    4. Jenkins Pipeline
    5. Validation


![aws9](https://user-images.githubusercontent.com/47071968/230105322-9641cc26-b872-4882-b016-d9fb3877b370.png)


## Goal

Goal of this project to Deploy Jenkins Pipeline to Build and Deploy Java Application.

## Pre-Requisites

    1. Create AWS EC2 Instance to configure Build environment
    2. Create AWS EC2 Instance to configure Apache Tomcat application server environment
    3. Migrate  Java Source Code to your own repository.
    
    
## Server Configuration

    1.Login to Build server and configure the Build environment with below packages
        a.Install and setup Apache Maven, JDK 11, Git, Jenkins
    2. Login to App server and configure the App environment with below configuration
        b. Install Apache Tomcat 8.x
        c. Create Tomcat Users to access the Manager Application with Admin access for UI and Script based access
        
## Jenkins Pipeline

## Jenkins Configuration

    1. Install Plugins
        a. Copy Artifact
        b. Deploy to Container
    2. Add Credentials 
        a. Add Bitbucket credentials to Credentials store
        b. Add Tomcat App credentials to Credentials store
        
  ## Build

    a. Create Freestyle Build Job with below steps
        1. Clone the Java Source Code from Bitbucket repo Master branch
        2. Build the source using mvn package command
        3. Archive the Artifacts
        4. Configure Post-Build Actions to build other projects (Deploy Job)
        5. Enable Jenkins remote build execution with secure token
        6. Configure Bitbucket repository with webhook URL

## Deploy

   1. Create Freestyle Deploy Job with below steps:
   
       a. Copy Artifact from Build Job (Copy Artifact Plugin)
       
       b. Deploy Artifact to Tomcat App server (Deploy to Container Plugin)
       
       
       ## Validation

    1. Commit a change to Bitbucket repository and verify if the webhook is invoked and Jenkins Pipeline is executed to Build and Deploy the Artifact to App server.
    2. Verify if you are able to access the application from public internet browser.
    
 ## Still not confident, repeat the steps again. Good Luck!



