# imagemagick

## URLS
* [Annotated List of Command-line Options](https://imagemagick.org/script/command-line-options.php)
* [imagemagick @ stackoverflow](https://stackoverflow.com/questions/tagged/imagemagick?tab=Votes)
* [reddit](https://www.reddit.com/r/imagemagick/)
* [dev.to](https://dev.to/search?q=imagemagick)
* [Examples of ImageMagick Usage](https://imagemagick.org/Usage/)
* [Fred Advanced Scripts](http://www.fmwconcepts.com/imagemagick/sharpedge/index.php)
* [info @ masayume](https://www.masayume.it/blog/content/imagemagick)
* [graphicdesign.stackexchange post list](https://graphicdesign.stackexchange.com/search?q=imagemagick)
* [Efficient Image Resizing With ImageMagick](https://www.smashingmagazine.com/2015/06/efficient-image-resizing-with-imagemagick/)
* [Make PNG font samples with ImageMagick](https://dev.to/danburzo/how-to-make-png-font-samples-with-imagemagick-part-1-29p8)

## Scripts Directory
```
masayume/Downloads/masayumeP/_SCRIPTS/MAGICK_scripts/
```

## Info (color, size etc.)
```
identify -verbose <FILE>
```

## convert, montage etc.

### Split (horiz%, vert%)
```
convert -crop 50%x100% input.png output.png
```

### Crop Image Serie from Center
```
for i in *.jpg; do
  convert ${i} -gravity center -crop 500x500+0+0 +repage _${i};
  rm ${i};
done
```

### Inline Image Crop
```
magick '\*.jpg' -crop widthxheight+x+y thumbnail%03d.jpg
```

### Rotate (60° clockwise)
```
convert flower_original.jpeg -rotate 60 rotate_clockwise_flower.jpeg
```

### generate PDF file from images
```
convert *.jpg -auto-orient pictures.pdf
```

### stitch images together horizontally
```
montage [0-4].png -tile 5x1 -geometry +0+0 out.png
```

### from frames to animated GIF
```
convert -delay 20 -loop 0 *.webp -scale 640x427 verge.gif
```

### sketch
- [edge detection with imagemagick](https://blog.jiayu.co/2019/05/edge-detection-with-imagemagick/)

### gradients
```
# simple linear gradient, two colours
convert -size 600x400 gradient:blue-red linear_gradient.png
# simple radiant gradient, two colours
convert -size 600x400 radial-gradient:blue-red radial_gradient.png
# a more complex, multi-colour gradient with bicubic interpolation
convert \( -size 600x400 gradient: -interpolate Bicubic -rotate 180 \
  \( +size xc:firebrick4 xc:crimson xc:MediumPurple xc:DarkSlateBlue -append \) \
  -clut \) \
  gradient.png
```


