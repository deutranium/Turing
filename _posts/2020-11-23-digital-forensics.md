---
layout: post
featured : true
title:  "Digital Evidence Forensics"
author: abhi
categories: [ Digital Forensics ]
image: assets/images/Digital-Fingerprint.jpg
---

So you're Felicity Smoak and Oliver hands you his bullet-ridden laptop. You now start salvaging everything you can from it... except you don't know how. This article is all that stands between you and losing your job.

<!-- Youtube video embed-->
<br>
<div class="embed-responsive embed-responsive-16by9">
<iframe width="560" height="315" src="https://www.youtube.com/embed/H-Hx7uFt4m0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>
<br>

In this article, we will go over how to use the Digital Evidence and Forensics Toolkit to retrieve data (including deleted data) from a storage drive (Ex: a flash drive). In the rest of this series of articles, we will delve into the algorithms used in each step of the way.

## What and why?

Digital Forensics is a science of finding evidence from digital media like a computer, mobile phone, server, or network. It is used to find and analyze digital evidence evidence from crime scenes to be used in courts of law. As the evidence obtained can be used in a court of law, it is crucial to make sure that the evidence itself is never tampered with and also to prove that any copies being analyzed are indeed the same as the evidence found at the crime scene.

## The basic steps of digital forensics

Digital forensics can be performed on nearly any electronic storage media (personal computers, mobile phones, external drives, etc). In this example, we will perform digital forensics on a 512 MB flash drive (the larger the drive is, the longer it takes to analyze it). Note that I will be using DEFT (Digital Evidence Forensics Toolkit) in this example. DEFT is a separate operating system with tools useful for digital forensics and can be run as a virtual machine.

There are 5 main steps to digital forensics:

1. **Disk Identification**:

   ​	Disk Identification is the process of finding out what evidence is present, where it is stored and how it is stored. In our example we used the following commands:

   - **fdisk -lu**: “fdisk -lu” is used to list out all drives/disks (internal and external) of the system. Using this command we identify which drive/disk we wish to perform data retrieval upon (in this case /dev/sdb1).
   - **fls**: “fls” is used to list out all files and directories present in the specified drive/disk. We can use this to check what data is stored in the pen drive before we begin the data retrieval process.
   - **fsstat**: “fsstat” displays information about the specified drive/disk. Things like the file system type label, the file system distribution (in sectors), etc.

   ​    Using these three commands we can identify the disk we want to perform data retrieval upon and understand more about what kind of data exists in the disk and about the disk itself.

2. **Disk Imaging**:

   ​	Disk imaging is the process of creating a replica or an "image" of a specific disk. The reason this step is important is to ensure that the actual data in the disk is not tampered with and preserves the disk as it is was found (these disk are normally taken from crime scenes as pieces of evidence).

   ​	A disk image share the properties of the disk and is essentially a copy of the disk. The disk image is later analyzed and searched to find relevant information, whether it has been deleted or is currently present.

   There are two main ways of creating a disk image:

   - **dd**: "dd" is a basic disk imaging command that takes a given file/disk and replicates the exact binary sequence that makes up that file/disk. This way we can create a file that has the exact same information and structure as the disk we want to analyze.
   - **ddrescue**: "ddrescue" is an evolved version of "dd". Not only can it replicate a disk, it can also replicate a **damaged** disk, i.e. a disk that contains errors when accessing certain disk sectors. Thus allowing you to retrieve information from even a slightly burnt/broken disk.

3. **Disk Hashing**:

   ​	Disk Hashing is the process of generating a "hash value" for the disk and disk image. A hash value is a unique value that is produced based on some calculation (differs with different hashing algorithms) done upon the provided file/disk. Thus, when the hash value of a disk image and the hash value of a disk are the same, the disk image is proved to be an exact replica of the disk. The main purpose of this is to prove the credibility of the evidence found from the disk image in court.

   ​	There are many different kinds of hashing algorithms and commands which will each give a different hash value for the same disk since their methods of calculating the hash values is different. If you want to learn more about the hashing algorithms, you can check them out [here]({% post_url 2020-11-23-digital-forensics %}).

   ​	The hashing algorithm we used is "md5sum" although almost any hashing algorithm will work. Some other hashing algorithms are sha1sum and sha256sum. They all do the same thing, just slightly differently. There are other commands like "dcfldd" and "dhash" which can be used to simultaneously create an image of the disk and create the hash values for the disk and disk image.

4. **Disk Carving**:

   ​	Disk Carving is one of the most interesting and important steps in digital evidence retrieval. Carving is the process of recovering files no longer referenced by the file system, through the recognition of the header and the footer of files. It's what's used to access the deleted files/data in a disk and analyze them. There are two main commands used in disk carving:

   - **foremost**: "foremost" is a very straight-forward command which can be used to recover deleted files directly a disk/disk image. "foremost" recovers the deleted files and sorts them based on file type.
   - **bulk_extractor**: On the other hand, "bulk_extractor" is a much more interesting command. "bulk_extractor" reads through the data and looks for things like phone numbers, email ids, etc. Not only does it look for such things, but it also creates histograms of the relevant data to make it even easier to analyze. All-in-all, "bulk_extractor" is a very useful command to look for and analyze certain kinds of information in a disk.

5. **Disk Analysis**:

   ​	Disk Analysis is done to analyze the content of the specified disk/disk image and obtain crucial information regarding the times of creation, edit, and deletion of files. This can assist an investigation in many ways such as analyzing the time frame in which a certain piece of evidence was used/made. Disk Analysis is done using the autopsy forensic browser (which can be run by using the “autopsy” command). 

   ​	

​	