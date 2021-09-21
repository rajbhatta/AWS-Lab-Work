## Creating AWS CodePipeline ##
- We'll start by creating and configuring the source stage using AWS CodeCommit. Then we'll create the build and test stage with AWS CodeBuild

- we'll create a deployment stage for this application using CodePipeline in the Elastic Beanstalk option, and all of this will be configured inside of CodePipeline. 

- From there, we'll trigger and test our pipeline by pushing commits to the CodeCommit repository and watching our entire pipeline automatically trigger. 

- So let's go over to the AWS console and get started. Over here in the AWS console, let's go to the Services drop‑down, and let's go over to the CodePipeline section. On this section, we'll be able to start creating our pipeline. Let's click Create pipeline here, and then we'll give this pipeline a name. 

- I'm going to call mine flasky3, which will automatically create a service role for us for this pipeline. Now, we'll need to make sure we have permissions to add roles in AWS, so make sure you're logged into a privileged user in this AWS account and not the developer user that we created a little while earlier in previous demos. That's because that user doesn't have permissions to necessarily create the roles that we need for this demo. 

- So once we've done this, let's click the Next button here, and then we'll click our first setup step, which is to add a source stage. We'll be able to pick from all the source providers that AWS CodePipeline offers, and we'll pick CodeCommit because that's where we'll end up keeping our code. Now, we have our previous flasky repositories, but in case you're still working on those demos, I don't want to make you overwrite them. 

- Typically, we would probably iterate on our application and add to it. But as this version of the flasky application will be deployed to AWS Elastic Beanstalk, I don't want to interfere with the other places we deployed our applications to. So let's go and create a new repository. I'll go to the Services drop‑down again, go over to CodeCommit, and I'll open this in a new tab so that we don't ruin our work in CodePipeline there, and then we'll create a new repository. We'll call this one flasky3, and then we'll scroll down and click Create. Now, from here, I'm going to assume that you still have the Git credentials set up from the earlier modules. 

- This means that you'll be able to go in here and click Clone URL, Clone SSH, and later use this URL in order to push tooth the repository here. If you haven't already gone through this setup in the module on CodeCommit, make sure you go back and take that module first. Now that we've copied the SSH URL, let's set up the demo files for this course. If you haven't already, go ahead and download them from Pluralsight. Then we can go over to the download folder for 06‑cicd‑with‑codepipeline. 

- There's another folder inside of that called demo1‑cicd‑codepipeline. Now, inside of there, the folder we're really interested in is called flasky3. So let's change directories into that inside of here. Now that we're in flasky3, let's double check we're in there because we need to be inside the flasky3 folder in order to initialize just that folder as a Git repository. I'm going to used the pwd, or print working directory, command just to make sure that flasky3 is the last folder we're in here. 

- Now, your terminal might not show it on the left side of the screen in blue like mine with the arrow pointing to it, so just make sure that when you run the commands to check the directory that flasky3 is at there at the end. So now that we've done this, let's clear the screen and let's get this repository set up to push all of the code that's inside of it to AWS CodeCommit. In the command.txt folder, I've included some Git commands that'll help you do that. They start with git init, or git initialize. 

- This sets up flasky3 as a Git repository. Now, inside of flasky3, there's a lot of files we're going to need, and I'll look through them in just a moment. But we need to get them into CodeCommit first, so let's go ahead and git add them to the changes that we'll be tracking. We'll do this with git add dot. This should move them all to being tracked. From here, we can do git commit, and we can commit these with a message called first commit just so we know that it's the first one we put in there. 

- This should add all of these different files in flasky3 to our repositories locally. This should add all of the different files in flasky3 to our repository locally, but now we need to push them into the cloud. In order to do this, we have to set up a remote. If we run the git remote command right now, nothing happens. If we run to git remote command with v, nothing happens either. That's the verbose flag here. What we want to do is set up a remote that we can push our code to. Now, I have included this inside of the commands.txt file to give you an example. We'll do git remote add origin, and then we'll paste in our SSH URL that we copied. 

- Once we've done this, we should be able to rerun the git remote ‑v flag and see that we currently have a fetch and push URL set up for origin. So let's clear the screen here and get started by pushing all of the commits we just made, just the one first commit, over to our repository. We'll do this with git push origin, and we'll send it to a master branch. Now that we've done this, if we go back to the AWS CodeCommit console and we refresh the screen, we should see all this code pushed into our new repository. 

- This is exactly what we're hoping for. So now, let's take a closer look at what's actually inside of flasky3. I've made some changes to our earlier versions of the flasky application. Previously, we started with a pretty simple API, but now I've gone inside of the application.py file instead of app.py file and changed a few things. The first is just that high‑level name. That's because when we're working with Elastic Beanstalk, which we'll be doing in just a moment, it'll expect application.py by default instead of app.py. And for the same reason, I've changed apponline3 to application if you compare it to the previous versions of this app. 

- So below this, we have some more text that helps us set up a website that returns some HTML, depending on what part of the site and what path in the URL bar we're actually visiting. We also kept all the same instructions from earlier about getting the data related to particular users if we go to their user_id. Now, this data still comes from the data.json file that we store locally here and deploy with our website, so it's not a real application that I advise you to use in production, but it does give us a scaffold to run the same tests we had before against this application. Now, with all this happening, we'll still have a requirements.txt file for our flask and pytest dependencies. Now, the main other change that I've made inside of here is to the buildspec.yml file and the elasticbeanstalk folder here. There's two different configuration files to determine what we'll be doing. 

- The elasticbeanstalk folder just has one that basically tells Elastic Beanstalk how we want to deploy this application with Elastic Beanstalk, and it'll handle the rest of everything there with CodePipeline. The other big change though is in buildspec.yml where instead of just having a build command that runs the tests and then outputs them to a directory, we also have a section at the very end called artifacts. This will output all the code from our repository and then pass it along to the next part of the build pipeline. In this case, Elastic Beanstalk, and CodePipeline will help us do everything there. So now that we know what's inside of here, let's move on to the next step, which is setting up a CodePipeline pipeline. Let's go back to CodePipeline and finish this up in the next part of the demo.

<img src="img/img1.png"/>
<img src="img/img2.png"/>
<img src="img/img3.png"/>
<img src="img/img4.png"/>
<img src="img/img5.png"/>
<img src="img/img6.png"/>
<img src="img/img7.png"/>
<img src="img/img8.png"/>
<img src="img/img9.png"/>
<img src="img/img10.png"/>
<img src="img/img11.png"/>
<img src="img/img12.png"/>
<img src="img/img13.png"/>
<img src="img/img14.png"/>
<img src="img/img15.png"/>
<img src="img/img16.png"/>
<img src="img/img17.png"/>
<img src="img/img18.png"/>
<img src="img/img19.png"/>
<img src="img/img20.png"/>
<img src="img/img21.png"/>
<img src="img/img22.png"/>
<img src="img/img23.png"/>
<img src="img/img24.png"/>
<img src="img/img25.png"/>
<img src="img/img26.png"/>
<img src="img/img27.png"/>