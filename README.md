# testing-pygame
import pygame

pygame.init()
screen = pygame.display.set_mode((600,800))
pygame.display.set_caption("develop")
WHITE = (255, 255, 255)
player_x = 300
player_y = 750
player_width = 20
player_height = 20
player_speed = 0.1

Game_on = True
while Game_on:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            Game_on = False



    keys = pygame.key.get_pressed()
    if keys[pygame.K_a]:
        player_x -= player_speed

    if keys[pygame.K_d]:
        player_x += player_speed

    if keys[pygame.K_s]:
        player_y += player_speed

    if keys[pygame.K_w]:
        player_y -= player_speed

    screen.fill((0, 0, 0))

    player = pygame.draw.rect(screen, WHITE, (player_x, player_y, player_width, player_height))


    pygame.display.update()





pygame.quit()
