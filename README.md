# Modular Freight Proforma System
A technical solution designed to streamline the creation, validation, and traceability of freight proformas in real-world logistics environments. Built for operations involving multiple transport providers, where documentation and responsibility must be clear, auditable, and scalable.

## Orchestrated Modular Architecture
The system is composed of independent modules, each with a specific responsibility. This allows for isolated validation, progressive evolution, and operational flexibility.

### CARGO_MANAGER.py
- `add_fletes(data)`: Adds new freight entries to the system.
- `collect_tolls(data)`: Calculates tolls associated with each trip.
- `select_client(name_or_rut)`: Selects a client by name or national ID.
- `autocomplete_client(client_id)`: Autocompletes client data based on ID.

### PROFORMA_CALCULATOR.cc
- `calculate_flete_cost(flete)`: Computes base freight cost.
- `calculate_subtotals(ws)`: Calculates subtotals by category.
- `calculate_total_general(ws)`: Computes the overall total of the proforma.
- `format_tariff_output(flete)`: Formats tariff output for presentation.

### DATABASE_MANAGER.py
- `load_excel(filename)`: Loads Excel file as data source.
- `get_existing_clients(ws)`: Retrieves registered clients.
- `find_client(ws, name_or_rut)`: Searches for a client by name or ID.
- `get_client_history(ws, client_id)`: Retrieves freight history for a given client.

### DATABASE_WRITER.py
- `insert_flete(ws, flete)`: Inserts a new freight entry into the database.
- `update_totals(ws)`: Updates overall totals.
- `update_tariffs(ws)`: Updates tariffs based on defined parameters.

### Scalability
Each module is designed to adapt to different operational contexts, cargo types, and business models. The system can evolve without requiring a full rewrite, supporting long-term growth and customization.

## Operational Integration
This system was designed based on direct observation of real logistics workflows. It is not a theoretical model, but a functional architecture intended for phased implementation and field validation.

## Authors
***Matías Toledo*** — Product Lead  
***Benjamin Contreras*** — Lead Developer


## License
This project is currently unlicensed.  
All rights reserved by the authors.  
Use, distribution, or modification is not permitted without explicit permission.

