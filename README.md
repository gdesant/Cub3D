[![Build](https://img.shields.io/badge/build-passing-green.svg?style=flat&color=B6D827)](https://choosealicense.com/licenses/mit/) [![Grade](https://img.shields.io/badge/grade-102/100-green.svg?style=flat&color=B6D827)](https://choosealicense.com/licenses/mit/)  



# 🏫 Cub3D 

This project is inspired by a famous game released in 1992 called [Wolfenstein 3D](https://fr.wikipedia.org/wiki/Wolfenstein_3D).\
The goal was to recreate this game graphic engine using the raycast technology.

# 


## Screenshots  

![App Screenshot](save.bmp) 

[![C](https://img.shields.io/badge/Made&#32;In-C-white.svg?style=for-the-badge&color=blue)]()\
 Using the [minilibx](https://github.com/42Paris/minilibx-linux)


## How to play  
------

You can move your player with W,S,A,D and rotate it with ← and →. You can pickup sprites by walking on them.

## Run Locally  
----------
Clone the project  

~~~bash  
  git clone https://github.com/gdesant/Cub3D.git
~~~

Go to the project directory  

~~~bash  
  cd Cub3D
~~~

Compile 

~~~bash  
make all
~~~

Start the game

~~~bash  
./Cub3D [map_path] (--save)
~~~

~~~
map_path : path of your .cub file with the map inside  

--save   : take a screenshot of the first frame of the Game and save it in .bmp
~~~


# Cub File  

The cub file given as an argument to Cub3D, is a file containing the map and the path of the textures of the game. You can find a map example [here](https://github.com/gdesant/Cub3D/blob/main/map.cub)

This project include a [map parser](https://github.com/gdesant/Cub3D/blob/main/lib/libcustom/map) to be sure that the map is valid before launching the game. If the map is invalid for any reason the parser will tell the user why the map is invalid and cancel the launch of the game.

## Game Data 
-----------------
The Game Data is the first part of the .cub and to be valid it must have multiple lines:

- The window size :
~~~~
R [width] [height]
~~~~
------
### Wall Textures :
------
- North face texture path :
~~~~
NO [path]
~~~~

- South face texture path :
~~~~
SO [path]
~~~~

- West face texture path :
~~~~
WE [path]
~~~~

- East face texture path :
~~~~
EA [path]
~~~~

- Sprites texture path :
~~~~
S [path]
~~~~
------


### Colors :
------
- Ceiling color :
~~~~
C [r],[g],[b]
~~~~

- Floor color :
~~~~
C [r],[g],[b]
~~~~
------

All of them must be in the .cub file for it to be valid but you can write them in any order.

## Map Data  :
-----------------


 
This map is composed of 4 types of cell:

- 0 is a free space where you can walk
- 1 is a Wall
- 2 is a pickable sprite
- N,S,E or W correspond to the player position and rotation (N: North, S: South, ....)

Any other character can turn the map invalid.

For this map to be valid it must have :

  - The map must be closed (surrounded by wall)
  - One player position



# Feedback  

If you have any feedback, please reach out to us at gdesant@student.42.fr
