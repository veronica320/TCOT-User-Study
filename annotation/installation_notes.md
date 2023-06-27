On my Mac, I met the following errors during installation. Here are their corresponding fixes:


1. `pipenv install` incurs the error of "mysql not found". I fixed it by manually installing mysql:

```
brew install mysql
# add the path to your PATH environmental variable
open -e ~/.zshrc
export PATH=$PATH:/path/to/your/mysql/bin
# apply the changes
source ~/.zshrc
```
On my mac, I did:
```
export PATH=$PATH:/usr/local/opt/mysql/bin
```

2. If you want to use VScode as the IDE, you'll need to install the `Better Jinja` extension, add also add the following to your `.vscode/settings.json':
```
    "files.associations": {
        "*.html": "jinja-html"
    }
```
so that it understands the mixed Javascript and Jinja syntax used in some of the html files.

