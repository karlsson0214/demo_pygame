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

'''
    plum_image = pygame.image.load("img/plum.png")
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
'''
Fiender
---------------

### förflyttning

### spawn

GUI
-----------

### knappar