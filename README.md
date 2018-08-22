# Ansible Role: WordPress
  Ansible role that installs and configures WordPress.

Features include:
-   Installation of any WordPress version to specified directory
-   Configuration of wp-config.php
-   [Fetch random salts for wp-config.php](https://api.wordpress.org/secret-key/1.1/salt/)

## Build Status
![alt text](https://travis-ci.org/chris1984/wordpress-role.svg?branch=master "Build Status")

## Installation

Using `ansible-galaxy`:
```shell
$ ansible-galaxy install chris1984.wordpress
```

Using `git`:
```shell
$ git clone https://github.com/chris1984/wordpress-role.git
```

## Requirements & Dependencies
-   Ansible 2.2 or higher
-   Curl

## Variables
Here is a list of all the default variables for this role, which are also available in `defaults/main.yml`.

```yaml
wordpress_wp_version: '4.9.8'
wordpress_wp_install_dir: '/var/sites/awesome_wordpress_site'
wordpress_wp_db_name: 'database_name_here'
wordpress_wp_db_user: 'username_here'
wordpress_wp_db_password: 'password_here'
wordpress_wp_db_host: 'localhost'

wordpress_wp_db_charset: 'utf8'
wordpress_wp_db_collate: ''
wordpress_wp_table_prefix: 'wp_'
wordpress_wp_debug: false

wordpress_wp_fs_method: 'direct'
wordpress_wp_lang: ''
```

## Example playbook
```yaml
- hosts: all
  vars:
    wordpress_wp_version: 4.0
    wordpress_wp_install_dir: '/var/sites/awesome_wordpress_site'
    wordpress_wp_db_name: 'database_name_here'
    wordpress_wp_db_user: 'username_here'
    wordpress_wp_db_password: 'password_here'
    wordpress_wp_db_host: 'localhost'
  roles:
  - chris1984.wordpress
```

## Testing
```shell
$ git clone https://github.com/chris1984/wordpress-role.git
$ cd wordpress-role
$ vagrant up
```

## Contributing
In lieu of a formal styleguide, take care to maintain the existing coding style. Add unit tests and examples for any new or changed functionality.

1.  Fork it
2.  Create your feature branch (`git checkout -b my-new-feature`)
3.  Commit your changes (`git commit -am 'Add some feature'`)
4.  Push to the branch (`git push origin my-new-feature`)
5.  Create new Pull Request

## License

Licensed under the MIT License. See the LICENSE file for details.

Copyright (c) 2014 [Chris Roberts](http://croberts.us/)
