# 2021-12-14 [@frederikstroem](https://github.com/frederikstroem) Modifications
Drew new images for a deep learning course on SDU.

**Drawing app:** [GIMP](https://www.gimp.org/)

**Graphics tablet:** [Wacom INTUOS Pen Small](https://101.wacom.com/UserHelp/en/TOC/CTL-480.html)

**OS:** Arch Linux

## GIMP settings
I drew white on black using the Paintbrush Tool settings:

![image](https://user-images.githubusercontent.com/17912119/145985789-885bf4df-c6c7-4de0-a5bc-c9c8750cdfb3.png)

# JPG-and-PNG-to-MNIST

Super simple method for converting a set of jpg and/or png images (or a mix) into mnist binary format for training (depends on imagemagick and python 2.7 PIL)

# Dependencies:

Use the following lines to install imagemagick and the python-imaging-library (PIL):

```bash
sudo apt-get update
sudo apt-get install imagemagick php5-imagick
pip install pillow
```

# Transform your images into an MNIST NN Ready Binary:


1\. Copy-pasta your jpg and/or png images into one of the class folders, as seen in  (e.g. dogs -> 0, cats -> 1, ... giraffes->9)

2\. Change the appropriate labels in `batches.meta.txt`

3\. then use the following bash script which processes the images, rescaling all of the png's you placed in the folders the MNIST standard 28x28pixel size

`./resize-script.sh`

4\. lastly, run the following python script to fold all the pics and categories into a single ble binary -- binary will appear as `ubyte` files ready to tar

`python convert-images-to-mnist-format.py`


# Victory!

You now have the files, and can replace the the conventional data in any standard mnist tutorial with your own data :D

Enjoy!

# Tree

example of where files will appear/where-to put png's (ignore placeholder.txt, this is only there so that git could check in their parent folders -- since empty folders can't be committed):
```

.
├── batches.meta.txt
├── convert-images-to-mnist-format.py
├── LICENSE
├── README.md
├── resize-script.sh
├── test-images
│   ├── 0
│   │   ├── home-cat.png
│   │   └── placeholder.txt
│   ├── 1
│   │   ├── dog-07.png
│   │   └── placeholder.txt
│   ├── 2
│   │   └── placeholder.txt
│   ├── 3
│   │   └── placeholder.txt
│   ├── 4
│   │   └── placeholder.txt
│   ├── 5
│   │   └── placeholder.txt
│   ├── 6
│   │   └── placeholder.txt
│   ├── 7
│   │   └── placeholder.txt
│   ├── 8
│   │   └── placeholder.txt
│   └── 9
│       └── placeholder.txt
└── training-images
    ├── 0
    │   ├── home-cat.png
    │   └── placeholder.txt
    ├── 1
    │   ├── dog-07.png
    │   └── placeholder.txt
    ├── 2
    │   └── placeholder.txt
    ├── 3
    │   └── placeholder.txt
    ├── 4
    │   └── placeholder.txt
    ├── 5
    │   └── placeholder.txt
    ├── 6
    │   └── placeholder.txt
    ├── 7
    │   └── placeholder.txt
    ├── 8
    │   └── placeholder.txt
    └── 9
        └── placeholder.txt
```
