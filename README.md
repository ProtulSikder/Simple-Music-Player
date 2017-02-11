'''A very simple music player
   using pygame

   By: Nasir Sikder Protul
'''

import glob
from pygame import mixer,time

#Put all your music files of a directory of format .mp3 in the list
ls = [i for i in glob.glob("F:\MP3\*.mp3")]

#Loop through your list.
for i in ls:
    mixer.init()

    #Load the music file
    mixer.music.load(i)

    #Play the loaded music
    mixer.music.play()

    '''A conventional loop don't work in playing a list of songs.
       So I was needed to hold the looping while
       one music is playing.You can try to loop without the
       following while part.If you do that only the last music
       file will be played.
     '''  
    while mixer.music.get_busy():
        time.Clock().tick(30000)

print("Playing over!")
