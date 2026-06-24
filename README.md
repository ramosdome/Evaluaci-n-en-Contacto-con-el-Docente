# Título del proyecto
**El impacto de las nuevas tecnologías en la sociedad: desarrollo y proyección de soluciones informáticas**

## Integrantes
**Doménica Fernanda Ramos Requenes**

## Objetivo del sistema
Desarrollar e implementar un **sistema de control de gastos personales semanales** en lenguaje Python, con el propósito de aplicar los principios básicos de la programación mediante el uso de variables, listas, funciones, estructuras condicionales, ciclos repetitivos y validación de datos. Este sistema busca simular en consola el registro y control de un presupuesto semanal, permitiendo al usuario almacenar sus gastos, consultar la información registrada y visualizar un resumen del estado de sus finanzas personales.

## Descripción de funcionalidades
La solución creada corresponde a un **programa en consola para el control de gastos personales semanales**, en el cual el usuario interactúa con el sistema para registrar su presupuesto, anotar sus gastos y visualizar reportes básicos sobre el dinero disponible. Entre sus funciones principales se encuentran las siguientes:

- **Registro del presupuesto semanal**, permitiendo al usuario establecer la cantidad de dinero disponible para organizar sus gastos durante la semana.
- **Registro de gastos**, mediante el ingreso de información como la descripción del gasto, su categoría y el monto correspondiente.
- **Validación de datos ingresados**, asegurando que el usuario proporcione montos numéricos válidos y campos de texto no vacíos.
- **Almacenamiento de gastos**, guardando cada registro dentro de una estructura de datos que permite organizar la información ingresada.
- **Visualización de gastos registrados**, mostrando al usuario la lista completa de gastos almacenados durante la semana.
- **Cálculo del total gastado**, sumando automáticamente todos los montos registrados en el sistema.
- **Cálculo del saldo restante**, comparando el presupuesto inicial con el total de gastos realizados.
- **Generación de un resumen general**, mostrando el presupuesto semanal, el total gastado, el saldo disponible y el porcentaje del presupuesto utilizado.
- **Control de excedente del presupuesto**, alertando al usuario cuando los gastos registrados superan la cantidad de dinero planificada.
- **Modificación del presupuesto semanal**, permitiendo cambiar el valor inicial del presupuesto en caso de ser necesario.
- **Continuidad de uso del sistema**, preguntando al usuario si desea realizar otra operación para seguir utilizando el menú sin cerrar el programa.

## Funcionamiento del sistema
El desarrollo del sistema sigue la siguiente secuencia:

1. El usuario inicia el programa e ingresa su presupuesto semanal.
2. El sistema almacena ese valor como referencia para controlar los gastos.
3. Se presenta un menú principal con las opciones disponibles.
4. Si el usuario selecciona **registrar gasto**, el sistema solicita la descripción, categoría y monto del gasto.
5. El programa valida los datos ingresados y almacena la información en la lista de gastos.
6. Después de registrar un gasto, el sistema verifica si el total acumulado supera el presupuesto semanal.
7. Si el usuario selecciona **mostrar gastos registrados**, el programa presenta en pantalla todos los gastos guardados.
8. Si el usuario selecciona **mostrar resumen general**, el sistema calcula y muestra el presupuesto, el total gastado, el saldo restante y el porcentaje consumido.
9. Si el usuario selecciona **cambiar presupuesto semanal**, el sistema permite ingresar un nuevo presupuesto y lo actualiza.
10. Después de cada operación, el programa pregunta si el usuario desea realizar otra acción.
11. El sistema continúa en ejecución hasta que el usuario decide salir.

## Relación con la estructura del código
La implementación del sistema se organiza mediante las siguientes funciones:

- **`solicitar_presupuesto()`**: solicita y valida el presupuesto semanal ingresado por el usuario.
- **`mostrar_menu()`**: presenta las opciones principales del sistema en consola.
- **`registrar_gasto(gastos)`**: registra un nuevo gasto y lo almacena en la lista general de gastos.
- **`mostrar_gastos(gastos)`**: muestra todos los gastos registrados hasta el momento.
- **`calcular_total_gastado(gastos)`**: suma los montos de todos los gastos almacenados.
- **`mostrar_resumen(presupuesto, gastos)`**: presenta el resumen general del presupuesto semanal, total gastado, saldo restante y porcentaje utilizado.
- **`verificar_presupuesto_excedido(presupuesto, gastos)`**: comprueba si los gastos superan el presupuesto y muestra una alerta.
- **`cambiar_presupuesto(gastos)`**: permite modificar el presupuesto semanal y actualizar su valor en el sistema.
- **`desea_otra_operacion()`**: consulta al usuario si desea continuar utilizando el programa o finalizarlo.
- **`main()`**: controla la ejecución general del sistema, coordina el menú principal y la interacción entre todas las funciones.

## Ejecución del proyecto
Para ejecutar el programa, se debe abrir la terminal en la carpeta del proyecto y utilizar el siguiente comando:

```bash
python codigo/control_gastos.py
```
## Fecha
28/06/2026