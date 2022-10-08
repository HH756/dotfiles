# DOTFILES

![PolybarConfiguation](https://user-images.githubusercontent.com/67608772/187841967-6da9a54f-3c37-4356-91ac-68971878ad09.png)
![Screenshot_2022-09-01_10-15-34](https://user-images.githubusercontent.com/67608772/187973794-35b71133-9c1b-4064-9c7c-eb1d65cb6459.png)
![image](https://user-images.githubusercontent.com/67608772/194721263-981c4bd4-63e0-46a5-99e2-acf1de5e7bee.png)
font - Typori ^
![Screenshot_2022-09-01_00-20-28](https://user-images.githubusercontent.com/67608772/187855602-370ba128-f7f5-425d-a7c3-6f26bd81bcde.png)
font - IBM Plex Mono ^

## Polybar icons not working
There are two fonts set inside the config file, I trust you can locate where they are declared. Font-0 is to used to declare the font you want any text or numbers to be shown in (these fonts usually can't draw icons, more on that in a sec). When polybar is run, it will begin drawing itself, the colours, width, radius and eventually the characters and icons. As polybar draws the characters it attemps to draw each character in font-0, however, as I mentioned a second ago, most fonts don't support the icons commonly used in Linux ricing. So they will present an error if you try to draw icons with them. So to allow us to see icons, while also not limiting ourselves to *one* icon font we can use a technique where we cycle fonts. As an example, let's pretend our bar has only an, "A" and a "W". When run polybar will attemp to draw the "A" with font-0, and in our example, we'll say it succeeds. However, when attemping the second character, the "W". Font-0 throws an error, declaring it doesn't recognize the character, and therefore can't draw it. This is the common error in the terminal `unmatched character`. After font-0 throws the error polybar cycles to font-1 (in my case NotoSansMono Nerd Font) which is an icon font, and does support the "W". At which point, it will be promptely rendered.

## Machine Specific Polybar Actions
I have set my openbox autostart to start polybar pulling the config from ~/Code/dotfiles/polybar/config. This is my dotfiles repo, you can do the same if you wish. If not, though, you will be required to change the openbox autostart file, changing the polybar entry from `polybar -r --config=~/Code/dotfiles/polybar/config.ini` to (for default config paths) `polybar -r` this will load the default polybar configuration file, or if you choose to do so, a config you moved to the default location. By default polybar pulls from `~/.config/polybar/config.ini`, `/etc/xdg/polybar/config.ini1`, or `/etc/polybar/config.ini`. You can move my, or any, configuration file to any of these locations and it will work without the `--config=<path to config>` flag in the terminal or autostart file.

## ALACRITTY USER SPECIFIC
The Alacritty window position will be different for everyone, based on preference and screen size. I have Alacritty configured for a high resolution display; the window position will be disturbed up on lower resolution displays. You will have to change the window size in the Alacritty config file yourself, to match your preference and screen size. 
