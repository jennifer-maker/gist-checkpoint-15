1. This file declares a class, `Player`, instantiates it, and assigns it to a global `player` variable.
2. The `Player` class contains four methods:
    - `constructor()`
    - `playPause()`
    - `skipTo()`
    - `setVolume()`
3. The `constructor()` method sets initial values for the `currentlyPlaying`, `playState`, `volume`, and `soundObject` properties.
    - `currentlyPlaying` is set to the first item in `album.songs`.
    -  The initial `playState` is `"stopped"`.
    -  The `volume` is set to the number `80`.
    -  The `soundObject` instantiates a new `buzz.sound` object using the `soundFileUrl` property of `this.currentlyPlaying`. The `buzz` variable doesn't appear to be initialized here, so presumably it's a dependency loaded elsewhere.
4. The `playPause()` method accepts one parameter, `song`. It sets it to `this.currentlyPlaying` by default. It checks to see if `this.currentlyPlaying` is different from `song`, and if so, it:
    - Stops the `soundObject` property.
    - Removes the `"playing"` and `"paused"` classes from the `element` property of `this.currentlyPlaying`.
    - Sets `this.currentlyPlaying` to the function's parameter, `song`.
    - Changes the `playState` property to `"stopped"`.
    - Instantiates a new sound object using `this.currentlyPlaying`, which was just updated to `song`.

5. The 'getDuration()' method accepts no parameters. It calls the soundObject's getDuration() method, and returns the value.

6. The 'getTime()' method accepts no parameters it calls the soundObject's getTime method, and returns the value.

7. The 'skipTo(percent)' method accepts one parameter, the percent

    - if the player state is not 'playing', immediately return
    - otherwise -- call the sound object's setTime method -- pass in the function argument/100 * the song's duration
8. The 'setVolume(percent)' method accepts one parameter, the percent

    - it sets the player's volume to the function argument
    - it calls the soundObject's setVolume method, again using the function argument
