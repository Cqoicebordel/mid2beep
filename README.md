# mid2beep
Play midi files on the motherboard speaker/buzzer

## Licence

Do whatever you want with this, just keep my pseudo associated with it.

## Prerequisite

* Have a speaker in your PC. I'm not talking about the one to listen to music, but the one that beeps when you do something wrong.
* Have `beep`, `midi2abc`, and `bc` installed (they should be in the repo of your Linux distro, the second under the name `abcmidi`)

## Install

Copy the script `mid2beep` in a folder in your `$PATH` (or any folder you want to run this script from), and make it executable (`chmod +x mid2beep`)

And that's all !

## Usage

`mid2beep` ships with good default values (I hope). So all you have to do is to run it with `mid2beep -m=/home/midifile.mid` and everything should be fine.

## Tips/Tricks/Traps

The program works the best with monophonic midi files. But you may be able to have something nice with polyphonic files too. You'll just have to choose the right channel for it.
By default, the channel 1 is used. You can use the option `-c=n` or `--channel=n` to choose the channel you want.  
To see the available channels, you might want to use the `-i` or `--info` option, that prints some infos about the file you are trying to use, including a list of all channels.  
If you want to script it, all that output of infos might not suit you. You can disable the progress info with `-p` or `--noprogress`, and you can disable the output of the `beep` command using `-b` or `--hidebeep`. Or maybe, you are working on a piece, and so, you don't want to listen to each iteration, so you can disable the sound by using `-q` or `--quiet`.  
Finally, maybe the tune doesn't have the right speed to your ears. It should automagically detect the right speed, but you might want to adjust the speed manually. In that case, use `-s=n` or `--speed=n`. Note that `n` isn't necessarily an integer (eg. 0.5 is half speed)

When using polyphonic files, I used the brute force method to render them : play only the first of two notes that start at the same time. It can create issues of rythm, but hey, it's a good starting point :)
