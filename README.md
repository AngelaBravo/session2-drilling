# session2-drilling

```bash
npm install             # si faltan los node_modules uso este comando 
npm run serve           # si quiero "levantar" el servidor para desarrollar
```

## la directiva v-for

1. requiere v-bind:key
2. Mejor si lo usas con index
3. Forma sintactica:

```html
<elementoMultiplicado v-for="(elActual, index) in miArreglo" :key="index">
  {{ elActual }}  
</elementoMultiplicado>

<elementoMultiplicado> 

<!--
Puede ser cualqueir elemento de HTML o componente Vue, se va a crear una copia por cada elemento del arreglo. Si mi arreglo contiene 3 items, se crearán 3 elementos y su contenido será para cada uno el del indice correspondiente.

La variable elActual puede ser cualquier cosa pero por estar en primer lugar representa el
elemento del arreglo siendo iterado actualmente. Index también se puede llamar de cualquier manera pero por ser el segundo argumento es el indice del arreglo 0,1,2..etc.

miArreglo, es el nombre de un arreglo en el objeto data()
-->
```