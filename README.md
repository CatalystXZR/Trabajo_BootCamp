1. CARGO_MANAGER.py
- add_fletes(data)
- collect_tolls(data)
- select_client(name_or_rut)
- autocomplete_client(client_id)

2. PROFORMA_CALCULATOR.cc
- calculate_flete_cost(flete)
- calculate_subtotals(ws)
- calculate_total_general(ws)
- format_tariff_output(flete)

3. DATABASE_MANAGER.py
- load_excel(filename)
- get_existing_clients(ws)
- find_client(ws, name_or_rut)
- get_client_history(ws, client_id)

4. DATABASE_WRITER.py
- insert_flete(ws, flete)
- update_totals(ws)
- update_tariffs(ws)
- preserve_format(ws)

- - No inputs ni prints dentro de los modulos, TODO sera controlado por el orquestador (main function), modularidad estricta.
- - El excel de SQM sera utilizado como base de datos, y se operara a traves de este software.
- - El objetivo principal de este software, es agilizar el excel que ya tienen. En vez de ingresar manualmente los datos en la hoja excel, seran ingresados por este software.
- - El excel sera empleado con la libreria openpyxl **ESTUDIARLA
- - Los modulos seran creados de manera estructurada. Totalmente independientes entre si. Sera el orquestador quien le de valores a las variables y los interconecte entre si.
- - Si yo modifico el modulo A, no tiene porque verse afectado el modulo b. INDEPENDIENTES. modularidad estricta.

FASES: 
1. Crear el CLI
- Seguir una estructura modular estricta operada por orquestador
- Integrar el excel de manera correcta, siguiendo el formato de la empresa
- Manejo de clientes (Crear uno nuevo, o si ya existe, que se rellenen los datos automaticamente. Que sea posible poder retomar una proforma de un cliente facilmente.)
2. Integrar C++
- Sera el modulo ""PROFORMA_CALCULATOR"" el que estara desarrollado en C++, dado que sera el motor de los calculos. Sera un modulo totalmente matematico.
- asignar una ID (a partir del formato de ellos) de manera automatica. Y que una vez que el cliente ya este creado, que no se le vaya a asignar otra ID. Es decir, que lo reconozca. Igualmente, validar el rut, para corroborar que es un rut real y no falso, ya que es de suma importancia en el proceso de facturacion.
3. Analizar escalabilidad
- Tal vez, en vez de hacer un orquestador a partir de CLI, poder hacerlo a traves de un mini frontend, para normalizarlo como aplicacion de escritorio, quizas con C#
