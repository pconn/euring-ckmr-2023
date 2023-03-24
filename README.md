# euring-ckmr-2023

Welcome to the Github repository for a short 3 hour course on CKMR by Paul Conn conducted at the
Euring 2023 technical meeting in Montpellier, France.  Much of the material
is derived from a full day course put on by Paul and Eric C. Anderson at the 2022 
Wildlife Society Meeting, and most of the clever Bookdown/Quarto/Github actions
stuff was originally put together by Eric.

Lab materials are
produced by this repository as a [bookdown](https://bookdown.org/)
document, and all the materials to generate it can be found in this
repository, which is, itself, an RStudio project.

You can render the bookdown document by cloning this repository
and then building the book with the "Build Book" button under the
RStudio "Build" panel, for example.  

The version of the bookdown document that appears online at
[https://pconn.github.io/euring-ckmr-2023/](https://pconn.github.io/euring-ckmr-2023/)
is generated from these source files; however, the actual rendering is done
via GitHub Actions.  

Slides for the workshop (the primary observed content) were put together with Quarto,
and are also available for viewing online at [https://pconn.github.io/euring-ckmr-2023/slides/slides.html](https://pconn.github.io/euring-ckmr-2023/slides/slides.html)

This repository is using the 'renv' package to manage all the package dependencies.
This should, in theory, make it relatively straightforward to get the same versions
of all the packages, etc., so that we will have a decent chance that this will
work on new computers, etc.

In order to clone the repository and get the packages so you can build this
book and run all the examples in it, here are the steps:

1. clone this repository.  If you are one of the authors, and expect to be pushing changes back to the repository, you will need to have an SSH key with GitHub and clone the repo via the ssh protocol, like this:

    ```sh
    git clone git@github.com:pconn/euring-ckmr-2023.git
    ```

2. open the repository with RStudio.  If you are working on a Mac, this
is easily done from the command line in the directory where the `git clone`
command was given, like this:

    ```sh
    open euring-ckmr-2023/euring-ckmr-2023.Rproj
    ```
    When Rstudio opens this way, you should get some messages about not
    having certain packages, and you should see in the R console that you
    need to restore the project package library with `renv::restore()`.

3. So, the next step is to issue this command in the R console of the project:

    ```r
    renv::restore()
    ```
    When you do this, you will be shown a long list of packages that
    will need to be updated.  Go ahead and respond "y" to the question of
    whether you want these updated or not.  If you already have these versions,
    it seems that `renv` will link to them.  If you these versions are different
    from the ones you have, `renv` should
    download them and store them locally in the repository, I hope.  In other
    words, it should not overwrite any existing packages in your normal
    R library tree.   You will need a compilation toolchain (RTools on Windows
    and the Developer tools on Mac OS) in order to install some of the tools.



4. After you have done this, quit the RStudio project, and then reopen it.
After you have done this, the "Build" panel in RStudio should have a "Build Book"
button.  Click on that.  RStudio will likely tell you it needs a new version
of a markdown-related package.  Say "Yes" to installing that.  The book should
get built and previewed in a window for you.  When it is done, you can also
get to the book by opening `_book/index.html` in a browser.


5. If you are an author, and have added any .Rmd files or edited any of them, you
don't have to commit the rendered files in the `_book` directory.  Just build the book
to make sure it works, and then commit the edited source files and push them
back to GitHub.  Then you can go to
[https://github.com/eriqande/tws-ckmr-2022/actions](https://github.com/eriqande/tws-ckmr-2022/actions)
to check up on progress that GitHub actions is making on producing the
rendered version of the updated book.




