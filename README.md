# GetMITHack

GetMIT is a spinoff of 2048 in which you merge different colleges until you get to MIT, and it's very popular in my school right now. People around my school post their impressive scores in an effort to be the best, but I haven't been able to show off any high scores because I'm just not very good at the game. I kept on losing and losing, never getting farther than Cornell (the 256 block), and as my dream of getting to MIT grew more and more distant, my gaze shifted from the game grid to the url: http://mitchgu.github.io/GetMIT/. I realized the code was on Github at https://github.com/mitchgu/GetMIT and I realized that I didn't have to be good at the game. I just needed a photo of me winning

## Commence Operation Win

I decided I wanted to hack the game, but before I could decide how I would hack it, I had to understand what the code did. I started off by looking at the .js folder to find that I didn't really understand all the javascript--I could understand big chunks of code, but not the specifics, which made it difficult to hack. I decided to take a step back and take a more methodical approach.

## The Approach
Heres what I was going to do:
1. Check the img folder which held the logos of all the schools used in the game in .png files
2. I then checked the main.css file in the style folder for .png files and I found the most crucial part of my investigation: the **tile object**  Each college was a seperate tile object and was named after its corresponding number in 2048 (tile.tile-number)

I experimented with this css file to confirm my thoughts on the css file by changing the png file in the tile.tile-2 object to the MIT.png file and found that the game was showing the Mit logo in place of the Caltech logo. I then decided to check the .js in order to find the tile object there.

## End Game

I now found the tile object appearing in the GameManager file. This file set up the game, and as I scrolled down I found that this.score was set to 0 in the beginning of the game. My first instinct was to change this to 10,000 and after making this change, my score started higher than I had ever gotten it myself. As I scrolled down farther I found the 'value' variable in line 62 (that was a property of the tile object). This variable holds the '2048 value' of the tile, so if I change the value from 2 to 64, I start off on the 6th level.

## Future Changes

I would like to make the end game look more realistic. I am considering bringing the starting value back down to 2 but changing the merging of the tiles so that the merged tiles would be 4x of what they were instead of 2x (as if it went from 2 to 8 to 32 in 2048). This would mean that the final position of the board (when no more moves can be made) would include the 2 and 4 blocks, making it look a lot more realistic (as there are no other ways to lose the game).
