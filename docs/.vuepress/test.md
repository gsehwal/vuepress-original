To try it out locally, clone this repo and generate a static site

```bash
# Clone the repo
$ git clone https://github.com/iwilfried/vuepress-boilerplate.git
$ cd vuepress-boilerplate

# Install dependencies
$ yarn  # OR npm install

# Run
$ yarn dev  # OR npm run dev

# Build
$ yarn build  # OR npm run build  (-> .vuepress/dist)
```

Check your site at `http://127.0.0.1:8080/`  or `localhost://8080`

<br />

## Review of the files in the project-directory 

.  
|---gitignore  
|---LICENSE  
|---README.md  
|---**docs**  
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|---README.md   
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|---welcome.md  
|---netlify.toml  
|---package.json  
|---yarn.lock  

<br />  

Let's start by explaining the meaning of some of these files.  

If you want to use the **One-Click Deploy** option, then Netlify needs a `netlify.toml` file.  

### netlify.toml  

```bash
[build]  
command = "yarn docs:build"  
publish = "docs/.vuepress/dist/"  
```

This file is used by netlify on deployment. Netlify pulls code from your github repo, and will run command to generate your static site. Once it's complete publish tells it where the public directory is to launch your site.


### package.json  

```bash  
{
  "scripts": {
    "docs:dev": "vuepress dev docs",
    "docs:build": "vuepress build docs"
  },
  "devDependencies": {
    "vuepress": "^0.10.2"
  }
}  
```

This file is the standard VuePress settings that you would have if you followed the official Vue Press installation guide.

### /docs  

|---**docs**  
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|---README.md   
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|---welcome.md  

<br />  

Lastly, the docs folder contains actual markdown files that will make up the content of our site itself. These files are committed to github, and netlify's cms will work with these via a CMS that we will have setup by the end of this tutorial.  

If you review these files, note that README.md is different than the other two because it's serving as the home page for the site. VuePress reads front matter to configure this post differently. There are a lot more options you can configure using these properties but I'll leave that to you to read the VuePress docs.  









For more information, see [VuePress Docs](https://vuepress.vuejs.org)
