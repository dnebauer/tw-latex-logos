# Packaging tiddlywiki plugin "Latex Logos"

## Ensure correct tiddlywiki setup ##

These instructions assume tiddlywiki is running under nodejs with tiddlers
saved to individual files rather than a single-file wiki.

These instructions are for packaging the plugin using Tinka
([project](http://tinkaplugin.github.io),
[repository](https://github.com/TinkaPlugin/Tinka)). Ensure the Tinka plugin is
installed in the tiddlywiki -- this requires restarting the tiddlywiki server
after installing the plugin.

## Uninstall the previous version ##

Skip this section if the plugin is not currently installed in the tiddlywiki
you intend to use for packaging.

Follow these steps:

1. Stop the tiddlywiki server.

2. Delete the plugin file which is located in `'<wiki_root>/tiddlers/'` and
   named `'$__plugins_.dtn_latex-logos.tid'`.

3. Copy the `*.tid` files from the `'source'` subdirectory to
   `'<wiki_root>/tiddlers'`.

4. Restart the tiddlywiki server.

## Package using Tinka ##

Open _Control Panel_ > _Tinka Plugin Management_ tab > _Create a new Plugin_ tab.

### Step 1: Enter Metadata ###

Enter the following metadata values:

|       Field|Value                                  |
|-----------:|:--------------------------------------|
| Plugin-Type|plugin                                 |
| Plugin Path|\$:/plugins/.dtn/latex-logos           |
|      Author|David Nebauer                          |
|      Source|---                                    |
|  Dependents|---                                    |
|        List|readme config credits license          |
|Plugin Title|Latex-related logos                    |
|     Version|_0.0.1_ or _increment previous version_|
|Core-Version|>=5.1.18                               |

### Step 2: Add Tiddlers ###

Search for the key phrase `latex-logos` and select the following tiddlers:

* \$:/config/plugin/.dtn/latex-logos/bibtex-ib
* \$:/config/plugin/.dtn/latex-logos/context-n
* \$:/config/plugin/.dtn/latex-logos/latex-a
* \$:/config/plugin/.dtn/latex-logos/luatex-a
* \$:/config/plugin/.dtn/latex-logos/tex-e
* \$:/config/plugin/.dtn/latex-logos/xelatex-ɘ
* \$:/config/plugin/.dtn/latex-logos/xetex-ɘ
* \$:/plugins/.dtn/latex-logos/macros
* \$:/plugins/.dtn/latex-logos/stylesheet
* \$:/plugins/.dtn/latex-logos/readme
* \$:/plugins/.dtn/latex-logos/config
* \$:/plugins/.dtn/latex-logos/credits
* \$:/plugins/.dtn/latex-logos/license

### Step 3: Package ###

Press the _Package plugin_ button.

Ignore the _Uncaught TypeError: Cannot read property 'ownerDocument' of
undefined_ internal javascript error, restart the tiddlywiki server, and reload
the wiki in your browser.

Warning: the tiddlers selected in Step 2 are deleted when the plugin file is
built.

## Save plugin file ##

Delete any files in the `plugin` subdirectory.

The plugin file is located in `'<wiki_root>/tiddlers/'` and named
`'$__plugins_.dtn_latex-logos.tid'`.

Save a copy of the plugin file to the `plugin` subdirectory.
