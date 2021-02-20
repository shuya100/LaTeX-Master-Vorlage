# LaTeX-Master-Vorlage

This is a forked English version of a-czyrny's [LaTeX-Master-Vorlage](https://github.com/a-czyrny/LaTeX-Master-Vorlage).

---
The Latex Master template can be used optimally for research projects, bachelor and master theses. Necessary packages are already included and settings are made. 

This [original LaTeX template](https://github.com/a-czyrny/LaTeX-Master-Vorlage) has already been used for master theses at the University of Applied Sciences Berlin (HTW Berlin), department 4.

If this template has been used for your thesis (or research project), please write the professor/examiner below to the list. 


# Example

[see PDF](main.pdf)

# Use

In order to use this template, the required software must be installed. Once this is the case, the template can be downloaded and customized.

## Recommended environment
The template has been successfully compiled under the [TEX Live](http://tug.org/texlive/) environment using the following programs.

- **Compiler**: lualatex
- **Bibliography**: biber
- **Index**: makeindex (note additions under comments)
- **glossary**: makeglossaries

## Installing the required software
### Windows
**Required software:**

* MikTex
* TexStudio

**Optional software:**

* ``git`` (for cloning and contributing)
* ``perl`` (for ``latexmk``)
* ``latexmk`` (via MikTex)

### Linux (tested with Debian Jessie)
**Required software:**

* wget (``apt-get -y install wget``)
* texlive (``apt-get -y install texlive``)
* texlive packages:
        wget http://mirror.ctan.org/systems/texlive/tlnet/install-tl-unx.tar.gz &&\
        tar -xzvf install-tl-unx.tar.gz &&\
        rm install-tl-unx.tar.gz
        echo I | install-tl*/install-tl
* Add packages to path
        PATH=/usr/local/texlive/2015/bin/x86_64-linux:$PATH    
* More settings:
        tlmgr conf texmf TEXMFHOME "/usr/local/texlive/2015/bin/x86_64-linux"

**Optional software:**

* ``git`` (for cloning and contributing)
* ``perl`` (for ``latexmk``)
* ``latexmk`` (via MikTex)

### MacOS (tested by Shuya Fuchigami)
**Required software:**
* [TEX Live](https://tug.org/mactex/)
* TexStudio

**Optional Software:**

* ``git`` (for cloning and contributing)
* ``homebrew`` (for installation)

## Downloading the LaTeX files
The template can be downloaded either with ```git clone https://github.com/a-czyrny/LaTeX-Master-Vorlage.git`` (see optional software) or with via the GitHub page as *.zip file.

## Editing and compiling the LaTeX files
### Windows
On **Windows**, [TexStudio](http://www.texstudio.org/) is the recommended editor.

If the default settings of TexStudio are used, two manual steps still have to be done:
1. the references for the glossary and the list of abbreviations have to be created. In the command line in the folder of the template:

    makeindex -s main.ist -t main.alg -o main.acr main.acn
    makeindex -s main.ist -t main.glg -o main.gls main.glo 

2. the LaTeX document must be compiled twice (``F5``) to resolve all references.

**Alternative** 

If ``latexmk`` has been installed (see optional software), ``latexmk`` can also be specified as default compiler in TexStudio under "Options / Configure TexStudio / Generate".
``latexmk`` will then also work from the command line
 
### Linux
Under **Linux** the template can be edited with the text editor of choice. For compiling you can use ``lualatex``:

    lualatex -synctex=1 -interaction=nonstopmode main
    biber main
    makeindex main
    makeindex -s main.ist -t main.alg -o main.acr main.acn
    makeindex -s main.ist -t main.glg -o main.gls main.glo
    lualatex -synctex=1 -interaction=nonstopmode main
    lualatex -synctex=1 -interaction=nonstopmode main
    
**Alternative**
If ``latexmk`` has been installed (see optional software), ``latexmk`` can also be specified in the directory. This will perform the above steps.
    

  
# Notes
## Index
To generate the glossary and abbreviation index, "makeinxed" must be called as follows:

*makeindex -s main.ist -t main.glg -o main.gls main.glo*

*makeindex -s main.ist -t main.alg -o main.acr main.acn*

The title in the header of the page must also be adjusted in the style file "[indexstyle.ist](indexstyle.ist)":

see: preamble "\\\markboth{**STICHWORTVERZEICHNIS**}{}\n\n\\begin{theindex}\n"

# Which professors/examiners have already approved papers with this template?
* Prof. Dr. Fortenbacher, master thesis


## Lizenz
[Attribution-NonCommercial-ShareAlike 4.0 International](https://creativecommons.org/licenses/by-nc-sa/4.0?ref=chooser-v1)