Instadrop
====================
Automatically sync your Instagram photos to Dropbox

A demo application of the Instagram real-time API.

It's live! <http://instadrop.appspot.com>


Installation on Google App Engine
---------------------------------
1. [Sign up](https://appengine.google.com/) for an App Engine account.
2. [Download](http://code.google.com/appengine/downloads.html) the App Engine SDK.
3. Fork and modify our code! Need help? Read the Google App Engine [Getting Started Guide](http://code.google.com/appengine/docs/)


Configure your App
------------------

e.g.

1. Register at http://progrium.com/localtunnel/, start it with something like `localtunnel -k ~/.ssh/id_rsa.pub 8100`.
   Note the url, e.g. `http://42tr.localtunnel.com:8100/`
2. Register at http://instagram.com/developer/clients/register/ - your "OAuth redirect_uri" should be something like `http://localhost:8100/instagram/callback`. Instagramm dow displays a `CLIENT ID` and `CLIENT SECRET` - copy them to the appropriate locations in `local_settings.py`
3. Got ro https://www.dropbox.com/developers/apps and Create an App. Copy the `App Key` and `App Secret` into `local_dropbox.ini`

    cp settings.py.sample settings.py
    sed -i '' -e "s/XxxSOMETHING_RANDOMxXX/`(date;md5 /etc/* 2&>/dev/null)|md5`/" settings.py

mooncrusher:Instadrop md$ cp prod_dropbox.ini.sample prod_dropbox.ini
mooncrusher:Instadrop md$ cp local_dropbox.ini.sample local_dropbox.ini
mooncrusher:Instadrop md$



Follow @instagramapi on Twitter
----------------------------
You should [follow @instagramapi on Twitter](http://twitter.com/#!/instagramapi) for announcements,
updates, and news about the Instagram API.


Join the mailing list!
----------------------
<https://groups.google.com/group/instagram-api-developers>


Did you fork this app to create something cool?
-----------------------------------------------
Add it to the [apps](http://github.com/Instagram/Instadrop/wiki/apps) wiki!


How this works
--------------

First the application requests OAuth access to Instagramm and Dropbox. It stores
the tokens received in an `Profile` instance.

The awsome [subscriptions](http://instagram.com/developer/realtime/) feature of Instagramm is
then used to make Instagramm notify us of all new images posted.
Since this uses the Pubsubhubub challenge flow it gets somewhat complicated:



Contributing
------------
In the spirit of [free software](http://www.fsf.org/licensing/essays/free-sw.html), **everyone** is encouraged to help improve this project.

Here are some ways *you* can contribute:

* by using alpha, beta, and prerelease versions
* by reporting bugs
* by suggesting new features
* by writing or editing documentation
* by writing specifications
* by writing code (**no patch is too small**: fix typos, add comments, clean up inconsistent whitespace)
* by refactoring code
* by closing [issues](http://github.com/Instagram/Instadrop/issues)
* by reviewing patches


Submitting an Issue
-------------------
We use the [GitHub issue tracker](http://github.com/Instagram/Instadrop/issues) to track bugs and
features. Before submitting a bug report or feature request, check to make sure it hasn't already
been submitted. You can indicate support for an existing issuse by voting it up. When submitting a
bug report, please include a [Gist](http://gist.github.com/) that includes a stack trace and any
details that may be necessary to reproduce the bug, including your Python version and
operating system. Ideally, a bug report should include a pull request with failing specs.


Submitting a Pull Request
-------------------------
1. Fork the project.
2. Create a topic branch.
3. Implement your feature or bug fix.
4. Add documentation for your feature or bug fix.
5. Commit and push your changes.
6. Submit a pull request.


Copyright
---------
Copyright (c) 2011 Instagram (Burbn, Inc).
See [LICENSE](https://github.com/Instagram/Instadrop/blob/master/LICENSE.md) for details.
