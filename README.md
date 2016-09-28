# HKReport2016
Git repository for the KTH Eco Cars 2016 final report.

# Repo instructions
This heading contains info about the files and folders in the repo.

__EcoCarsReport.txt__: Notes about the reports content and layout.

__Latex/__: The folder containg all Latex code for the project.

__.gitignore__: File telling Git which files to not add to the repo.

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
    
## Sections
Latex uses a tiered section system where `\section{}` is above 
`\subsection{}` and that in turn is above `\subsubsection{}`. In this report,
`\section{}` is reserved for the chapters. This means that within each seperate
chapter, one can use `\subsection{}` and `\subsubsection{}`.

