.. _ml4kids_and_scratch:

ML for Kids × Scratch — Symmetry Project
========================================

Welcome to the Symmetry Explorer! This project helps you learn about symmetry in a fun way using machine learning and colorful patterns.

This project combines `Machine Learning for Kids <https://machinelearningforkids.co.uk>`_ and `Scratch <https://scratch.mit.edu/>`_ to perform pattern classification. There are three parts to this:

1. **Understand the Symmetry Group**
2. **Train your ML model using ML for Kids**
3. **Try it out using *Scratch*!**

.. note::

   **What You'll Do**
   - Train a machine learning model to recognize symmetry patterns
   - Test it in Scratch using colorful images
   - Compare how different training data affects what the computer learns


Understanding Symmetry Groups
-----------------------------

Before using machine learning, let’s learn what symmetry groups are!

A symmetry group describes how patterns repeat or remain invariant under:

- flips (like looking in a mirror)
- rotations (like turning a steering wheel)
- translations (like tiling a floor)
- or combinations (like flipping and then rotating)

There are 17 wallpaper symmetry groups in total. This project uses two examples:

.. figure:: _static/P1_example_blue.png
   :width: 200px
   :align: center
   :alt: P1 symmetry example

.. figure:: _static/P2_example_blue.png
   :width: 200px
   :align: center
   :alt: P2 symmetry example

**P1 Symmetry Group** — No symmetry

This pattern doesn't repeat in a special way. It is just a simple copy of the same pattern.

**P2 Symmetry Group** — 180° Rotation Symmetry

This pattern looks upside down in alternating rows due to 180° rotational symmetry.

Why does this matter?
^^^^^^^^^^^^^^^^^^^^^

These symmetry groups help us understand pattern repetition — and our goal is to train a computer to tell them apart. This may be easy for us, but not for a machine!


Training a Machine Learning Model
---------------------------------

To train a model, we use the `Machine Learning for Kids <https://machinelearningforkids.co.uk>`_ platform.

1. **Log in or Sign up**
   - Visit the `login page <https://machinelearningforkids.co.uk/#!/login>`_.
   - Log in, sign up, or try it without signing up.

2. **Create a New Project**
   - Go to **Projects** in the top menu.
   - Click **add a new project**
   - Name your project
   - Choose **recognizing images** as the project type
   - Select **In your web browser** as storage
   - Click **CREATE**

.. figure:: _static/ml4kids_new_project.png
   :width: 1000px
   :align: center

After clicking **CREATE**, you should see this screen:

.. figure:: _static/ml4kids_project_home.png
   :width: 1000px
   :align: center

3. **Train the Model**
   - Click **Train** (①)
   - Click **Add new label** (top right) to create classes
   - Add `P1` and `P2` as your labels

.. figure:: _static/ml4kids_train_w_arrow.png
   :width: 1000px
   :align: center

Use images from:
- P1: https://www.crystalmathatnyu.org/p1_general
- P2: https://www.crystalmathatnyu.org/p2_general

Drag-and-drop selected images into their corresponding classes:

.. figure:: _static/Before_drag_w_cursor.png
   :width: 400px
   :align: center

.. figure:: _static/After_drag_w_cursor.png
   :width: 400px
   :align: center

4. **Train and Test the Model**
   - Go back to the previous page
   - Click **Learn & Test** (②)
   - Wait for training to complete (status = **Available**)
   - If an **unknown error** occurs, close the tab and retry. Clearing the browser cache may help.

5. **Use the Model in Scratch**
   - Return to the project page
   - Click **Make** (③)
   - Click **Open in Scratch 3** to launch Scratch with your ML model linked

.. figure:: _static/scratch_init.png
   :width: 1000px
   :align: center


Writing a Scratch Program
--------------------------

Download the Scratch example project here:
`Example Scratch Project (sb3) <https://github.com/rogalj/dmref-outreach/blob/main/mlforkids/patterns/simpler_figs/dataset/paw_dataset/DK_gen_template_with_paw_all.sb3>`_

(Right-click → “Save link as…” if it doesn’t auto-download.)

1. **Load the Template Project**
   - In Scratch, go to **File → Load from your computer**

2. **Modify the Code**
   - Add ML elements from the **Extensions** section
   - Insert ``recognise image costume image (confidence)`` into the ``set conf to`` block
   - Insert ``recognise image costume image = P1`` or ``= P2`` in the ``if`` condition

.. figure:: _static/scrtach_with_template.png
   :width: 1000px
   :align: center



Other Datasets
--------------

The ``dataset`` folder contains image classification examples. Summary:

.. list-table:: Dataset Summary
   :widths: 10 10 20 10 40
   :header-rows: 1

   * - Image
     - Symmetry Group
     - Training Set
     - # of Images Used
     - Observation
   * - .. image:: _static/deer.png
          :width: 50px
     - P1 & P2
     - Control: colored and B&W  
       Biased: only B&W
     - 30
     - Control classifies color images; biased does not.
   * - .. image:: _static/bear_paw.png
          :width: 50px
     - P1 & P2
     - Control: colored and B&W  
       Biased: only B&W
     - 20
     - Control classifies color images; biased does not.
   * - .. image:: _static/banana.png
          :width: 50px
     - P1 & P2
     - Control: regular & 90° rotated  
       Biased: only regular
     - 30
     - Control classifies rotated images; biased does not.
   * - .. image:: _static/horse.png
          :width: 50px
     - P1 & P2
     - Control: regular & zoomed  
       Biased: only regular
     - 60
     - Control classifies zoomed images; biased does not.
   * - .. image:: _static/shark.png
          :width: 50px
     - P1 & P2
     - Control: regular & zoomed  
       Biased: only regular
     - 30
     - Control classifies zoomed images; biased does not.
   * - .. image:: _static/triangle.png
          :width: 50px
     - P1 & P2
     - Control: regular, rotated, and zoomed  
       Biased: only regular
     - 90
     - Control classifies zoomed/rotated images; biased does not classify rotated images.


Try it out and see what your computer learns!




