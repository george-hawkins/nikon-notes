PiFuHD
======

This directory contains the resources used in creating a 3D model of me (that you can see [here](https://skfb.ly/o6RyT) on Sketchfab) and generated by following Jonathan Kron's [tutorial](https://www.youtube.com/watch?v=8AQsoA_B1_I) on YouTube that covers creating human models with PiFuHD and then texturing the model from the original photos with Blender.

`result_front_256.obj` is the `.obj` created by working thru the Colab [notebook](https://colab.research.google.com/drive/11z58bl3meSzo6kFqkahMa35G5jmh2Wgt). Note you need to make a copy (that ends up in your own Google Drive). They note that you may have to install `git+https://github.com/facebookresearch/pytorch3d.git@stable'` (via the notebook) if you experience errors - this was the case for me, installation took a considerable amount of time.

Note: the Colab version is only capable of handling images at most 256 pixels tall - if you want more you'll need to get the GitHub [project](https://github.com/facebookresearch/pifuhd) working locally.

Jonathan Kron's the tutorial suggests using _Smart UV Project_ unwrapping which results in overlapping faces (which may be fine for background characters but caused big issues for me). By trial and error, I chose _Lightmap Pack_ instead which doesn't result in overlapping but has its own issues (you can see the unusual "noise" on the texture as bits of the texture break through from other areas of the model). Ideally, I guess one would manually add seams and unwrap as in the human unwrapping tutorial linked to below.

Better results yet could probably be achieved by manually adding seams and unwrapping - as described [here](https://www.youtube.com/watch?v=y8vZraSY3ZE) for a human form.

`george.blend.gz` is the `.blend` file with all the UVs setup ready for painting, it has two base UVs - `Base` and `Base2`. `Base` is the UV unwrapped using _Smart UV Project_ and `Base2` is unwrapped using _Lightmap Pack_. In the end, I didn't use `Base` as at all.

`george-minus-uvs.blend.gz` is the finished `.blend` with all UVs, except `Base2`, removed. I found Sketchfab (and the babylon.js and three.js sandboxes) were're confused by the `.glb` files I produced from `.blend` file containing all UVs (I'm sure it must be possible to get a useable `.glb` file without doing this).

`george-minus-uvs.glb.gz` is the final `.glb` that was uploaded to Sketchfab. I also tried `.obj` but `.glb` seems better supported (and a `.obj` export actually involves two files, the `.obj` and the textures which are stored in an accompanying `.mtl` file that you have to remember to upload to any viewer with the `.obj`).

The original photos can be found in [`images`](images).