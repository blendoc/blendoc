# 1.1.1 Set up a directory structure

A video project is most likely a combination of several different assets. You can merge them into three broad categories.

* Video files: video clips \(or movies in Blender-talk\), photos, graphic files \(charts, logos, ...\), and Visual Effects \(VFX\) such as masks, lens flares, animation.
* Audio files: recorded dialog, voice-over, music, and Sound Effects \(SFX\) such as environmental sounds, swooshes, ...
* Project files: the blend files and backups, \(partial\) render results, documentation such as scripts and storyboards.

Together they can form rapidly an untangible heap of files. It's good practice to collect all those assets in one project directory with appropriate subdirectories. Why? It will lower the probability that you accidentally delete a file \(which will result in a 'file not found' error\) or that you forget to include a necessary file when transferring the project \(file is missing\). And most of all, an appropriate directory structure will help you to keep a clear overview of your assets.

```text
Blender can incorporate some files within the blend-file (see Packed Data). However, for the VSE, this is not good practice because video files can have very huge filesizes and some data types cannot be packed; e.g. movie-files. It's better to assure that your project directory contains all neccessary files.
```

It's also good practice to use some kind of naming convention and add metadata. Figure 1 shows a possible example, based on our categorization of the assets above. The directories are numbered so that they mimic a normal workflow.

[![1 1 organizing your project 1.svg](https://static.miraheze.org/blendocwiki/thumb/e/e4/1_1_organizing_your_project_1.svg/1920px-1_1_organizing_your_project_1.svg.png)](https://blendoc.miraheze.org/wiki/File:1_1_organizing_your_project_1.svg)

Blender does not have a full-blown asset manager yet, but with the File Browser, you already can go a long way. For example, with `Display Settings` you could recursively browse up to three levels of directories. Because the 'demo-project'-directory is selected in figure 1, "1\_video" \(first level\), "1-1-movie" \(second level\), and "Spring - Blender Open Movie.mp4" \(third level\) are displayed. With `Filter Settings"` you could prevent the display of certain types of files.

