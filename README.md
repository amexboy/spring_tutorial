# Spring frameworks + git + gradle tutorial
This repository is created to show the basics of working with spring based web application projects along side using git to manage versioning and gradle to handle builds.

In these days, using plain programming languages to build everything is obselete. If we do that, we would be evading one of the most fundamental principlece of Software Engineering -- Don't repeat yourself. If someone already invented the wheal, we use it. We don't re invent it. 

## Git
Imagine this scenario, 

You were working on a project. Finished major part of the project. Let us say, the project was SIMS. And you finished the part of the project that concerns the registrar so that the coming year's registration could be done with the system. Then they started registering new students. And you started adding other features. You made a lot of changes and project doesn't even compile now because you are not done with it yet. You're still coding it. But, saddenly, the registrar notice that you missed the part where you need to add a logout button.

What would you do then?

The old days, I would be carefull and I would create a folder for each working code. I would name it `SIMS_LIVE` and copy that folder and name it `SIMS_WIP` then when I start to change what is on live I would copy `SIMS_LIVE` and name it `SIMS_LIVE_OLD`. You see where I'm going with this. It gets ugly pretty quickly. And as you were working on some part of the system you may be blocked because you don't have all the necessary reqirments yet, so you want to start with another part of the system. You will create another folder for that too. Man! That is just hard. 

And what is worst is, you have to add the changes you made on one folder to the other folders. This dosn't work for a developer whose moto is

> Strive to be lazy

That is what every good programmer is. Lazy! I know I am. I don't mean to say I'm a good programmer, I just aspire to be one and being lazy helps a lot. If you don't trust me http://blogoscoped.com/archive/2005-08-24-n14.html or just google `Strive to be lazy` and it will tell you a lot about why! So, lazy programmers, they work to stop working.

Once upon a time a man named `Linus Trovalds` created `git` and it has bean one of the most amaizing things the software world have ever seen. It took over the world and soon it will take our jobs too. JK, it is just a version cotroll system. 

Remember the scenario I mentioned earlier. So, if I was using git, here's what I would do. (I don't expect you to know what the commands are, I just wanted to show you how easy it is)

     git init 
     //work on the project
     git add .
     git commit -m "Finishing registration"
     git tag "v1.00"
     //now to start working on something else
     git checkout -b working_on_teachers_lounge
     //work on that
     git add .
     git commit -m "added feature"
     //work on it but now it doesn't compile
     //and they asked you to fix the bug
     git commit -m "WIP"
     git checkout master 
     //fix bug 
     git commit -m "Fixing bug"
     git tag "v1.0.1"
     git checkout working_on_teachers_lounge
     git rebase master
     .....
     //then when you finished doing it 
     git checkout master
     git merge working_on_teachers_lounge
     
     
I only needed one folder and what I did on one branch is `merged` to master. And I can have as many branches I would like, so that I can work on things parallely and `git` is smart when merging code. It is not human smart, so we will talk about `merge conflicts` later.


So to start learning git, head over to https://git-scm.com/ and https://try.github.io/levels/1/challenges/1

## To be continued 
