# HKReport2016
Git repository for the KTH Eco Cars 2016 final report.

# Repo instructions
This heading contains info about the files and folders in the repo.

__EcoCarsReport.txt__: Notes about the reports content and layout.

__Latex/__: The folder containg all Latex code for the project.

__.gitignore__: File telling Git which files to not add to the repo.

# Git quick guide

This is a quick reference to the simplest commands in Git. Pleas see [this](https://www.atlassian.com/git/tutorials/comparing-workflows/centralized-workflow/) guide for further details.

To download this repo, _clone_ the repository.

    $ git clone https://github.com/KTH-EcoCars/HKReport2016.git

This will add the folder to your computer. Before you start coding, always pull the latest changes from the repo.

    $ git pull

After you have done changes, add them to the coming commit.

    $ git add --all

Create the actual commit and add a useful comment.

    $ git commit -m "Write a good message here."

All the changes are still on your computer. Push them to the central repo by writing

    $ git push origin master

Quick tip: You can do several commits on your computer before pushing them to the central repo. The push command will push them all at once.


# Latex instructions
This section contains info about how to write and compile the report.
## Software needed
To write and compile Latex, you can download
[TexMaker](http://www.xm1math.net/texmaker/). You will also need 
[MikTex](http://www.miktex.org/download).
 __Important: Install the correct 64 or 32 bit of MikTex, depending on 
your computer!__

## Report structure
The report uses a modular structure. Each chapter has its own folder that is
then included into _main.tex_. This file is then what is compiled into pdf.

### Folder structure
Each chapter in the main report has its own folder. Latex uses relative
paths to include folders and files, i.e. the path `./` is the path to 
the folder containg the _main.tex_ file. To reach a child folder, the code
`./folder/` is used. The file _chapter.tex_ in the child folder _chapter/_ 
is included into the report via the following code:

```
\include{./chapter/chapter}
```
If you want to include a file into a chapter file, __always use _\input{}_ __,
i.e to include the file _./chapter/subchapter/example.tex_, you write:

```
/input{./chapter/subchapter/example}
```

### Images
All images are put into the folder _./img/_. Always follow the naming scheme 
described below:

1. Prefix all pictures with the name of the chapter in which they are used.
2. Always use informative names.

For example, a picture of Adam playing ice hockey used in chapter _motivation_ 
would be named `./img/motivation_dork_on_skates.jpg`.

Including pictures in the report is done by using the _includegraphics_ command
combined with the _figure_ environment. The syntax of including a picture is:

    \begin{figure}[H]
        \centering
        \label{fig:picturename}
        \includegraphics[width=size\textwidth]{./path/to/picture}
        \caption{Caption text.}
    \end{figure}

It is recommended to use `width=0.5\textwidth`. Using the example picture from
above, one would get:

    \begin{figure}[H]
        \centering
        \label{fig:motivation_dork_on_skates}
        \includegraphics[width=0.5\textwidth]{./img/motivation_dork_on_skates}
        \caption{This is a dork trying to play ice hockey.}
    \end{figure}
    
### Bibliography
The bibliography is the reference list. It uses the Latex library _natbib_. Add
new references to _mainbib.bib_. For more info, check out [this](https://en.wikibooks.org/wiki/LaTeX/Bibliography_Management#BibTeX)
link.

#### Reference format
A reference looks like this

    @type { referenceName,
            author = "Author name",
            title = "Title name",
            year = "2016",
            ...
    }

The available types are given in the table in the previous link. Depending on
the type of citation, some fields must be given. These are available in the table
displayed in the previous link.

#### Making a reference
To make a reference, use the `\cite` command. Example based on the citation
above:

    This is a Latex text. It has been proven that Latex is widely superior to any other word processing program \cite{referenceName}.

## Sections
Latex uses a tiered section system where `\section{}` is above 
`\subsection{}` and that in turn is above `\subsubsection{}`. The `\chapter{}` section is above all of these. 
In this report,`\chapter{}` is reserved for the chapters, the main parts of the report. 
This means that within each seperate chapter, one can use `\section{}, \subsection{}` and `\subsubsection{}`.
This does not apply to appendices, (for now) all appendices sould be in a separate \chapter{}

If you need to include an additional package this should be done in the main.tex file.

