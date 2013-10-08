About
=====

 This is a ruby script to generate png image from text (pango markups.)

How to Use
==========

* Install `ruby`, `ruby-pango` from the repository.

```bash
$ sudo apt-get install ruby ruby-pango
```

* Create a text file containing corresponding text/[pango markup](https://developer.gnome.org/pango/stable/PangoMarkupFormat.html) for each image to generate. See `examples` directory for example files.

```bash
$ cat noacct.txt
<span face="Ubuntu 12">No Account yet? Register <span foreground="blue"><u>here</u></span>!</span>
```

* Generate images

```bash
$ ./text2png.rb examples/*.txt
```

* Auto-crop and optimize images. (Must have `imagemagick` installed)

```bash
$ for image in *.png; do convert "$image" -trim -strip -quality 86 "$image";done
```
