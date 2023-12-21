import requests

url = "https://dummy.restapiexample.com/api/v1/employees"

respuesta = requests.get(url)

if respuesta.status_code == 200:
    datos = respuesta.json()
    lista_de_empleados = datos.get('data', [])

    if lista_de_empleados:
        numero_empleados = len(lista_de_empleados)
        promedio_salario = sum(
            float(empleado.get('employee_salary', 0)) for empleado in lista_de_empleados) / numero_empleados
        promedio_edad = sum(int(empleado.get('employee_age', 0)) for empleado in lista_de_empleados) / numero_empleados

        salarios = [float(empleado.get('employee_salary', 0)) for empleado in lista_de_empleados]
        salario_minimo = min(salarios)
        salario_maximo = max(salarios)

        edades = [int(empleado.get('employee_age', 0)) for empleado in lista_de_empleados]
        edad_minima = min(edades)
        edad_maxima = max(edades)

        print(f"Número de empleados: {numero_empleados}")
        print(f"Promedio de salario: {promedio_salario}")
        print(f"Promedio de edad: {promedio_edad}")
        print(f"Salario mínimo: {salario_minimo}")
        print(f"Salario máximo: {salario_maximo}")
        print(f"Edad mínima: {edad_minima}")
        print(f"Edad máxima: {edad_maxima}")
    else:
        print("No hay datos de empleados en la respuesta del API.")
else:
    print(f"Error al realizar la solicitud. Código de estado: {respuesta.status_code}")
