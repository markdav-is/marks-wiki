---
title: How to initialize an Oqtane Repo
date: 2023-02-04
---

# How to initialize an Oqtane Repo
There are official guides online for getting started with Oqtane.  I've been an Oqtane fan from the start and use it as the primary way to deliver Blazor apps for work and Civic projects. This is not a post about the merits of Oqtane but rather how best to get started when working in groups.  I'm a strong believer that onboarding contributors to your repo should be as simple as pulling the dev branch and everything you need should be available.  This method has some additional steps that will include the source for Oqtane in your project and allow you to modify your fork of the framework if needed.

## tracking your own versions of Oqtane in a submodule.
Having the source of Oqtane available to the team is handy for seeing how things are done in the framework as well as a rich debugging experience. To make sure everyone is on the proper version of Oqtane, we have a local fork and create release branches using gitflow style release/v3.2.1 format that matches the release tags in the source Oqtane repo. These release branches come in handy when defining the submodule to pull a [specific version](https://stackoverflow.com/questions/1777854/how-can-i-specify-a-branch-tag-when-adding-a-git-submodule). When you init your repo, you can start with a readme and a .gitmodules file like the following:

``` 
[submodule "oqtane.framework"]
	path = oqtane.framework
	url = https://github.com/[your-org]/oqtane.framework
	branch = release/v3.2.1
	ignore = dirty
```

special note:  I've seen many time that specifying the branch doesn't work for whatever reason and folks need to double-check that the submodule is indeed pointing at the proper release branch.

## creating your base module
After pulling your repo and updating the submodule you should be set to run Oqtane.Server for the first time.  Open the Oqtane.sln, set Oqtane.Server as the startup project and run the app.  In the startup screen go with the defaults, and create a user named 'host' with any complex password you can remember for a few minutes. Once the database is created and the site launches head to the admin panel, module management and create a new module.  The new modules will be created in the root folder of your repo next to the framework. Exit the running app, and close the solution.

## changing package references to project references
the base module is created with three projects that have package references to the Oqtane.Server, Client and Shared libraries.  In every case you need to change those package references to project references.  Visual studio may get confused when you do this and you might ned to double-check your changes by re-opening the solution before committing and pushing your changes.

## ready to roll
Now you are ready to get rolling building your module or modules.  This approach gives you a nicely contained set of repo under your control and a full set of source for reference as well as a full debugging experience.

