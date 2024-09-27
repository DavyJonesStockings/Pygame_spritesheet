# Pygame_spritesheet
This is a module for PyGame that will return pygame.Surface objects (sprite images) from a spritesheet, either individually or as a list of many. This is significantly more efficient
than loading every image into PyGame. Additionally, it will prevent cluttering of code with large lists of PyGame image.load calls. This was created by me in 2021,
but has since been updated and improved throughout the past few years.

# Documentation
While this module is rather small and can be easily understood with a small amount of time looking at the code, this is an easier alternative to that.

## image_at()

  `image_at(rectangle, colorkey, scale) -> pygame.Surface`

  This return a pygame.Surface object with the specified image loaded on. Note that these surfaces are converted surfaces.
  
  `rectangle`: (x position, y position, width, height)

  `colorkey`: Default value: `None`. Set to -1 to take the pixel at (0,0) as the transparency colorkey. This means that every pixel of the same exact color as the pixel at (0,0) will be 
  made transparent. If your spritesheet is already transparent how you want it, you can ignore this option.

  `scale`: Default value `1`. This is a scalar integer, which scales the image accordingly. If your sprite is already at the correct dimensions for your project, you can ignore this option.
