> [!WARNING]
> This installer is not working because the [Download page](https://download.sdkbox.com/) is down

# Intro
SDKBOX doc site uses [mkdocs](http://www.mkdocs.org) to generate static pages from markdown files

## Install
To view the site locally, you have to install mkdocs first
```
sudo pip install mkdocs==0.14.0
```

Or use pipenv
```
sudo -H pip install pipenv
pipenv install mkdocs==0.14.0
pipenv run ./publish.sh #test
```

## Documents generator
* We use generator to generate cocos plugins' documents, so don't edit files in `docs/plugins/` manually.
Instead, use the following command to generate documents
* If you want to edit cocos plugins, you should edit the templates at `src/<plugin name>`
```
cd src
./doc.py all
```

Some documentations require [jsdoc](https://www.npmjs.com/package/jsdoc)

Make sure you install [nodejs](https://nodejs.org/en/) and jsdoc with
```
npm install jsdoc -g
```

Also you need to set `CSC_PATH` that points to SDKBOX repository

## Build

You can start a local server by
```
mkdocs serve
```
Open http://127.0.0.1:8000/ in browser

Or, build a static `site` folder and serve it with a web server
```
mkdocs build
cd site
python -m SimpleHTTPServer
```

## Editor
We recommend using [marked2](http://marked2app.com) while editing markdown document, because it supports the way we embed documents.

However use local server is equally efficient.

>   After editing the docs, you can test them with running `publish.sh test`. This command will build and run a server in your local enviornment.


## Publish
Use the following command to publish document to live

```
brew install jsdoc3
export CSC_PATH=/path/to/sdkbox_core/
```

```
mkdocs gh-deploy --clean
```

>   Executing `publish.sh` is a convenient way to publish the docs.

## Contributors
@slackmoehrle

@darkdukey

@yinjimmy

@hugohuang1111

@kaizhao

@pabitrapadhy

@bluetriggerfish

@cheerayhuang

@pineoc
