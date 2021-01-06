[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Alfred: 4](https://img.shields.io/badge/alfred-4-blueviolet.svg)](https://alfredapp.com)

# aws-alfred-snippets

A collection of snippets related to AWS services for text expansion using Alfred.

## Introduction

This is a collection of snippets in the format Alfred understands for use in text expansion.  

A snippet consists of the following fields:

* Name - the snippet name.
* Keyword - the term that gets expanded.
* Collection - what snippet collection the snippet belongs to, can be inherited from the collection.
* Auto expansion allowed - a boolean inherited from Alfred preferences, ideally set to true.
* Type - at the moment I'm only allowing: 'Plain Text Snippet'.
* Snippet - the text resulting from the expansion.
* uid - a globally unique (within the scope of any Alfred account) identifier for the snippet, usually a guid.

These are described in a json file like the one below:

```
{
  "alfredsnippet" : {
    "snippet" : "AWS Outposts 1U Servers",
    "uid" : "6ACF5D57-86F3-4380-B851-5B34F1524A4F",
    "name" : "1u",
    "keyword" : "1u"
  }
}

```

A collection is a zip archive with the file extension ```.alfredsnippets```.  At the root of the archive are the json snippet files and ```info.plist``` file containing the expansion prefix or suffix.  Expansion prefixes (and suffixes) preceed (follow) the keyword to distinguish it from regular text.  I think the use of one or the other is best practice as long as the keys are easily accessible on the keyboard.  I've put an angle bracket suffix because it is easy to reach on a UK keyboard.  I won't accept PR's that change that but you should feel free to fork the repo and choose the appropriate character for yourself before building.
   
## Contributing

My hope is that people will contribute.  In the absence of contributions however I'll just grind through all the AWS services as I find the time.  There are a couple of particular problems with this process and they are these: 1) What should the keyword be and 2) what should the name be.  The latter is less important and is really about organizing the list of snippets because there will be so many.  The former is much more important because it may make the expansion usable or not.  If it's too obscure it won't be used, if it's too parsimonious it won't be remembered, if it's too verbose it will be easier to do with out it.  I don't know a way to solve this.  I was wondering if I should do a poll on each new addition or some sort of roadtest.  Or, possibly there is a pattern I can discern based on capitlization in the text or something else.  I'm open to suggestions.

As I mention above, I won't accept PR's on the ```info.plist``` file. 

I will use [semver](https://semver.org) for the version numbers.  A breaking change (and major version increment) will be where any of the keywords have changed. A non-breaking change and minor version increment will be the addition of new snippets.  A patch will be correction of a name or text expansion (snippet).   

## Analytics

It would be great if prior to using the collection you go to Alfred Preferences->Usage and make a note of the figure for expansions for the previous period.  Then do the same one month afterwards and report the difference in an issue.  Then I can get some crude non-scientific idea about how much it gets used and how much time it might have saved users.   
