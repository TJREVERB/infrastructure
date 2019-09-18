# Issue Template

### Componenets
**This provides a rough structure for the current(2019) TJCUBESAT flight software development. This is open to change if needed**

#### Title
* Provide a small title describing the issue
  - i.e. "Implement Threading Locks"

#### Body
**This part will differ depending on your tag.**

**The boxed part is to be placed as a comment for the new issue**
##### Enhancement Body
```
# Tasks
## Data Structures
(List out any required data structures needed in enhancement)

## Methods
(List out any required methods. DO NOT INCLUDE HELPER FUNCTIONS)

## Threads
(List out any required threads)

## General (optional)
(List out any previously unadded information)
```
* The main idea of a body is to properly describe the task at hand so that the developer can properly understand what needs to be done with minimal explanation from the leads

##### Bug Body
```
# Description
(List out description of bug)

# Affected areas
(List out areas affected by the bug)

# Recommended fix (optional)
(List out any recommended fixes. These recommendations will be considered but may or may not be implemented. )
```

##### Test Body
**It important that a tester be given specific details on how to test a feature. Supply all test cases and how to execute such cases. Do not assume that the tester will know anything, because they most likely will not**
```
# Methods to Test

## [Method 1]
(Method to be tested)
### Inputs
(What to be inputted to the method)
### Outputs
(Expected outcome)


**IMPORTANT** Unit testing should not include an intermediary. These tests should directly interface with the submodule file and only output can be viewed on an intermediary. (e.x. Test recieve() by sending from another file, not from the GS Terminal)
```

---
Last Modified on 09/18/2019 by Anup Bagali