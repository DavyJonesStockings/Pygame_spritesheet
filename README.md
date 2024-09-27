# Pygame_spritesheet
This is a module for PyGame that will return pygame.Surface objects (sprite images) from a spritesheet, either individually or as a list of many. This is significantly more efficient
than loading every image into PyGame. Additionally, it will prevent cluttering of code with large lists of PyGame image.load calls. This was created by me in 2021,
but has since been updated and improved throughout the past few years.

# Documentation
While this module is rather small and can be easily understood with a small amount of time looking at the code, this is an easier alternative to that.

## image_at()

  `image_at(rect, colorkey, scale) -> pygame.Surface`

  This function returns a pygame.Surface object with the specified image loaded on. Note that these surfaces are converted surfaces.
  
  (tuple)`rectangle`: (x position, y position, width, height)

  (int)`scale`: Default value `1`. This is a scalar integer, which scales the image accordingly. If your sprite is already at the correct dimensions for your project, you can ignore this option.

  (int)`colorkey`: Default value: `None`. Set to -1 to take the pixel at (0,0) as the transparency colorkey. This means that every pixel of the same exact color as the pixel at (0,0) will be 
  made transparent. If your spritesheet is already transparent how you want it, you can ignore this option.

## images_at()

  `images_at(rects, scale, colorkey)`

  This function returns a list of pygame.Surface objects

  (list)`rects`: A list of rects you want to have loaded in a single list, formatted as (x position, y position, width, height).

  (int)`scale`: Default value `1`. [See image_at()](#image_at)

  (int)`colorkey`: Default value `None`. [See image_at()](#image_at)

## load_row()

  `load_row(rect, image_count, scale, colorkey)`

  This function returns a list of pygame.Surface objects from a row. The user should specify the size of each sprite, and how many sprites there are. This function only works under the
  assumption that each sprite has the same dimensions.
  Note that, while all the sprites you want from this must be in the same row, you can get a collection of sprites without taking the whole row.
  This scans the spritesheet from left to right, starting with the sprite you provide through `rect`.

  (tuple)`rect`: (x position, y position, width, height). Dimensions of the first sprite and its location on the sprite sheet. This should be uniform for all sprites in the row.

  (int)`image_count`: This is how many pictures are in the row. Remember, the stylesheet is scanned left to right.

  (int)`scale`: Default value `1`. [See image_at()](#image_at)

  (int)`colorkey`: Default value `None`. [See image_at()](#image_at)

## load_column()

  `load_column(rect, image_count, scale, colorkey)`

  **This function works the same as [load_row()](#load_row)**

  This function returns a list of pygame.Surface objects from a column. The user should specify the size of each sprite, and how many sprites there are. This function only works under the
  assumption that each sprite has the same dimensions.
  Note that, while all the sprites you want from this must be in the same column, you can get a collection of sprites without taking the whole column.
  This scans the spritesheet from top to bottom, starting with the sprite you provide through `rect`.

  (tuple)`rect`: (x position, y position, width, height). Dimensions of the first sprite and its location on the sprite sheet. This should be uniform for all sprites in the row.

  (int)`image_count`: This is how many pictures are in the row. Remember, the stylesheet is scanned left to right.

  (int)`scale`: Default value `1`. [See image_at()](#image_at)

  (int)`colorkey`: Default value `None`. [See image_at()](#image_at)