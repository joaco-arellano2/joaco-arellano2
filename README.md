import pygame

# Inicializar pygame
pygame.mixer.init()

# Ruta del archivo de sonido
ruta_sonido = input("Ingresa la ruta del archivo de sonido que deseas reproducir (mp3 o wav): ")

# Cargar el sonido
try:
    pygame.mixer.music.load(ruta_sonido)
    print("Reproduciendo sonido...")
    pygame.mixer.music.play()
    
    # Mantener el programa activo mientras el sonido se reproduce
    while pygame.mixer.music.get_busy():
        pass

    print("Sonido finalizado.")
except pygame.error as e:
    print(f"No se pudo reproducir el sonido. Error: {e}")
    
