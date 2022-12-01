# Contribution guide
We encourage you to make some changes to a topic to make it more understandable or fix grammar mistakes or translate it into other languages.

## Pull Requests
- **Sync** - Please make sure your repository is up to date with ours to avoid conflicts as much as possible.
- **Language** - Please make sure to check your contribution for grammar mistakes and typos as much as possible.
- **One pull request per feature** - If you want to do more than one thing, send multiple pull requests.
- **Send coherent history** - Make sure each individual commit in your pull request is meaningful. If you had to make multiple intermediate commits while developing, please [squash them](http://www.git-scm.com/book/en/v2/Git-Tools-Rewriting-History#Changing-Multiple-Commit-Messages) before submitting.

## Translation
- Create a new folder with the language code. [Available languages codes](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes).
- Copy all available files into your folder and then translate their content.
- Finally, add the language name and `README.md` path inside the main `README.md` file.

#### Example
```
│   README.md
│    ...    
│
└───  language-code eg:fr (French)
    │   README.md
    │   ...
```
