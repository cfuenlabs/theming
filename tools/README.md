# Tools🗜️

Where any apps or scripts that aid in CFuen Labs theming reside.

# ct2vsix <img alt="Python logo" src="https://logos-download.com/wp-content/uploads/2016/10/Python_logo_icon.png" width="22">

A simple tool to quickly package VSCode color theme .json files into .vsix packages instead of having to create a project and package it with yeoman.

### Usage

Just execute the script with the Python interpreter:

```bash
py tools/ct2vsix.py your_colors.json
```

A little temp folder will be created, that's where the package will be created. During the packaging process, you will be prompted for input twice. Both times you have to agree by typing 'y' and hit enter.

```bash
WARNING  A 'repository' field is missing from the 'package.json' manifest file.
Do you want to continue? [y/N] y

WARNING  LICENSE.md, LICENSE.txt or LICENSE not found
Do you want to continue? [y/N] y
```

And that's it! You will find `your_colors-0.1.0.vsix` chilling where you ran the script and the temp folder will be gone. Now you can [manually install the extension](https://stackoverflow.com/a/50232194), without having to [distribute in the VSCode Marketplace](https://youtu.be/pGzssFNtWXw?si=OWwgse3HzHcO5Z8d&t=596), which is an unnecesary and convoluted process if all you want to do is rice VSCode.

### Dependencies

Since this depends on the [VSCode Extension Manager](https://github.com/microsoft/vscode-vsce) (a.k.a `vsce`) for packaging, you must install `vsce` beforehand with your favorite node package manager.

```bash
npm install -g vsce
# or
yarn global add vsce
# or
pnpm install -g vsce
```