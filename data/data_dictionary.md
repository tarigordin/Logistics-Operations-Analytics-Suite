# 📖 Logistics Operations Data Dictionary

## 1. Fact Tables
* **`delivery_events`**: Transactional records for individual delivery runs. Contains `delivery_id`, `route_id`, `driver_id`, `actual_transit_time`, `planned_transit_time`, `on_time_flag`, and `detention_minutes`.
* **`loads`**: Load fulfillment data including `load_id`, `customer_id`, `load_weight`, and `shipping_revenue`.
* **`maintenance_records`**: Maintenance events tracking `maintenance_id`, `truck_id`, `service_type` (Engine, Inspection, Tire, Preventive, Repair), `parts_cost`, and `labor_cost`.
* **`fuel_purchases`**: Fuel consumption transactions tracking `purchase_id`, `truck_id`, `gallons`, `total_cost`, and `fuel_type` (Diesel).

## 2. Dimension Tables
* **`Calendar`**: Continuous date table establishing temporal granularity across month, quarter, and year.
* **`drivers`**: Master driver directory containing `driver_id`, `full_name`, `employment_status`, and safety performance ratings.
* **`facilities`**: Hubs, warehouses, and terminal points including `facility_name`, `city`, and dwell compliance benchmarks.
* **`routes`**: Origin-to-destination corridors containing `route_id`, `origin_city`, `destination_city`, and standard mileage.
* **`customers`**: Client directory including `customer_id`, `customer_name`, and contractual SLA tier specifications.
