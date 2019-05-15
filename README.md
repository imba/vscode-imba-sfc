## Imba tooling for VSCode
###

### Features
- Syntax Highlithing (with support for Single File Components)

### For more information

* [Imba.io](https://imba.io)
* [Spectrum](https://spectrum.chat/imba)
* [Gitter](https://gitter.im/imba/lobby)

**Enjoy!**

In Imba, the template and script sections are already merged into one
concept. Yet, styling is required to be placed in other files. In order to support the concept of SFC's in Imba, we only need to add in support for styles. This is done a little different than Vue. Since it's obvious that
we only need to support CSS, we can just directly specify the language on a line by itself, left justified. 

The Imba example looks like:

<img width="729" alt="Imba component" src="https://user-images.githubusercontent.com/142875/52330289-59dbb800-29b2-11e9-9fb0-a81e9591c9d1.png">

In order to regenerate these syntax files, use the following:

```bash
cd syntaxes
yarn global add yaml2json

# convert json to yaml
json2yaml imba.tmLanguage.json > imba.tmLanguage.yaml

# convert yaml to json
yaml2json imba.tmLanguage.yaml | jq --indent 2 . > imba.tmLanguage.json

# convert json to plist
plutil -convert xml1 imba.tmLanguage.json -o imba.tmLanguage
```
