# [AASTBIS](https://github.com/Youssef1701/aastbis)

> Real time code sharing for your lectures and presentations.

[Website](https://github.com/Youssef1701/aastbis)

## What is AASTBIS

Start AASTBIS inside your project folder, share the URL with your audience and start coding.
Any time you save a file, viewers will receive those changes. They can browse through the files, go back in history, copy the code, download the project, preview images, chat with other viewers, ask the presenter to slow down, etc.


## User instructions

#### 1 - Install AASTBIS globally

You must have [NodeJS](https://nodejs.org/en/) and [NPM](https://www.npmjs.org) already installed.
In your console, run:

<sup>(You may need to add `sudo` at start for Mac)</sup>
<sup>(You may need to run `Set-ExecutionPolicy RemoteSigned` first at windows powershel)</sup>

```
npm install -g aastbis
```


#### 2 - Launch AASTBIS inside your project folder

In your console, navigate to your project folder.
Then launch AASTBIS:

```
cd ./my-awesome-project
aastbis
```

AASTBIS should open in your default browser and start watching any changes you make inside the folder.

#### 3 - Share the URL with your audience

Simply share the URL that should appear and your audience will have access to your code through AASTBIS.
By default, you must be on the same network.

## Configuration

You can add configuration arguments when calling AASTBIS.

```
aastbis "My project" --debug 0 --port 1234 --exclude "node_modules/**" --open true --test true --limit 200 --max-file-size 99999
```

And you can use shortcuts for those same arguments.

```
aastbis "My project" -d 0 -p 1234 -e "node_modules/**" -oti -l 200 -m 99999
```

All those arguments are optional. You can simply run aastbis.

```
aastbis
```

Arguments list

||Debug level|
|---|---|
|parameter|`--debug`|
|shortcut|`--d`|
|default value|*(number)*`1`|
|description|How much logs should be shown<br>`0`: almost no log<br>`1`: primary logs<br>`2`: too much logs|

|||
|---|---|
|parameter|`--name`|
|shortcut|`-n`|
|default value|*(string)* folder name|
|description|Project name<br>(you can simply add a string after `aastbis` keyword like `aastbis "My project"`)|

|||
|---|---|
|parameter|`--exclude`|
|shortcut|`-e`|
|default value|*(string)*`**/.DS_Store,**/node_modules/**,**/vendor/**,**/.git,**/.vscode,**/.env,**/.log,.idea/**,**/*___jb_old___,**/*___jb_tmp___`|
|description|List of paths to exclude (glob pattern with comma seperation)|

|||
|---|---|
|parameter|`--open`|
|shortcut|`-o`|
|default value|*(bool)*`true`|
|description|Open AASTBIS in default browser|

|||
|---|---|
|parameter|`--test`|
|shortcut|`-t`|
|default value|*(bool)*`false`|
|description|Start a test project with demo contents<br>:warning: Only for development purpose|

|||
|---|---|
|parameter|`--limit`|
|shortcut|`-l`|
|default value|*(number)*`99`|
|description|Limit of files above which nothing will be sent at start<br>:warning: Too much files may cause issues|

|||
|---|---|
|parameter|`--max-file-size`|
|shortcut|`-m`|
|default value|*(number)*`99999`|
|description|Maximum file size in octets<br>(99999 ≈ 100ko)|

|||
|---|---|
|parameter|`--server`|
|shortcut|`-s`|
|default value|*(bool)*`false`|
|description|Start aastbis server only<br>(if you want to run an online instance)|

|||
|---|---|
|parameter|`--host`|
|shortcut|`-h`|
|default value|*(string)*``|
|description|Server host<br>(if you want to connect to an online instance)|

|||
|---|---|
|parameter|`--port`|
|shortcut|`-p`|
|default value|*(number)*`1571`|
|description|Server port|

## Online instance

You can run aastbis online. Anyone with access to the server will be able to see the projects without having to be on the same network as you.

aastbis doesn't provide any host solution. You'll have to use your own server.

#### On the server

Install Node.js

Install aastbis

```
npm install -g aastbis
```

Start a aastbis instance with the `--server` parameter

```
aastbis --server
```

#### On you local machine

Start AASTBIS with the `--host` parameter and server domain as the value

```
aastbis "My awesome project" --host 12.34.56.78
```

## Features

- Work in any modern browser
- File tree
- Fuzzy search
- File history/versions
- File versions differences
- Easy copy to clipboard
- Accessible by anyone on the same network
- App like design
- Syntax coloring
- Multiple projects in one AASTBIS instance
- Chat with other viewers and associate specific files and lines with your messages
- Open in default browser
- Download file button
- Download project button
- Alert button
- Tooltips
- Online support

## Developer instructions

#### Structure

`/app/`: aastbis front part
`/bin/`: Main folder only containing `index.js` that will run what's located in `/lib/` folder
`/lib/`: aastbis application classes
`/resources/`: Random resources (not directly use)
`/site/`: Website
`/text/`: Demo folder

#### Tasks

Installation

- `npm install`

AASTBIS application

- `npm run demo-folder`: To run the AASTBIS application with a demo project located in `/test/`
- `npm run app-dev`: To run the AASTBIS front part (you'll need to run AASTBIS application in order to have the front to connect to something)
- `npm run app-build`: To build the front part
- `npm run dev`: To run both `demo-folder` and `app-dev`

Website

- `npm run site-dev`: To run the website
- `npm run site-build`: To build the website
- `npm run site-deploy`: To deploy the website to GitHub Pages

#### Requirements

- Install EditorConfig on your editor
- Install ESLint on your editor

#### Deployment

- `npm run app-build` to build the app
- `npm version major|minor|patch` to update the version (will create a commit)
- `git commit --amend` to update the commit message and add `:bookmark:` at the beginning ([GitMoji](https://gitmoji.carloscuesta.me/))
- `git push` to push to GitHub
- `npm publish` to send to NPM (you need to be logged in and have the right to update AASTBIS on NPM)

## Credits

##### Development

- Youssef Ehab ([GitHub](https://github.com/Youssef1701), [LinkedIn](https://www.linkedin.com/in/youssef-ehab-92b9791a2/), [Site](https://www.youssefehab.com/))

##### Idea

Done by AAST-SV BIS students under supervision of Assoc. Prof. Dr. Ahmed Elseddawy
