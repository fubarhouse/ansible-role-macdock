# Ansible Role: Dockutil

[![Build Status](https://travis-ci.org/fubarhouse/ansible-role-macdock.svg?branch=master)](https://travis-ci.org/fubarhouse/ansible-role-macdock)

Install [Dockutil](https://github.com/kcrawford/dockutil) and remove, add and and rotate items on OSX's dock on macOS.

During the roles execution, icon cache will also be cleared however may require a restart if there are continuing problems.

## Requirements

None.

## Role Variables

### Administration
````yaml
# The URL to the physical file where dockutil is available.
dockutil_url: https://raw.githubusercontent.com/kcrawford/dockutil/master/scripts/dockutil
# The installation path the above URL will be downloaded to.
dockutil_install_path: /usr/local/bin/dockutil
````

### Removal of dock items

Dock items to remove:

````
dockitems_disabled:
  - Launchpad
  - Mail
  - Safari
  - Contacts
  - Notes
  - Reminders
  - Maps
  - Photos
  - Messages
  - FaceTime
  - iTunes
  - iBooks
  - App Store
  - System Preferences
  - Calendar
  - Terminal
````

#### Remove all: Preferred method
```
dockitems_remove_all: true
```
#### Remove all: Alternative method:
````
dockitems_disabled:
  - all
````

### Adding dock items

Dock items to add, including name, path and weight/position:

````
dockitems_enabled:
  - name: Google Chrome
    path: "/Applications/Google Chrome.app"
    pos: 1
  - name: Tower
    path: "/Applications/Tower.app"
    pos: 2
  - name: FirefoxDeveloperEdition
    path: "/Applications/FirefoxDeveloperEdition.app"
    pos: 3
  - name: Sublime Text
    path: "/Applications/Sublime Text.app"
    pos: 4
  - name: iTerm
    path: "/Applications/iTerm.app"
    pos: 5
  - name: TeamViewer
    path: "/Applications/TeamViewer.app"
    pos: 6
````

## Dependencies

None.

## Example Playbook

````
    - hosts: localhost
      roles:
        - fubarhouse.macdock
````

## License

MIT / BSD

## Author Information

This role was created in 2016 by [Karl Hepworth](twitter.com/fubarhouse).
