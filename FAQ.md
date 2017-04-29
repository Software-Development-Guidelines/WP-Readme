Index of pages:
---------------

* [Summary](/README.md)
* [Introduction](/README.md)
* [CMS Changelog (CMSchangelog)](/CHANGELOG.md)
* [Why CMS Changelog](/WHY.md)
* [FAQ](/FAQ.md)
* [ABOUT](/ABOUT.md)
* [Who is using CMS Changelog?](/USERS.md)


# FAQ

## How can I minimize the effort required?
Always have an "Unreleased" section at the top for keeping track of any changes.

This serves two purposes:

* People can see what changes they might expect in upcoming releases
* At release time, you just have to change "Unreleased" to the version number and add a new "Unreleased" header at the top.

## Which type of changelog should avoid?
Alright…let’s get into it.

* Dumping a diff of commit logs. Just don’t do that, you’re helping nobody.
* Not emphasizing deprecations. When people upgrade from one version to another, it should be painfully clear when something will break.
* Dates in region-specific formats. In the U.S., people put the month first ("06-02-2012" for June 2nd, 2012, which makes no sense), while many people in the rest of the world write a robotic-looking "2 June 2012", yet pronounce it differently. 

## Is there a standard change log format?
Sadly, no. Calm down. I know you're furiously rushing to find that link to the GNU change log style guide, or the two-paragraph GNU NEWS file "guideline". The GNU style guide is a nice start but it is sadly naive. There's nothing wrong with being naive but when people need guidance it's rarely very helpful. Especially when there are many situations and edge cases to deal with.

## What should the change log file be named?
Well, if you can’t tell from the example above, CHANGELOG.md is the best convention so far.

Some projects also use HISTORY.txt, HISTORY.md, History.md, NEWS.txt, NEWS.md, News.txt, RELEASES.txt, RELEASE.md, releases.md, etc.

It’s a mess. All these names only makes it harder for people to find it.

## Why can’t people just use a git log diff?
Because log diffs are full of noise — by nature. They could not make a suitable change log even in a hypothetical project run by perfect humans who never make typos, never forget to commit new files, never miss any part of a refactoring. The purpose of a commit is to document one atomic step in the process by which the code evolves from one state to another. The purpose of a change log is to document the noteworthy differences between these states.

As is the difference between good comments and the code itself, so is the difference between a change log and the commit log: one describes the why, the other the how.

## Can change logs be automatically parsed?
It’s difficult, because people follow wildly different formats and file names.

Vandamme is a Ruby gem created by the Gemnasium team and which parses many (but not all) open source project change logs.

## Why do you alternate between spelling it "CHANGELOG" and "change log"?
"CHANGELOG" is the name of the file itself. It's a bit shouty but it's a historical convention followed by many open source projects. Other examples of similar files include README, LICENSE, and CONTRIBUTING.

The uppercase naming (which in old operating systems made these files stick to the top) is used to draw attention to them. Since they're important metadata about the project, they could be useful to anyone intending to use or contribute to it, much like [open source badges project](http://shields.io/).

When I refer to a "change log", I'm talking about the function of this file: to log changes.

## What about yanked releases?

Yanked releases are versions that had to be pulled because of a serious bug or security issue. Often these versions don't even appear in change logs. They should. This is how you should display them:

		## 0.0.5 - 2014-12-13 [YANKED]

The <[YANKED]> tag is loud for a reason. It's important for people to notice it. Since it's surrounded by brackets it's also easier to parse programmatically.
Should you ever rewrite a change log?

Sure. There are always good reasons to improve a change log. I regularly open pull requests to add missing releases to open source projects with unmaintained change logs.

It's also possible you may discover that you forgot to address a breaking change in the notes for a version. It's obviously important for you to update your change log in this case.






## How should I deal with revisions in the 0.x.y.z initial development phase?

The simplest thing to do is start your initial development release at 0.1.0.0 = 0.1.0 and then increment the FEATURE version for each subsequent release.


## How do I know when to release 1.0.0.0?

If your software is being used in production, it should probably already be 1.0.0.0. If you have a stable API on which users have come to depend, you should be 1.0.0.0. If you're worrying a lot about backwards compatibility, you should probably already be 1.0.0.0.

## Doesn't this discourage rapid development and fast iteration?

ENHANCED version zero is all about rapid development. If you're changing the API every day you should either still be in version 0.x.y.z or on a separate development branch working on the next major version.

## -If even the tiniest backwards incompatible changes to the public API require a major version bump, won't I end up at version 42.0.0 very rapidly?

This is a question of responsible development and foresight. Incompatible changes should not be introduced lightly to software that has a lot of dependent code. The cost that must be incurred to upgrade can be significant.
Having to bump major versions to release incompatible changes means you'll think through the impact of your changes, and evaluate the cost/benefit ratio involved.

## Documenting the entire public API is too much work!

It is your responsibility as a professional developer to properly document software that is intended for use by others. Managing software complexity is a hugely important part of keeping a project efficient, and that's hard to do if nobody knows how to use your software, or what methods are safe to call. In the long run, CMS Versioning (CMSver), and the insistence on a well defined public API can keep everyone and everything running smoothly.

## What do I do if I accidentally release a backwards incompatible change as a FEATURE version?

As soon as you realize that you've broken the CMS Versioning (CMSver) spec, fix the problem and release a new minor version that corrects the problem and restores backwards compatibility. Even under this circumstance, it is unacceptable to modify versioned releases. If it's appropriate, document the offending version and inform your users of the problem so that they are aware of the offending version.

## What should I do if I update my own dependencies without changing the public API?

That would be considered compatible since it does not affect the public API.
Software that explicitly depends on the same dependencies as your package should have their own dependency specifications and the author will notice any conflicts. Determining whether the change is a PATCH version level or FEATURE version level modification depends on whether you updated your dependencies in order to fix a bug or introduce new functionality. I would usually expect additional code for the latter instance, in which case it's obviously a minor level increment.

## What if I inadvertently alter the public API in a way that is not compliant with the version number change (i.e. the code incorrectly introduces a major breaking change in a patch release)

Use your best judgment. If you have a huge audience that will be drastically impacted by changing the behavior back to what the public API intended, then it may be best to perform a ENHANCED version release, even though the fix could strictly be considered a patch release. Remember, CMS Versioning (CMSver) is all about conveying meaning by how the version number changes. If these changes are important to your users, use the version number to inform them.

## How should I handle deprecating functionality?

Deprecating existing functionality is a normal part of software development and is often required to make forward progress. When you deprecate part of your public API, you should do two things: (1) update your documentation to let users know about the change, (2) issue a new minor release with the deprecation in place. Before you completely remove the functionality in a new ENHANCED version release there should be at least one FEATURE version release that contains the deprecation so that users can smoothly transition to the new API.

## Does CMS Versioning (CMSver) have a size limit on the version string?

No, but use good judgment. A 255 character version string is probably overkill, for example. Also, specific systems may impose their own limits on the size of the string.



---



[Start page](./)

