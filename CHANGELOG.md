Index of pages:
---------------

* [Summary](/README.md)
* [Introduction](/README.md)
* [CMS Changelog (CMSchangelog)](/CHANGELOG.md)
* [Why CMS Changelog](/WHY.md)
* [FAQ](/FAQ.md)
* [ABOUT](/ABOUT.md)
* [Who is using CMS Changelog?](/USERS.md)
* [How to create an Historical](/HISTORICAL.md)


# CMS Changelog (CMSchangelog)

A good change log sticks to these principles:
--

* ADDITIONS for new features.
* ENHANCEMENTS for changes in existing functionality.
* BUGFIXES for any bug fixes.
* SECURITY to invite users to upgrade in case of vulnerabilities.
* REMOVED for deprecated features removed in this release.
* DEPRECATED for once-stable features removed in upcoming releases.


For a more detailed information you can use ADDITIONS, ENHANCEMENTS, BUGFIXES, SECURITY, REMOVED, DEPRECATED. inside the next changelog keywords: Adds, Allow, Contains, Displays, Improves, Fixes, Fixes an issue,  Fixes a compatibility issue, Improves, Introduces, Introduces a feature, Introduces the, Made it possible, Makes, Moves, Only includes, Prevent, Prevented, Removes, Removes unused, Rename, Setup, Specify, Splits, Throws, Updated.
 
  
The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](http://tools.ietf.org/html/rfc2119).


1. Software using CMS Changelog MUST declare all the changes of the software. This changes
could be declared in the code itself or exist strictly in documentation.
However it is done, it should be precise and comprehensive.

1. It’s made for humans, not machines, so legibility is crucial. Each change 
Must be short and easy to understand

1. One section per version
Easy to link to any section (hence Markdown over plain text).

1. List releases in reverse-chronological order
Newest on top.

1. The Format MUST NOT be change. Changelog files
are organized by paragraphs, which define a unique change within a function or file and MUST be writen with bulletpoints.

1. The format MUST HAVE one header with information
header with Version and Rlease date

	```
	1.2.3.0. - 2015-10-21
	```
1. CMSchangelog MAY use CMSver
SEMVER or other ways to name your releases are allowed but we RECOMMENDED to use CMSver as we believe it could adapt better to each situation.
Explicitly mention whether the project follows [CMS Versioning](https://software-development-guidelines.github.io/CMScver/).

1. Dates MUST be in YYYY-MM-DD format. It’s international, sensible, and language-independent.
Include release date for each release you do. People like to know when a release was done. The ISO 8601 format YYYY-MM-DD works logically from largest to smallest, doesn't overlap in ambiguous ways with other date formats, and is an [ISO standard](http://www.iso.org/iso/home/standards/iso8601.htm). Thus, it is the recommended date format for change logs.

1. The format MUST HAVE Group changes in sub-sections to describe their impact on the project
with the name of the sub-sections if any ADDITIONS, ENHANCEMENTS, BUGIXED, SECURITY, REMOVED, DEPRECATED.
Example of sub-section

	```
	* ADDITIONS new feature #1
	* ADDITIONS new feature #2
	* BUGIXED Fix bug #1
	* BUGIXED Fix bug #2
	```
or

	```
	* ADDITIONS
	  * new feature #1
	  * new feature #2
	* BUGIXED
	  * Fix bug #1
	  * Fix bug #2
	```
1. Always have an "UNRELEASED" section at the top for keeping track of any changes. This serves two purposes
People can see what changes they might expect in upcoming releases and at release time, you just have to change "Unreleased" to the version number and add a new "Unreleased" header at the top.

1. Contributors name SHOULD be writen in the Changelog and the commit MAY be added too
When you introduce someone else’s changes, put the contributor’s name in the ending of the paragraph of the change of the changelog   rather than in other place and between brakets.
props to @UserName;
props to @UserName for the suggestion;
props to @UserName for the report.
If there is an Git or CVS commit, MUST be afther the name of the contributor: 
see #123.

	```
	* ADDITIONS new feature #1 (props to @UserName; see #123)
	```
1. Always inform about the "BREAKING CHANGES" 
for keeping track of any changes.

	```
	* ADDITIONS new feature #1 (BREAKING CHANGES)
	```

1. List the Revised Files. This show 
where to find the changes. Organize it as: Added, Modified and Copied or renamed

	```
	List of Files Revised
	-----------------------
	settings.php
	admin/customize.php
	admin/css/customize.css
	```
1. Publicly available
The changelog MUST be publicly available. If you offer in a zip, that’s only accessible to clients. In this case you SHOULD have a page up on your website that includes the changelog and keep it up to date.

1. Example of changelog
The file start with a header level 1 with the name of the file. A header level 2 for any version An the level 3 are the grups of changes.

	```
	= Changelog =
	All the NOTABLE changes will be documented in that file.
	
		== 1.2.3.0. - 2015-10-21 ==
	  		
			* ADDITIONS
			  * new feature #1
			  * new feature #2 (props to @UserName; see #123)
			* BUGIXED
			  * Fix bug #1
			  * Fix bug #2 (props to @UserName; see #124)
			  
		== 1.2.4.0. - 2015-10-21 ==
	  		
			* ADDITIONS
			  * new feature #1
			  * new feature #2 (props to @UserName; see #123)
			* BUGIXED
			  * Fix bug #1
			  * Fix bug #2 (props to @UserName for the report)
				  
				    
	= List of Files Revised =
	-----------------------
	settings.php
	admin/customize.php
	admin/css/customize.css
	```

---



[Start page](./)

