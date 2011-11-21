Git BigJobbies and Mercurial Large Files
========================================

Mercurial 2.0 released a '''large files extension''' which enables partial
clones of a repository, without cloing a project's full history. This was
done to allow Mercurial to store files that don't compress well (such as
compiled output or media-heavy resources), but which may be stored in the
repository as well and acquired on demand.

More information about the 
large files extension can be found at
 http://mercurial.selenic.com/wiki/LargefilesExtension
and more information on Mercurial's RevLog format can be found at 
 http://mercurial.selenic.com/wiki/Revlog

Owing to the way Mercurial files are stored on disk (with the RevLog format),
this change was not trivial to implement. In addition, it requires that any
existing repository be upgraded to support large files, along with a new
flag `--large` to indiciate that the data is to be handled differently.

The LargeFiles extension is a way of putting the Centralised back into
DeCentralised, since if the repository is no longer contactable you cannot
resolve your data.

Git BigJobbies
--------------

Git BigJobbies is both a demonstration for how to create Git extensions
(created as part of @alblue's "Git Tip of the Week" series, available from
 http://alblue.bandlem.com/search/label/gtotw ), and a simplistic way of
achieving the same support for out-of-branch files as Mercurial LargeFiles.

It is not intended as a practical or useful extension; rather, it is a
demonstration that Git's object storage model can easily be adapted to new
use cases if so desired.

The extension has known bugs, is not recommended for general use, and is
for light entertainment purposes only. Generally the use of Git Submodules
is recommended for separation of large binary assets from source code;
or alternatively on separate branches (or other references) within the
same repository.

Use
---

Download and install `git-bigjobbies` somewhere in your PATH.

* `git bigjobbies add path/file` - add the file as a bigjobby to the repository
* `git bigjobbies rm path/file` - remove the file as a bigjobby to the repository
* `git bigjobbies resolve` - resolves all bigjobbies in this checkout

Known Issues
------------

This is generally a bad idea; the point of decentralised version
control systems is that they should be decentralised, not introduce
a centralised system which is needed in order for the operation to work.
