# Bevy 0.9
This is my own fork for the perposes for updating to bevy 0.9, see the original at https://github.com/cadyn/bevy_crt

changes:
- added all #[derive(Resource)]
- overode Framecount2dPlugin<M> is_unique() to return true
- ExtractResourcePlugin::<ExtractedFrameCount>::default() was being added multiple times, moved to build_common() in plugin.rs
- removed BufferUsages::MAP_READ and BufferUsages::MAP_WRITE from line 47 in plugin.rs, I don't actually know what I'm doing here but removing this works?

below is the original readme.

# bevy_crt
CRT Effect for the Bevy Engine
My first crate for rust in general, as well as for the Bevy engine.
Feedback and PRs are welcomed.

![2022-08-30 13-13-37](https://user-images.githubusercontent.com/35672377/187535191-5a59a122-fe55-41d6-9110-2740e7dab6e9.gif)

# Usage
To use the crate, you need to also include the shaders which you can get from the source code, or from a bundle that I will provide manually with each release.
Simply add the crate to your dependencies, then depending on your needs add either bevy_crt::plugin::Crt2dPlugin, or bevy_crt::plugin::Crt3dPlugin depending on which type of camera you need.
Do note that the plugin will create a camera which it expects you to use for your project. If you need to modify the camera in any way, Query for the bevy_crt::plugin::PrimaryCamera component and you will find the camera and transform attached.

# Credit
The original shaders used in this project were created by someone known as guest.r on the libretro forums. I've done the work of adapting them to work with the Bevy engine, but I did not create these shaders myself.
Original forum post: https://forums.libretro.com/t/new-crt-shader-from-guest-crt-guest-advanced-updates/25444

# License
Everything under the src folder was written by me or adapted from the Bevy source code and/or examples. All of my code is licensed under GPL 3.0, as well as the shaders provided in the assets folder.

# Note
This project is likely going to be on the sideline for a bit. There are definitely improvements I want to make, but I only created this package to use it in my current main project which is https://github.com/cadyn/Pong-Multiplayer-RS I will be keeping an eye here for an issues which prevent use of the package and fixing them as well as updating it alongside my main project. The big things like giving more fine tuned control over the shaders and perhaps trying to make the code more readable and maintainable are likely going to have wait until I've reached a point in my main project where I'm more fine with shifting focus.
