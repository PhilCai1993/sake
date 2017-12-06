# Releasing sake

In this documents you'll find all the necessary steps to release a new version of `sake`.

> Although some of the steps have been automated, there are some of them that need to be executed manually.

1. First of all, create a new release branch with the following name `release/x.x.x` where `x.x.x` is the new version that is going to be released.
2. Update the `CHANGELOG.md` adding a new entry at the top with the next version. Make sure that all the changes in the version that is about to be released are properly formatted. Commit the changes in `CHANGELOG.md`.
3. Validate the state of the project by executing `bundle exec rake ci`
4. Generate the release with `bundle exec rake release`.
5. Update the Homebrew formula running `bundle exec rake update_formula`.
6. Create a new release on [GitHub](https://github.com/xcodeswift/sake) including the information from the last entry in the `CHANGELOG.md`.
7. Close the GitHub Milestone associated to that release and open a new one for the next release.
8. Rebase the `release/x.x.x` branch into `master`.

### Notes
- If any of the steps above is not clear above do not hesitate to propose improvements.
- Release should be done only by authorized people that have rights to crease releases in this repository and commiting changes to the Tap repository.