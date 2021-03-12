# 1.1.2 Blender's strip types

##  <a id="firstHeading"></a>

 A strip is a container that carries frames provided by one or more sources \(input\). It is defined by a Start Frame and a Length and is displayed as a colored horizontal rectangle.

  
 For adding strips, you can use the Add menu in the header or hover your mouse cursor over the Sequence workspace and press Shift-A. The start frame of the newly created strips will be placed at the position of the frame indicator. When loading multiple files \(movie and sound\) at the same time each will be added one after the other. Strips are color-coded in the VSE and each type of strip has its own unique color.[![adding strips](https://static.miraheze.org/blendocwiki/thumb/8/80/Video-editing_sequencer_strips_introduction_add-menu.png/119px-Video-editing_sequencer_strips_introduction_add-menu.png)](https://blendoc.miraheze.org/wiki/File:Video-editing_sequencer_strips_introduction_add-menu.png)

**&gt;&gt;&gt; TODO**: adding animage with add menu and colored strips

* Scene strip: Light green.
* Clip strip: Dark blue.
* Mask strip: Red.
* Movie strip: Aquamarine.
* Image strip: Purple.
* Sound strip: Turquoise.
* Each of the effect strips has its own color.

### Contents <a id="mw-toc-heading"></a>

* [1 Movie strip](https://blendoc.miraheze.org/wiki/Blender%27s_strip_types#Movie_strip)
* [2 Image/](https://blendoc.miraheze.org/wiki/Blender%27s_strip_types#Image/Seqyence_Strip)Sequence[ Strip](https://blendoc.miraheze.org/wiki/Blender%27s_strip_types#Image/Seqyence_Strip)
* [3 Image Sequence strip](https://blendoc.miraheze.org/wiki/Blender%27s_strip_types#Image_Sequence_strip)
* [4 Image strip](https://blendoc.miraheze.org/wiki/Blender%27s_strip_types#Image_strip)
* [5 Sound strip](https://blendoc.miraheze.org/wiki/Blender%27s_strip_types#Sound_strip)
* [6 Scene Strip](https://blendoc.miraheze.org/wiki/Blender%27s_strip_types#Scene_Strip)
* [7 Text & Color Strip](https://blendoc.miraheze.org/wiki/Blender%27s_strip_types#Text_&_Color_Strip)
* [8 Color Strips](https://blendoc.miraheze.org/wiki/Blender%27s_strip_types#Color_Strips)

### Movie strip

You can use the menu Add or the shortcut `Shift - A` to add a movie \(with or without audio\). A File Browser pops up where you can select a movie.[![File Browser to add a Movie Strip](https://static.miraheze.org/blendocwiki/thumb/b/bf/Add_movie_strip.png/800px-Add_movie_strip.png)](https://blendoc.miraheze.org/wiki/File:Add_movie_strip.png)

* Relative Path: store the location of the image file relative to the blend-file.
* Start Frame: the Start Frame to place the left handle of the strip.
* Channel: the Channel to place the strip.
* Replace Selection: replaces the currently selected strips with the new strip.
* Fit Method: determines how images with an aspect ratio different than the Scene are scaled to fit inside the render area.
  * Scale to Fit: adjusts the strips Scale Transforms so the visual contents of the strip to fit exactly within the project’s Dimensions while maintaining the original aspect ratio. This may mean that the transparent areas may be added along the content’s border to fit the content in the rendered area.
  * Scale to Fill: Adjusts the strips Scale Transforms so the visual contents of the strip to span the project’s Dimensions while maintaining the original aspect ratio. This may mean that portions of the original image no longer fit the content inside the rendered area.
  * Stretch to Fill: adjusts the strips Scale Transforms so the visual contents of the strip to fill the project’s Dimensions. Note, unlike the other two methods described above, Stretch to Fill does not maintain the original aspect ratio. This may mean that the original image becomes distorted to fit the content inside the rendered area.
* Sound: add a Sound Strip that contains the movie’s audio track.
* Use Movie Frame Rate: sets the Scene Frame Rate to the frame rate encoded in the movie file.

### Image/Sequence Strip

### Image Sequence strip

An image sequence is a numbered list of images \(e.g. \*-0001.jpg, \*-0002.jpg, \*-0003.jpg, etc, of any image format\). Navigate into the directory and LMB click and drag over a range of names to highlight multiple files. You can page down and continue Shift-LMB click-dragging to add more to the selection. Press A to select/deselect all files in the directory. Each image will be one frame, in sort order, and can be a mix of file types \(jpg, png, exr, etc.\).

[![File Browser for adding an Image Sequence](https://static.miraheze.org/blendocwiki/thumb/6/62/Add_image_sequence.png/800px-Add_image_sequence.png)](https://blendoc.miraheze.org/wiki/File:Add_image_sequence.png)

Dealing with different-sized images and different-sized outputs is tricky. If you have a mismatch between the size of the input image and the render output size, the VSE will try to auto-scale the image to fit it entirely in the output. This may result in clipping. If you do not want that, use Crop and/or Offset in the Input panel to move and select a region of the image within the output. When you use Crop or Offset, the auto-scaling will be disabled and you can manually re-scale by adding the Transform effect.

You can add an Image Sequence with the menu Add or the shortcut Shift - A.

* Relative Path: store the location of the image file relative to the blend-file.
* Start Frame: the Start Frame to place the left handle of the strip.
* End Frame: the end frame to place the right handle of the strip. Subtract the Start Frame from the End Frame to get the strip’s duration.
* Channel & Replace Selection & Fit Method: see [Movie strip](https://blendoc.miraheze.org/w/index.php?title=Movie_strip&action=edit&redlink=1)
* Use Placeholders: image sequences can use placeholder files. This works by enabling Use placeholders checkbox when adding an image strip. The option detects the frame range of opened images using Blender’s frame naming scheme \(filename + frame number + .extension\) and makes an image sequence with all files in between even if they are missing. This allows you to render an image sequence with a few frames missing and still the image strip will have the correct range to account for the missing frames displayed as black.

When the missing frames are rendered or placed in the same folder, you can refresh the Sequencer and get the missing frames in the strip. The option is also available when using the Change Data/File operator and allows you to add more images to the range.

### Image strip

When you add a single still image \(\*.jpg, \*.png, etc.\), Blender creates a 25 frames long strip which will show this image along the strips range.

The supported graphics formats [\[1\]](https://docs.blender.org/manual/en/dev/files/media/image_formats.html) are: BMP, Iris, PNG, JPEG, JPEG2000, Targa, Cineon & DPX, OpenEXR, Radiance HDR, and TIFF.

### Sound strip

As well as images and movies the VSE can also edit audio tracks. The following audio codecs \[image [https://docs.blender.org/manual/en/dev/files/media/video\_formats.html](https://docs.blender.org/manual/en/dev/files/media/video_formats.html)\] are supported: AAC, AC3, FLAC, MP2, MP3, Opus, PCM and Vorbis. The audio from an encoded video file can also be used.

[File:Https://docs.blender.org/manual/en/dev/ images/video-editing sequencer strips sound editing.png Example of sound editing](https://blendoc.miraheze.org/w/index.php?title=Special:Upload&wpDestFile=Https://docs.blender.org/manual/en/dev/_images/video-editing_sequencer_strips_sound_editing.png_Example_of_sound_editing)

A sound strip is just like any other strip in the VSE. You can select and move it, adjust its starting offset using LMB over the strip handles, and K cut it into pieces. A useful example is cutting out the “um’s” and dead voice time.

You can have as many sound strips as you wish and the result will be the mixing of all of them. You can give each strip its own name and volume via the Sidebar region.

Overlapping strips are automatically mixed down during the rendering process. For example, you can have the announcer on channel 5, background music on channel 6, and Foley sound effects on channel 7.

In the Playback Popover menu of the Timeline, you will find some options concerning audio playback behavior. Animating Audio Track Properties

To animate sound strips simply hit I over any of its values. Examples of animating an audio strip are to fade in/out background music or to adjust volume levels. Layered/crossed sound strips are added together; the lower channel does not override and cut out higher channels \(unlike image and video strips\). This makes Blender an audio mixer. By adding audio tracks and using the curves to adjust each tracks’ sound level, you have an automated dynamic multi-track audio mixer!

There are two ways to render out your audio. You can either have it encoded with a video file or in its own audio file. Read more on how to select a proper audio format and how to start rendering.

You can add a Sound Strip with the menu Add &gt; Sound or the shortcut `Shift - A`.

Relative Path: store the location of the image file relative to the blend-file. Start Frame: the Start Frame to place the left handle of the strip. Channel: the Channel to place the strip. Replace Selection: replaces the currently selected strips with the new strip. Cache: cache the sound in memory, enables Caching in the Source properties. Mono: merge all sound channels into one channel, enables Mono in the Sound properties.

### Scene Strip

Scene strips are a way to insert the render output of another scene into your sequence. Instead of rendering out a video, then inserting the video file, you can insert the scene directly. The strip length will be determined based on the animation settings in that scene. Scene strips cannot be used to reference the sequence’s own scene; a secondary scene must be used instead. Options

The Properties panel of a Scene strip contains a subpanel Scene. The following options can be set.

Input: camera or sequencer

???Use Sequence: Expand the scenes sequence strips, allowing one scene to reuse another scene’s edit \(instead of taking the render output from the scene\). This is similar to how Meta Strips work, with the added advantage of supporting multiple instances of the same data.

Volume: the volume of the audio taken from the chosen scene can be overridden.

Camera: if input is set to camera, here you can choose which camera to use \(if multiple cameras are available\). This can be used to override the scene’s camera with any other object. It is useful to support switching views within a single scene.

Show Grease Pencil: shows Grease Pencil in non render preview i.e. Solid mode.

Transparent: creates a transparent background. This is useful for doing overlays like rendering out Grease Pencil films via the Sequencer.

Scene strips do not render individual Render Passes; only the Combined render pass will be used.

### Text & Color Strip

The Text strip allows you to directly display text in the Sequence editor. The strip will display the text inserted in its text field on the final sequence.

[![Example of a Text Strip](https://static.miraheze.org/blendocwiki/thumb/2/2a/Text_strip_example.svg/800px-Text_strip_example.svg.png)](https://blendoc.miraheze.org/wiki/File:Text_strip_example.svg)

* Text: the actual text displayed.
* Wrap Width: wraps the text by the percentage of the frame width, setting this to zero disables word wrapping.
* Font: data-Block Menu to choose which font-file is used to render the text.
* Size: size of the text.
* Color: the text color.
* Shadow: creates a shadow of the specified color under the text. If Box \(blow\) is selected then the shadow is created for the box; otherwise, the text itself gets a shadow.
* Box: creates a background for the text to improve the readability and clarity of text in some situations. The color and opacity of the box can be adjusted using the color selector.
* Box Margin: the distance the box boundaries extends from the boundaries of the font glyphs. The distance is measured as a factor of the image’s width.
* Location X, Y: positions the text on the X, Y axis. Expressed in proportions \(percentage\): \(1,1\) is at the top right corner.
* Anchor X, Y: horizontal \(X\) or vertical \(Y\) anchor point of the text relative to the location.

All Text strips in a video sequence can be exported as a SubRip file. This is useful when using Text strips as subtitles.

### Color Strips

This effect generates solid color frames. By default, when it is created, the color strip is 25 frames long, but you can extend it by selecting and moving one of the ends. Use this strip crossed with your main movie to provide a fade-in or fade-out.

