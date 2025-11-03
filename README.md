# Juan-Franco
Trabajo sobre Json
 import json

#1. Buscar por deporte ----
deporte = input("Ingrese un deporte: ")

print("\nPersonas que practican", deporte + ":")
for usuario, info in datos.items():
    if deporte in info["deportes"]:
        print(info["nombres"], info["apellidos"])

# 2. Buscar por rango de edad ----
print("\nAhora buscaremos por rango de edades.")
edad_min = int(input("Edad mínima: "))
edad_max = int(input("Edad máxima: "))
# Nuevo JSON
print("\nPersonas entre", edad_min, "y", edad_max, "años:")
for usuario, info in datos.items():
    if edad_min <= info["edad"] <= edad_max:
        print(info["nombres"], info["apellidos"])

deportes_dict = {}

for usuario, info in datos.items():
    for dep in info["deportes"]:
        if dep not in deportes_dict:
            deportes_dict[dep] = []
        deportes_dict[dep].append(usuario)

# Guardar el nuevo JSON
with open("deportes.json", "w", encoding="utf-8") as archivo:
    json.dump(deportes_dict, archivo, indent=4, ensure_ascii=False)

print("\nSe creó el archivo 'deportes.json' con la información de los deportes.")


