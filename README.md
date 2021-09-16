GitHub in Remix IDE
Remix release v0.18.0 now includes full support for an app that allows you to interact with GitHub as if you were doing it on your terminal or in VSCode.
It supports cloning, pushing - with force even - , pulling, using branches, working with remotes & checking out previous commits & files. It also includes a nifty diff viewer.
What is doesn't do is more advanced tasks such as rebasing, squashing and the likes. But you will find the basics to be ample. 
The app that does all this is called dGit and you will find it in the list of plugins.
Dangerous clones

Remix operates in the browser and that is where it stores your files - unless you're using remixd of course.
That storage is limited, very limited. So if you're planning on cloning a large repo you will kill your running Remix. That is why dGit offers you the option not to clone all branches plus to specify the depth of your clone. This last options limits the amount of commits you import. Most of the time you'd be working on the last commit anyway, right? 
So clone safe, clone carefully, don't clone Open Zeppelin, pick a repo that deals with designing solidity contracts, not an npm package. If you do happen to destroy Remix and flood it with data it will freeze, the only thing you can do then is clear your local storage in your browser.
DGit features a nice meter that shows you how far you are in filling up the storage. Keep it clean, if you're not working on a workspace remove it or push it to GitHub or IPFS for safe keeping.
Personal tokens
When you want to work with GitHub like this, pushing and pulling and using private repositories, you will need a personal token that allows you to do this. You can create such a token in your GitHub settings -> Developer settings. You will need to get a token that has REPO privileges. You copy that token and past it in the dGit GitHub settings. 
As is customary when using git you will also need to set a name and email, just like you do on the terminal or in VSCode. This will tell GitHub who is doing the commit. Easy!
Workspaces
In case you haven't noticed, Remix uses workspaces to manage sets of files. DGit will treat each workspace as a git repo. When you switch workspaces & create a new one dGit will follow and track your files. 
A lesson in Git?
This will not be necessary but let us sketch a basic scenario of how to use it.
You've created an empty git repo on GitHub, private or public.
You would then clone it in dGit.

This will automatically set the remote for you and call it 'origin'. You can add more remotes if you need them.

You work on your files, stage them and commit them

You push to your repo

M is for Modified
DGit tracks changes in your files in a similar way VSCode does it. If there are no changes or new, untracked files you won't see anything.
For everything else dGIt shows you codes which represent the status of the file:
M stands for Modified
U stands for Untracked
D stands for deleted

The stage is yours
By clicking on 'Stage all' or a plus button you can add files to the staging area. 
You can also undo your changes or remove your files from staging.
The log provides you the status of your repo. Mind you, if you have only cloned limited commits, this won't be filled up with entries but you'd still be working on the repo as it is. 
Ch-ch-ch-ch-changes
If you click on any file in 'Files' it will either open the file in the editor or when it's been modified open it in the diff viewer.
Interplanetary…
If you don't care much for cloud storage or just need to publish your code in a fire-and-forget way where you don't want to create a repo for it, you can use IPFS to publish your work. DGit offers the option to do this. Read more about this in this article: https://medium.com/@filip.mertens/decentralised-git-in-remix-d6dc7335e436
