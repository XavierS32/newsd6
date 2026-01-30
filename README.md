# newsd6 - IPv6-Only Fork

This is a downstream fork of the [newsd](https://github.com/erco77/newsd)
project with added support for IPv6-only environments and other minor fixes.
This version retains all functionality of the original project while ensuring
compatibility with IPv6-only networks.

**Important:** This fork hasn't undergone rigorous testing and may introduce new
bugs. Use it at your own discretion. See the [GNU General Public
License](https://www.gnu.org/licenses/) for more details.

## What’s New

### IPv6-Only Support

* Migrated socket logic from IPv4 to IPv6-only.
* Enhanced `Listen/Port` configuration directive with parsing logic for
  `[IPv6]:port`.
* Set `IPV6_V6ONLY` to ensure that only IPv6 connections are accepted.

### Compatibility Fixes

* **[EXPERIMENTAL/RISK]** Fixed `EBADF` error in `flock(LOCK_SH)` by changing
  the open mode to `O_RDWR`, improving compatibility with NFSv4 filesystems.
  * **WARNING:** This change may introduce lock-related issues under certain
    conditions, as identified by upstream maintainers. Use with caution in
    production environments. (See [upstream
    discussion](https://github.com/erco77/newsd/pull/4) for details.)

## Usage

For detailed installation instructions and usage, please refer to the original
project's README: [newsd README](https://github.com/erco77/newsd).

## Branching Strategy

- **`master`**: Used to synchronize with the upstream project.
- **`develop`**: This is the main development branch, where all feature branches
  are merged before being considered stable. It holds the current working
  version of the project.
- **`feat/..`**: Used for developing new features and changes.

## License & Credits

* Original author: Greg Ercolano, Michael Sweet.
* Licensed under GPL 2.0 or later.