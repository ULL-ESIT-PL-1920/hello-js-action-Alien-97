# Reto hello-world-javascript-action

- Autor: Alien Embarec Riadi
- Curso: 2019/2020

- Centro Docente: ESIT, Universidad de la Laguna

- Asignatura: Procesadores de Lenguajes, Grado en Ingeniería Informática

## Descripción

Esta acción imprime "Hello World" o "Hello" + el nombre de la persona. El nombre de la persona se le paso como argumento a través de un workflow de GitHub (en otro repositorio) que hace uso de esta acción

## Inputs

### `who-to-greet`

`who-to-greet` es el nombre de la persona a saludar, que recibe como argumento en forma de variable de entorno.

Lo que permite comunicar al evento y al código fuente de la acción es un paquete de GitHub llamado [`@actions/core`](https://github.com/actions/toolkit/tree/master/packages/core). Que nos permite manejar excepciones, mostrar mensajes de entrada-salida a través de variables de entorno etc.

Hacemos uso de dos de las funciones de ese paquete, que son `getInput(nombreEvento)` para obtener el nombre de la persona a la que saludar.

Y `setOutput('time', time)` para mostrar el la hora en la que se hace el saludo.

Si en el workflow no se especifica ninguna persona a quien saludar, se saludará por defecto a World.

**Required** The name of the person to greet. Default `"World"`.

## Outputs

### `time`

Una vez se saluda, se muestra la hora por pantalla en la que se hizo el saludo.

## Example usage

Aquí se puede ver un ejemplo del fichero `YAML` que especificamos en el cliente para poder usar la acción. Previamente es imprescindible haber publicado la acción en el marketplace de GitHub para usarla.

```yaml
uses: ULL-ESIT-PL-1920/hello-world-javascript-action@v1
with:
who-to-greet: 'Mona the Octocat'
```
