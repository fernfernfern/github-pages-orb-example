
# github-pages-orb example repo

1. Fork this repo

1. go to `https://circleci.com/add-projects/gh/<your username/org>` to add the project and click "start building". It will fail the first time. Have faith.

1. go to `https://circleci.com/gh/<your username/org>/github-pages-orb-example/edit#checkout` and click "Authorize with GitHub" in the Add User Key section.

1. You can now edit the site source code and push commits to master to have your website tested and deployed to github pages automatically.

## details

1. The source code for the jekyll site must live in `master`.
1. never push code to the `gh-pages` branch. The orb does that for you.
1. When code is pushed to any branch besides master it will only run the test job. If code is pushed directly to `master` or merged there from a pull request it will also trigger a deploy from `master` to `gh-pages`.
1. The test job will lint/validate your html markup (including opengraph) with `html-proofer` gem and validate any `json` files it finds in the compiled source with `jsonlint` gem.
1. you have access to use any jekyll plugins that you want such as the `jekyll-paginate-v2` plugin, which is not supported by GitHub pages natively.
