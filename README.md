# tmux snap package -devmode only

Note: This snapcraft.yaml was developed from:

 - https://github.com/shawn111/tmux.snap
 - https://github.com/chrmod/snap-tmux
 
This snap package is for tmux for `devmode` only.  As such, it can be installed
(currently) on Ubuntu Core 16, whereas `classic` mode snaps can't be installed.

I'm not putting it in the snap store as it really is a developer tool ONLY and
shouldn't really be used on Ubuntu Core 16 as it shouldn't be needed except
when mucking around on a system (like I am!)

Also, it's not an overly polished snap; e.g. the command could be worked out
properly, but I did enough to make it work for me.

## Steps

1. Clone the repo.
2. In the same directory as the snapcraft.yaml run `snapcraft snap`
3. This will build the `tmux-devmode_2.6_amd64.snap`.
4. Copy this to your Ubuntu Core 16 device; (or you may have been building this
   on the device using the `classic` snap).
5. Install the snap using `snap install tmux-devmode_2.6_amd64.snap --dangerous --devmode`
6. Connect the snap to the home directory: `snap connect tmux-devmode:home`

To actually run tmux with a .tmux.conf file, I've set up an alias on my Ubuntu
Core machine in `.bash_aliases` as:

```bash
alias tmux='tmux-devmode.tmux -f ~/.tmux.conf'
```
