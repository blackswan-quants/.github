This documentation aims to be a guideline for new programmers in the Quantitative Finance Division at Starting Finance Polimi club. In this document, the following topics will be covered:

- How much you should know about python.
- What code editor to use, how to collaborate with teammates using Github.
- How to use Git, gitignore, venv, in order to make coding cleaner and more efficient.
- How to plan for a project, and write correct documentation for it.

**Huge disclaimer**: This is my personal opinion about the entire process I recommend to people using Python on Windows, it's based on the methods and dynamics we've experimented in the club, and here you'll find the strategies that came out as the best ones. 

# Prerequisites

## Programming language

The programming language chosen to be used for the projects of the club is **Python**. 

The concepts necessary to proceed as a programmer in the club, in terms of knowledge, are:

1. **Data Structures**: Lists, tuples, dictionaries, sets, strings
2. **Control Structures**: If statements, loops (for and while)
3. **Functions**: Defining functions, parameters and arguments, returning values, lambda functions
4. **Object-Oriented Programming (OOP)**: Classes and objects, inheritance, encapsulation, polymorphism
5. **Exception Handling**: Try-except blocks, raising exceptions, handling specific exception types, custom exception classes
6. **File Handling**: Opening and closing files, reading and writing files, file modes, working with different file formats
7. **Modules and Packages**: Creating and importing modules, organizing code into packages, using third-party libraries
8. **Functional Programming**: Lambda functions, map, filter, and reduce, list comprehensions, generators and iterators
9. **Concurrency and Parallelism**: Threading, multiprocessing, asynchronous programming (asyncio), concurrent programming libraries
10. **Regular Expressions**: Syntax and patterns, searching and matching text, substitution and manipulation
11. **Testing and Debugging**: Writing unit tests (unittest/pytest), debugging techniques, logging and error handling
12. **Documentation and Code Style**: Writing clear code, using meaningful variable and function names, writing docstrings and comments, following PEP 8 style guidelines
13. **Advanced Topics**: Metaprogramming, decorators, context managers, iterators and generators, descriptors

In case one is to intelligently decide to indulge themselves in some revising, here is a [link](https://www.freecodecamp.org/news/learn-python-free-python-courses-for-beginners/) for some resources.

# How do we operate?

## Code editor and collaboration

The recommended code editor is [VSCODE](https://code.visualstudio.com/), which allows you to make sure the code you write is sent to your personal online branch (more on that on the third chapter) directly from the editor.

Now let's get talking about collaborating with the other programmers: _drumsounds_ enters Github. Strap up and follow along:

- You get into the club, congratulations.
- You receive on your email, an invitation to the Organization on Github. Accept it, and you'll be granted access to all the repositories of the projects made by programmers in the QF Division, yay.

Now, you'll be facing a two possible ways of proceeding: the red pill of Terminal, or the blue pill of Github Desktop. I will tell you how to set up both ways.

#### Github Desktop and it's shortlived easy personality,

- install Github Desktop.
- The heads will assign you to a project. You will find the project's repository in the 'Repositories' section. Click on it.
- See the big green button written 'code'? Click on it. Now, click on 'Open with github desktop'. You will be redirected to the app, which, if you followed me, is now installed.
- Moving on, the app will allow you to clone the repository. Do that, and now you have a local copy of the repository, in your beautiful computer, which will be the one VSCODE will open whenever you decide to ruin the Head of Software Engineering's day by coding something.


#### or Terminal, the hero we didn't know we needed

It can seem painful at first, but in the long term, it is the best way to proceed. Maybe I'm biased, but oh well. If you want a detailed tutorial of how to 1. clone, commit into github using terminal and vscode and 2. how to set up a venv and some other cool-programmer-things, which please, do that, read this [gist](https://gist.github.com/Maarrk/961d8dc94b283cffa3fdd99dffd5e055). If you follow the whole thing, you can skip steps 1, 2, 3 of the following chapter! 

Either you picked the red or blue pill, you arrived at this point, where you set up your branch and commit online:

---

Before you do anything, some theory: branches. See them as your personal version of the code, and the things you write there, stay between you and God. Now that you have the repository open on Github Desktop or Github Site, you want to click on the top middle 'branch' and 'add', where you will add a branch that is all yours to keep. Now that you have your branch selected, you can open  Visual Studio Code, and access it by clickling on the lower left button, changing it from 'main' to 'yourbranchname'.

---

- Now, fast-forwarding in time, say you code real good and you're confident the code can be added **to the main and latest version of the script everyone is working on**, well, first of all, that's very presumptuous of you; second of all, you will, in Vscode, COMMIT the changes and SYNC.
- Open Github (Desktop OR Online) and request a PULL REQUEST. Write a cute message (more on that on third chapter), put a bow on it, and send. The head of Software Engineering (they're the only ones with the permission to do so) will allow your changes by MERGING it into the main branch. Congrats, you just contributed to the projects.

# How to Structure a Project for Reproducibility and Maintainability

Some concepts to know:

### 1. Directory Structure:

- **Root Directory**: Contains main project files and documentation.
- **src/**: Source code directory.
- **docs/**: Documentation directory.
- **venv/**: Virtual environment directory (created using `venv` or `virtualenv`).
- **requirements.txt**: File containing project dependencies.

### 2. Virtual Environment:

- Use virtual environments (`venv` or `virtualenv`) to manage project dependencies.
- Create a virtual environment in the project directory (taken from [Gist](https://gist.github.com/Maarrk/961d8dc94b283cffa3fdd99dffd5e055)):

_"Create the virtual environment in the venv folder, wait a moment for it to complete. When VS Code asks you if you want to select it as the interpreter for the folder, click “Yes”._

```
python -m venv venv
```

_When you open the terminal, see if the prompt (the line before you type your command) starts with (venv). If it doesn’t, type av and press Enter - this will run .\venv\Scripts\Activate.ps1 for you because of the alias we set up earlier._

_When you have the venv active and only then you can use pip command to install packages for this project, for example you should install formatter in every project:_

```
pip install autopep8
```

_When you have a .py file open in VS Code, make sure the section with Python version in bottom right part of the window is showing “venv”. If it doesn’t, click there (or run “Python: Select Interpreter”) command and choose the “venv”. This will ensure that the code analysis takes into account the packages you installed for the project, and will also activate the venv for you whenever you open a new terminal."_

### 3. Dependency Management:

#### Gitignore file

_In a properly set up repository, the venv folder should be gray in the explorer view on the left, indicating that Git will ignore changes inside it. If the folder is shown in the changes list in “Version Control” view, then you should add a line venv to the .gitignore file if it exists._

_If the .gitignore file doesn’t exist, I strongly recommend https://www.toptal.com/developers/gitignore/ page. Put all the languages you use in the search field (in this case just Python), click “Create”, and then paste the entire page (Ctrl+A then Ctrl+C) into a .gitignore file you create in VS Code._

#### Installing packages from list

_If there is a file called requirements.txt, someone has saved for you what the project needs to run. Make sure you have venv active, and run the following (just type up to req and use Tab-completion):_

```
pip install -r requirements.txt
```

#### Saving used packages

_"When you know you have a set of packages that is needed for the project to run, you can run the following to put them into a file for everyone (as usual, don’t touch pip without (venv), save the unicorns)._

```
pip freeze > requirements.txt
```

_If the file already exists, it will be overwritten with everything you have installed and available with currently used pip. This is the main reason we use venv at all, to make sure you save what you need, no more no less."_

### 4. Version Control:

Use a version control system like Git, our golden boy.**Please** for the sake of the Head, write clear and descriptive commit messages following conventions like [Conventional Commits](https://www.conventionalcommits.org/).
And, most importantly, **never merge directly into main/master branch, use feature branches and pull requests instead.**

### 5. Documentation:

Maintain comprehensive documentation in the `docs/` directory, using tools like Sphinx for generating documentation from docstrings. Include installation instructions, usage guides, and API references.

### 6. Project Structure:

Keep the project structure organized and modular. Divide code into logical modules and packages. Follow a consistent naming convention for files and directories.

By following these guidelines, you can ensure that your project is reproducible, maintainable, and conducive to collaboration.

# Project Planning

All projects must have a extensive and clear documentation attached to it, to which all programmers have access. The reason behind doing so is to guarantee clear information and traciability of the steps needed to the conclusion of the projects.

Before any project is started, three documents must be written; either by the Heads, or by the person assigned as main author:

- **Overall documentation** with details on goals of the project, output expected, literature used, libraries and APIs selected, and a detailed roadmap.
- A **prototype** of the project, in which a project of smaller dimensions would be developed by all programmers involved, but still relevant and representative of the functionalities expected from the official model. The decision to dedicate time to this phase is primarily motivated by two convictions: this week would serve as an evaluation phase, where roles would be defined, concepts officially studied. This would allow everyone to decide whether they are actually interested in the project or not, learn the synergies between members, and provide a tutorial on methods and models; the second conviction is, above all, because in the reality of software and product development, the strategy that involves omitting prototyping and iterations (known as "Waterfall") has proven to be ineffective. Currently, the most widespread strategy is Agile, but it often proves too demanding given the limited time availability of the members. Therefore, the prototyping phase would be a compromise, with the expectation of emerging more aware of the development phases, more experienced in the topics, and with the ability to avoid initial mistakes, thus preventing the so-called "technical debt".
- **A precise timeline** that keeps tracks of macrophases and dependencies. The recommended framework is a **Gantt chart** made as a byproduct of an effective study of the time needed to conclude every task and the dependencies among them (example of how to calculate so: [CPM](https://www.pmcalculators.com/critical-path-method-calculator/)). You can make a very pretty and versatile Gantt chart using [Mermaid](https://www.mermaidchart.com/product).

Once done and presented, the documentation is to be added to the repository of the project. Ideally, the prototype file will also be in such repository.
