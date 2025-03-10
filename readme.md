Rita
---------------------

rektangel, cirkel, ...

01_draw_move_shapes.py

Text
----------------
02_text.py


Förflyttning
----------------------

### Tangentbord

03_move_left_right.py

### Mus

Plocka föremål och poäng
----------------

04_droppings...

Tre olika sätt att spara data för ett plommon finns. Kort genomgång nedan. 
Vilket alternativ gillar du bäst? Välj motsvarande fil att arbeta i.

### Data för ett plommon i en lista
04_droppings_v1_list.py


    plum_image = pygame.image.load("img/plum.png")
    plums = []
    plum_radius = (plum_image.get_width() + plum_image.get_height()) / 4
    # plums
    # Chance of having a new plum.
    if (random.randint(0, 100) < 2):
        plum_x = random.randint(0, 600)
        # Add plum coodinates to the list.
        plums.append([plum_x, 0, 0]) # x, y, speed

    # move plums
    for plum in plums:
        # Move the plum down.
        plum[1] += plum[2]
        # Increase the speed of the plum.
        plum[2] += 0.2
        # Remove plums that have gone off the screen.
        if plum[1] > 800:
            plums.remove(plum)
        # Check for collisions with the snake.
        if collides(snake_x, snake_y, snake_radius, 
                    plum[0], plum[1], plum_radius):
            plums.remove(plum)

### Data för ett plommon i dictionary
04_droppings_v2_dictionary.py

    plum_image = pygame.image.load("img/plum.png")
    plums = []
    plum_radius = (plum_image.get_width() + plum_image.get_height()) / 4

    # plums
    # Chance of having a new plum.
    if (random.randint(0, 100) < 2):
        plum_x = random.randint(0, 600)
        # Add plum coodinates to the list.
        plum = {}
        plum['x'] = plum_x
        plum['y'] = 0
        plum['speed'] = 0
        plums.append(plum) # x, y, speed
    
    # move plums
    for plum in plums:
        # Move the plum down.
        plum['y'] += plum['speed']
        # Increase the speed of the plum.
        plum['speed'] += 0.2
        # Remove plums that have gone off the screen.
        if plum['y'] > 800:
            plums.remove(plum)
        # Check for collisions with the snake.
        if collides(snake_x, snake_y, snake_radius, 
                    plum['x'], plum['y'], plum_radius):
            plums.remove(plum)

### Data för ett plommon i en sprite
04_droppings_v3_sprite.py

    plum_image = pygame.image.load("img/plum.png")
    plums = pygame.sprite.Group()
    plum_radius = (plum_image.get_width() + plum_image.get_height()) / 4

    # plums
    # Chance of having a new plum.
    if (random.randint(0, 100) < 2):
        plum_x = random.randint(0, 600)
        # Add plum coodinates to the list.
        plum = pygame.sprite.Sprite()
        plum_width = random.randint(20, 40)
        plum_radio = plum_image.get_height() / plum_image.get_width()
        plum.image = pygame.transform.scale(plum_image, (plum_width, plum_width * plum_radio)) 
        plum.rect = plum.image.get_rect()
        plum.rect.x = plum_x
        plum.rect.y = 0
        plum.speed = 0
        plum.radius = (plum.image.get_width() + plum.image.get_height()) / 4
        plums.add(plum) # x, y, speed
    
    # move plums
    for plum in plums:
        # Move the plum down.
        plum.rect.y += plum.speed
        # Increase the speed of the plum.
        plum.speed += 0.2
        # Remove plums that have gone off the screen.
        if plum.rect.y > 800:
            plums.remove(plum)
        # Check for collisions with the snake.
        plum = pygame.sprite.spritecollideany(snake, plums)
        if plum != None:
            plums.remove(plum)


Fiender
---------------

### förflyttning

### spawn

GUI
-----------

### knappar