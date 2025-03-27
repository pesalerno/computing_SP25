Protocol for collaborating on git
------

>> This very simple protocol is for collaborating with a single person on a project... it gets a lot more complicated with more people! 

Ideally, every time you begin to work on your local machine files for the git repository, you PULL before you do anything else. So, from within your active git repo, you type: 

		git pull

And it should update you to the online repo.... Now let's say you had forgotten to pull, and made a bunch of changes in your local computer.... if you pull without doing anything else... **you lose ALL the work on your local computer that you didn't commit!** So, here's what to do before doing ***git pull*** or anything else with your local git repo before connecting online. 

1. First, check the status:

		git status 
	
If there is nothing there to update, just ***git pull*** the online repo. If something is flagged as changed but not added, then do the usual:

		git add name_of_file(s)
		git commit -m "message for commiting change(s)"
		git push origin master

Now, if it's not up-to-date with the online branch of the repository, it will give you an error and not upload! Now what? 

		git pull

Hm.... this gives you a strange error message and jumps into this weird-looking file... follow these instructions to get out safely: 

		i #simply type i on your machine
		### go to the second line with the down arrow, type a message for "merging branches"
		### press [ESC]
		: ##type colon
		wq ##type wq then enter

VOILA! Now you can do: 

		git push origin main

with no issues! your commits/changes have been merged to the other branch... this is provided you didn't change the EXACT same lines that had been changes on the online branch.... In that case, you'll go down another rabbit hole.... 

In general, to avoid all this, it's better to always just PULL before any changes.... NEVER forget to check status and commit any changes BEFORE you pull an older branch to not lose your local work!!

	




