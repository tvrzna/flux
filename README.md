# Flux &ndash; Lightweight CI Server

Flux is a simple, [Flask][] based continuous integration server
that responds to push events triggered by [Gogs][] and GitHub.

For security reasons, Flux should be deployed over an SSL
encrypted proxy pass server (eg. via NGinx) and only for
internal purpose since it does not provide any mechanism
to prevent bad code from being executed.

__Development Status__ alpha (active)

__What's the license, duh?__ See [#6](https://github.com/NiklasRosenstein/flux/issues/6).

__Screenshots__

<table><tr>
  <td><p align="center">Dashboard</p><a href="http://i.imgur.com/je9SrzQ.png"><img src="http://i.imgur.com/je9SrzQ.png"></a></td>
  <td><p align="center">Repository Overview</p><a href="http://i.imgur.com/sj85Pav.png"><img src="http://i.imgur.com/sj85Pav.png"></a></td>
  <td><p align="center">Repository Settings</p><a href="http://i.imgur.com/0cHh7ui.png"><img src="http://i.imgur.com/0cHh7ui.png"></a></td>
  <td><p align="center">Build Details</p><a href="http://i.imgur.com/hXKJhLs.png"><img src="http://i.imgur.com/hXKJhLs.png"></a></td>
</tr></table>

__Features__

* [x] Lightweight and easy to deploy
* [x] Operational on Windows, Linux and Mac OS
* [x] Supports [Gogs][] & GitHub
* [x] Web interface to view realtime build queue, build logs
      and download artifacts with user access control

__Todo__

* [ ] Support for GitLab and BitBucket [#12](https://github.com/NiklasRosenstein/flux/issues/11)
* [ ] Decide on a license [#6](https://github.com/NiklasRosenstein/flux/issues/6)
* [ ] Distributed/multi-platform builds with build slaves [#9](https://github.com/NiklasRosenstein/flux/issues/9)
* [ ] Built-in SSL support using pyOpenSSL [#10](https://github.com/NiklasRosenstein/flux/issues/10)
* [ ] Ability to re-queue builds [#11](https://github.com/NiklasRosenstein/flux/issues/11)

__Requirements__

* Python 3
* Git 2.3 (for `GIT_SSH_COMMAND`)
* [Flask][]
* [SQLAlchemy][]

__Configuration__

Check out [`flux_config.py`](flux_config.py) for the configuration
template and the parameter documentation.

__Installation__

```
$ git clone https://github.com/NiklasRosenstein/flux.git
$ cd flux
$ virtualenv --python python3 .env
$ source .env/bin/activate
(.env) $ pip install -r requirements.txt
(.env) $ ./flux_run.py
```

__Additional Links__

* [Gogs Webhook](https://gogs.io/docs/features/webhook)
* [GitHub Push](https://developer.github.com/v3/activity/events/types/#pushevent)
* [GitLab Push](https://gitlab.com/gitlab-org/gitlab-ce/blob/master/doc/web_hooks/web_hooks.md#push-events)
* [BitBucket Push](https://confluence.atlassian.com/bitbucket/event-payloads-740262817.html#EventPayloads-Push)

  [Flask]: http://flask.pocoo.org/
  [SQLAlchemy]: http://www.sqlalchemy.org/
  [Gogs]: https://gogs.io/
