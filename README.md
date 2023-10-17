# Obsidian-Zotero workflow

This git describes a set-up process to use obsidian in combination of Zotero for scientific research, aimed for a Linux distribution (and in particular a Fedora distribution since it is my set-up).

## Workflow description

Most research processes can be decomposed in the following way:
1) Reading scientific articles and annotating them
2) Formatting those notes in a more detailed manner, organizing citations
3) Creating drafts and idea notes, directly linking to the literature to use as reference when writing an article

The workflow described here will have the following separation:
* Steps 1. and 2. should be handled in Zotero directly, using most of its default tools.
* Step 3. is handled in Obsidian

The important part is now to link Zotero and Obsidian. This repository will serve as guideline for this process to work without issue, mostly on a Linux distribution. 

## Illustrated presentation
First, I read the article in Zotero and take notes by highlighting and annotating important parts.
![zotero example](assets/zotero_notes_taking.png)

Then, I import the note into Obsidian using a specific template. Every annotation is directly transferred as an obsidian note. 

![Obsidian note result](assets/obsidian_notes_imported.png)

One important thing to note is that you can also jump directly from Obsidian to Zotero if your installation is performed correctly. A working installation took some time out of me, hence this repository objective: simplify this installation process, as well as showcase Obsidian's capabilities.

From this point, I can directly reference those notes or some specific paragraphs in my Obsidian notes that I use to develop ideas, my daily notes or my TODOs, as I would do for any other obsidian file. Here is an example of my TODO file, that links to all the article I plan to read in the future:
![Zotero Todo example](assets/obsidian_notes_example.png)
One neat thing is that you can also import aliases in the note, which means that when trying to reference a Zotero Item, any attribute of the item can be used to find the corresponding note, such as title, author name, citation key.... You only need to set it up correctly


I can also display them in my graph views to organize my literature view.
![excalidraw example](assets/excalidraw_example.png)

Finally, if my Zotero notes are even changed later on, I can simply re-import them into Obsidian to update everything dynamically.

Moreover, all the different types of notes can be identified directly in the graph view, which also allows to group them together.
![graph view example](assets/graph_view_example.png)

## Installation
Because of Linux's features, some problems can be found when linking Zotero to Obsidian. In particular, installations using `snap` or `flatpack`, which are the main installations packages for both of these applications. This is due to their containment policies, forbidding obsidian from detecting Zotero.

### Installing Zotero
Go to the [official release page](https://www.zotero.org/download/). This should provide you with the latest version in a compressed folder. You can then follow their [installation guide](https://www.zotero.org/support/installation) for your system. You may also want to install the Zotero connector on your browser, since it is a very powerful tool.

Furthermore, you also will need to install the `better-bibtex` extension. Find the `.xpi` file necessary, and then import it in Zotero under `Tools>Add-ons` and selecting `Install add-on from file`.
<!-- TODO: complete this part -->

### Installing Obsidian
Two ways to install obsidian are available. Go to their [official download page](https://obsidian.md/download). From there, you can either:
* Use the `.deb` file (not natively supported on Fedora to my knowledge)
* Use the `AppImage` installation 

For the AppImage version, the simplest way to then have Obsidian readily available is to use AppImageLauncher. For this, go to the [official release page](https://github.com/TheAssassin/AppImageLauncher/releases) and install AppImageLauncher, using either the `.rpm` or the `.deb` file. This should be sufficient to completely set up 

Either case, Obsidian should be installed, you can try to launch it and create a vault to try.

### Setting up Zotero Integration
First, you need to install the `Zotero Integration` plugin that can be found directly from obsidian under `Community plugins>Browse`.

Once it is installed, you need to use a template to import your notes. My personal template file can be found in this repository under `Templates/Zotero_import_template.md` 

Templating for `Zotero-Integration` works using `nunjucks`
You should also look at the [package's documentation](https://github.com/mgmeyers/obsidian-zotero-integration/blob/main/docs/Templating.md) if you want to set up your own template. 

The template used here is a manually modified version of this [templating repo](https://github.com/nocona71/obsidian-literature-note/blob/main/README.md). You can also use their basic version and fine-tune it to the shape you prefer.

To copy the templates, if you want to synchronize with this git repository, you should perform the following command:
```bash
ln /path/to/this/repo/Templates/* /path/to/your/obsidian/vault/Templates/
```
Otherwise, you can simply copy the file and then modify it as you see fit.

Finally, you need to set up Obsidian to use this template to import your Zotero notes. Go to the plugin option, and look for `Import Formats`. You need to create an item and set up the directories you want those notes to be located at in your vault. The result should roughly look like this:
![zotero integration settings](assets/zotero_integration_settings.png) 
One important thing is to use the `{{citekey}}` expression at some point: this is the name of the file, and it must be unique for each item. Other attributes could be used, but it should not matter to much.


From then, you can call the command palette, and type the name you gave your template (for this example, `Basic Template`). This should bring up a Zotero prompt, in which you can type the name of the item you want to import. Alternatively, there is a scrolling menu, in which you can find an option to import multiple items at once in "Classic View". What I often do (when I modify my template for instance) is re-import my entire Zotero collection via this menu in a few clicks.  


![The Zotero integration prompt](assets/zotero_integration_prompt.png)
<!-- TODO: explain how to set up the template inside obsidian with screenshots -->

### List of recommended Obsidian packages
* `Image Toolkitt`: This plugin allows you to zoom in on an image by clicking it, instead of having to open the image inside Zotero. To me, it is a must-have if you integrate images in your notes.
* `Periodic Notes`: This plugin generalizes the concept of obsidian's daily notes, and allows you to create weekly or monthly notes. This can also use a template, albeit much simpler. Some basic example templates are available under `Templates/`
* `Calendar`: This plugin is a good synergy with `Periodic Notes`, as it allows to visualize the month in a calendar and to simply access the daily or weekly notes of a given day or week. 
* `KanBan`: This plugin allows for a very neat TODO items visualization, used in a screenshot above.
* `Advanced Tables`: A neat table edition toolbar that is lacking in Obsidian, making editing big table less painful. If you plan to use tables, I definitely recommend you take a look.
* `Emoji-Shortcode`: This plugin lets the user type emojis as they would in Discord, which is very convenient for me. 


### TODOS:
* [ ] Add a section for Periodic notes set-up, in particular the dating scheme.
* [ ] 