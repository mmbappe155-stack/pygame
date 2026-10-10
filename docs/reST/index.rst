py -m pip install pygame
import pygame

# Initialiser Pygame
pygame.init()

# Creer la fenetre du jeu
fenetre = pygame.display.set_mode((800, 600))
pygame.display.set_caption("Abysso Game")

# Definir les couleurs
BLEU = (40, 100, 200)
VERT = (50, 220, 100)

# Creer le personnage
joueur_x = 375
joueur_y = 275
vitesse = 5

# Boucle principale du jeu
jeu_en_cours = True

while jeu_en_cours:
    for evenement in pygame.event.get():
        if evenement.type == pygame.QUIT:
            jeu_en_cours = False

    # Lire les touches du clavier
    touches = pygame.key.get_pressed()

    if touches[pygame.K_LEFT]:
        joueur_x -= vitesse
    if touches[pygame.K_RIGHT]:
        joueur_x += vitesse
    if touches[pygame.K_UP]:
        joueur_y -= vitesse
    if touches[pygame.K_DOWN]:
        joueur_y += vitesse

    # Dessiner le fond et le personnage
    fenetre.fill(BLEU)
    pygame.draw.rect(fenetre, VERT, (joueur_x, joueur_y, 50, 50))

    # Actualiser l'affichage
    pygame.display.flip()

    # Limiter la vitesse du jeu
    pygame.time.Clock().tick(60)

pygame.quit()py abysso_game.py
