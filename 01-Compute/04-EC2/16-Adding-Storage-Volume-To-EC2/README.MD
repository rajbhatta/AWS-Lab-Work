# Adding a Storage Volume to an EC2 Instance #

- Let's take a look at how we can add an EBS storage volume to our instance. We're going to go through the entire process. 

- We'll first create the volume in the AWS console and attach it to an instance and then mount it so that it's available for use. Let's get started. First, from the EC2 dashboard, hit Volumes under Elastic Block Store. Here is where all of our volumes are listed. 

- Let's make a new one. We'll set the size to the minimum possible. We also need to set the availability zone. This volume will only be available to the instances that are in that zone. You can optionally choose a snapshot, in other words a backup, to restore the volume from and choose if you'd like to have the volume encrypted. Hitting Create Volume will finalize this process. 

- You should now see it present in the list of volumes. You'll notice that it's in the available state. Available means that it has been created and is ready to be attached to an instance. To attach it to one, select the volume, hit Actions and then Attach Volume. Here, we can search for the instance that we want to attach the volume to. 

- Let's select the one that we launched previously. We can also select a name for the device, but we'll leave that as the default. If we hit Attach, you'll notice that the volume has gone into the in‑use state since it is now attached to an instance. 

- In order for our instance to actually use this drive, we'll need to format it because new volumes are raw block devices, and then mount it so that it's accessible from our instances file system. 

- We need to do this from within the instance, so let's first connect to it with SSH. Now, let's use the lsblk command to view the drives available to our machine. The simplest way to tell which volume is the new one is by the size that is listed. 

- I know that I created the instance with an 8‑GB root volume, and we specified that we want our new volume to be 1 GB. So, we can spot this one out. Its name is xvdf. Now, we need to make sure our volume has a file system on it. 

- We can check if it does by running sudo file ‑s with the device name. This returns data, which means it does not have a file system on it. To build one, we can use the mkfs, or make file system command, assigning it an XFS file system. Let's do another check to verify that this worked. 

- As you can see, the command output the file system information instead of data. Now, we need to create a mount point for the volume. Let's create a directory called my‑mount‑point and then use the mount command, specifying the volume and this directory. Now that that's done, when accessing the my‑mount‑point directory, we'll actually be accessing the volume. 

- To recap what we did, we use the AWS console to create and attach a volume to our instance. Next, we connected it to our instance, formatted the volume, created a directory that will act as a mount point, and finally, we mounted our volume to that mount point.

# Snapshots #
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