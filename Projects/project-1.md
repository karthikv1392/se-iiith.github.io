---
layout: page
title: Project 1
permalink: /projects/project-1
parent: Projects
nav_order: 1
---

# Overview

Welcome to the first project of the CS6.401. Software Engineering course. Your objective in this project is to apply the concepts you have learned (and will learn) in the class to improve an existing software system. You will reverse engineering the design of the system and refactor it following grounded software engineering principles. You will use some tools to analyze the code and collect metrics to aid this process.

Music, a web-based music server will serve as the testing ground for the project. The app can be used to organize your music collection and download music from different sources (well, that's what it can do for now). You can find the original repository at [https://github.com/sismics/music](https://github.com/sismics/music). We will use a class-specific fork which has been slightly streamlined for ease of use.  

The project also contains two bonus components, which although optional are encouraged to be attempted, as these can help you make up for marks lost in other components throughout the course.

# GitHub Classroom

You should be part of a team already. If not, quickly follow the instructions in [this Moodle post](https://courses.iiit.ac.in/mod/forum/discuss.php?d=32017) section to join your team.

For this project, follow [this link](https://classroom.github.com/a/w8NFAxXI) to accept the assignment for your team. Your team will then be assigned a private repository on GitHub. This is where you will be working on the project. All relevant instructions for running the project will be present in the repository.   

# Specification

## 1 Mining the repository

Music is organized in several components, and to make meaningful improvements and contributions to it we need to become familiar with its structure and organization. The first task revolves around this.

Consider the following features -

1. User management - Several users can use the same Music server for managing their libraries. Music thus has a user management system, with users needing to login to add music to the library. In its current state, it is quite rudimentary. The users share the same library rather than having their specific libraries, and the only way to create new accounts is through the admin account.

2. Library Management - Wouldn’t be much of a music application without this. Users can add songs to Music with a two-step process. First, new music is imported in one of two ways - uploading local files, or downloading files from external sources. Once the file is imported, they can be added to the library after adding metadata information. 
Users can also edit existing songs. They can change the metadata information, add album cover art, or add the songs to new playlists.

3. Last.fm integration - Last.fm is an online service that, according to Wikipedia, "using a music recommender system called 'Audioscrobbler', builds a detailed profile of each user's musical taste by recording details of the tracks the user listens to, either from Internet radio stations, or the user's computer or many portable music devices". Music allows users to link their Last.fm profile, and sync their listening history with it.

4. Administrator features - In addition to the above features that are available to all users, the administrator has further privileges. To be precise the features that we are concerned with are - they can create and delete user accounts and change the local directory to which the music is stored, or add new directories.

*Task 1- Identify the classes responsible for these features, and document their functionality and behavior. Use UML class diagrams (you may need multiple) along with OOP concepts such as inheritance, association, aggregation etc. with an appropriate level of abstraction to paint a clear and concise picture of the system. Present observations and comments such as points of strengths and weaknesses of the system as part of this. You will be evaluated on the completeness and correctness of your documentation. You can make simplying assumptions if necessary, but clearly state these in your report. Contact the TAs in case of any queries*

## 1E Bonus - Transition System

This is a bonus question. You will learn about transition systems in class very soon. We will apply those principles here. 

*Task 1E - Using the Transition Systems approach for modeling behavior, document the behavior of the four features (think of them as subsystems) by modeling each of them as a transition system. Given that these subsystems interact with each other to provide the intended functionality, also describe the connections amongst various U (actions) and Y (observables), in equation form as well as in diagram form.*


## 2 Analysis

We now know how Music works. The next task is to know how *well* it works. For this, we will use automatic code evaluation tools to help with this.

### 2a Design Smells

Design smells are structures and patterns in code that while not incorrect, are indicative of violating fundamental design principles. These can hinder development by leading to recurring problems down the line and should be avoided. Many automated tools exist to identify these. We will use Sonarqube for serving this purpose in our project. The [official documentation](https://docs.sonarqube.org/latest/try-out-sonarqube/) is a good resource for learning how to use it.  

Sonarqube identifies *code* smells in a given repository. Code smells are closely related to design smells, but are more specific in nature. Make sure that you list design smells, not code smells. Note that Sonarqube is not perfect, use your own judgement wherever. 

*Task 2a - Identify 5-8 design smells in the project. Use the code smells identified by Sonarqube to support your analysis.*

> PS - Sonarqube and the project itself require different Java versions to run. Instructions for handling this are provided in the project README 

### 2b Code Metrics

Code metrics are objective, repeatable, empirical measure of a project’s properties. Many tools exist for computing these for software repositories such as Checkstyle, PMD etc. We will use some of these tools to get some metrics for our project in its initial state. You are free to use any tools you find fit for this purpose.   

*Task 2b - Report up to 6 code metrics for the project (and mention the tools used). What implications do you think these have? Do they guide your decision process for refactoring in any way?* 

## 3 Refactoring

We have now thoroughly understood the organization and performance of our system. It's finally time to get our hands dirty. In the previous task you have identified various metrics and design smells for the repository which inform us of the code quality and how well it works. There's plenty of room for improvement, right? As the final part of this phase, we will address this.

### 3a Design Smells

You identified 5-8 design smells previously. We now to want to fix these by refactoring the code to improve its design. Note that we do not want to throw away the previous code or fundamentally change its functionality.

*Task 3a - Improve the code quality by refactoring it to remove the design smells identified. You don’t need to be exhaustive, but ensure that your refactoring is not trivial in nature. Remember that you should not change the program’s behavior. You will be evaluated on the correctness of your refactoring*

### 3b Code Metrics

Now that you’re done with refactoring, let’s see how the metrics have been impacted. 

*Task 3b - Remeasure the metrics previously measured after refactoring. Have they improved or worsened? Is the trend consistent across all metrics? Does this match your expectations? Also attempt to analyze what contributed to this.*

## 3E Bonus - Automatic Refactoring  
This is a bonus question. Automatic refactoring is a topic of great interest in software engineering research. As the name suggests, it is the process of automatically refactoring code according to certain constraints and requirements. Why not try our hand at this?  

*Task 3E - Propose an approach for automating the process of refactoring code according to the requirements of this project (i.e addressing design smells with consideration for code metrics). While you don't need to implement this, you need to describe your solution in detail. You will be graded on the clarity and feasibility of your solution. Make reasonable assumptions, but feel free to think outside the box. And note that simple is fine, but frivolous is not.*

# Submission

The submission for this phase will be through GitHub classroom. The codebase will be automatically downloaded at the deadline, so ensure that everything is up in time. No exceptions will be granted.   

In addition to the code changes required for Task 3a, you also need to submit a report containing your responses for each task. The report should be present in the `docs` directory, titled `project1_<team_number>.pdf`. If you are attempting the bonus, submit a separate document titled `project1_bonus_<team_number>.pdf` containing the corresponding responses. 

Accurately report the contribution of each team member at the end of the report. This will be considered when evaluating the project. 

Soft deadline - 15th February, 2022

Hard deadline - 22nd February, 2022

**Note: Bonus can be submitted till the hard deadline without any penalty. Late days are not applicable for bonus components**  
The course policy menitioned on this website will be followed for late submissions and associated penalties/late days. 
