> - Didn't commit the code to not harm the gameplay of others.
> - Feel free to reach me [here](https://www.linkedin.com/in/colinjulien/) if you are interested 
> - **Curiosity-driven** work (Atm the goal isn't to build a real solid software)

<img src="https://user-images.githubusercontent.com/3730187/150880054-625b4c7b-5734-4ec3-8f2c-26ef1037ce9a.png" alt="YouTube logo" height="14"/>Demo on [Youtube](https://www.youtube.com/watch?v=Zyk_SdwdpuU) 👀 

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

![Diagram](https://user-images.githubusercontent.com/3730187/150878031-6492dfcb-7e4d-4bed-b913-3d4a243f5969.png)

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

###### ✅ OCR's Result isn't accurate (Multiple data on the same line)
→ 💡 Split this date in multiple cropped images + OCR them 1 by 1
<details>
  <summary>details here</summary>
When scanning this: <img src="https://user-images.githubusercontent.com/3730187/150847610-4530d14f-fb5f-48d4-a058-bba338d1f564.jpg"/>

Tesseract can return:
- `460 Dye 220/1,540 @ 84/100 &, 4.0K`
- `460 Dye 220/1,540 @ PAPAL!) &, 4.0K`
- `even worse cases...`  

It is better like this:
![marchunit_screenshot_0_name](https://user-images.githubusercontent.com/3730187/150859366-79bdf1c2-c75c-49fc-bab8-2901e5ed5e27.png)

![marchunit_screenshot_0_power](https://user-images.githubusercontent.com/3730187/150859369-bd19366f-785d-4c3b-af14-fc47090c43ee.png)

![marchunit_screenshot_0_stamina](https://user-images.githubusercontent.com/3730187/150859371-0a447f78-f78b-4ad8-bf22-1fcaf52d0afa.png)
</details>

###### ✅ OCR's Result isn't accurate (Application graphics aren't always aligned the same way)
→ 💡 Find better values for thoses crop zones
<details>
  <summary>details here</summary>
See those 2 cases with different stamina:

![image](https://user-images.githubusercontent.com/3730187/150863164-87dcfde7-f0a4-4f78-97c1-9cb6e177099e.png)

OCR Result: `100/100`

![image](https://user-images.githubusercontent.com/3730187/150863232-039bc04f-33e2-4c3b-a8d3-2d62eca2aa50.png)

OCR Result: `PAPAL!)` 🤯

I hardcoded the crop zone value when stamina was 100/100. When Stamina drops to 93/100, crop zone is bad (because it contains part of the insect image). 
OCR
This produces noise and a bad OCR result like
</details>

###### ☑️ OCR not consistent
→ 💡 
<details>
  <summary>details here</summary>
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
