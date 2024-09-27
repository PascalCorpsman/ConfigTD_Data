# General game informations

This file holds a unordered list of informations about the game that could be helpfull if you want to contribute.
Use the following jump table to easy navigate:

| Category | Topic |
| --- | --- |
| graphics | [Which graphic dimensions shall i choose ?](#which-graphic-dimensions-shall-i-choose)
| graphics | [Which image format shall i choose ?](#which-image-format-shall-i-choose)
| graphics | [How to make transparent effects ?](#how-to-make-transparent-effects)
| map design | [Which strength shall i give buildings / opponents / heros ?](#which-strength-shall-i-give-buildings--opponents--heros)

If you have more general questions (especially in creating things or the general gameplay) maybe the user [manual](https://github.com/PascalCorpsman/ConfigTD/blob/main/documentation/Readme.md) can help.

### Which graphic dimensions shall i choose ?
The game engine works on a discrete grid, with no zoom a grid coordinate is 10x10 pixels big. If you design buildings its is highly recommended to use multiples of 10x10 pixels for all graphics. But they do not need to be in a quadratic shape or completly filled (see [How to make transparent effects ?](#how-to-make-transparent-effects)).

### Which image format shall i choose ?
The game engine supports:
- Windows bitmaps (.bmp)
- JPEG Files (.jpg)
- Portable Network Graphics (.png)
- Anifiles (.ani)

In General it should not make a difference wether you choose one or another file format, but in detail it could be difficult, so here is a recommended way:

| File format | when to use 
| --- | --- 
| .bmp | Windows Bitmaps are good if you are developing new images by hand, but as they have the biggest filesize and do not support smooth transparency, it is highly recommended to not use them at all (or only for very small images)
| .jpg | JPEG images are highly compressed images, which makes them perfect for background (big) images, do not use them, when you want transparent effects, as due to the compression the transparency color gets disturbed
| .png | This is the most recomended file format for units, buildings, opponents, weapons
| .ani | The game is shipped with the animation editor, which has its own documentation [here](https://github.com/PascalCorpsman/Examples/tree/master/OpenGL/Animation_Editor). Recommended file format for the animation editor is .png or .bmp

### How to make transparent effects ?
The game engine supports two different kinds of transparency.

#### "Binary transparency"
The game engine interprets the color fuchsia (R=255, G=0, B=255) as transparent. If you use this color in a image it will not be rendered.

#### "Floating transparency"
If you want to use transparancy values between opak and seethrough you have to use the .png file format. If you do not have a program to edit the alpha channel directly you can download and use the [PNG Editor](https://github.com/PascalCorpsman/mini_projects/tree/main/miniprojects/PNG_Editor) which is able to split the alpha channel into a separate .bmp file and merge back.

### Which strength shall i give buildings / opponents / heros ?
Balancing is a quite hard task and even modern games struggle a lot with it, so there can be only general informations given.
- do not mix the package's (as they not necessarily need to be compatible in kind of balancing)
- use exponential increasing values (see [balancing.ods](../balancing.ods) for that)
- use the "restart last wave" function during developing new maps
- when developing new maps always use "hard" or "normal" settings, never "easy"