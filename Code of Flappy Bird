import pygame
import random

# Inisialisasi Pygame
pygame.init()

# Warna yang digunakan
WHITE = (255, 255, 255)
BLACK = (0, 0, 0)

# Ukuran layar
SCREEN_WIDTH = 400
SCREEN_HEIGHT = 600

# Membuat layar permainan
screen = pygame.display.set_mode((SCREEN_WIDTH, SCREEN_HEIGHT))
pygame.display.set_caption('Flappy Bird')

# Menggambar burung
bird_img = pygame.image.load('bird.png')
bird_width = 50
bird_height = 35
bird_x = 50
bird_y = SCREEN_HEIGHT // 2 - bird_height // 2

# Menggambar pipa
pipe_img = pygame.image.load('pipe.png')
pipe_width = 70
pipe_height = 400
pipe_x = SCREEN_WIDTH
pipe_y = random.randint(-pipe_height // 2, pipe_height // 2)

# Kecepatan dan gravitasi
bird_movement = 0
gravity = 0.25
bird_jump = -5

# Fungsi untuk menggambar burung
def draw_bird(x, y):
    screen.blit(bird_img, (x, y))

# Fungsi untuk menggambar pipa
def draw_pipe(x, y):
    screen.blit(pipe_img, (x, y))

# Memulai game
running = True
while running:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False
        if event.type == pygame.KEYDOWN:
            if event.key == pygame.K_SPACE:
                bird_movement = bird_jump

    # Gerakan burung
    bird_movement += gravity
    bird_y += bird_movement

    # Menampilkan background
    screen.fill(WHITE)

    # Menampilkan burung dan pipa
    draw_bird(bird_x, bird_y)
    draw_pipe(pipe_x, pipe_y)

    # Memperbarui posisi pipa
    pipe_x -= 3
    if pipe_x <= -pipe_width:
        pipe_x = SCREEN_WIDTH
        pipe_y = random.randint(-pipe_height // 2, pipe_height // 2)

    # Memperbarui layar
    pygame.display.update()

    # Batas atas dan bawah layar
    if bird_y <= 0 or bird_y >= SCREEN_HEIGHT - bird_height:
        running = False

# Menutup Pygame
pygame.quit()
