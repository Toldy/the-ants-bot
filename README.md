> - Didn't commit the code to not harm the gameplay of others.
> - Feel free to reach me [here](https://www.linkedin.com/in/colinjulien/) if you are interested 
> - **Curiosity-driven** work (Atm the goal isn't to build a real solid software)

#### What is The Ants - Bot?

A program who will play for you when you cannot play at [The Ants: Underground Kingdom](https://play.google.com/store/apps/details?id=com.star.union.planetant)

<img src="https://user-images.githubusercontent.com/3730187/150842114-b77003ab-70fd-4da0-9dc3-155166860532.png" alt="The Ants logo" width="400"/>

#### What can it do?

- ✅ Farm resources by attacking world monsters
- ☑️ Resource gathering
- ☑️ Provide Allance Help
- ☑️ Claim Alliance Gifts
- ☑️ Upgrade buildings of your AntHill

#### How it works?

// TODO: Provide a diagram

#### Stack

- MacOS Monterey
- [Dart](https://dart.dev): All the codebase
- [BlueStacks](https://www.bluestacks.com/fr/index.html): Android device emulation on my Mac
- [CliClick](https://github.com/BlueM/cliclick): Simulate user taps
- [MacOS Screencapture CLI](https://ss64.com/osx/screencapture.html): Screenshot emulator
- [Tesseract](https://github.com/tesseract-ocr/tessdoc): Text recognition (OCR) on Screencaptures (from emulator)
- [ImageMagick](https://github.com/ImageMagick/ImageMagick): Image cropping + Image preprocessing for Tesseract

#### Problems encountered

###### ☑️ BlueStacks sometimes makes my Mac BlackScreen during its startup
###### ✅ Ocr doesn't work well when scanning a March Unit
→ 💡 Make multiple crops + OCR
<details>
  <summary>details here</summary>
When scanning this: <img src="https://user-images.githubusercontent.com/3730187/150847610-4530d14f-fb5f-48d4-a058-bba338d1f564.jpg"/>

Tesseract can return:
- `460 Dye 220/1,540 @ 84/100 &, 4.0K`
- `460 Dye 220/1,540 @ PAPAL!) &, 4.0K`
- `even worse cases...`  
</details>

## Bot modes

#### 1. AutoFarming
###### Goal
Farm resources by attacking monsters as much a possible. 
###### Advantages
- You wake up with a lot resources :)
- Provides XP for your special Ants
###### Features
- ✅ Computes which resource you need the most before attacking a monter
- ✅ Use all March Units available (only the first two are used at the moment)
- ☑️ Automatically refills your March Units with available soldier ants
###### Prerequisites
You build your March Units before launching the bot 
