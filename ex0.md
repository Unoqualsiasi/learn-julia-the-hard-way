{% import "macros/ork.jinja" as ork with context %} 

#Exercise 0: The Setup

First things first – we'll have to setup your computer to work with Julia. Fortunately, this is quite easy regardless of the OS you use!

## Binaries

If you use Windows, Mac OS X, Ubuntu, Fedora/RHEL/CentOS or a generic Linux distribution that does packages, the download page for the Julia language (<http://julialang.org/downloads/>) is the easiest way to obtain an installer or package version of Julia. For the purposes of this book, we will assume you're using version v0.3.3. Julia is a young language, and it is developing quite a lot. There is, currently, no guarantee that the final version –&nbsp;or, indeed, the next version! – will look anything like it currently does.

## Package managers

If you're using a *NIX distribution, you might be able to use your distro's package manager to get Julia.

For Ubuntu users, there is a PPA provided for Julia, so all you need to do is get a shell and run the following commands:

    sudo add-apt-repository ppa:staticfloat/juliareleases
    sudo add-apt-repository ppa:staticfloat/julia-deps
    sudo apt-get update
    sudo apt-get install julia

Or, in Fedora:

    sudo dnf copr enable nalimilan/julia
    sudo yum install julia


## Compiling from source

Julia changes rapidly, with often more than a dozen average changes per day (!) to the source code. Therefore, some people tend to simply pull the most recent nightly build from Git and recompile it every few days. This is a great way to stay ahead of the curve, and also to come across more bugs than one would want to when learning a new language. By all means do use nightly builds when you are confident with Julia, but I do not recommend doing so for the time you are trying to navigate your way through it.

If you do want to use nightly builds, simply pull the master branch from the [Julia GitHub repo](<https://github.com/JuliaLang/julia>) and compile by typing make into the Terminal. To speed up the process, you might wish to use a number of concurring processes (make -j n, where _n_ is the number of concurrent processes you are going to use).


##IJulia

There is an implementation of the vastly successful IPython notebook environment for Julia. The IPython system, now known as the Jupyter project, is a great way to interactively use Julia in a notebook environment that users of Mathematica or similar software might be used to. It also allows literate coding, mixing Markdown notes and formatting with executable code. To install IJulia, you will need an existing IPython installation, either a distribution like Anaconda or by installing Python and the IPython notebook environment by downloading the Python distribution for your operating system. Once that is in place, install Julia using the instructions above. Then launch Julia and install IJulia using the `Pkg.add("IJulia")` command. Congratulations, you now have your very own notebook environment for Julia!

To launch your environment, either use the profile IPython parameter:

    $ ipython notebook --profile julia

Alternatively, you can fire up the Julia REPL and launch IJulia by:

    using IJulia
    notebook()


## A word on IDEs

As previously noted, this book diverges from Zed Shaw's framework a little. As such, I will not take you through the intricacies of setting up an IDE or a text editor. To cut a rather long story short – use what works for you! Fortunately, most text editors do have some form of support for Julia:

-   Vim: [julia-vim](<https://github.com/JuliaLang/julia-vim>)
-   Emacs: Julia highlighting is provided via [Emacs Speaks Statistics](<http://ess.r-project.org/>) (ESS) through [this](<https://github.com/emacs-ess/ESS/wiki/Julia>) package.
-   Textmate: a [Julia TextMate Bundle](<https://github.com/WestleyArgentum/Julia.tmbundle>) is available, which includes syntax support and somewhat rudimentary bundle features
-   Sublime Text: [Sublime-IJulia](<https://github.com/quinnj/Sublime-IJulia>) integrates IJulia into Sublime Text - installation is a little complex at this time, but worth it!
-   Notepad++: [Syntax highlighting](<https://gist.github.com/catawbasam/3858496>) is available for Notepad++.
-   Light Table: supports Julia out of the box and with more IDE-like features through [Juno](<http://junolab.org/docs/installing.html>).

There is an application similar to RStudio in the works, called [Julia Studio](<http://forio.com/labs/julia-studio/>), aspiring to be more of a fully-fledged IDE rather than a mere text editor. Unfortunately, at the time of writing, it does not yet support Julia 0.3.


## Ready teddy?

Open up Julia by launching IJulia, opening the Julia app provided with the OS X version or calling Julia from the terminal (usually, julia). You are greeted by the Julia REPL.

    _
    \_ \_ \_(\_)\_ | A fresh approach to technical computing
    (\_) | (\_) (\_) | Documentation: <http://docs.julialang.org>  
    \_ \_ \_| |\_ \_\_ \_ | Type "help()" for help.
    | | | | | |/ \_\` | |
    | |\_| | | | (\_| | | Version 0.3.3 (2014-11-23 20:19 UTC)
    \_/ |\_\_'\_|\_|\_|\_\_'\_| | 'Official <http://julialang.org/> release'
    |\_\_/ | x86\_64-apple-darwin13.3.0
	  
    julia>

Your version may differ, as will the architecture (final line). If you seek help on Julia forums, always be sure to mention what build you have (the final three lines).

Congratulations. Your adventure begins here.
