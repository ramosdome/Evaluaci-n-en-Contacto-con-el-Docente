
# Esta función solicita al usuario el presupuesto semanal.
# Su objetivo es validar que el valor ingresado sea numérico
def solicitar_presupuesto():

    # Se utiliza un ciclo while True para repetir la solicitud
    # hasta que el usuario ingrese un dato correcto.
    while True:
        try:
            # input() permite al usuario escribir un dato.
            # float() convierte ese dato a número decimal.
            presupuesto = float(input("Ingrese su presupuesto semanal: $"))

            # Se valida que el presupuesto sea mayor que cero.
            if presupuesto > 0:

                # return devuelve el valor válido a la función principal.
                return presupuesto
            else:
                # Si el número es cero o negativo, se muestra un error.
                print("Error: el presupuesto debe ser mayor que cero.")

        except ValueError:
            # ValueError ocurre si el usuario escribe texto
            # o un valor que no puede convertirse en número.
            print("Error: debe ingresar un número válido.")

# Esta función presenta en pantalla las opciones principales
# del sistema para que el usuario seleccione una operación.
def mostrar_menu():

    # "\n" agrega un salto de línea antes del menú.
    print("\n" + "=" * 55)

    # Se muestra el título del sistema.
    print("   SISTEMA DE CONTROL DE GASTOS PERSONALES")

    # Línea decorativa para separar visualmente el menú.
    print("=" * 55)

    # Cada print representa una opción disponible.
    print("1. Registrar gasto")
    print("2. Mostrar gastos registrados")
    print("3. Mostrar resumen general")
    print("4. Cambiar presupuesto semanal")
    print("5. Salir")

    # Línea final del menú.
    print("=" * 55)

# Esta función permite registrar un nuevo gasto en el sistema.
# Recibe como parámetro la lista de gastos para poder agregar
# un nuevo registro dentro de ella.
def registrar_gasto(gastos):

    # Se muestra el título de la sección.
    print("\n--- REGISTRO DE GASTO ---")

    # Se solicita al usuario la descripción del gasto.
    descripcion = input("Ingrese la descripción del gasto: ").strip()

    # strip() elimina espacios al inicio y al final del texto.
    # El ciclo valida que la descripción no quede vacía.
    while descripcion == "":
        print("Error: la descripción no puede estar vacía.")
        descripcion = input("Ingrese la descripción del gasto: ").strip()

    # Se solicita la categoría del gasto.
    categoria = input("Ingrese la categoría del gasto: ").strip()

    # Se valida que la categoría no esté vacía.
    while categoria == "":
        print("Error: la categoría no puede estar vacía.")
        categoria = input("Ingrese la categoría del gasto: ").strip()

    # Se inicia un ciclo para validar el monto ingresado.
    while True:
        try:
            # Se solicita el monto y se convierte a número decimal.
            monto = float(input("Ingrese el monto del gasto: $"))

            # Se verifica que el monto sea mayor que cero.
            if monto > 0:
                # Si el monto es válido, se sale del ciclo.
                break
            else:
                print("Error: el monto debe ser mayor que cero.")

        except ValueError:
            # Si el usuario no escribe un número válido, se muestra un error.
            print("Error: debe ingresar un número válido.")

    # Se crea un diccionario para guardar la información del gasto.
    # Un diccionario almacena datos en pares clave-valor.
    gasto = {
        "descripcion": descripcion,  # Guarda la descripción ingresada.
        "categoria": categoria,      # Guarda la categoría ingresada.
        "monto": monto               # Guarda el monto ingresado.
    }

    # append() agrega el diccionario del gasto al final de la lista.
    gastos.append(gasto)

    # Se informa al usuario que el gasto fue guardado correctamente.
    print("Gasto registrado correctamente.")

# Esta función muestra en pantalla todos los gastos almacenados.
# Recibe como parámetro la lista general de gastos.
def mostrar_gastos(gastos):

    # Título de la sección.
    print("\n--- GASTOS REGISTRADOS ---")

    # Se verifica si la lista está vacía.
    if len(gastos) == 0:
        # len() devuelve la cantidad de elementos de la lista.
        print("No hay gastos registrados todavía.")

        # return finaliza la función porque no hay nada que mostrar.
        return

    # enumerate() permite recorrer la lista y numerar cada gasto.
    # start=1 hace que la numeración comience desde 1.
    for i, gasto in enumerate(gastos, start=1):

        # Se muestra el número del gasto y su descripción.
        print(f"{i}. Descripción: {gasto['descripcion']}")

        # Se muestra la categoría del gasto.
        print(f"   Categoría : {gasto['categoria']}")

        # Se muestra el monto con dos decimales.
        print(f"   Monto     : ${gasto['monto']:.2f}")

        # Línea decorativa para separar cada registro.
        print("-" * 40)

# Esta función recorre la lista de gastos y suma todos los montos.
# Devuelve el total acumulado de dinero gastado.
def calcular_total_gastado(gastos):

    # Variable acumuladora que inicia en cero.
    total = 0

    # Se recorre cada gasto almacenado en la lista.
    for gasto in gastos:

        # Se suma el monto del gasto actual al total acumulado.
        total += gasto["monto"]

    # Se devuelve el total calculado.
    return total

# Esta función presenta un resumen general del estado financiero.
# Muestra el presupuesto semanal, el total gastado, el saldo
# restante y el porcentaje del presupuesto consumido.
def mostrar_resumen(presupuesto, gastos):

    # Título de la sección.
    print("\n--- RESUMEN GENERAL ---")

    # Se obtiene el total gastado llamando a otra función.
    total_gastado = calcular_total_gastado(gastos)

    # Se calcula el saldo restante restando lo gastado al presupuesto.
    saldo_restante = presupuesto - total_gastado

    # Se calcula el porcentaje del presupuesto utilizado.
    porcentaje_consumido = (total_gastado / presupuesto) * 100

    # Se muestran los resultados en pantalla con formato de dos decimales.
    print(f"Presupuesto semanal : ${presupuesto:.2f}")
    print(f"Total gastado       : ${total_gastado:.2f}")
    print(f"Saldo restante      : ${saldo_restante:.2f}")
    print(f"Porcentaje usado    : {porcentaje_consumido:.2f}%")

    # Se evalúa si el usuario superó, igualó o mantiene saldo del presupuesto.
    if total_gastado > presupuesto:
        print("ALERTA: Ha superado su presupuesto semanal.")
    elif total_gastado == presupuesto:
        print("ATENCIÓN: Ha utilizado exactamente todo su presupuesto.")
    else:
        print("Aún dispone de saldo dentro de su presupuesto.")

# Esta función revisa inmediatamente si los gastos acumulados
# ya superan el presupuesto semanal.
def verificar_presupuesto_excedido(presupuesto, gastos):

    # Se calcula nuevamente el total gastado.
    total_gastado = calcular_total_gastado(gastos)

    # Si el total es mayor que el presupuesto, se muestra una alerta.
    if total_gastado > presupuesto:
        print("\nALERTA: El gasto acumulado ha superado el presupuesto semanal.")

# Esta función permite modificar el presupuesto semanal durante
# la ejecución del sistema.
def cambiar_presupuesto(gastos):

    # Título de la sección.
    print("\n--- CAMBIAR PRESUPUESTO SEMANAL ---")

    # Se solicita un nuevo presupuesto usando la función ya creada.
    nuevo_presupuesto = solicitar_presupuesto()

    # Se calcula el total gastado actual.
    total_gastado = calcular_total_gastado(gastos)

    # Se compara el total gastado con el nuevo presupuesto.
    if total_gastado > nuevo_presupuesto:
        print("\nADVERTENCIA: El total de gastos ya registrados supera el nuevo presupuesto.")
    elif total_gastado == nuevo_presupuesto:
        print("\nATENCIÓN: El total gastado es igual al nuevo presupuesto.")
    else:
        print("\nPresupuesto actualizado correctamente.")

    # Se devuelve el nuevo presupuesto para actualizarlo en main().
    return nuevo_presupuesto

# Esta función pregunta al usuario si desea continuar usando
# el sistema o finalizar el programa.
def desea_otra_operacion():

    # Se repite la pregunta hasta recibir una respuesta válida.
    while True:

        # Se captura la respuesta del usuario.
        # strip() elimina espacios y lower() convierte a minúsculas.
        respuesta = input("\n¿Desea realizar otra operación? (s/n): ").strip().lower()

        # Se verifica si la respuesta corresponde a "sí".
        if respuesta in ["s", "si", "sí"]:

            # True indica que el usuario desea continuar.
            return True

        # Se verifica si la respuesta corresponde a "no".
        elif respuesta in ["n", "no"]:

            # False indica que el usuario desea salir.
            return False

        else:
            # Si la respuesta no es válida, se vuelve a pedir.
            print("Error: ingrese únicamente 's' para sí o 'n' para no.")

# Esta función controla el flujo general del programa:
# solicita el presupuesto, muestra el menú, ejecuta la opción
# elegida y mantiene el sistema activo hasta que el usuario salga.
def main():

    # Se muestra el encabezado de bienvenida.
    print("=" * 55)
    print("BIENVENIDO AL SISTEMA DE CONTROL DE GASTOS")
    print("=" * 55)

    # Se solicita el presupuesto inicial.
    presupuesto = solicitar_presupuesto()

    # Se crea una lista vacía para almacenar todos los gastos.
    gastos = []

    # Ciclo principal del programa.
    # while True mantiene el sistema en funcionamiento
    # hasta que el usuario decida finalizar.
    while True:

        # Se muestra el menú principal.
        mostrar_menu()

        # Se solicita la opción del usuario.
        opcion = input("Seleccione una opción: ")

        # Opción 1: registrar un gasto.
        if opcion == "1":
            registrar_gasto(gastos)
            verificar_presupuesto_excedido(presupuesto, gastos)

        # Opción 2: mostrar los gastos registrados.
        elif opcion == "2":
            mostrar_gastos(gastos)

        # Opción 3: mostrar el resumen general.
        elif opcion == "3":
            mostrar_resumen(presupuesto, gastos)

        # Opción 4: cambiar el presupuesto semanal.
        elif opcion == "4":
            # Se actualiza la variable presupuesto con el nuevo valor.
            presupuesto = cambiar_presupuesto(gastos)

        # Opción 5: salir del sistema.
        elif opcion == "5":
            print("\nGracias por utilizar el sistema de control de gastos.")

            # break finaliza el ciclo principal.
            break

        else:
            # Si la opción no es válida, se muestra un error.
            print("Error: opción no válida.")

            # continue reinicia el ciclo y vuelve a mostrar el menú.
            continue

        # Después de ejecutar una operación válida,
        # se pregunta si desea realizar otra.
        if not desea_otra_operacion():

            # Si la función devuelve False, el programa finaliza.
            print("\nGracias por utilizar el sistema de control de gastos.")
            break

# __name__ es una variable especial de Python.
# Esta condición asegura que main() solo se ejecute
# cuando este archivo se corre directamente.
if __name__ == "__main__":
    main()