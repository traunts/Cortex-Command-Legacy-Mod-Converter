# Cortex Command Legacy Mod Converter

## Introduction
This project automates ***most*** of the conversion work required to convert the legacy `Cortex Command` mods into `Cortex Command Community Project` compatible mods.

![project-icon](cclmc-icon.png)

## How does it work
Put the mods you want to convert in the `input` folder and run `convert.py`. After `convert.py` is done, the converted mods are found in the `output` folder and can then be tested in `CCCP`.

## Disclaimer
This program will do most of the conversion work for you, but some conversion steps are too hard to automate, so it's likely that `CCCP` will still crash and/or output errors into the console. If this happens, you'll have to manually make some final adjustments to the converted mods found in the `output` folder.

> "There are going to be cases that require user intervention. Priority, for example, is one of them. Few things should be setting sound priority, and the scale has completely changed such that 0 is highest and 128 (I think) is lowest. The correct way to deal with this is, either at the time of or at the end, show the user these cases and either tell them to deal with it manually, or give them a few options." -Gacyr

## How to use it
* Download Python3, and change directory to the `cc-legacy-mod-converter` folder
* Run `python convert.py` if you want to convert old mods
* `conversion_rules.py` has the `conversion_rules` dictionary inside of it. The dictionary contains entries that look like `'foo': 'bar',` which means means that any time `foo` will be encountered by `convert.py`, it will replace it with `bar`. You can add extra cases to it, see the next sections on how to do this.

## Contributing
Feel free to submit `Pull Requests` or `Issues` on this GitHub project for any additional cases that you'd like to have supported.

**You don’t need all of these programs to get started, feel free to use whatever alternative programs you prefer:**
* [Download “Everything”](https://voidtools.com/) - It’s like File Explorer on Windows, but way faster + more advanced.
* [Download “SourceTree”](https://www.sourcetreeapp.com/) - It’s like GitHub Desktop, but way more advanced.
* [Download “NotePad++”](https://notepad-plus-plus.org/downloads/) - It’s like Notepad, but way more advanced (hence ++). You can also use an IDE like [VS Code](https://code.visualstudio.com/) instead.

## How to fix an error with the program Everything

| ![Alt Text](https://i.imgur.com/WXZ09s2.png) |
| :---: |
| Let's say you've converted your old mod, but Cortex Command still crashes with the converted mod. |

| ![Alt Text](https://i.imgur.com/vliMjVg.png) |
| :---: |
| The first thing you should do is open up the program *Everything*, which is used to search for any file on your computer, while also being much faster than Windows's standard File Explorer program. |

| ![Alt Text](https://i.imgur.com/bLXi1qv.png) |
| :---: |
| You can now click the `Search` button at the top of the program, then `Advanced Search...`, and then you can type what you want to search in the `all these words:` field. If the your search result should contain multiple keywords, you can just place a space character between those keywords. |

| ![Alt Text](https://i.imgur.com/spZ8Wp8.png) |
| :---: |
| As you can see, there are way too many results for this search, so we'll have to narrow down the search. |

| ![Alt Text](https://i.imgur.com/mjQTNKS.png) |
| :---: |
| By adding the `Ronin.rte\` keyword (the `\` is really important to indicate it's a folder!) there's only a single search result left, which is our new path we were looking for. You can verify if this path leads to the same image as the original, Steam version of Cortex Command did if you want to make extra sure this is correct. |

| ![Alt Text](https://i.imgur.com/dpuTSvO.png) |
| :---: |
| Open `conversion_rules.py` with any text editor of your choice, and add `'': ''`, somewhere in the `conversion_rules` dictionary. In the left set of `''` you want to add the old path which couldn't be found, which should have been mentioned in your error. In the right set of `''` you want to add the new path you've obtained with *Everything*. |

Now run `convert.py` again, and it should automatically fix the error for you by replacing any mention of `Ronin.rte/Effects/Gibs/GibA.bmp` with `Ronin.rte/Devices/Shared/Gibs/WeaponGibA.bmp`. The main advantages of creating a case in the dictionary - instead of manually replacing any mention of `Ronin.rte/Effects/Gibs/GibA.bmp` - are:
1. Being able to create a Pull Request on GitHub of that new case you added, which can then be used by the rest of the converters. If everyone were to make a Pull Request for every single case they found, the converter would become way more effective.
2. If there are multiple locations where `Ronin.rte/Effects/Gibs/GibA.bmp` is mentioned, you don't have to search for every single mention of it in every single file. Manually mass replacing stuff can be messed up.

### Getting help
If you need help with anything, you can contact the creator of this repository directly (`#MyNameIsTrez1585` on Discord), or you can ask the kind people in the CCCP Discord server in `#modding-discussion` for help. It helps us if you mention where you've gotten stuck while reading this README file.