from numpy import *

import sys, random, math, pygame
from pygame.locals import *
# from math import sqrt,cos,sin,atan2,pi

#Colors
white = 255, 240, 200
black = 20, 20, 40
gray  = 80, 80, 80
red   = 255, 0, 0
green = 0  , 255, 0
cyan  = 0, 183, 235

#constants
XDIM = 1200
YDIM = 800
WINSIZE = [XDIM, YDIM]

# ----  World definition ----
world = [ (-550,  300, -400,  300),
          (-400,  300, -400,  280),
          (-400,  280, -300,  280),
          (-300,  280, -300,  200),
          (-300,  200, -200,  200),
          (-200,  200, -200,  250),
          (-200,  250,  200,  250),
          ( 200,  250,  200,  220),
          ( 200,  220,  550,  220),
          ( 550,  220,  550, -320),
          ( 550, -320, -100, -320),
          (-100, -320, -100, -260),
          (-100, -260, -500, -260),
          (-500, -260, -550, -260),
          (-550, -260, -550,  300)]
n_walls = 15

world_tranform =[]
#--------------------------------

# ---- Funtions -----------------
def drawFrame(screen):
    screen.lock()

    pygame.draw.line(screen,red, ( -5.0+(XDIM/2),-1*( 0.0)+(YDIM/2) ),( 30.0+(XDIM/2),-1*( 0.0 )+(YDIM/2) ) )
    pygame.draw.line(screen,green, (  0.0+(XDIM/2),-1*(-5.0)+(YDIM/2) ),(  0.0+(XDIM/2),-1*(30.0 )+(YDIM/2) ) )

    screen.unlock()


def drawWorld(screen):
    #origin in the center of the screen
    for elem in world:
        world_tranform.append( ( elem[0]+(XDIM/2),-1*elem[1]+(YDIM/2)  ) )
        world_tranform.append( ( elem[2]+(XDIM/2),-1*elem[3]+(YDIM/2)  ) )


    screen.lock()
    for i in range(0,n_walls):
        pygame.draw.line(screen, white, world_tranform[i*2],world_tranform[i*2+1])

    screen.unlock()
#--------------------------------



def main():
    print("Init 2D Simulator...")


    #initialize and prepare screen
    pygame.init()
    screen = pygame.display.set_mode(WINSIZE)
    pygame.display.set_caption('2D Simulator')

    loop = True

    fps = 30
    clock = pygame.time.Clock()

    while loop:

        screen.fill(black)

        # ---- Key handler ----
        for event in pygame.event.get():
            #Press esc to quit
            if event.type == QUIT or (event.type == KEYDOWN and event.key == K_ESCAPE ):
                pygame.quit()
                sys.exit("Quit")
        #---------------------------

        
        #World
        drawWorld(screen)
        drawFrame(screen)

        # display
        pygame.display.update()
        clock.tick(fps)


# if python says run, then we should run
if __name__ == '__main__':
    main()
