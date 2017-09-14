## Creating Animated GIFs

Animated GIFs, such as the one given below are easy to create.  Among the possibilities are using `gifsicle` from [Gifsicle](https://www.lcdf.org/gifsicle/) and `convert` from [ImageMagick](https://www.imagemagick.org/)

### Using `gifsicle`
From [Gifsicle](https://www.lcdf.org/gifsicle/man.html):

- put all the GIF images, appropriately named so that they fall in the correct order of appearance when listed/sorted alphabetically (sometimes tricky), in one folder/directory
- `cd` (change into) the directory containing the GIF images then issue the following command to create the animated GIF `all.gif`:
```bash
gifsicle --colors 256 -d 100 *.gif > all.gif
```

### Using `convert`
 From [ImageMagick](https://www.imagemagick.org/Usage/anim_basics/): 

- put all the PNG (or GIF) images, appropriately named so that they fall in the correct order of appearance when listed/sorted alphabetically (sometimes tricky), in one folder/directory
- `cd` (change into) the directory containing the PNG (or GIF) images then issue the following command (for PNGs) to create the animated GIF `all.gif`:
```bash
convert -delay 100 *.png all.gif  
```

Instead of using a wildcard (*.png) on the command-line, one may also use a list (a text file, e.g., listOfImages.txt) of images in which the filenames of the images to be combined are listed (in one column, one filename per row) in the proper order of appearance.  This is specially useful when it is not easy to syncronize the names of the files with the order of appearance:
```bash
convert @listOfImages.txt all.gif
```
One can get a list of images in a directory by using (at the command-line within the directory):
```bash
ls --color=never > listOfImages.txt
```
and editing this list so that the images are listed in the order of appearance in the animated GIF to be created using `convert`.  (In some installs of ImageMagick, one uses the `magick`, instead of `convert`, command-line tool.)

### Notes
- For `gifsicle`, the `-d 100` option causes a delay of 1 second (=100 \* 1/100th of a second) between frames, i.e., `d -250` causes a 2 1/2 s delay, `-d 325` causes a 3 1/4 s delay.  The `-delay 100` option of `convert` is similar.
- `mogrify` - from ImageMagick, can be used to convert PNGs to GIFs (and vice-versa):
```bash
mogrify -format gif *.png
```
- `animate` - from ImageMagick, allows a preview of the to-be-created animated GIF from the PNG images in a directory:
```bash
animate -loop 0 -delay 100 *.png
```  
(the `-loop 0` option means an infinite loop; use `Ctrl-C` or the x-button to exit from the preview GUI).
- `display` - from ImageMagick, gives a GUI that allows one to examine, study, edit, save changes made to an existing image, e.g., change the speed of animated GIFs.
- [Animator for Android](https://play.google.com/store/apps/details?id=com.mobilelabs.animator&hl=en) - an example of an Android app (availabe from Google Play Store) that creates animated GIFs.  An excerpt from the app's "READ MORE" page:  
> Animator is a tool for making animated cartoon videos and exporting them to Gif or Video formats. 
> Make funny videos - no advanced drawing skills required! Just doodle, have fun and amaze your friends. 
> You can create amazing animations without any expertise! Animation is made easy, better than any 
> other animation software. 

There are a  number of other alternative Android apps from the Google Play Store (search under <tt>animator</tt>).

## Example
The screenshot (partly edited) of a [`t3C` tic-tac-toe game](https://github.com/justineuro/tic-tac-toe) session given below was created using `gifsicle` and the images in the [images-gif](./images-gif) folder, i.e., issue the command
```bash
gifsicle --colors 256 -d 300 *.gif > t3C-all.gif
```
under (the copy in your computer) of the `images-gif` subdirectory given above.      
![tic-tac-toe: The Game!](./t3C-all.gif)

## License
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/80x15.png" /></a><br /><span xmlns:dct="http://purl.org/dc/terms/" property="dct:title"><b>animatedGIFs</b></span> by <a xmlns:cc="http://creativecommons.org/ns#" href="https://github.com/justineuro/" property="cc:attributionName" rel="cc:attributionURL">Justine Leon A. Uro</a> is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.<br />Based on a work at <a xmlns:dct="http://purl.org/dc/terms/" href="https://github.com/justineuro/mdginabc2svg" rel="dct:source">https://github.com/justineuro/animatedGIFs</a>