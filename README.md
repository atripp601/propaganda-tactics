# Propaganda Tactics

This repository contains the source code for the XWiki-based application at propaganda-tactics.com.
Currently, all code is under the xwiki directory.

# Xwiki Files
Everything in the xwiki directory was created using the XWiki "Export" feature.
Each top-level directory (e.g. Articles) is a top-level page that appears in the Navigation panel in the top left of the website.
A few directories are not included here:
* Themes for Flamingo - not needed to recreate the website
* Job Scheduler - not needed
* XWiki - not needed and contains user information

# How To Use
To import these pages into XWiki, you need to pack them up into a .xar file and import that:
* Download these files from this github repository with "git clone" or similar.
* Download and install the JDK. 
* Go to the directory where you've saved these files and run "jar -cvf tactics.xar ."
* Get your own XWiki instance running.
* On your XWiki instance, go to the "Global Administration: Import" page and import the tactics.xar file that you just created.
* You should now see these pages in the Navigation panel at the top left.

# More Details
At the top level, we have pages like "About", "Articles", etc. These are XWiki non-terminal pages, written in XWiki 2.1 syntax.
Many also contain velocity code. For example, the Articles page contains velocity code to show a summary of all the children article pages in a table.
To make the the code modular, most of the velocity code is kept in the Dev directory. For example, the Dev/ArticleMacros page contains a velocity macro called "#showArticlesTable()". So the Articles page is actually nothing more than an "include" line to include that other page, and a call to that "#showArticlesTable()" macro.

The Dev directory contains all the development-related pages, and so it's not displayed to end users. It includes:
* Velocity macros
* XWiki Sheets, Templates, and Template Providers
* An Images page to hold all images for any page to refer to

To learn about XWiki Sheets, Templates, and Template Providers, See [Creating a FAQ Application (Manual)](https://www.xwiki.org/xwiki/bin/view/Documentation/DevGuide/Tutorials/FAQTutorial/FAQTutorialManual).


The Contributor Info directory contains information for Contributors - people who can create and edit pages. Thus, it's hidden from the general public. 
Contributors is an XWiki group with Edit permissions. The "unregistered guest" user is only allowed to view and comment on pages.


