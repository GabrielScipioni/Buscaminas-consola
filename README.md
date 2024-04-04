# Buscaminas en Java

![Portada](https://avatars.githubusercontent.com/u/149858423?v=4)

## Índice

1. [Instrucciones de uso](#instrucciones-de-uso)
2. [Código](#código)
3. [Notas](#notas)

## Instrucciones de uso

Este es un simple juego de buscaminas implementado en Java. El programa solicita al usuario las dimensiones del tablero y la cantidad de bombas que se desean colocar, luego muestra el tablero inicial con las bombas ocultas.

1. Ejecuta el programa `Main.java`.
2. Sigue las instrucciones en la consola para ingresar el número de columnas, filas y la cantidad de bombas.
3. Observa el tablero generado con las bombas ocultas representadas por el caracter `+` y los espacios vacíos con `-`.

## Código

```java
package org.example;

import java.util.Random;
import java.util.Scanner;

public class Main {
    // Aquí va el código...
}


```java
package org.example;

import java.util.Random;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        // Inicializar scanner y random
        Random ran = new Random();
        Scanner scan = new Scanner(System.in);

        // Ingresar el número de columnas
        System.out.println("Indique el número de columnas:");
        int x = scan.nextInt();

        // Ingresar el número de filas
        System.out.println("Indique el número de filas:");
        int y = scan.nextInt();

        // Ingresar la cantidad de bombas
        System.out.println("Indique el número de bombas:");
        int bombas = scan.nextInt();

        // Crear una matriz en base a (x;y)
        char[][] tablero = new char[y][x];

        // Matriz dibujada con guiones
        for (int i = 0; i < y; i++) {
            for (int j = 0; j < x; j++) {
                tablero[i][j] = '-';
            }
        }

        // Dibujar bombas
        for (int k = 0; k < bombas; k++) {
            int fil = ran.nextInt(y);
            int col = ran.nextInt(x);
            tablero[fil][col] = '+';
        }

        // Mostrar el numerado
        System.out.print("  ");
        for (int i = 0; i < x; i++) {
            System.out.print(" " + (i + 1));
        }

        // Mostrar matriz
        System.out.println();
        for (int i = 0; i < y; i++) {
            System.out.print((i + 1) + " ");
            for (int j = 0; j < x; j++) {
                System.out.print(" " + tablero[i][j]);
            }
            System.out.println();
        }
    }
}
```

## Notas

- El programa genera un tablero con las bombas ocultas representadas por el caracter `+` y los espacios vacíos con `-`.
- Este código es una implementación básica de un buscaminas y puede ser extendido con funcionalidades adicionales como la detección de casillas adyacentes a las bombas y la interacción del usuario para descubrir las casillas.
