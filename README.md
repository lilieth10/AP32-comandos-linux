# AP 3.2 Comandos Linux

## Ejercicio 1
```bash
cd Sistemas
```
## Ejercicio 2
```bash
mkdir AP32
cd AP32
```
## Ejercicio 3
```bash
mkdir ventas marketing desarrollo direccion
```
## Ejercicio 4
- `mkdir a b c` crea tres directorios independientes en la ruta actual.
- `mkdir a/b/c` crea `c` dentro de `b`, que está dentro de `a`. Si `a/b` no existe, da error. Con `mkdir -p a/b/c` se crea toda la cadena.

## Ejercicio 5
```bash
cd ventas
touch enero febrero marzo
```
## Ejercicio 6
```bash
cd ..
cp ventas/* marketing/
ls marketing
```
## Ejercicio 7
```bash
cd marketing
mkdir ../ventas/2026
cp enero febrero marzo ../ventas/2026/
```
## Ejercicio 8
```bash
cd ../ventas
mkdir 2025
cp ../marketing/*ero 2025/
```
## Ejercicio 9
```bash
cd ../desarrollo
mkdir ventas_2025
cp ../ventas/2025/* ventas_2025/
```
## Ejercicio 10
```bash
rm -r ../ventas/2025
```
## Ejercicio 11
```bash
cd ..
mv desarrollo/ventas_2025 desarrollo/ventas2025
```
## Ejercicio 12
```bash
cd ventas
mv ../desarrollo/ventas2025 ../desarrollo/v_2025
```