# How to deploy a react app on Github

For starters, run the following command to create a repository names my-app using ```create-react-app```: 

```
$ npm init react-app my-app
```

Then you need to install the [gh-pages](https://www.npmjs.com/package/gh-pages) package as a dev-depedency. 

```
$ cd my-app
$ npm install gh-pages --save-dev
```

Add the following property at the top of your ```package.json``` file :
```http://{username}.github.io/{repo-name}```

Also add to the scripts : 
```
"scripts": {
//...
"predeploy": "npm run build",
"deploy": "gh-pages -d build"
}
```

For the next step, you need to create a Github repository with your app name and add it as a remote in your local git repository. 
```
$ git init
```
```
$ git remote add origin https://github.com/user/repo.git
# Set a new remote

$ git remote -v
# Verify new remote
> origin  https://github.com/user/repo.git (fetch)
> origin  https://github.com/user/repo.git (push)
```

Finally, to deploy your application you can run : 
```
$ npm run deploy
```
## References : 
[Official react doc](https://create-react-app.dev/docs/deployment/#github-pages-https-pagesgithubcom)

## Notes : 

The master branch is supposed to hold the source code, while the gh-pages branch holds the built code. Though the deployment works just fine in my case, I can't seem to be able to push my source code onto the master branch (might be a problem ?) cf. https://www.freecodecamp.org/forum/t/question-about-deploying-react-pages/179636 for possible solution.
