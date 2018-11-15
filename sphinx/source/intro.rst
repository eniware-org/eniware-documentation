.. _introduction:

1. Introduction
=================


.. _brief-proc:


1.1. Brief description of the documentation process
---------------------------------------------------

1.1.1. Basic steps
^^^^^^^^^^^^^^^^^^

The process of creating documentation is carried out in the following basic steps:

1. **Creating the main source files of the documentation** - the process of generating its content and layout using the **reStructuredText** (reST) format.
2. **Building documentation** – automated creation of static web pages.
3. **Deployment / hosting the documentation** for the given project.

The three main steps can be implemented in different ways depending on the situation (creation of new project documentation; correcting or updating existing project documentation, cloning of documentation, etc.).

The source format of the documentation is based on the **reStructuredText** (reST) format. Basic rules for working with reStructuredText (reST) are discussed in detail :ref:`here <reST-rules>`.

The created source files (**rst-files**) can be processed by the Python documentation system **Sphinx** to generate static web pages and/or pdf-files. Using Sphinx to create documentation is discussed in detail here :ref:`here <extended>`.

The root directory of a Sphinx collection of reStructuredText document sources is called the **source directory**. This directory also contains the Sphinx configuration file **conf.py**, where you can configure all aspects of how Sphinx / Read The Docs reads your sources and builds your documentation (for more information see :ref:`here <conf-py>`).

It is recommended to use either **Eclipse** or **Atom** as an integrated development environment (IDE) for creating rst-files. However, any standard text editor can be used as well (such as **Notepad ++**, **Pluma**, etc.). The process of developing documentation using Eclipse is described in :ref:`Basic Scenario chapter <basic>`, and by using Atom - in :ref:`Alternative Scenario chapter <alternative>`.

The source rst-files of the created documents are intended to be stored on **GitHub repository created for the particular project(s)**.

The documentation can be built locally, after which the documentation can be deployed using GitHub Pages as it is described in :ref:`Extended Scenario chapter <extended>`.

Another considered option is automated building and deployment of the documentation directly from the source rst-files using the interconnection between GitHub repository and Read The Docs platform (see :ref:`Basic Scenario chapter <basic>`).

As an example, the process of :ref:`automatically creating and hosting API documentation <api-doc>` will be considered as well.


1.1.2. Main scenarios
^^^^^^^^^^^^^^^^^^^^^

This guide describes three main scenarios of documentation development:

* :ref:`Basic Scenario <basic>`: Creating, building and deploying Documentation using Eclipse - GitHub - Read The Docs: The source :ref:`rst-files <rest-s>` are created (or cloned) by using :ref:`Eclipse <eclipse-s>` and stored as a project in :ref:`GitHub <github-s>` repository created  for the particular project. The processes of building and deployment are automated by establishing interconnection between GitHub repository and :ref:`Read The Docs <rtd-s>` platform.
* :ref:`Extended Scenario <extended>`: Creating and building documentation using Sphinx / Eclipse - GitHub - GitHub Pages / Read The Docs: The source rst-files are created (or cloned) by using Eclipse. The building process is done locally using :ref:`Sphinx <sphinx-s>` - the created static pages can be viewed and tested locally (and eventually hosted on a random site). The source files are stored as a project in GitHub repository and the static web pages - in special **docs** folder in the same repository. The content of this **docs** folder is hosted by using :ref:`GitHub Pages <git-pages-s>` which is a static site hosting service. At the same time, the source rst-files are built and hosted automatized by the Read The Docs service as in the **Basic Scenario** described above.
* :ref:`Alternative Scenario <alternative>`: Creating and building Documentation using Sphinx / Atom - GitHub - GitHub Pages / Read The Docs: This scenario is the same as the **Expanded Scenario**, but instead of Eclipse as an IDE, an :ref:`Atom <atom-s>` is used.



1.1.3. Comparison of the main scenarios
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
    :header-rows: 0
    :stub-columns: 0

    * - **Type of scenario**
      - **Advantages**
      - **Disadvantages**
      
    * - **Basec Scenario:** 
         Creating, building and deploying Documentation using *Eclipse - GitHub - Read The Docs*
      - - Easy and fast process suitable for quick corrections of existing documentation.
        - Requires a minimal amount of software tools (Eclipse with appropriate plugins only).
        - Requires the smallest storage volume in the GitHub repository (only source rst-files are pushed).
      - - Hard to use when creating the documentation.
        - Lack of sufficient control over the processes.
        - Unable to build if errors occur in the syntax of source rst-files.
        - Documentation can not be built and deployed locally - these processes depend on Read The Docs' external services.
        - Mandatory use of plugins to work with reStructuredText in Eclipse to create the **conf.py** configuration file needed for the documentation build process.
      
    * - **Extended Scenario:**
         Creating and building Documentation using *Sphinx / Eclipse - GitHub - GitHub Pages / Read The Docs*
      - - Suitable for initial documentation creation.
        - Allows locally deployment of documentation for error control and testing purposes.
        - The created static web pages of documentation can be hosted through user-selected services.
        - The created documentation is deployed simultaneously on two different platforms (GitHub Pages and Read The Docs).
      - - Requires additional software - installing Python and Sphinx.
        - Requires more storage space in GitHub repository - stores both source rst-files and build files.
        - When changing source rst-files, both the local files and the build files should be updated in GitHub repository (if using the GitHub Pages service).
      
    * - **Alternative Scenario:**
         Creating and building Documentation using *Sphinx / Atom - GitHub - GitHub Pages / Read The Docs*
      - - Same as in Extended Scenario.
        - For Atom, better plug-ins for work and visualization with reStructuredText are developed.
        - Better integration with GitHub.
      - - Same as in Extended Scenario.






.. _brief-soft:

1.2. Brief description of the used software tools and services
--------------------------------------------------------------

.. _rest-s:

1.2.1. reStructuredText (reST)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`reStructuredText <http://www.sphinx-doc.org/en/master/usage/restructuredtext/index.html>`_ is an easy-to-read, what-you-see-is-what-you-get plaintext markup syntax and parser system. It is useful for in-line program documentation (such as Python docstrings), for quickly creating simple web pages, and for standalone documents. **reStructuredText** is designed for extensibility for specific application domains.
The primary goal of **reStructuredText** is to define and implement a markup syntax for use in Python docstrings and other documentation domains, that is readable and simple, yet powerful enough for non-trivial use. The intended purpose of the markup is the conversion of reStructuredText documents into useful structured data formats.
**reStructuredText** is the default plaintext markup language used by `Sphinx <http://www.sphinx-doc.org>`_.



.. _sphinx-s:

1.2.2. Sphinx
^^^^^^^^^^^^^

`Sphinx <http://www.sphinx-doc.org>`_ is a tool that makes it easy to create intelligent and beautiful documentation, written by Georg Brandl and licensed under the BSD license.
It was originally created for the Python documentation, and it has excellent facilities for the documentation of software projects in a range of languages.

The following features should be highlighted:

* **Output formats:** HTML (including Windows HTML Help), LaTeX (for printable PDF versions), ePub, Texinfo, manual pages, plain text.
* **Extensive cross-references:** semantic markup and automatic links for functions, classes, citations, glossary terms and similar pieces of information.
* **Hierarchical structure:** easy definition of a document tree, with automatic links to siblings, parents and children
* **Automatic indices:** general index as well as a language-specific module indices
* **Code handling:** automatic highlighting using the Pygments highlighter
* **Extensions:** automatic testing of code snippets, inclusion of docstrings from Python modules (API docs), and more
* **Contributed extensions:** more than 50 extensions contributed by users in a second repository; most of them installable from PyPI.

**Sphinx** uses **reStructuredText** as its markup language, and many of its strengths come from the power and straightforwardness of reStructuredText.


.. _eclipse-s:

1.2.3. Eclipse
^^^^^^^^^^^^^^^

`Eclipse <http://www.eclipse.org/>`_ is an integrated development environment (IDE) used in computer programming, and is the most widely used Java IDE. It contains a base workspace and an extensible plug-in system for customizing the environment.
The Eclipse project is composed of three subprojects, Platform, Java development tools (JDT), and Plug-in development environment (PDE). The Eclipse Platform is an open extensible IDE for anything and yet nothing in particular. It allows tool builders to independently develop tools that integrate with other people's tools so seamlessly you can't tell where one tool ends and another starts. The JDT project provides the tool plug-ins that implement a full-featured Java IDE supporting the development of any Java application, providing refactoring support, incremental compilation, smart editing etc. The JDT project allows Eclipse to be a development environment for itself. The PDE project provides the mechanisms that enable the community to build plug-ins for eclipse.


.. _atom-s:

1.2.4. Atom
^^^^^^^^^^^

`Atom <https://atom.io/>`_ is a free and open-source text and source code editor for macOS, Linux, and Microsoft Windows with support for plug-ins written in Node.js, and embedded Git Control, developed by GitHub. Atom is a desktop application built using web technologies. Most of the extending packages have free software licenses and are community-built and maintained. Atom can also be used as an integrated development environment (IDE).
Like most other configurable text editors, Atom enables users to install third-party packages and themes to customize the features and looks of the editor. Packages can be installed, managed and published via Atom's package manager *apm*.



.. _github-s:

1.2.5. GitHub
^^^^^^^^^^^^^

`GitHub Inc. <https://github.com/>`_ is a web-based hosting service for version control using Git. It is mostly used for computer code. It offers all of the distributed version control and source code management (SCM) functionality of Git as well as adding its own features. It provides access control and several collaboration features such as bug tracking, feature requests, task management, and wikis for every project


.. _git-pages-s:

1.2.6. GitHub Pages
^^^^^^^^^^^^^^^^^^^

`GitHub Pages <https://pages.github.com/>`_ is a web hosting service offered by `GitHub <https://github.com/>`_ for hosting static web pages for GitHub users, user blogs, project documentation, or even whole books.
It is integrated with the `Jekyll software <https://jekyllrb.com/>`_ for static web site and blog generation. The Jekyll source pages for a web site can be stored on GitHub as a Git repository, and when the repository is updated the GitHub Pages servers will automatically regenerate the site.
As with the rest of GitHub, it includes both free and paid tiers of service. Web sites generated through this service are hosted either as subdomains of the `github.io <github.io>` domain, or as custom domains bought through a third-party domain name registrar.


.. _rtd-s:

1.2.7. Read The Docs
^^^^^^^^^^^^^^^^^^^^

`Read the Docs <https://readthedocs.org/>`_ is a software documentation hosting platform. The source code is freely available, and the service is also free to use. 
With Read The Docs, users can identify how they want their documentation to be created in either a Python documentation generator **Sphinx** file or a `MkDocs <https://www.mkdocs.org/>`_ Markdown file format. Users enter the GitHub repository name where their project is stored (for example, their open source API project), and Read The Docs will automatically generate and host the documentation at the main `Read the Docs site <https://readthedocs.org/>`_. Having an open source project's documentation shared in the Read The Docs library may also be a way to aid discoverability of the API documentation among the open source community. Additional features are available, including the ability to link Google Analytics to the documentation so that API providers can track engagement, as well as the ability to host the documentation generated a provider's own domain.
One of the main benefits of using Read The Docs is its leverage of a "continuous documentation" mindset. When changes are made to the GitHub repository for the documentation source code, the documentation is automatically updated to reflect those changes. There is also support for versioning so user can build docs from tags and branches of project code in the repository.



1.2.8. Comparison between GitHub Pages and Read The Docs services
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^


.. list-table::
    :widths: 10 50 50
    :header-rows: 0
    :stub-columns: 0

    * - **Features**
      - **GitHub Pages**
      - **Read The Docs**
      
    * - **Integration** 
      - - GitHub Pages is a web hosting service offered by GitHub
      - - GitHub integration through the use of `webhooks and webhook integrations <https://docs.readthedocs.io/en/latest/webhooks.html>`_.
       
    * - **License**
      - - Supports different `types of licenses <https://help.github.com/articles/licensing-a-repository/>`_. 
      - - Read the Docs is Open Source software (MIT License). Free for public repositories. Free documentation hosting for open source projects.
       
    * - **Security**
      - - `HTTPS support <https://help.github.com/articles/what-is-github-pages/#guidelines-for-using-github-pages>`_.
      - - HTTPS support.
       
    * - **Domain**
      - - *https://organization-name.github.io/project-name/*
        - `Custom domain <https://help.github.com/articles/user-organization-and-project-pages/>`_ with GitHub Pages is available.
      - - *https://name-of-project.readthedocs.io*
        - Support for custom domains, subdomains, and a shorturl.
         
    * - **Versioning**
      - - With GitHub pages this will have to be done manually, but can be better integrated into the theme.
      - - Multiple versions of documentation. Read The Docs automates this, but versioning doesn't integrate well with the page theme except for `RTD theme <https://pypi.org/project/sphinx_rtd_theme/>`_. However the latter has major usability issues.
        
    * - **Compatiblity**
      - - GitHub Pages don't interfere with Sphinx build process.
      - - Read The Docs interferes with Sphinx builds breaking some of the features (possibly due to their customizations).
       
    * - **Access**
      - - GitHub Pages sites are `always publicly accessible when published <https://help.github.com/articles/what-is-github-pages/>`_, even if their repository is private. 
      - - `Different Privacy levels <https://docs.readthedocs.io/en/latest/privacy.html>`_ - 3 different privacy levels on 2 different objects: *Public*, *Protected*, *Private* on *Projects* and *Versions*.
      
    * - **Reliability**
      - - Didn't notice any issues with GitHub pages so far.
      - - Read The Docs builds can remain broken for long periods without a way to cancel them.
       
    * - **Specific features**
      - Nothing specifically related to the documentation process itself.
      - - Multiple formats support – the documentation is built and hosted for the web, but it is also vieweable as PDFs, as single page HTML, and for eReaders. No additional configuration is required.
        - Localization of Documentation and Internationalization pages.
        
    * - **Limitations**
      - GitHub Pages sites are subject to the following usage `limits <https://help.github.com/articles/what-is-github-pages/#usage-limits>`_:
         - GitHub Pages source repositories have a recommended limit of 1GB .
         - Strict limit of files exceeding 100 MB in size
         - Published GitHub Pages sites may be no larger than 1 GB.
         - GitHub Pages sites have a soft bandwidth limit of 100GB per month.
         - GitHub Pages sites have a soft limit of 10 builds per hour.
      - Every documentation build has `limited resources <https://docs.readthedocs.io/en/latest/builds.html?highlight=limitations>`_. The current build limits are: 
         - 15 minutes
         - 1 GB of memory

