A very work-in-progress library of fabric stuff for deploying twisted
infrastrucutre. The immeidate goal is to be able to redeploy everything from
cube onto dornkirk.

This package is a library of tools for deploying individual services. It also
currently contains a fabfile for global configuration of dornkirk.

The idea is that each individual service (e.g., t-names, www-data, trac,
buildbot) will have a configuration repo with a fabfile that uses braid to
deploy itself on a given machine.


Currently Supported Services
============================

- [t-names](https://github.com/twisted-infra/t-names)
- [twisted-website](https://code.launchpad.net/~tom.prince/twisted-website/twisted-website-braided)
- [buildbot](https://github.com/twisted-infra/twisted-buildbot-configuration)
- [diffresource](https://code.launchpad.net/~tom.prince/twisted-trac-integration/braided-diffresource)
- [kenaan](https://github.com/twisted-infra/kenaan)
- [hiscore](https://twistedmatrix.com/~tomprince/hiscore)
- [trac (WIP)](https://github.com/twisted-infra/trac-config)


style-notes
===========
Things that want to root want to be run with `sudo`, and files `put` with
`use_sudo`. When dealing with things that want to be run as other users,
`run` should be used, and a ssh connection as that user (with
`settings(user='user')` or the like. `braid.base.sshConfig` sets things up so
anybody with root keys can log-in as any user in the `service` group.
