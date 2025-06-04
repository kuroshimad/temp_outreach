Using the Symmetry Code
=======================


The Google Colab notebook allows you to generate symmetric wallpapers of your desired image using tiling and transformation.

Currently supported wallpaper groups:
- P1
- P2
- P4
- Pm
- Pg
- P2mm
- P2mg
- P2gg
- Cm
- P3m 

Notebook link:
`wallpaper_symmetry_generator.ipynb <https://colab.research.google.com/github/rogalj/dmref-outreach/blob/main/mlforkids/patterns/simpler_figs/wallpaper_symmetry_generator.ipynb>`_

Notebook Overview
-----------------

The notebook is structured into several cells. Here's what each one does:

Cell 1: Load Modules
~~~~~~~~~~~~~~~~~~~~
Imports all necessary Python libraries, including:
- `google.colab` for uploading images directly from the user’s computer
- `PIL` (Python Imaging Library) — for opening and processing image files
- `matplotlib` for displaying images and plots
- `numpy` for handling numerical arrays and computations
- `scipy.ndimage` for zooming and other image computations
- `random` for generating random numbers
- `.transforms.Bbox` — for defining bounding boxes in image plots
- `os` for saving output files

.. code-block:: python

   from google.colab import files
   from PIL import Image
   import matplotlib.pyplot as plt
   import numpy as np
   from scipy.ndimage import zoom
   import random
   from matplotlib.transforms import Bbox
   import os


Cell 2: Upload User Image
~~~~~~~~~~~~~~~~~~~~~~~~~

Allows the user to upload an image from their local machine. The image should be in square and have a transparent background.

.. code-block:: python

   uploaded = files.upload()

   for fn in uploaded.keys():
       img_path = fn
       img = Image.open(img_path)
   print("This is the uploaded image.")
   img

Cell 3: Define wallpaper group
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Defines the functions needed to generate specific wallpaper symmetry groups.


.. code-block:: python

   #Mirror functions
   def create_mirror_left_right(img):
   def create_mirror_top_bottom(img):

   #Tiling functions for wallpaper groups.
   def tile_image_p1(img_path, rows, cols):
   def tile_image_p2(img_path, rows, cols):
   def tile_image_pm(img_path, rows, cols):
   def tile_image_pg(img_path, rows, cols):
   def tile_image_p2mm(img_path, rows, cols):
   def tile_image_p2mg(img_path, rows, cols):
   def tile_image_p2gg(img_path, rows, cols):
   def tile_image_p4(img_path, rows, cols):
   def tile_image_p3m(img_path, rows, cols):

Cell 4: Test functions
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Test and visualize the tiled output generated from the functions defined above.



Cell 5: Define wallpaper group
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Provides helper functions for image zooming, color transformation, and rotation.

.. code-block:: python
   
   #This function zooms in the image.
   def zoom_image(img, zoom_factor, final_size, color,color_rand, color_lst,ROT,ROT_rand,rot):
   #This function change the color of the image to random color.
   def color_change(img):
   #This function change the image to the user defined color.
   def set_color(img,color_lst):
   #This function rotates the image. 
   def rotate_img(img_array,ROT_rand,rot):


Cell 6: Define parameter 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Customize the generation with the following parameters:

- **sym_lst**: List of desired symmetry types. Please choose from ["p1", "p2", "p4", "pm", "pg", "p2mm", "p2mg", "p2gg"]
- **Zoom**: `True` to random zoom, `False` to keep the original size. 
- **zoom_ratio**: Ratio of zooming. When ratio is 1, there will be no zoom.
- **COLOR**: `True` to apply color changes, `False` to keep the original color. 
- **COLOR_rand**: `True` for random color, `False` to use specific color. 
- **color_lst**: RGB color list. Default color is purple.
- **ROT**: `True` to apply rotation, `False` to skip. 
- **ROT_rand**: `True` for random angle, `False` for a fixed rotation. 
- **rot_lst**: Rotation angle in degree. 
- **out_dir**: Output directory name Default is "train"
- **user_name_lst**: Base name for output images. 
- **N_img**: Number of images to generate.. 
- **random.seed**: Set seed for reproducibility. 
- **rep**: Number of image replication. 
- **final_size**: Output image dimensions in pixels. 


Cell 7: Download in zip file
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Compresses the output images and downloads them as a zip archive.

.. code-block:: python

   files.download(output_zip)

