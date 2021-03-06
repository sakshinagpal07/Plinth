# Change Log
All notable changes to this project will be documented in this file.

## [Unreleased]
### Added
- Added screenshots to Readme.
- repro: Open up RTP ports.

### Fixed
- Upstream patch from Debian bug #837206 to fix DB and log file
  permissions. Also switch to new setup command.
- Include module static files in build, required for Debian package build.

### Changed
- repro: Use firewalld provided SIP services.

## [0.11.0] - 2016-09-21
### Added
- Added loading icon for other busy operations.
- Added basic front page with shortcuts to web apps, and information
  about enabled services.
- Allow initial setup operation to happen without package
  installation.
- networks: Add polkit rules for network management.
- Update man page to add setup operations.
- Add argument to list packages needed by apps.
- networks: Add batctl as dependency.

### Fixed
- users: Fixed checking restricted usernames.
- users: Display error message if unable to set SSH keys.
- help: Minor updates and fixes to status log.
- Updated translations to fix weblate errors.
- Fixed spelling errors in datetime and letsencrypt modules.
- users: Flush nscd cache after user operations.
- monkeysphere: Adopted to using SHA256 fingerprints.
- monkeysphere: Sort items for consistent display.
- monkeysphere: Handle new uid format of gpg2.
- monkeysphere: Fixed handling of unavailable imported domains.
- minetest: Fixed showing status block and diagnostics.
- Fix stretched favicon.

### Changed
- dynamicdns, monkeysphere, transmission, upgrades: Use actions where
  root is required, so that Plinth can run as non-root.
- xmpp: Switched to using ruamel.yaml to modify ejabberd config.
- Exit with error if any of the setup steps fail.
- actions: Hush some unneeded output of systemd.
- letsencrypt: Depend on the new certbot package.
- Switch base template from container-fluid to container. This will
  narrow the content area for larger displays.
- Readjust the responsive widths of various tables.
- Print django migrate messages only in debug.
- Tune log message verbosity.
- Plinth no longer runs as root user.  Fix all applications that were
  requiring root permission.
- xmpp: Replace jwchat with jsxc. Bump module version number so
  current installs can be updated.
- ikiwiki: Allow only alphanumerics in wiki/blog name.

### Removed
- Remove width management for forms.

## [0.10.0] - 2016-08-12
### Added
- Added Disks module to show free space of mounted partitions and
  allow expanding the root partition.
- Added Persian (fa) locale.
- Added Indonesian (id) locale.
- Added options to toggle Tor relay and bridge relay modes.
- Added Security module to control login restrictions.
- Added a page to display recent status log from Plinth. It is
  accessible from the 500 error page.
- networks: Added ability to configure generic interfaces.
- networks: Added 'disabled' IPv4 method.
- networks: Added configuration of wireless BSSID, band, and channel.
- networks: Added NetworkManager dispatcher script to configure
  batman-adv mesh networking.
- radicale: Added access rights control.
- tor: Added spinner when configuration process is ongoing.
- Allowed --setup command to take a list of modules to setup.
- Added Vagrantfile.
- Added Snapshots module to manage Btrfs snapshots.

### Removed
- networks: Removed hack for IP address fetching.

### Fixed
- Improved Dynamic DNS status message when no update needed.
- Improved Ikiwiki description.
- Added check if a2query is installed before using it, since apache2
  is not a dependency for Plinth.
- networks: Fixed incorrect access for retrieving DNS entries.
- Fixed issue with lost menus in Django 1.10.
- Added workaround for script prefix problem in stronghold.
- users: Fixed editing users without SSH keys.

### Changed
- Added suggested packages for ikiwiki. Removed recommends since they
  are installed automatically.
- users: Switched to using dpkg-reconfigure to configure several
  packages. This will work even if the package is already installed.
- Bumped required version of Django to 1.10.

## [0.9.4] - 2016-06-14
### Fixed
- Fixed quoted values in nslcd config.

## [0.9.3] - 2016-06-12
### Added
- Added Polish translation.
- Added check to Diagnostics to skip tests for modules that have not
  been setup.
- Added sorting of menu items per locale.
- Allowed setting IP for shared network connections.

### Fixed
- Fixed issue preventing access to Plinth on a non-standard port.
- Fixed issue in Privoxy configuration. Two overlapping
  listen-addresses were configured, which prevented privoxy service
  from starting.
- Fixed issues with some diagnostic tests that would show false
  positive results.
- Fixed some username checks that could cause errors when editing the
  user.
- Switched to using apt-get for module setup in Plinth. This fixes
  several issues that were seen during package installs.

### Changed
- Moved Dynamic DNS and Pagekite from Applications to System
  Configuration.

### Deprecated
- Dealt with ownCloud removal from Debian. The ownCloud page in Plinth
  will be hidden if it has not been setup. Otherwise, a warning is
  shown.

### Removed
- Removed init script and daemonize option.
- Removed writing to PID file.

### Security
- Fixed issue that could allow someone to start a module setup process
  without being logged in to Plinth.

[Unreleased]: https://github.com/freedombox/Plinth/compare/v0.11.0...HEAD
[0.11.0]: https://github.com/freedombox/Plinth/compare/v0.10.0...v0.11.0
[0.10.0]: https://github.com/freedombox/Plinth/compare/v0.9.4...v0.10.0
[0.9.4]: https://github.com/freedombox/Plinth/compare/v0.9.3...v0.9.4
[0.9.3]: https://github.com/freedombox/Plinth/compare/v0.9.2...v0.9.3
