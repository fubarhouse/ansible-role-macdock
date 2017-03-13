# Ansible Role: Dockutil

[![Build Status](https://travis-ci.org/fubarhouse/ansible-role-macdock.svg?branch=master)](https://travis-ci.org/fubarhouse/ansible-role-macdock)

Install [Dockutil](https://github.com/kcrawford/dockutil) and remove, add and and rotate items on OSX's dock on macOS.

## Requirements

 - Homebrew

## Role Variables

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

Or, if you want to remove all dock items, use:

```
dockitems_disabled:
  - all
```

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
