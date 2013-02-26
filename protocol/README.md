Protocol
========

A guide for getting things done.

Write a feature
---------------

Create a local branch based off dev.

    git checkout dev
    git pull --rebase
    git checkout -b your-initials-new-feature

Rebase frequently to incorporate upstream changes.

    git fetch origin
    git rebase origin/master
    <resolve conflicts>

When feature is complete and tests pass, commit the changes.

    rake
    git add -A
    git status
    git commit -v

Write a [good commit message](http://goo.gl/w11us). Example format:

    Present-tense summary under 50 characters

    * More information about commit (under 72 characters).
    * More information about commit (under 72 characters).

    http://project.management-system.com/ticket/123

Share your branch.

    git push origin [branch]

Submit a [Github pull request](http://goo.gl/Kmdee).

Review code
-----------

A team member other than the author reviews the pull request. They follow
[Code Review](../code-review) guidelines to avoid
miscommunication.

They make comments and ask questions directly on lines of code in the Github
web interface or in Campfire.

For changes which they can make themselves, they check out the branch.

    git checkout <branch>
    rake db:migrate
    rake
    git diff staging/master..HEAD

They make small changes right in the branch, test the feature in browser,
run tests, commit, and push.

When satisfied, they comment on the pull request `Ready to merge.`

Merge
-----

Rebase interactively. Squash commits like "Fix whitespace" into one or a
small number of valuable commit(s). Edit commit messages to reveal intent.

    git rebase -i origin/master
    rake

View a list of new commits. View changed files. Merge branch into master.

    git log origin/master..[branch]
    git diff --stat origin/master
    git checkout master
    git merge [branch] --ff-only
    git push

Delete your remote feature branch.

    git push origin :[branch]

Delete your local feature branch.

    git branch -d [branch]

Deploy
------

View a list of new commits. View changed files. Deploy to
[Heroku](https://devcenter.heroku.com/articles/quickstart) staging.

    git fetch staging
    git log staging/master..master
    git diff --stat staging/master
    git push staging master

Run migrations (if necessary).

    heroku run rake db:migrate -r staging

Restart the dynos if migrations were run.

    heroku restart -r staging

[Introspect](http://goo.gl/tTgVF) to make sure everything's ok.

    watch heroku ps -r staging

Test the feature in browser.

Deploy to production.

    git fetch production
    git log production/master..master
    git diff --stat production/master
    git push production master
    heroku run rake db:migrate -r production
    heroku restart -r production
    watch heroku ps -r production

Watch logs and metrics dashboards.

Close pull request and comment `Merged.`

Set Up Production Environment
-----------------------------

* Make sure that your
  [`Procfile`](https://devcenter.heroku.com/articles/procfile)
  is set up to run thin.
* Make sure the PG Backups add-on is enabled.
* Create a read-only [Heroku Follower](http://goo.gl/xWDMx) for your
  production database. If a Heroku database outage occurs, Heroku can use the
  follower to get your app back up and running faster.
