---
title: Welcome to the VuePress + Netlify Example 
---  

<a href="https://vuepress.vuejs.org/" target="_blank" rel="nofollow">
    <img width="280" src="https://raw.githubusercontent.com/vuejs/vuepress/master/docs/.vuepress/public/hero.png" alt="logo" />
  </a>  
  

# VuePress

*This is a Starter template for a [VuePress](https://vuepress.vuejs.org) site and it integrates the NetlifyCMS with VuePress. 
VuePress is focused on content-centric static sites and provides features tailored for technical documentation out of the box.*




## Quickstart 

[Life Demo on Netlify](https://nifty-williams-038c26.netlify.com/)

Use the one-click deploy button and get a copy of this base-template as a repositary in your own GitHub account and additionally
a live-server version on Netlify for free. Every change in the GitHub **README.md** file will then automatically change 
on this server too.


## One-Click Deploy

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/iwilfried/vuepress-boilerplate)

Documentation of other free server deployments like GitHub Pages, Gitlab Pages, Gitlab CLI, Google Firebase, Surge, Heroku 
you can find under [vuepress.vuejs.org/guide/deploy](https://vuepress.vuejs.org/guide/deploy.html)

``If you edit the files in Github direct, the changes are automatically done on the server too.``



## Local Development - Getting Started  

### Step 1: Install VuePress.  
You need: Node (npm), Yarn, Vuepress, Git and an editor for your development. Read more...  

Create a project directory called myProject.

```bash
mkdir myProject
```
Go into that directory.  

```bash
cd myProject
```  

I am using Yarn as a package manager, so let us pull the package using the following command.  

```bash
yarn add vuepress
```  

If you are not using Yarn, then you can pull through NPM.  

```bash
npm install vuepress --save  
```
Now, open the project in your favorite editor.

```bash
code .  
```  

### Step 2: Create a folder inside the root.
Inside the project root folder, create one folder called docs.
Now, in that folder, make one **markdown** file called a **README.md**.
In the README.md file, just write the following line of code.  

```bash
# Hello World  
```
Okay, now we need to run the project.  


### Step 3: Run the Project in development server.
Go into your root folder, and open the terminal and hit the following command.  

```bash
npx vuepress dev docs  
```  

Calling npx when isn't already in your $PATH will automatically install a package with that name from the npm registry for you and invoke it.


``Switch to your browser and go to this URL: http://localhost:8080/``

You can see the Hello World. Here # means h1 tag equivalent to **HTML**. It is simple Markdown syntax.
You can add the scripts to **package.json** file.  

```bash
{
  "scripts": {
    "docs:dev": "vuepress dev docs",
    "docs:build": "vuepress build docs"
  }
}  
```

Now, stop the server by **control + c** and then start the server with the following command.

```bash
npm run docs:dev
```
You can also generate the static assets using the following command.
```bash
npm run docs:build  
```
By default, the built files will be in **docs/.vuepress/dist**, which can be configured via the dest field in **docs/.vuepress/config.js** The created files can be deployed to any static file server.

### Step 4: Configuration.  
For creating a configuration file, we need to first create a folder inside the docs folder called **.vuepress**.

Inside .vuepress folder, create a  javascript file called **config.js** file.

```bash
// config.js

module.exports = {
  title: 'First VuePress Project',
  description: 'Exploring VuePress'
}  
``` 

Okay, if your development server is running, then you can see that the page now has a header with the title and a search box.  
VuePress comes with built-in headers-based search – it automatically builds a simple search index from the title, h2, and h3 headers from all the pages.

![](https://github.com/iwilfried/vuepress-boilerplate/blob/master/docs/.vuepress/public/images/helloWorld.png)  

There are more configurations that you can apply, for example, base, title, head, Google Analytics, Port number and other stuff.

### Step 5: Asset Handling  

In our project, docs folder is mainly reacting as a root folder, so we need to create one folder called images inside docs folder, and them move any local image to that folder. We can access using this syntax.

```bash
README.md  
# Hello World  
![An image](./images/Krunal.jpg)  
```
You can see, now we can see the image in our page.  You can check out the more options here.

### Step 6: Create second md file inside docs folder.
Okay, now create second Markdown file inside docs folder called Demo.md. Write the following line inside that file and save it.

```bash
# This is second demo  
```
Now, see the project in the browser.

You can see here, the content is displaying in the browser and after clicking that link, we can redirect to a new route, and that is **Demo.html**.   

We have not defined any route but still, VuePress takes that second file as another route, and after clicking that link we redirect to that page. How cool is that!! It automatically figures it out by itself.

You can check out the [markdown extensions](https://vuepress.vuejs.org/guide/markdown.html). It is handy for creating content.

In future, we will build an entirely static website with the help of VuePress.

### Conclusion
It is the perfect framework for the creating technical documentation and blog. It is server-side rendered so entirely SEO friendly. VuePress Tutorial For Beginners is over.

-------------------------------------

------------------------------------------

# Getting Started
It is the perfect framework for the creating technical documentation and blog. It is server-side rendered so entirely 
SEO friendly.

## Inside an Existing Project  

If you have an existing project and would like to keep documentation inside the project, you should install VuePress 
as a local dependency. This setup also allows you to use CI (Integration) or services like Netlify for **automatic deployment** on push.

### Create a docs directory
``mkdir docs``  


<img src="http://res.cloudinary.com/iicamp/image/upload/v1531130948/VuePress/dir-structure-01.png" />

::: warning
It is currently recommended to use Yarn instead of npm when installing VuePress into an existing project 
that has webpack 3.x as a dependency. Npm fails to generate the correct dependency tree in this case
:::  


### Install VuePress as a local dependency
  
| `` yarn add -D vuepress ``|  **or**  |  ``npm install -D vuepress ``|   

<br />
 
<img src="http://res.cloudinary.com/iicamp/image/upload/v1531132990/VuePress/dir-structure-02.png" />



### Create README.md (index) file  

``echo '# Hello VuePress' >docs/README.md``  

<img src="http://res.cloudinary.com/iicamp/image/upload/v1531134493/VuePress/dir-structure-03.png" />

The file-name for the first page must be **README.md**, because this is always the index-file


Then, add some scripts to package.json:


<img src="http://res.cloudinary.com/iicamp/image/upload/v1531143372/script-package_rwq2ym.png" />


You can now start writing with:

```bash
yarn docs:dev # OR npm run docs:dev  
```  

To generate static assets, run:

```bash
yarn docs:build # Or npm run docs:build  
```
By default the built files will be in **.vuepress/dist**, which can be configured via the **dest** field 
in **.vuepress/config.js**. The built files can be deployed to any static file server. 

<img src="http://res.cloudinary.com/iicamp/image/upload/v1531144645/dir-structure-04_wm3pyq.png" /> 
 
See [Deployment Guide](https://vuepress.vuejs.org/guide/deploy.html#github-pages) 
for guides on deploying to popular services.  





## Quickstart 

Use the one-click deploy button and get a copy of this base-template as a repositary in your own GitHub account and additionally
a live-server version on Netlify for free. Every change in the GitHub **README.md** file will then automatically change 
on this server too.

### [Life Demo on Netlify](https://nifty-williams-038c26.netlify.com/)


## One-Click Deploy

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/iwilfried/vuepress-boilerplate)

Documentation of other free server deployments like GitHub Pages, Gitlab Pages, Gitlab CLI, Google Firebase, Surge, Heroku 
you can find under [vuepress.vuejs.org/guide/deploy](https://vuepress.vuejs.org/guide/deploy.html)

``If you edit the files in Github direct, the changes are automatically done on the server too.``
