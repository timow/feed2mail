feed2mail
=========

feed2mail fetches entries from web feeds and sends them out as emails.


Requirements
------------

- pandoc         (tested with version 1.5.1.1)
- python         (tested with version 2.6.6)
- further python modules
    - argparse   (tested with version 1.1)
    - feedparser (tested with version 5.1.3)
    - yaml       (tested with version 3.09)


Note that feed2mail needs a recent version of feedparser. The version available
as a Debian package is not sufficient (as it does not provide 'updated_parsed'
attributes).

On Debian, the following command installs all required components

    aptitude install pandoc \
        python \
        python-argparse \
        python-yaml

    wget http://feedparser.googlecode.com/files/feedparser-5.1.3.tar.bz2
    tar xaf feedparser-5.1.3.tar.bz2
    cd feedparser-5.1.3
    python setup.py install


Installation
------------

feed2mail consists of a single Python script. For installation, copy the script
to a directory in your $PATH (e.g., /usr/bin).

    cp feed2mail /usr/bin


Configuration
-------------

feed2mail is configured on a per-user basis, by default via ~/.feed2mailrc.
Copy the template file feed2mailrc.template to ~/.feed2mailrc and adjust the
settings.

    cp feed2mailrc.template ~/.feed2mailrc
    vim ~/.feed2mailrc


Usage
-----

    % feedmail -h'
    usage: feed2mail [-h] [--log LOG] [--config CONFIG]

    optional arguments:
      -h, --help       show this help message and exit
      --log LOG        log level (debug, info, warning, error, critical)
      --config CONFIG  path to config file
