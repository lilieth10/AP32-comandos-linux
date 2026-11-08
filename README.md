# AP 3.2 Comandos Linux


## Ejercicio 1: Moverse a la carpeta Sistemas
```bash
cd Sistemas
```

## Ejercicio 2: Crear la carpeta AP32
```bash
mkdir AP32
cd AP32
```

## Ejercicio 3: Crear cuatro subdirectorios desde AP32
```bash
mkdir ventas marketing desarrollo direccion
```
**¿Puedes hacerlo en un solo comando?** Sí, porque `mkdir` acepta varios nombres a la vez y crea un directorio por cada uno.

## Ejercicio 4: Diferencia entre `mkdir a b c` y `mkdir a/b/c`
Comandos de prueba:
```bash
mkdir a b c
mkdir x/y/z
mkdir -p x/y/z
```

**¿Qué ocurriría en cada caso?**

- **`mkdir a b c`**: crea tres directorios independientes (`a`, `b` y `c`), todos al mismo nivel dentro de la carpeta actual. Ninguno está dentro de otro.
- **`mkdir a/b/c`**: intenta crear un solo directorio `c` dentro de `b`, que a su vez debe estar dentro de `a`. Es una ruta, no tres directorios separados. Si `a` y `a/b` no existen, el comando falla con el error "No existe el fichero o directorio" (`No such file or directory`) y no se crea nada.

**Reflexión:** la diferencia está en los espacios. Con espacios, `mkdir` recibe varios nombres y crea varios directorios hermanos. Con barras `/`, recibe una única ruta y necesita que las carpetas intermedias ya existan. Para crear toda la cadena de una vez se usa la opción `-p`: `mkdir -p a/b/c` crea `a`, luego `b` dentro de `a`, y luego `c` dentro de `b`.

## Ejercicio 5: Crear tres ficheros en ventas
```bash
cd ventas
touch enero febrero marzo
```
Se usa `touch`, que crea ficheros vacíos.

## Ejercicio 6: Copiar los ficheros de ventas a marketing
```bash
cd ..
cp ventas/* marketing/
ls marketing
```
**¿Puedes hacerlo con solo un comando?** Sí, con `cp ventas/* marketing/`, ya que el comodín `*` representa todos los ficheros de ventas y los copia de una vez.

**Verificación:** `ls marketing` muestra `enero febrero marzo`, así que los ficheros se copiaron correctamente.

## Ejercicio 7: Crear el directorio del año actual en ventas y copiar los ficheros
```bash
cd marketing
mkdir ../ventas/2026
cp enero febrero marzo ../ventas/2026/
```

## Ejercicio 8: Crear el directorio del año anterior y copiar los ficheros que terminan en -ero
```bash
cd ../ventas
mkdir 2025
cp ../marketing/*ero 2025/
```
El patrón `*ero` coincide con `enero` y `febrero`, pero no con `marzo`.

## Ejercicio 9: Copiar el contenido de ventas/2025 en desarrollo/ventas_2025
```bash
cd ../desarrollo
mkdir ventas_2025
cp ../ventas/2025/* ventas_2025/
```

## Ejercicio 10: Borrar el directorio ventas/2025
```bash
rm -r ../ventas/2025
```

## Ejercicio 11: Renombrar desarrollo/ventas_2025 como desarrollo/ventas2025
```bash
cd ..
mv desarrollo/ventas_2025 desarrollo/ventas2025
```

## Ejercicio 12: Renombrar desarrollo/ventas2025 como desarrollo/v_2025
```bash
cd ventas
mv ../desarrollo/ventas2025 ../desarrollo/v_2025
```

## Resultado final
Comprobación con `ls -R` desde la carpeta AP32:

```
.:
desarrollo  direccion  marketing  ventas

./desarrollo:
v_2025

./desarrollo/v_2025:
enero  febrero

./direccion:

./marketing:
enero  febrero  marzo

./ventas:
2026  enero  febrero  marzo

./ventas/2026:
enero  febrero  marzo
```