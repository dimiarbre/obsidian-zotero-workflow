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

<!-- TODO: add screenshots of my setup here, with notes examples, graph view etc -->

## Installation
Because of Linux's features, some problems can be found when linking Zotero to Obsidian. In particular, installations using `snap` or `flatpack`, which are the main installations packages for both of these applications. This is due to their containment policies, forbidding obsidian from detecting Zotero.

### Installing Zotero
Go to the [official release page](https://www.zotero.org/download/). This should provide you with the latest version in a compressed folder. You can then follow their [installation guide](https://www.zotero.org/support/installation) for your system. You may also want to install the Zotero connector on your browser, since it is a very powerful tool.


### Installing Obsidian
Two ways to install obsidian are available. Go to their [official download page](https://obsidian.md/download). From there, you can either:
* Use the `.deb` file (not natively supported on Fedora to my knowledge)
* Use the `AppImage` installation 

For the AppImage version, the simplest way to then have Obsidian readily available is to use AppImageLauncher. For this, go to the [official release page](https://github.com/TheAssassin/AppImageLauncher/releases) and install AppImageLauncher, using either the `.rpm` or the `.deb` file. This should be sufficient to completely set up 

Either case, Obsidian should be installed, you can try to launch it and create a vault to try.

### Setting up zotero-export

The template used here is a manually changed version of this [templating repo](https://github.com/nocona71/obsidian-literature-note/blob/main/README.md). You can also use their basic version and fine-tune it to the shape you prefer.

To copy the templates, if you want to synchronize with this git repository, you should perform the following command:
```bash
ln /path/to/this/repo/Templates/* /path/to/your/obsidian/vault/Templates/
```

<!-- TODO: explain how to set up the template inside obsidian with screenshots -->

### List of recommended Obsidian packages
<!-- TODO -->