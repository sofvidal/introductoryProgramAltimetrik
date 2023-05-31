# Git branching strategies and flows.

What is a branching strategy?
A “branching strategy” refers to the strategy a software development team employs when writing, merging, and shipping code in the context of a version control system like Git. A branching strategy ensures everyone on the team is following the same process for making changes to source control. The right strategy enhances collaboration, efficiency, and accuracy in the software delivery process, while the wrong strategy (or no strategy) leads to hours of lost effort. 

Common types of branches
Trunk branch
Every Git repository has a trunk (also referred to as main, mainline, or the master branch). When a Git repository is created, the trunk exists automatically as the implicit first branch. The use of a trunk and the timing of changes landing on it vary depending on the exact branching strategy being used. In trunk-based development, the trunk is the central branch to which all developers send their code changes.

Development branch
The development branch is a long-lived feature branch that holds changes made by developers before they’re ready to go to production. It parallels the trunk and is never removed. Some teams have the development branch correspond with a non-production environment. As such, commits to the development branch trigger test environment deployments. Development and trunk are frequently bidirectionally integrated, and it’s typical for a team member to bear the responsibility of integrating them.

Feature branch
A feature branch can be short- or long-lived depending on the specific branching flow. The branch often is used by a single developer for only their changes, but it is possible to share it with other developers as well. Again, the branching strategy will determine how exactly you define a “feature branch”. 

Release branch
A release branch can be either short-lived or long-lived depending on the strategy. In either case, the release branch reflects a set of changes that are intended to go through the production release process.

Hotfix branch
A hotfix branch is a branch that’s used generally to hold changes related to emergency bug fixes. They can be short-lived or long-lived, though generally they exist as long-lived branches split off from a release branch. They tend to be more common in teams with explicitly versioned products, such as installed applications.

What are some common Git branching strategies?
GitFlow:
Considered to be a bit complicated and advanced for many of today’s projects, GitFlow enables parallel development where developers can work separately from the master branch on features where a feature branch is created from the master branch.
Afterwards, when changes are complete, the developer merges these changes back to the master branch for release.
This branching strategy consists of the following branches:
Master 
Develop
Feature
Release
Hotfix

GitHub Flow:
GitHub Flow is a simpler alternative to GitFlow ideal for smaller teams as they don’t need to manage multiple versions. Unlike GitFlow, this model doesn’t have release branches. You start off with the main branch then developers create branches, feature branches that stem directly from the master, to isolate their work which are then merged back into main. The feature branch is then deleted. The main idea behind this model is keeping the master code in a constant deployable state and hence can support continuous integration and continuous delivery processes.

GitLab Flow:
GitLab Flow is a simpler alternative to GitFlow that combines feature-driven development and feature branching with issue tracking. With GitFlow, developers create a develop branch and make that the default while GitLab Flow works with the main branch right away. GitLab Flow is great when you want to maintain multiple environments and when you prefer to have a staging environment separate from the production environment. Then, whenever the main branch is ready to be deployed, you can merge back into the production branch and release it. Thus, this strategy offers propers isolation between environments allowing developers to maintain several versions of software in different environments.

Trunk-based development:
Trunk-based development is a branching strategy that in fact requires no branches but instead, developers integrate their changes into a shared trunk at least once a day. This shared trunk should be ready for release anytime.
The main idea behind this strategy is that developers make smaller changes more frequently and thus the goal is to limit long-lasting branches and avoid merge conflicts as all developers work on the same branch. In other words, developers commit directly into the trunk without the use of branches.
Consequently, trunk-based development is a key enabler of continuous integration (CI) and continuous delivery (CD)  since changes are done more frequently to the trunk, often multiple times a day (CI) which allows features to be released much faster (CD).
This strategy is often combined with feature flags. As the trunk is always kept ready for release, feature flags help decouple deployment from release so any changes that are not ready can be wrapped in a feature flag and kept hidden while features that are complete can be released to end-users without delay. 


Sources: https://launchdarkly.com/blog/git-branching-strategies-vs-trunk-based-development/, https://www.flagship.io/git-branching-strategies/ 
