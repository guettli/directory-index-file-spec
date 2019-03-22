# directory-index-file-spec

## Intro

This spec describes a simple way to give a directory an index file. This index file can be used to create a preview of this directory.

It can be used for a preview if you use a cloud storage like nextcloud or seafile. Or  it can be used as preview on the desktop.

## Supported formats

The index file can have one of these names:

* index.html
* index.txt
* index.md

The file ending has this meaning:

* html: HTML file
* txt: utf8 text file
* md: Markdown markup language

## Support in full text search

If the system which contains a directory "foo-dir" with an index-file "index.X" (X can be one of the supported endings) does provide a full text search, then the text in the index file should be indexed. If a search term matches a term in the index-file, then the match should mean 'you have found directory "foo-dir"' and not "you have found the file index.X".


The content of the index file should be rendered above the other files in this directory.

## #hashtag support

Words in this file which start with the hashtag sign (#) should be treated like hashtags.

Hashtags should be rendered and act like hyperlinks. If a user clicks on a hashtag, the user should be able to see the other index files which have this hashtag.

## Example usecase

UseCase: A user stores his images in a directory tree according to this format: YYYY/YYYY-MM/YYYY-MM-DD/ (Y means year, M means month, D means day) 

A concrete index file could be: 2018/2018-12/2018-12-31/index.txt

The content of this could could be:

    Celebrating new year with #Peter and #Mary.

There is an other index file like this: 2019/2019-02/2019-02-03/index.txt with this content:

    Cooking with #Peter 
    
The user interface should provide a simple way to navigate through the files which have the same hashtag.

In this example both files have the hashtag #Peter.



## Where I would like to see this implemented

I would like to see this implemented in my favorite tools:

* GNOME Desktop Environment
* Nextcloud: open file hosting


