testme
======

Sample repo for testing gitlab features

## Usage in testing and development

`gitlab-test` is used to seed your local gdk GitLab application and is also used in rspec tests.
Because of this, when building and testing features that require a specific type of file, you can
add them to the `gitlab-test` repo in order to access that blob during development or testing.

1. Push a new file on a new branch to [gitlab-org/gitlab-test](https://gitlab.com/gitlab-org/gitlab-test).
2. Execute `rm -rf tmp/tests` in your gitlab repo.
3. Add your branch and its head commit to the `BRANCH_SHA` hash in [`test_env.rb`](https://gitlab.com/gitlab-org/gitlab-ce/blob/master/spec/support/test_env.rb#L7-42).

In rspec, you can use `create(:project)` to create an instance of `gitlab-test` that has a `path` of `gitlabhq`.
