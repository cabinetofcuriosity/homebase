# Cabinet of Curiosity: Exploratory analysis of Natural History Databases

## About

Natural history data is broad in scope and can range from species occurrence data to environmental measurements to basically any data that describes how organisms interact with each other and their environment.  In the past 15 years there has been an increasing drive to digitize this data and make this data available through public databases.  This project explores these vast datasets from a data science perspective. We will be performing both team and self-directed exploratory analyses with immediate products in the form of medium length reports that will be published on-line at the [Cabinet of Curiosity Website](https://github.com/cabinetofcuriosity/cabinetofcuriosity_site).  

The purpose of this work is to:

1. provide tutorials on how to access and analyze this data 
2. survey the types of questions that are possible in these databases 
3. Provide critical analysis and make recommendations / build tools to increase usability of these databases 
4. perform biological / ecological research that can be expanded in greater depth for peer reviewed publication.  

## Team - Fall 2018

The team consists of CS, Data Science, and Applied Math majors at UC Berkeley. 

- Yihui Zhu
- Jesse Woo
- Samantha Tang
- Yuqing Lu
- Zoe Liu
- Yikang Li
- Ollie Downs
- Winifred Chung 

## Skills Objectives 

- learn to ask research questions
- statistical analysis of research questions
- telling a story with data
- visualization of data
- data science portfolio
- write collaborative code
- learn reproducible methods
- Handel different types of data
- merge different types of data
- critical analysis of code
- write documentation

## Questions that need to be answered when exploring these databases this semester

- What features you find most useful?
- What kind of questions can we ask when using this database?
- What tools are available top use this database?
- What skills are required to use this database? Are there different options depending on skill level?
- How do you get the data?
- What external tutorials helped you access the database?
- What are the challenges to using this data?
- What are the rules for using this database? Are their specific licenses?
- Are there tools that you can imagine being built that would make using this database more usable?
- What other databases can you use to merge into your database easily?

## Steps for posting on the Cabinet of Curiosity Site

1. Fork repository (repo) into your Github user account.
2. Clone repository onto your local machine. 
3. Place a new post in the `_posts/` folder
4. `git add file` to stage file to commit.
5. `git commit -m "message about commit"` to commit file.
6. `git push origin gh-pages` to push commit to your remote Github user account.
7. Make a pull request on Github website.
8. Wait for someone (likely Ciera) to approve of your commit. 
9. Tada.  It should be online.

## Steps for keeping your local repo upto date with the downstream repo

When collaborating on projects on Git, one thing you have to keep doing is making sure your forked rep is update with the "main repo".  Here are the steps for updating.  Please do this before you push to Github and update frequently to avoid merge conflicts. Essentially you have to 1. [Configure a remote for your fork](https://help.github.com/articles/configuring-a-remote-for-a-fork/) 2. [Sync you fork](https://help.github.com/articles/syncing-a-fork/).

1. The common term for your forked repo is "upstream". So the first step is assigning the forked repo as a remote repo name `upstream`. 
2. `git remote -v` to see your remote repos
3. `git remote add upstream https://github.com/ORIGINAL_OWNER/ORIGINAL_REPOSITORY.git` to assign the main repo to a remote repo called `upstream`
4. `git remote -v` Check to make sure it worked
5. `git pull origin master`Pulls all the changes that were made in the upstream repo and merges with your local repo

Now everything should be up to date.....unless there were merge conflicts.
