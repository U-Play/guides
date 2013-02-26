Best Practises
==============

Some of the most important rules, copied from other sections.

General
-------

* Don't write code that guesses at future functionality. Focus on current issues.
* Prefer small methods. One line is best.
* Prefer small objects with a single, well-defined responsibility.
* [Tell, don't ask](http://goo.gl/Ztawt).

* Avoid optional parameters lists, or too many parameters. Does the method do too much?
* Avoid monkey-patching.

Rails
-----

* Don't change a migration after it has been merged into master.
* Validate the associated `belongs_to` object (`user`), not the database column (`user_id`).

Bundler
-------

* Avoid exact version numbers in `Gemfile` except for non-framework gems.
* Pay attention to the [Pessimistic Version Constraint](http://docs.rubygems.org/read/chapter/16#page74)
* Checkout Gemfile.lock in applications, but not gems
* Use an [exact version](http://robots.thoughtbot.com/post/35717411108/a-healthy-bundle#exact-version)
  in the `Gemfile` for fragile gems, such as Rails.
* Use [versionless](http://robots.thoughtbot.com/post/35717411108/a-healthy-bundle#versionless)
  `Gemfile` declarations for gems that are safe to update often, such as pg,
  thin, and debugger.
