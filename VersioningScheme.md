To manage timer iteration updates and consolidate documentation changes for fixes, corrections will follow a simple of set of rules and requirements to allow convey readers to better navigate future changes as repository content dependencies, links/reference utilized across as .

Convention

Releases and pre-releases for this timer iteration repository does not have any software (code) needed to assemble the project. Nevertheless, I will use common software versioning scheme com versioning details code-centric repository to not reflect  that follows similar 'SemVer' with unique releases to  reflect the focused on storing and documenting full engineering project hardware omission of 'software' as no code is needed for building and creating project:



#### **Releases** 
_( Sample title 'Release vX.X.X')_
- **Major** _(**X**.X.X)_: Changes to second (referend by 'X')  placeholder signify **backward-incompable** changes, which have been verified and testing for comprehension. ~~Note that only Major releases include date of publication, denoted by vYYYY.MM.DD.~~ 
- **Minor** _(X.**X**.X)_: Changes to second placeholder denote releases that adds **backwards-compatable** new features/documentation to guide without changing previous instructions or materials. ~~Titles in Minor Releases do not include Calendar information in title (e.g., no  "Release v1.1.0" .~~ Some examples include:
-  adding additional diagrams/illustrations better explaining concepts
-  adding new documentation that explains how to contribute to repository or create pull request.
- Fixing broken links with intended compatable previous link
- Updating Instructions to accomodate previous linked product/pages a part of a patch version release 
- filling in previous placeholder for supplementary media 
  
- **Patch Version** _(X.X.**X**)_: Changes to third placeholder denote changes that are **Backwards Incompatible** and no longer adhere to previous instructions. In other words, these refer to changes in repository contents that will no longer support instructions or materials in the previous version. 
-  previous documentation  errors are corrected, which may come in the form of:

Major version zero (0.y.z) is for initial development. Anything may change at any time. The public instructional guide should not be considered stable.


Version 1.0.0 defines the public instructional guide. Once this release has been created, expect documentation and provided instructions is ready for public use.
>- Assumptions after Version 1.0.0 is released
>   1. Is well-written and presentable to allow reader to follow along without 
>   2. Include date of release with each iteration to denote time created for public
>   3. Have should have all referenced material checked for links and/or ensure placeholders have specific details of respective item

If these criteria can't be met or changes have not been properly verified, use pre-releases versions. 

#### Pre-releases:
_( Sample title 'Release vX.X.X-unstable')_
Minor changes prior that haven't been verified should come in the from of pre-release versions.
1. Notation & Precedence:
 Pre-releases are denoted by appending a dash and a series of dot separated identifiers immediately following the patch version. Identifiers MUST be comprised of only ASCII alphanumerics and dash [0-9A-Za-z-]. Furthermore, pre-releases precedence MUST be determined by comparing each dot separated identifier as follows: identifiers consisting of only digits are compared numerically and identifiers with letters or dashes are compared lexically in ASCII sort order. Pre-release versions satisfy but have a lower precedence than the associated normal releases version. sample pre-release titles (with precedence included):  1.0.0-alpha.1.0.1 < 1.0.0-beta < 1.0.0-beta.1 < 1.0.0-beta.1.0.1 < 1.0.0-unstable < 1.0.0-unstable.2 < 1.0.0-unverified.1


- New Pre-releases Samples with precendence ordering (lowest to highest): 
1. alpha: as higher precedence labels require. don't change instructions, and quick changes without prior categorization of type of release. 
2. beta: should be used for breaking down alpha releases and specifying modifications from prior releases.
3. Unstable: Changes that clearly modify and remove previous documentation should follow this approach. Additionally, this appending string should be used with multiple intended changes that would benefit without tremendous effort and time.  If you are unsure of changes from previous version, or can't recall previous version without looking back, start with "X.X.X-unstable.0" and break into major, minor, patch once all required updates needed have been met.

4. Unverified : Should be last stage before updating the Release version, this pre-release pre-release option should be used after release has been checked with a 1 in pre-release place holder for intended release change ready for reviewal









For instance, "Release X.X-unstable.0" will continue to increase the integer '0' integer as release contains unverified/untested documentation:


- creation of new files
- addition/removal of supplementary links
- minimal finalizations of files are made
Each subsequent version will increase number added release will change, based on  
1. Verified: Once pre-release is ready to be read meaning 
  


> **Notes:**
> - Specified versioning scheme does not follow standard SemVer Versioning scheme as repository. This is due to the repository contents not being software oriented but rather intended to help readers follow along a full engineering build.