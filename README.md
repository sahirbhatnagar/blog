How to deploy a blog post
================================

 - On master branch in root of blog directory, make a post or whatever changes. A new post can be made via
 
 ```r
 blogdown::new_post(title = "Name of new post", ext = ".Rmd")
 ```
 
 - You do not need to compile the `.Rmd` file because the `blogdown::build_site()` in the deploy script does it for you.
 - `git add --all` and then `git commit -m "message"` and then `git push origin master` so that you keep the source of the blog up-to-date and version controlled
 - then run `./deploy "enter a commit message here in quotes"` from the root of the blog directory on the master branch. this will build the site and push to gh-pages branch (you will be prompted for password)
 - this will leave un-committed changes to the residual files from building the website in the `content/` and `static` folder. Not sure what to do with these. I guess leave it for now. It will get committed the next time you commit something on master. Or manually remove them before the next commit. 
 - command so that git doesnt ask you for passwords all the time:
 
 ```bash
 git config --global credential.helper 'cache --timeout=3600'
 ```
