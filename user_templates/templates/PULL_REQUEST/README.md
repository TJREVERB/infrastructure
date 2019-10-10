# User Templates
## Pull Requests

### What are Pull Requests?
It is good practice to always save a copy of working code. The way to do this using `git` is through `branches`. A `branch` is a copy of the current development code, each different `branch` having a different name. By convention, the non-developmental, working code is under the `master` branch. Anything that changes code inside the `master` branch(i.e. issues) should first be done on a separate branch. Once development has finished on a certain branch, that branch can be merged into `master`. The way we review and merge branches is through Pull Requests
Learn More About [Pull Requests](https://help.github.com/en/articles/about-pull-requests)

### Why do we use Pull Requests?
Since we wish to maintain a `master` branch, it is necessary to use Pull Requests to conduct ad hoc code reviews and merge proper code. Be creating Pull Requests code that is ready to merge can be reviewed first before being merged into the `master` branch

### How do you open a Pull Requests?
[Opening Pull Requests](https://help.github.com/en/articles/creating-a-pull-request)
1. Navigate to the current flight software repository
	* The repository for the 2019(current) mission is at [TJREVERB/pfs](https://github.com/TJREVERB/pfs)
2. Click on the Pull Requests tab on the top repository navigation bar
3. Click on the green New pull request button
4. Two dropboxes should appear. Leave the first one as master, select your branch in the second dropbox
(i.e. master <- [YOUR_BRANCH_NAME])
5. Follow the format in `PULL_REQUEST.md` to create a new Pull Request
6. Assign the current programming lead and team leads to the Pull Request
7. Submit the Pull Request

### What should you do after opening a Pull Request?
The leads shall:
* Review submitted Pull Request changes and make comments on recommended changes
* Approve and merge the Pull Request if no changes are required

The developer shal:
* Wait until a review is submitted for their Pull Request
* As soon as a review is submitted, make the appropriate changes and resubmit the Pull Request as soon as possible, making sure to request reviews


---
Last Modified on 09/18/2019 by Anup Bagali