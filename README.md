# Game
#Abhishek Shinde (ams9mb) and Grant Kim (gtk4cf)

import pygame
import gamebox
camera = gamebox.Camera(1000,600)

game_start = True
game_on = False

def tick(keys):

    global game_start
    global game_on

    if game_start:
        camera.clear('white')
        camera.draw("Infinite Runner", "Arial", 50, "blue", 500, 300)
        camera.draw("Abhishek Shinde (ams9mb) and Grant Kim (gtk4cf)", "Arial", 20, "blue", 500, 350)
        camera.draw("Instructions: Press SPACE to jump and survive as long as you can...", "Arial", 25, "blue", 500, 500)

    if pygame.K_RETURN in keys:
        game_on = True
        game_start = False

    if game_on:

    camera.display()

ticks_per_second = 30

# keep this line the last one in your program
gamebox.timer_loop(ticks_per_second, tick)
