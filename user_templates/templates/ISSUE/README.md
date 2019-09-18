# User Templates
## Issue

### What is an Issue?
An issue is a projected change to the current flight software.
An issue may be(but is not limited to) an enhancement, bug, or test pertaining to the current developing flight software code.
Learn More About [Issuses](https://help.github.com/en/articles/about-issues)

### Why do we use Issues?
Issues organize the way we assign and record tasks. Github provides a seamless integration with Issues and their specific repository. Issues are stored on Github itself and do not get lost.

### How do you open a new Issue?
1. Navigate to the current flight software repository
	* The repository for the 2019(current) mission is at [TJREVERB/pfs](https://github.com/TJREVERB/pfs)
2. Click on the Issues tab in the top repository navigation bar
3. Click on the green `New Issue` button
4. Follow the format in `ISSUE.md` to create a new issue
5. Assign assignees, tags, and projects as necessary
	* Assignees are current team members who have the responsibilty in resolving this issue
	* Tags denote the issues' relevancy(enhancement, bug, test, etc.)
	* Projects point to the current project board for the repository
6. Submit the Issue

### What should you do after opening a new Issue?
After an issue is opened it is time for a developer to start submitting code to resolve the issue. 

**The issue assignee should be the developer responsible for resolving the issue.**

The developer shall:
1. Create a new branch with name `[TAG_NAME]-[ISSUE_NUMBER]`
2. On their local repository(personal copy) run `git fetch`
3. On their local repository run `git checkout [BRANCH-NAME]`
4. Start developing code to resolve the issue
5. Push new code to `origin/[BRANCH-NAME]`
6. Open a Pull Request once finished