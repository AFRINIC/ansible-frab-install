AFRIINC.frab
============

An Ansible role to install the **[frab](http://frab.github.io/frab/)** free and open conference management system.

This is not portable code in regards to target OS/Architecture. It's currently very specific to it's intended infrastrcuture:

* Targeted and tested on CentOS 7. Should thus work on RHEL 7 too. Will **NOT** work on other flavours.

The role set's up the frab (rails) app listening on it's default port (`:3000`), and also does *not* set up Apache (or any other reverse proxy). This needs to be done as an additional task, separately.

Role Variables
--------------

    # variables with optional default values

    frab_environment: development   # development, test, production
    frab_install_dir: /srv/frab
    frab_git_repo: "https://github.com/frab/frab.git"
    frab_git_release: master
    frab_db_host: "127.0.0.1"
    frab_db_port: "3306"
    frab_db_name: db_frab
    frab_db_user: user_frab

Example Playbook
----------------

      roles:
        - { role: afrinic.frab,
            frab_environment: production,
            frab_git_release: 0f9e0c9b1ec343ff8f21c5b350c12e158a61391f,
        }

License
-------

Apache
