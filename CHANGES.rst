Changelog
=========

1.1.7 (2015-02-28)
------------------
1st release under cooperative ownership:

- #65, #66: Improve Auth for private repos by supporting i
  password protected package listings and downloads,
  in addition to uploads (use the -a, --authenticate option
  to specify which to protect).
- #67: Add cache-control http-header, reqed by pip.
- #56, #70: Ignore non-packages when serving.
- #58, #62: Log all http-requests.
- #61: Possible to change welcome-msg.
- #77, #78: Avoid XSS by generating web-content with SimpleTemplate 
  instead of python's string-substs.
- #38: Instruct to use --extra-index-url for misspelled dependencies to work. 
 

1.1.6 (2014-03-05)
------------------
- remove --index-url cli parameter introduced in 1.1.5

1.1.5 (2014-01-20)
------------------
- only list devpi-server and proxypypi as alternatives
- fix wheel file handling for certain wheels
- serve wheel files as application/octet-stream
- make pypiserver executable from wheel file
- build universal wheel
- remove scripts subdirectory
- add --index-url cli parameter

1.1.4 (2014-01-03)
------------------
- make pypiserver compatible with pip 1.5
  (https://github.com/pypiserver/pypiserver/pull/42)

1.1.3 (2013-07-22)
------------------
- make guessing of package name and version more robust

1.1.2 (2013-06-22)
------------------
- fix "pypi-server -U" stable/unstable detection, i.e. do not
  accidentally update to unstable packages

1.1.1 (2013-05-29)
------------------
- add 'overwrite' option to allow overwriting existing package
  files (default: false)
- show names with hyphens instead of underscores on the "/simple"
  listing
- make the standalone version work with jython 2.5.3
- upgrade waitress to 0.8.5 in the standalone version
- workaround broken xmlrpc api on pypi.python.org by using HTTPS

1.1.0 (2013-02-14)
------------------
- implement multi-root support (one can now specify multiple package
  roots)
- normalize pkgnames, handle underscore like minus
- sort files by their version, not alphabetically
- upgrade embedded bottle to 0.11.6
- upgrade waitress to 0.8.2 in the standalone script
- merge vsajip's support for verify, doc_upload and remove_pkg

1.0.1 (2013-01-03)
------------------
- make 'pypi-server -Ux' work on windows
  ('module' object has no attribute 'spawnlp',
  https://github.com/pypiserver/pypiserver/issues/26)
- use absolute paths in hrefs for root view
  (https://github.com/pypiserver/pypiserver/issues/25)
- add description of uploads to the documentation
- make the test suite work on python 3
- make pypi-server-standalone work with python 2.5

1.0.0 (2012-10-26)
------------------
- add passlib and waitress to pypi-server-standalone
- upgrade bottle to 0.11.3
- Update scripts/opensuse/pypiserver.init
- Refuse to re upload existing file
- Add 'console_scripts' section to 'entry_points', so
  'pypi-server.exe' will be created on Windows.
- paste_app_factory now use the the password_file option to create the
  app. Without this the package upload was not working.
- Add --fallback-url argument to pypi-server script to make it
  configurable.

0.6.1 (2012-08-07)
------------------
- make 'python setup.py register' work
- added init scripts to start pypiserver on ubuntu/opensuse

0.6.0 (2012-06-14)
------------------
- make pypiserver work with pip on windows
- add support for password protected uploads
- make pypiserver work with non-root paths
- make pypiserver 'paste compatible'
- allow to serve multiple package directories using paste

0.5.2 (2012-03-27)
------------------
- provide a way to get the WSGI app
- improved package name and version guessing
- use case insensitive matching when removing archive suffixes
- fix pytz issue #6

0.5.1 (2012-02-23)
------------------
- make 'pypi-server -U' compatible with pip 1.1

0.5.0 (2011-12-05)
------------------
- make setup.py install without calling 2to3 by changing source code
  to be compatible with both python 2 and python 3. We now ship a
  slightly patched version of bottle. The upcoming bottle 0.11
  also contains these changes.
- make the single-file pypi-server-standalone.py work with python 3

0.4.1 (2011-11-23)
------------------
- upgrade bottle to 0.9.7, fixes possible installation issues with
  python 3
- remove dependency on pkg_resources module when running
  'pypi-server -U'

0.4.0 (2011-11-19)
------------------
- add functionality to manage package updates
- updated documentation
- python 3 support has been added

0.3.0 (2011-10-07)
------------------
- pypiserver now scans the given root directory and it's
  subdirectories recursively for packages. Files and directories
  starting with a dot are now being ignored.
- /favicon.ico now returns a "404 Not Found" error
- pypiserver now contains some unit tests to be run with tox

0.2.0 (2011-08-09)
------------------
- better matching of package names (i.e. don't install package if only
  a prefix matches)
- redirect to the real pypi.python.org server if a package is not found.
- add some documentation about configuring easy_install/pip

0.1.3 (2011-08-01)
------------------
- provide single file script pypi-server-standalone.py
- better documentation

0.1.2 (2011-08-01)
------------------
- prefix comparison is now case insensitive
- added usage message
- show minimal information for root url

0.1.1 (2011-07-29)
------------------
- don't require external dependencies

0.1.0 (2011-07-29)
------------------
- initial release