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


