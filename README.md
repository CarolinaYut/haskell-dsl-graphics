# Haskell DSL para Composición de Figuras 

Implementación de un **Domain Specific Language (DSL) en Haskell** para describir y componer figuras geométricas mediante transformaciones y operadores combinatorios, con interpretación gráfica utilizando **OpenGL / GLUT**.

Este proyecto fue desarrollado originalmente en contexto académico y adaptado para portfolio personal, explora el diseño de **lenguajes embebidos (EDSL)**, **tipos algebraicos polimórficos** y **funciones de alto orden** dentro del paradigma funcional.

---

## Descripción


El objetivo fue diseñar e implementar un pequeño lenguaje descriptivo capaz de:

- Definir figuras básicas
- Aplicar transformaciones geométricas (rotación, espejado, rotación 45°)
- Componer figuras (apilar, juntar, encimar)
- Interpretar las expresiones del lenguaje y renderizarlas gráficamente

---

## Organización del Proyecto

- `Dibujo.hs` → Definición del DSL y combinadores derivados  
- `Pred.hs` → Manipulación estructural usando *folds* y predicados  
- `Interp.hs` → Interpretación semántica a gráficos (OpenGL / GLUT)  
- `Basica/` → Ejemplos y composiciones (`Ejemplo`, `BasicaDoble`, `Escher`)  
- `Main.hs` → Punto de entrada configurable  

---

## Cómo Ejecutar

### Requisitos

- GHC (Glasgow Haskell Compiler)
- Biblioteca `GLUT` instalada

Si no está instalada:

```bash
cabal update
cabal install --lib GLUT
```

## Ejecutar el programa

Desde la raíz del proyecto

```bash
ghci Main.hs -package GLUT
```

Luego, dentro de ghci:

```bash
main
```

## Cambiar el dibujo mostrado

El archivo Main.hs permite seleccionar distintas composiciones ubicadas en Basica/.

Modificar el import segun corresponda:

```bash
import qualified Basica.Ejemplo as E
```

o
```bash
import qualified Basica.BasicaDoble as E
```

o

```bash
import qualified Basica.Escher as E
```
## Caso especial: Escher

Si se utiliza Basica.Escher, también modificar:

```bash 
fig = E.escher 2 E.Fish
```

(se puede usar cualquier figura del tipo Escher.)

Y ajustar la configuración:

```bash
conf = E.Escher
```

Luego ejecutar nuevamente:

```bash
main
```



