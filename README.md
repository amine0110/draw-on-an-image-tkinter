# Draw on an image tkinter
To do this project, we need to work with Tkinter, because the best way to draw on an image is to create a `Tkinter` canvas, we put the image in the canvas then the drawing will be easier.
This draw will be using the `mouse`, so it will be a random shape.

## The steps
- Create the application
- Create a canvas
- Put an image on the canvas
- Draw lines on the canvas using the mouse

To create an empty GUI, there are only 3 lines of code, and here are:

```Python
from tkinter import *
app = Tk()
app.mainloop()
```

To create a canvas, you need only these 2 lines:
```Python
canvas = Canvas(app, bg='black')
canvas.pack(anchor='nw', fill='both', expand=1)
```

And these are the important part in this project, because they control the event of the mouse then convert each click into color to that pixel.
```Python
def get_x_and_y(event):
    global lasx, lasy
    lasx, lasy = event.x, event.y

def draw_smth(event):
    global lasx, lasy
    canvas.create_line((lasx, lasy, event.x, event.y), fill='red', width=2)
    lasx, lasy = event.x, event.y
```

----------------------------------------------
To see more information about this project, you can visite my blog post in [this link](https://pycad.co/how-to-draw-on-an-image/).


This is an example about how the drawing will look like:


![image](https://github.com/amine0110/draw-on-an-image-tkinter/blob/main/example.png)
