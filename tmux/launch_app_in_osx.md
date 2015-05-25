# Launch applications from tmux in OSX

In OSX tmux is changing the bootstrap to system domain when it shouldn't [(issue in macports)](https://trac.macports.org/ticket/18357). Older versions of launchd worked around this bug in tmux, but the rewritten launchd in OS X Yosemite does not work around this tmux bug.

Solution using `reattach-to-user-namespace`:

```
brew install reattach-to-user-namespace
```

then add following line in `.tmux.conf`:

```
set -g default-command "reattach-to-user-namespace -l /bin/bash"
```

