Cgit
====

An ansible role that install cgit with nginx and fcgiwrap.

Role Variables
--------------

Available variables are listed below, along with default values
(see `defaults/main.yml`):

	cgit_username: "git"

The user you use to connect and fetch repositories. If you were to change it
to "foo", your remote repository would look like
"foo@git.example.com:repository".

	cgit_ssh_keyfiles:
		- "{{ lookup('env, 'HOME') }}/.ssh/id_rsa.pub"

Each item of the list must be a file containing a public SSH key. These keys
will be used to authorize connections to the cgit user. Having the private
part of one of these key is necessary to push to this remote.

	cgit_domain_name: "git.example.com"

This is used both for the web interface and the remote repositories. If you
change it to "foo.bar.com", the web interface would be available under this
name and your remote repositories would looke like
"git@foo.bar.com:repository".

	cgit_css_endpoint: "/cgit.css"

The endpoint used by the web interface to fetch the CSS and style the page.

	cgit_css_location: "/usr/share/cgit/cgit.css"

The location of the CSS file associated with the above endpoint.

	cgit_logo_endpoint: "/cgit.png"

The endpoint used by the web interface to fetch the logo.

	cgit_logo_location: "/usr/share/cgit/cgit.png"

The location of the logo file associated with the above endpoint.

	cgit_repo_dir: "/srv/git/"

The directory where your repositories will be stored.

Dependencies
------------

* Nginx (from geerlingguy)
* fcgiwrap (from debops)

License
-------

BSD
