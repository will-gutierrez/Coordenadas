# Coordenadas
Descripcion: Este programa hace que reeborg se desplace,
dando unas coordenadas  (x y y), él deja una estrella
y luego regresa a casa.
pre: 1<x<= y<= 10; Reeborg mira al norte y lleva estrellas.
pos: Reeborg vuelve a casa o a la coordenada (1,1), además
indica la distancia recorrida.
Autor: William Gutierrez
fecha: 12/ Agosto/ 2019

'''
def coordenadas(x,y):
   y= y-1 # se resta una unidad para llegar a la coordenada correcta
   x= x - 1 # se resta una unidad para llegar a la coordenada correcta
   while(y >0): # hace que el robot se mueva tantas posiciones se da en la coordenada
    
    move()
    y = y- 1 # hace el descuento, para no generar un bucle infinito
   repeat 3:
       turn_left()
   while(x >0):
    move() # reeborg avanza, dependiendo del numero dado en x
    x= x -1 
   put("star") # ya estando en la coordenada dada se pone la estrella
# Regreso a casa
'''
Descripcion: Reeborg hace el regreso a casa, utilizando
la misma cordenada dada, solo que es el proceso contrario
pre: Reeborg mira al este y se encuentra en la coordenada dada
pos: Reeborg esta en cas(1,1), con una estrella menos
'''
def regreso(x,y):
   repeat 3: # reeborg gira para regresar a casa
       turn_left()
   y= y-1 # se resta una unidad para llegar a la coordenada correcta
   x= x - 1# se resta una unidad para llegar a la coordenada correcta
   while(y >0): # hace que el robot se mueva tantas posiciones se da en la coordenada
    
    move()
    y = y- 1
   repeat 3:# reeborg gira para regresar a casa
       turn_left()
   while(x >0):
    move()
    x= x -1
   repeat 3:
    turn_left()# reeborg gira para mirar al norte
'''
Descripcion: se imprime en pantalla la distancia recorrida }
por el robot 
pre: Reeborg ha hecho un recorrido valido
pos: Reeborg esta en casa(1,1), muestra la distancia en centimetros 
'''
def distancia(x,y):
    distancia=(((x-1)**2)+((y-1)**2))**(1/2) # se halla la distancia
    print("Distancia recorrida: ", distancia, "cm")
# primer caso de prueba
coordenadas(5,7)
regreso(5,7)
distancia(5,7)
# segundo caso de prueba
coordenadas(9,7)
regreso(9,7)
distancia(9,7)
# tercer caso de prueba
coordenadas(5,10)
regreso(5,10)
distancia(5,10)
