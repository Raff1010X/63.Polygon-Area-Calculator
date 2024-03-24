# [freeCodeCamp Scientific Computing with Python](https://www.freecodecamp.org/learn/scientific-computing-with-python)

## [Polygon-Area-Calculator](https://www.freecodecamp.org/learn/scientific-computing-with-python/scientific-computing-with-python-projects/polygon-area-calculator)

My git repo: https://github.com/Raff1010X/01.Roadmap

```python
class Rectangle:
    def __init__(self, width, height):
        self.width = width
        self.height = height
    
    def __str__(self):
        return f'{self.__class__.__name__}(width={self.width}, height={self.height})'

    def set_width(self, width):
        self.width = width
    
    def set_height(self, height):
        self.height = height

    def get_area(self): 
        return self.width * self.height
    
    def get_perimeter(self): 
        return 2 * self.width + 2 * self.height
    
    def get_diagonal(self): 
        return ((self.width ** 2 + self.height ** 2) ** .5)
    
    def get_picture(self):
        if max(self.width, self.height) > 50: 
            return 'Too big for picture.'
        picture = ''
        for lines in range(self.height):
            picture += '*' * self.width + '\n'
        return picture

    def get_amount_inside(self, shape):
        vertical = self.width // shape.width
        horizontal = self.height // shape.height
        return vertical * horizontal
        

class Square(Rectangle):
    def __init__(self, side):
        self.width = side
        self.height = side
    
    def __str__(self):
        return f'{self.__class__.__name__}(side={self.width})'

    def set_side(self, side):
        self.width = side
        self.height = side
    
    def set_width(self, width):
        self.set_side(width)

    def set_height(self, height):
        self.set_side(height)


# tests
rect = Rectangle(50, 511)
print(rect.get_area())
rect.set_height(3)
print(rect.get_perimeter())
print(rect)
print(rect.get_picture())

sq = Square(9)
print(sq.get_area())
sq.set_side(4)
print(sq.get_diagonal())
print(sq)
print(sq.get_picture())

rect.set_height(8)
rect.set_width(16)
print(rect.get_amount_inside(sq))
```
