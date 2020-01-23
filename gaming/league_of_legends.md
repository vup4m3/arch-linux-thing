# League of legends installation guide 

## INSTALATION

Make sure you have lastest drivers for your GPU (64 and 32 bit!)

[AMD](https://wiki.archlinux.org/index.php/AMDGPU)

[NVIDIA](https://wiki.archlinux.org/index.php/NVIDIA) 

Install Vulkan (64 and 32 bit!)

    https://wiki.archlinux.org/index.php/Vulkan

Install Wine

    https://wiki.archlinux.org/index.php/Wine

Install Lutris from AUR

    https://lutris.net/downloads/

Go to https://lutris.net/games/league-of-legends/ and click install in first installation with golden dot(MPORTANT: Uncheck 'Launch League of Legends now?' at the end of the League install wizard.)

Sometimes you must run this command in terminal if game wont run: sudo sh -c '`sysctl -w abi.vsyscall32=0'`

## OPTIMALIZATION

### Lutris

    Go to configure tab in lutris

    Go to "runner options" tab

    Make sure you have this options, if not change it

    "Enable D9VK" - Enabled (Better performance)

    "D9VK Version" - Use the latest (Best performance)

    "Enable Esync" - Enabled (Its like +100 Fps)

    "Use GLSL" - Disabled (Making Client a lot smoother and boosting fps in game a bit)

    Go to "System options" tab

    Make sure you have this options, if not change it

    "Prefer system librares" - Enabled

    "Disable desktop effects" - Enabled (Its disables compositing in your DE, you might want disable it manually too)

    In Environment variables you can add Key: "DXVK_HUD" Value: "1" It will show fps driver version and vulkan version in left corner, its not usefull becouse you can turn on fps counter in league by "ctrl + f" but if that HUD isn't showing up it means that you have problem with vulkan/D9VK

    In Enviromental variables you can add (KEY) - (Value) Its like +20 FPS

    (PBA_Disbale) - (0)

    (__GL_THREADED_OPTIMIZATIONS) - (1)

    (mesa_glthread) - (true)

    (pulse_latency) - (true)

### Client

    Lunch game, if the bugsplat is showing up just close it and if in lutris the big "Stop" button will change to "Play" click it again, if the button is "Stop" for longer time just wait its propably will launch if not you can post logs in comment and i or someone else will try to help

In client settings turn on

    Enable low spec mode

    Close client during the game

    In interface tab uncheck

    Enable HUD Animations

In-Game Video settings

    Lower settings - better fps (obvious)

    Turn off

    Character inking

    Anti aliasing

    Wait for vertical sync (it will cap your fps to your monitor refresh rate, if you have 60Hz monitor your FPS will be capt at 60, 120Hz - 120 FPS and so on)

    Cap your fps at +1 step that your monitor Hz, if i have 60Hz monitor i cape fps at 120 it will not overload your GPU and CPU but give your PC a buffer
