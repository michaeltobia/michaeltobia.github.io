---
layout: project
title: Computer Vision - Image Stitch
date: December 15, 2018
image: https://michaeltobia.github.io/public/images/image_stitch_project.png
permalink: "/image-stitch.html"
---

## Image Stitching

This is a project completed for my Introduction to Computer Vision course at Northwestern.
The goal was to combine two photos of roughly the same view and combine them into a
single, larger image.

Applications of image stitching are numerous. For instance, one could create a
thermal map of an area by stitching together frames of a video feed from a drone
flown overhead. Another great example of image stitching technology in use can be seen
at [Gigapan.com](gigapan.com), a website focused on massive 'gigapixel' resolution
images. Image stitching's most commonly seen use today is in most smart phones'
panorama image features.

The actual image stitching pipeline comes in three steps:
1. Features are detected and matched between the images to be stitched

2. The camera movement between the two images, or the images' projection, is calculated,
and one of the two images is warped, or transformed, using this calculated projections

3. After the images are warped to match, the matching features found earlier are used
to super impose one image on the other, creating the stitched image. Feathering can
be applied to smooth the seam created by super imposing the images, but this was
not done in this project.

If you're interested in reading more about this project, you can find my presentation
on it [here](https://michaeltobia.github.io/public/documents/ImageStitching_EECS332_Presentation_MichaelTobia.pdf)
