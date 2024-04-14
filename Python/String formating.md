-----------------
- Tags: #scripting #python
----------------------

Existen varias maneras de formatear una cadena de texto:

**1. Usando %: 

```python
name = "Sebax"
rol = "lammer"
edad = 23
print("Hola, mi nombre es %s y soy un %s. Actualmente tengo %d años" % (name, rol, edad))
```

**2. Usando índices para indicar la variable que se quiere incluir en el texto:**

```python
name = "Sebax"
rol = "lammer"
edad = 23

print("Hola mi nombre es {}!".format(name))
print("Hola, soy {0}! y tengo {1} años. No es broma, mi nombre real es {0}".format(name, edad))
```

**3. Usando String Formating:**

```python
name = "Sebax"
rol = "lammer"
edad = 23

print(f"Hola mi nombre es {name}!")
print(f"Hola, soy {name}! y tengo {edad} años. No es broma, mi nombre real es {name}")
```

