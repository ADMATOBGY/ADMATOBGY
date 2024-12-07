pip install pygame
import pygame
import sys

# إعداد Pygame
pygame.init()
WIDTH, HEIGHT = 800, 800
SCREEN = pygame.display.set_mode((WIDTH, HEIGHT))
pygame.display.set_caption("لعبة الشطرنج")

# ألوان
WHITE = (255, 255, 255)
BLACK = (0, 0, 0)

# رسم اللوحة
def draw_board():
    block_size = WIDTH // 8
    for row in range(8):
        for col in range(8):
            color = WHITE if (row + col) % 2 == 0 else BLACK
            pygame.draw.rect(SCREEN, color, (col * block_size, row * block_size, block_size, block_size))

def main():
    clock = pygame.time.Clock()

    while True:
        for event in pygame.event.get():
            if event.type == pygame.QUIT:
                pygame.quit()
                sys.exit()

        draw_board()
        pygame.display.flip()
        clock.tick(60)

if __name__ == "__main__":
    main()
