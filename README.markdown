ActiveRecord Sybase Adapter (TDS branch)
========================================

This adapter is an almost complete rewrite of the original Sybase
adapter by John R. Sheets, brought up to date with Rails 3.1 and
with the database driver changed from the original Sybase CT with
[Tiny TDS](http://rubydoc.info/gems/tiny_tds/frames).

It depends on a [sybase Visitor for AREL](http://github.com/ifad/arel-sybase-visitor)
that implements LIMIT and OFFSET using Cursors on ASE 15 and temp
tables on ASE 12.5. Because of this difference, the adapter does
*NOT* depend explicitly on the visitor, but rather you must use
Bundler to require the branch you need in your Gemfile.

Caveats
-------

We are not releasing this adapter on rubygems.org in order to not
disrupt live rails application depending on the age old adapter
still available on gems.rubyonrails.org.

Credits
-------

Tiny TDS support was initiated by Darrin Thompson <darrinth@gmail.com>
and completed by Marcello Barnaba <vjt@openssl.it>. Rails 3.1 support,
Code reordering and clean up thanks to Simone Carletti <weppos@weppos.net>.

UFSC version
-------

The adapter is being used in production with a Sybase ASE 16.2 using a
specific (non-ASCII) charset. Column names with non-ASCII characters 
are accepted. 
Test cases have been created (and are planned to be released) for rails
version 3.2.22.5.