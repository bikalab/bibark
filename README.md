Bibark 
=====

Bibark is a command-line installer for Windows.

Requirements:

* [PowerShell 3](https://www.microsoft.com/en-us/download/details.aspx?id=34595)
* PowerShell must be enabled for your user account e.g. `set-executionpolicy remotesigned -s cu`

To install:

    iex (new-object net.webclient).downloadstring('https://bibark.bikalab.com')

Once installed, run `bibark help` for instructions.

What does Bibark do?
-------------------

Bibark installs programs from the command line with a minimal amount of friction. It tries to eliminate things like:
* Permission popup windows
* GUI wizard-style installers
* Path pollution from installing lots of programs
* Unexpected side-effects from installing and uninstalling programs
* The need to find and install dependencies
* The need to perform extra setup steps to get a working program

Bibark is very scriptable, so you can run repeatable setups to get your environment just the way you like, e.g.:

```powershell
bibark install sudo
sudo bibark install 7zip git openssh --global
bibark install curl grep sed less tail touch
bibark install python ruby go perl
```

If you've built software that you'd like others to use, Bibark is an alternative to building an installer (e.g. MSI or InnoSetup)—you just need to zip your program and provide a JSON manifest that describes how to install it.

### [Documentation](https://github.com/bikalab/bibark/wiki)

Inspiration
-----------

* [Homebrew](http://mxcl.github.io/homebrew/)
* [sub](https://github.com/37signals/sub#readme)

What sort of apps can Bibark install?
------------------------------------

The apps that install best with Bibark are commonly called "portable" apps: i.e. compressed program files that run stand-alone when extracted and don't have side-effects like changing the registry or putting files outside the program directory.

Since installers are common, Bibark supports them too (and their uninstallers).

Bibark is also great at handling single-file programs and Powershell scripts. These don't even need to be compressed. See the [runat](https://github.com/bikalab/bibark/blob/master/bucket/runat.json) package for an example: it's really just a GitHub gist.

