-----------------
- Tags: #scripting #python
----------------------
### Ciclo for:

```python
for i in range(5): #La cantidad que se indica menos 1
    print(f"El nombre para esta vuelta es {name}")
```

```python
nombres = ["Alicia", "Pepe", "s4vitar", "Lobotec", "Hackermate"]

for contador, nombre in enumerate(nombres):
    print(f"Nombre[{contador + 1}]: {nombre}")
```

**Nota: con break se rompe el ciclo que se está ejecutando y con continue se interrumpe la iteración actual y se pasa a la siguiente**
### For anidado

```python
my_list = [[1, 4, 5],[2, 6, 8],[9, 4, 1]]

for element in my_list:
    print(f"\n[+] Vamos a desglosar la lista {element}\n")
    for element_in_list in element:
        print(element_in_list)
```

### Listas de comprensión

```Python
odd_list = [1, 3, 5, 7, 9]
cuadrado = [i ** 2 for i in odd_list]

print(cuadrado)
```

### Ciclo while:

```python
while i < 5:
    print(i)
    i += 1
```

A los ciclos while se pueden inclulir un else que sirve para ejecutar código en el caso en el que se ejecute de manera satisfactoriamente el bucle

```Python
i = 0

while i < 16:
    if i == 10:
        print("Salimos antes de tiempo")
        break

    i += 1

else:
    print("El bucle while ha finalizado satisfactoriamente")

# --------------------
print("Estamos saliendo del bucle")
```

