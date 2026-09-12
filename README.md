# x1-scripts

A collection of scripts I've written for my laptop.
Mostly focused on optimizing it for use as a media center.

It is safe to assume that most of these scripts depend on each other to function properly.

## [gpl3](./gpl3)

Add a copy of the [GNU General Public License v3](https://www.gnu.org/licenses/gpl-3.0.en.html)
to the current directory.

## [alert](./alert)

Display a flashing full-screen alert in huge text on every monitor. Highly configurable.

**Requires:** `gtk4-layer-shell`

## [qbittorrent-autopreview](./qbittorrent-autopreview)

After a torrent is added, automatically monitor it and play it as soon as it becomes playable.
This allows for watching movies almost immediately, assuming there's enough seeders.
Obviously, this only supports
[video container formats](https://en.wikipedia.org/wiki/Comparison_of_video_container_formats)
that allow for streaming.

**Uses:** `start_movie` to play the movie when ready

**Requires:** `gtk4-layer-shell`, `python-vlc`

## [start_movie](./start_movie)

Pause everything, make a loud noise, and open VLC with the provided file.

**Requires:** `mpv`, `playerctl`

## [intermission](./intermission)

Pause everything, and display a countdown.
Makes a loud noise and flashes violently when the countdown is over.

**Requires:** `mpv`, `playerctl`

## mode_switcher

A multi-part system for automating a lot of annoying tasks when switching between monitor setups.

### [mode_switcher_daemon](./mode_switcher_daemon)

Monitor for changes that would warrant switching modes, i.e. when a new monitor is plugged in.

**Uses:** `mode_switcher` to switch modes

### [mode_switcher](./mode_switcher)

Switch between Laptop, Desktop, and Television mode.
Changes a LOT of annoying things like audio output, screen resolution, brightness, bluetooth, Do Not Disturb mode, sleep inhibition, etc.

**Uses:** `mode_switcher_inhibitor` to inhibit sleep

**Requires:** `bluetoothctl`, `qdbus6`, `wpctl`, `kscreen-doctor`


### [mode_switcher_inhibitor](./mode_switcher_inhibitor)

Prevent automatic sleeping while this process is alive.
