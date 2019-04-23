# Summary

The Meridion service provides automated tasks and a user interface to any number of [Nomicon](Nomicon.md) games, using the KeyMaster and GateKeeper for authentication, the Compository for a backing store, and a blockchain such as [Tesseract](Tesseract.md) for recording assets and records.

# Operation

Meridion is connected to a repo by giving it ownership of one or more branches. It could initially be given control of its own branch to test the system, and once verified it would be given ownership of the master branch.

Once connected it will monitor pull requests (PRs) on the branch. When a user "votes" on a proposal by approving or rejecting the review, Meridion will track the equity voted for or against. When the total equity voted reaches a configurable threshold (say, 75% for example), if the proposal passes then Meridion will automatically merge the proposal into its branch and record the new HEAD commit on its blockchain. The details will be contained in the commit message accessible by the commit's hash to anyone that has access to the repo.

All relevant configuration and smart contracts are committed into the repo just like any other document so falls under the same control process.
