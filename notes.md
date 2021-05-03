## Create github for fcc-handwashing
https://github.com/Mujirin/fcc-handwashing

## Cloning
At the '/Users/thomas/Documents/svelte/hwa' directory
```bash
    $ git clone github.com-Mujirin:Mujirin/fcc-handwashing.git
```
Copy git file inside fcc-handashing and place it in hwa dir, and then delete the folder fcc-handwashing
```bash
    $ git status
    $ rm .DS_Store 
    $ git status
    $ git add .
    $ git commit -m "blank svelte app"
    $ git status
    $ git push
```
And then creating this note and push again
## Adding font
https://fonts.google.com/specimen/Lato?query=lato#standard-styles
## If dev not run in 5000
```bash
    $ sudo killall node
```
## Installing blue print css
https://blueprintcss.dev/docs
```bash
    $ npm install blueprint-css --save-dev
```
## Installing rollup-plugin-css-only
To work with blueprint css one need to install this 'https://www.npmjs.com/package/rollup-plugin-css-only'
```bash
    $ npm install --save-dev rollup-plugin-css-only
```
## Pushing to Github
- checkout to
- create new branch from
	- branch name new
	- choose master
- checkout to master
- pull from new branch
- push
## Github Pages
This is for hosting in the app in github
### Install Github Pages
```bash
    $ npm install --save-dev gh-pages
```
### change something in rollup.config.js
Importing the gh-pages
    `import ghPages from 'gh-pages';`
And in line 77 from
    `production && terser();`
to 
    `production && terser() && ghPages.publish('public', (err) => {console.log("publish to github", err);`
```bash
    $ npm run build
```
## Github pages
- settings
- see Github pages link
https://mujirin.github.io/fcc-handwashing/
## Source
Source lesson from video on Youtube with title:

    "Learn the Svelte Javascript Framework-Full Cource"