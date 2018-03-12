
| Author            | Gavin Venters     | Version     | 1.0              | Status | Draft |
|-------------------|-------------------|-------------|------------------|--------|-------|
| Date Issued       | 22 September 2017 | Valid until | 30 November 2017 |
| Product Reference | CMMV\_1\_2017     | Type        | Discussion Paper |
| Location          | tba               |
| Comments To       | GV gavin@nhs.net  |

<span id="_Toc349038167" class="anchor"><span id="_Toc350177024" class="anchor"><span id="_Toc350181013" class="anchor"></span></span></span>Definitions, Acronyms and Abbreviations
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

|                                                                                        |
|----------------------------------------------------------------------------------------|
| <span id="_Toc333842861" class="anchor"></span>Definitions, Acronyms and Abbreviations |
| Term                                                                                   |
| CMVC                                                                                   |
| Branch                                                                                 |
| Release                                                                                |
| Merge                                                                                  |
| Codebase                                                                               |
| Fork                                                                                   |
| Trunk                                                                                  |
| Repository                                                                             |
| Commit                                                                                 |
| Changesets                                                                             |
| CLA                                                                                    |

**  
**

Table of Contents

Document Control Summary 1

1 Introduction 3

2 Version Control Systems (VCS) 4

3 Version Control Tools and Hosting Services 5

4 VC Use cases 6

5 Current Position In NSS (and NHSS) 7

6 Demand management 7

7 Recommendations 8

8 Next steps 9

Appendix A Draft Service Definition 10

Appendix B References 12

Appendix C Hosting Services 13

9 Document Control 14

<span id="_Toc350177023" class="anchor"><span id="_Toc350181012" class="anchor"><span id="_Toc222039290" class="anchor"><span id="_Toc348984032" class="anchor"><span id="_Toc493843959" class="anchor"></span></span></span></span></span>Introduction
=======================================================================================================================================================================================================================================================

> > Configuration Management serves to ensure that as-built
> > configurations conform to their “documented requirements and are
> > built to the correct versions of those documents.“ \[1\]

Configuration management and version control (CMVC) is a key activity
for the production of software \[2\]. Software developers need a way of
making sure that the software they produce is packaged consistently so
that every consumer of a given version of a product (often referred to
as a *release*) gets exactly the same thing. Without management of the
changes to a codebase, proper release management is not possible.

Configuration management and version is essential to be able to confirm
that customer requirements are reflected in delivered code, to properly
track bugs and issues and to support the product once installed. Audit
and change management activities are also unmanageable without
appropriate configuration control.

Tools for configuration management have been divided into three
categories:

-   Defect, enhancement, issue, and problem-tracking tools. These tools
    are used in connection with the problem-tracking issues associated
    with a particular software product.

-   Version control and management tools. These tools are involved in
    the management of multiple versions of a product.

-   Release and build tools. These tools are used to manage the tasks of
    software release and build. The category includes installation tools
    which have become widely used for configuring the installation of
    software products.

Used in combination, these types of tool support models of continuous
change, integration and deployment of releases so that improvements can
be distributed to users much more regularly.

This paper focuses particularly on version control and management tools,
though many of the VC hosting services considered contain additional
features relating to the other categories of CMVC.

Version Control Systems (VCS)
=============================

In addition to their role in packaging up releases, CMVC tools support
the day-to-day workflows of coding. Software development at any scale
involving more than one developer is very much a collaborative
production. CMVC tools support this collaboration, allowing multiple
people to work on the same codebase, synchronising their work and
managing potential conflicts when more than one person is working on the
same file at one time.

> *In its simplest form, a version control system provides a basic
> principle and method of storing files and changes done to them. This
> is achieved by using a repository. The repository contains the most
> recent version of each file and the change history that has led to
> that representation. Usually every change includes additional
> information such as the author and short description.* \[3\]

There are two main models of version control system, centralised and
distributed. \[4\] In centralised models, there is typically a single
repository for each project. Developers check-out files from this
source, work on them and then commit the changes back into the
repository.

Fig1. Centralised version control

In distributed VCS, contributors download their own complete copy of the
(master) repository and works on it locally. Changes are merged back
together to create the new master copy. Rights to merge with the master
codebase are controlled – in e.g. Git, users who do not have rights to
merge their commits into the master copy can generate a pull request
which is a request to the repository maintainer to *pull* their changes
into the master copy.

Fig2. Distributed version control

Although both styles of VCS offer the same basic functionalities,
distributed models are typically seen as being more open to
contributions across (and outside of) organisational boundaries.

Version Control Tools and Hosting Services
==========================================

The most popular version control systems are Git \[17\],
Subversion(SVN)\[18\] and Mercurial (Hg) \[19\], all three of which are
currently used within \[---content removed -------\]. (There is also
some code stored in CVS which may be considered legacy and residual use
of MS TFVC \[20\] which is being replaced by use of Git.) Of the three
main systems, Git is currently the most widely used and supported \[21\]
(see also appendix A).

Git and Hg are distributed version control systems, while SVN, TFVC and
CVS are centralised systems. Facilities, capabilities and system command
sets in Git, SVN and mercurial are broadly equivalent and all three are
open source which means they can be used without licencing costs. All of
the systems mentioned above can be run in an on-premises setting on
freely downloadable server software. \[---content removed -------\]

A distinction must be made however, between *version control systems*
and *version control hosting services*. Version control hosting services
\[22\] are facilities that provide for the hosting of source code
repositories. Examples in use include GitHub, BitBucket, GitLab,
Perforce, Sourceforge, Codeplex and Visualstudio Team Services. Although
in some cases (e.g. GitLab) these are available as an on-premises
option, typically they are offered through Software as as Services
(SaaS). Because the generic activity of repository management is broadly
the same across VC systems, hosting services tend to support more than
one system. For example, Github has support for SVN and Hg as well as
Git itself (see table in Appendix B for systems supported by a range of
hosting services).

Hosting services typically also offer a range of supporting tools such
as automated build and integration tools, bug and issue tracking, code
review and monitoring.

Pricing models
--------------

Pricing models for these services vary, but there is a often a
distinction made between public (where anyone has potential access to
download – though not to submit back) and private (which are not visible
to unauthorised users). Github and bitbucket, for example, do not charge
for public repositories, but do charge for private ones (on a per user
basis). Team foundation server and visual studio team services are may
have licencing included with MSDN and as such may not incur additional
cost for users of Visual Studio development tools.

VC Use cases
============

> *The open nature of the site facilitates collaborations and
> connections. An interested viewer can watch (sign up for notifications
> of changes), star (mark as favourite), and fork a repository; these
> metrics are like citation counts for code. For programmers, GitHub
> accounts function as résumés, too, complete with these built-in
> commendations from their peers. \[7\]*

The most widely known use-case for version control systems is software
development. However, requirements for version control and collaborative
working is common across many areas and there are examples for systems
being used for collaborative development of legal documents \[14\],
books \[23\], technical documentation, creation of data sets \[25\] and
government policy development \[13, 16\]. Librarians can use the
information in repositories as a solution to archival and digital
preservation \[7\] Github has been described as a combination of social
network and collaborative platform \[10\].

Increasingly, contribution to, or ownership of repositories is used as a
proxy measure of developer expertise \[28\] and the extent to which an
organisation is digital \[27\].

There are numerous precedents of public sector organisations using
Github for open development practice (see table below) – this “coding in
the open” \[26\] approach fits with the Digital First Service Standard
mandate for digital services \[27\].

| **                                   
 **Organisation                        | Url                                             | Public Repositories available |
|--------------------------------------|-------------------------------------------------|-------------------------------|
| Scottish Government                  | <https://github.com/scottishgovernment>         | 17                            |
| U.S. General Services Administration | <https://github.com/GSA>                        | 369                           |
| East Sussex County Council           | <https://github.com/east-sussex-county-council> | 89                            |
| 18F                                  | <https://github.com/18F>                        | 929                           |
| NHS (E)                              | <https://github.com/nhsuk>                      | 82                            |
| GDS                                  | <https://github.com/alphagov>                   | 653                           |
| SCVO                                 | <https://github.com/scvodigital>                | 10                            |

\[---content removed -------\]

References
==========

Google trends comparison of version control systems

<img src="./media/image3.png" width="601" height="234" />

Publications search results on Safari books

3342 search results for git

1772 search results for svn

916 search results for mercurial

Hosting Services 
=================

Indicative costs per user per month are given below for a number of repo
hosting services. Additional features (e.g. HA, DR and backup may incur
additional costs.)

| **                   
 **System              | Private/Public   | Git | SVN | Mercurial    | Support for MFA | Cost per seat p.m.\*    |
|----------------------|------------------|-----|-----|--------------|-----------------|-------------------------|
| Github               | Both             |    |    |             |                | £9 - £20                |
| BitBucket            | Both             |    |    | (via plugin) |                | £2-£5                   |
| Perforce (Helix)     | Both + on-prem   |    |    |             |                 |                         |
| Sourceforge          | Open source only |    |    |             |                 | n/a                     |
| GitLab               | Both + on-prem   |    |     |              |                | £0-£3-£17               |
| Codebase             | private          |    |    |             |                 | £9-£59\*\*              |
| Beanstalk            | Private          |    |     |             |                 | £1 - £3                 |
| Visual Studio Online | Public/Private   |    |     |              |                 | Rights to use with MSDN |
| Kiln                 | Private          |    |    |              |                 | £4-£2                   |
| XP-DEV               |                  |    |    |             |                 | £5-£100\*\*             |
| Unfuddle             |                  |    |     |             |                 | £2 - £5                 |

\* Use of public repos may not have a cost, cost given is for private
repos.

\*\* Cost based on storage rather than user numbers £5 p.m. for 2Gb,
£100 for 90Gb

See also:
<https://en.wikipedia.org/wiki/Comparison_of_source_code_hosting_facilities>

1.  <span id="_Toc350181035" class="anchor"><span id="_Toc493843970" class="anchor"></span></span>Document Control
    ==============================================================================================================

    1.  <span id="_Toc219882829" class="anchor"><span id="_Toc222039291" class="anchor"><span id="_Toc348984033" class="anchor"><span id="_Toc350181036" class="anchor"></span></span></span></span>Document history
        ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

| **        
 **Version  | Date       | Details of Changes included in update |
|-----------|------------|---------------------------------------|
| 1.0       | 22/09/2017 | First draft for comment.              |
| 1.1       | tbd        | Fixed references                      |
|           |            |                                       |

<span id="_Toc219882830" class="anchor"><span id="_Toc222039292" class="anchor"><span id="_Toc348984034" class="anchor"><span id="_Toc350181037" class="anchor"></span></span></span></span>References
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

|                                                                                                                                                                                                 |                                                                                                                                                                                                                                                                                       |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span id="_Toc219882832" class="anchor"><span id="_Toc222039294" class="anchor"><span id="_Toc348984035" class="anchor"><span id="_Toc350181038" class="anchor"></span></span></span></span>Ref | Title                                                                                                                                                                                                                                                                                 |
| 1.                                                                                                                                                                                              | IpX (formerly Institute of Configuraion Management) https://icmhq.com/                                                                                                                                                                                                                |
| 2                                                                                                                                                                                               | SWEBOK 3.0                                                                                                                                                                                                                                                                            |
| 3                                                                                                                                                                                               | EIA-649B Configuration Management Standard                                                                                                                                                                                                                                            |
| 4                                                                                                                                                                                               | Seppänen, Vili. "Open Source Version Control Software." (2015).                                                                                                                                                                                                                       |
| 5                                                                                                                                                                                               | Collins-Sussman B., Fitzpatrick, B. W., Pilato C. M., (2011), Version Control with Subversion, <http://svnbook.red-bean.com/en/1.7/svn-book.pdf>                                                                                                                                      |
| 5                                                                                                                                                                                               | https://en.wikipedia.org/wiki/Version\_control                                                                                                                                                                                                                                        |
| 6                                                                                                                                                                                               | Vasilescu, B., Schuylenburg, S. v., Wulms, J., Serebrenik, A., & Brand, M. v. (2014). Continuous Integration in a Social-Coding World: Empirical Evidence from GitHub. arXiv: Software Engineering, 401-405. Retrieved 10 09 2017, from http://dl.acm.org/citation.cfm?id=2706118     |
| 7                                                                                                                                                                                               | Davis, R. C. (2015). Git and GitHub for Librarians. Behavioral & Social Sciences Librarian, 34(3), 158-164. Retrieved 9 8, 2017, from <http://academicworks.cuny.edu/cgi/viewcontent.cgi?article=1034&context=jj_pubs>                                                                |
| 8                                                                                                                                                                                               | https://en.wikipedia.org/wiki/Branching\_(version\_control)                                                                                                                                                                                                                           |
| 9                                                                                                                                                                                               | Mergel, I. (2014). Introducing Open Collaboration in the Public Sector: The Case of Social Coding on Github. Retrieved 9 8, 2017, from <http://papers.ssrn.com/abstract=2497204>                                                                                                      |
| 10                                                                                                                                                                                              | Lima, A., Rossi, L., & Musolesi, M. (2014). Coding Together at Scale: GitHub as a Collaborative Social Network. arXiv: Social and Information Networks. Retrieved 08 09, 2017, from <http://dblp.uni-trier.de/db/journals/corr/corr1407.html> (via) <https://arxiv.org/abs/1407.2535> |
| 11                                                                                                                                                                                              | Lanubile, Filippo, et al. "Collaboration tools for global software engineering." IEEE software 27.2 (2010).                                                                                                                                                                           |
| 12                                                                                                                                                                                              | IEEE 1042-1987 IEEE Guide to Software configuration management                                                                                                                                                                                                                        |
| 13                                                                                                                                                                                              | alter B., (2015), Four characteristics of modern collaboration tools <https://ben.balter.com/2015/11/18/tools-to-empower-open-collaboration/>                                                                                                                                         |
| 14                                                                                                                                                                                              | <https://blog.abevoelker.com/gitlaw-github-for-laws-and-legal-documents-a-tourniquet-for-american-liberty/>                                                                                                                                                                           |
| 15                                                                                                                                                                                              | <https://readwrite.com/2013/11/08/seven-ways-to-use-github-that-arent-coding/>                                                                                                                                                                                                        |
| 16                                                                                                                                                                                              | McMillan, R. (2013), “Now You Can Fork U.S. Government Policy ... On GitHub” <https://www.wired.com/2013/05/opendata/> Retrieved 14/09/2017                                                                                                                                           |
| 17                                                                                                                                                                                              | Git –everything-is-local <https://git-scm.com/> Retrieved 14/09/2017                                                                                                                                                                                                                  |
| 18                                                                                                                                                                                              | Collins-Sussman B, Fitzpatrick W. F., Pilato CM., (2011) Version Control wth Subversion Michael Pilato <http://svnbook.red-bean.com/> Retrieved 10/09/2017                                                                                                                            |
| 19                                                                                                                                                                                              | Mercurial source control management <https://www.mercurial-scm.org/> Retrieved 14/09/2017                                                                                                                                                                                             |
| 20                                                                                                                                                                                              | Microsoft (2017), Choosing the right version control for your project <https://docs.microsoft.com/en-us/vsts/tfvc/comparison-git-tfvc> Retrieved 12/09/2017                                                                                                                           |
| 21                                                                                                                                                                                              | RhodeCode (2017) Version Control Systems Popularity in 2016 [https://rhodecode.com/insights/version-control-systems-2016](https://rhodecode.com/insights/version-control-systems-2016Retrieved%2020/09/2017) Retrieved 20/09/2017                                                     |
| 22                                                                                                                                                                                              | Wikipedia, (2017) Comparison of source code hosting facilities [https://en.wikipedia.org/wiki/Comparison\_of\_source\_code\_hosting\_facilities retrieved 17/09/2017](https://en.wikipedia.org/wiki/Comparison_of_source_code_hosting_facilities%20retrieved%2017/09/2017)            |
| 23                                                                                                                                                                                              | Five College Consortium., “Digital Preservation: A Planning Guide for the Five Colleges,” <https://www.fivecolleges.edu/libraries/digital-preservation/digital-preservation-a-guide-for-the-five-colleges> Retrieved 20/09/2017 .                                                     |
| 24                                                                                                                                                                                              | Pessé, S, How to Make a Computer Operating System in C++, GitHub, <https://github.com/SamyPesse/How-to-Make-a-Computer-Operating-System>                                                                                                                                              |
| 25                                                                                                                                                                                              | Datamade, <https://datamade.us/> <https://github.com/datamade>                                                                                                                                                                                                                        |
| 26                                                                                                                                                                                              | Stewart James, (2012), “Coding in the Open”, GDS Team, Gov.uk, <https://gds.blog.gov.uk/2012/10/12/coding-in-the-open/> retrieved 20/09/2017                                                                                                                                          |
| 27                                                                                                                                                                                              | DFSS Point 15 Open Source <http://scottishgovernment.github.io/criterion/open-source/>) retrieved 20/09/2017                                                                                                                                                                          |
| 28                                                                                                                                                                                              | Huang, Weizhi, et al. "Automatically Modeling Developer Programming Ability and Interest Across Software Communities." International Journal of Software Engineering and Knowledge Engineering 26.09n10 (2016): 1493-1510.                                                            |

Other resources

https://www.software.ac.uk/resources/guides/choosing-repository-your-software-project

Distribution
------------

| Version | Date | Copies to |
|---------|------|-----------|
|         |      |           |
|         |      |           |
|         |      |           |
|         |      |           |
|         |      |           |

Document Location
-----------------

<https://sprocket.scot.nhs.uk> in folder:
