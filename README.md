# ItsAllRelativeTo
How many elephants is a killer whale?

This project is a web-based application with the goal of measuring real-world objects in terms of other objects. The project is publicly available under the MIT License. See [LICENSE] for more details.

## Technologies Used

* [git](https://git-scm.com/) for source code version control. We recommend the [GitKraken](http://www.gitkraken.com/) client, though any client will work.

## How to Contribute

Contact [blakeoxx](https://github.com/blakeoxx) to be added as a collaborator to this project. We loosely follow the git branching model proposed by Vincent Driessen: [A successful Git branching model](http://nvie.com/posts/a-successful-git-branching-model/).

- **Environment branches**: The only permanent branches are *master* and *dev*. These two branches represent the production and development/staging/testing environment, respectively.
  - The only branches that should be merged to *master* are release branches and hotfixes. These are discussed further down.
  - Merges to an environment branch should be followed by a deployment to the environment they represent, either immediately or publicly scheduled for a later date.
- **Features and Bugfixes**: All features and bugfixes should be branched from *dev*, named descriptively, and merged back to *dev* with ```git merge --no-ff myfeature``` upon completion.
- **Releases**: When the *dev* codebase is ready for production, it should be branched to a release. Release branches are named release-VERSION and should be merged back to *master* and *dev* when all smaller bugfixes are completed. When merging to *master*, the merge should be tagged with the release version number: ```git tag -a VERSION```.
  - While a release branch is open, major feature additions merged to *dev* should not be merged to the release branch. Bugfixes may be merged to *dev* and the release branch directly. Major features should be planned for future releases by branching to another release.
- **Hotfixes**: Hotfixes are critical bugfixes that need to go to production quickly. They should be branched from *master*, merged back to *master*, *dev*, and any current release branches. As with releases, hotfixes should be tagged with the updated version number: ```git tag -a VERSION```. Perform hotfixes sparingly.
