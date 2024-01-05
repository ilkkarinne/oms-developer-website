# OMS Developer Website
Observations, Measurements and Samples (OMS) developer website

The theme used is a Node/Pug to Jekyll/Liquid conversion of the [Agency](https://startbootstrap.com/theme/agency) one page HTML theme for Bootstrap by [Start Bootstrap LLC](https://startbootstrap.com/). 

The contributor understands that any contributions, if accepted by the OGC Membership, MAY be incorporated into OGC documents and that all copyright and intellectual property SHALL be vested to the OGC.

## Powered by GitHub Pages and Jekyll

The website is automatically built and deployed by GitHub using [Jekyll](https://jekyllrb.com/) and the source files in the ```docs``` directory of the ```main``` branch. Pushing any committed changes to theses source files will trigger an automatic site build and deployment process and, within a few minutes, result in an updated version of the site.

## Site development and local testing

It's a good idea to test the changes out before pushing them to the main branch in order not to break the site by accident. [Docker](https://docs.docker.com/get-docker/) and the [Docker GitHub Pages](https://github.com/Starefossen/docker-github-pages) container can be used to run a Jekyll configuration very similar to the one used by GitHub Pages locally on developers' computers.

Steps to follow:

1. [Install Docker Engine](https://docs.docker.com/engine/install/), ja [git command line](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git), if not already done.
1. If making any bigger changes, or if you don't have push permission to the OMS Development Website GitHub repo, create your own [fork](https://docs.github.com/en/get-started/quickstart/fork-a-repo) of the repo. It's usually also a good idea to create a feature branch to your forked repo for the intended change. 
1. [Clone](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository) the repo or your own fork to your local computer:
   ```sh
   $ git clone https://github.com/<your-gh-account>/oms-developer-website.git
   ```
1. Change to folder ```oms-developer-website/docs```
1. Start Docker Engine if not already running 
1. Run Docker GitHub Pages container at port 4000:
   ```sh
   $ docker run -it --rm -v "$PWD":/usr/src/app -p "4000:4000" starefossen/github-pages
   ```
1. After a successful build the local development version of the site will become available at http://localhost:4000/ 
   If you see an error message "docker: Cannot connect to the Docker daemon...", make sure your Docker Engine is running in the background.
1. Open another terminal or use an editor with a graphical UI to make any necesary changes. Jekyll running in the Docker GitHub Pages container will notice the changes and rebuilt the site automatically (monitor the terminal running the container to see when the rebuilds are done). Make sure no syntax errors were made and the changes look as intended.
1. Commit any changes (remember describe what you did in commit comments). Commit as soon as you get the smallest working change done (and while you still remember which files you changed and why).
1. When you are finished, push the changes to your fork repo (or directly to the main repo if you are confident and have the necessary permissions)
1. If working with a fork repo, create a [Pull request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests) from your feature branch to the main repo. Repo admins will check your change and either merge it or ask you to make some changes in order to fix possible problems.

