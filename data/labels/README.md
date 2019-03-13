We use [git-labelmaker][git-labelmaker] to manage our labels and within this
directory is the data we used broken up by category.

Before running `git-labelmaker`, make sure you're in the directory of the repo
that you want to manage the labels for. [Generate][generate-access-token] your
personal access token and then run `git-labelmaker`. Inside git-labelmaker,
follow the prompts to enter your token and then password protect it. Now
you're set to create the labels. Choose `Add Labels From Package` and then
enter the path to one of the category json files that you'll find in this
directory. Rinse and repeat for each file.

[git-labelmaker]: https://github.com/himynameisdave/git-labelmaker
[generate-access-token]: https://github.com/settings/tokens
