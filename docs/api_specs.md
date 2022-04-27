# Activity Records API Reference

# Valid API routes:

## scope1/stationary-combustion:

    required: 
        provider_name [string],
        account_number [string],
        date [string],
        fuel_type [string],
        total_amount [float],
        unit [string]
        
    allowed: 
        building_address [string],
        total_cost [float]
        
## scope1/mobile-combustion: 

    required: 
        vehicle_type [string],
        account_number [string],
        date [string],
        total_amount [float],
        fuel_type [string],
        unit [string]
        
    allowed: 
        total_cost [float]
        
## scope1/fugitive-emissions/purchased-gases-data:

    required: 
        refrigerant_type [string],
        total_amount [float],
        unit [string]

    allowed: 
        year [integer],
        total_cost [float]



## scope1/fugitive-emissions/simplified-material-balance-data:

    required: 
        refrigerant_type [string],
        new_units_charge [float],
        new_units_capacity [float],
        existing_units_recharge [float],
        disposed_units_capacity [float],
        disposed_units_recovered [float]

    allowed: 
        year [integer],
        new_units_charge_unit [string],
        new_units_capacity_unit [string],
        existing_units_recharge_unit [string],
        disposed_units_capacity_unit [string],
        disposed_units_recovered_unit [string]


        
## scope1/fugitive-emissions/screening-data:

    required: 
        type_of_equipment [string],
        refrigerant_type [string]

    allowed: 
        manufacturer [string],
        model_number [string],
        new_units_charge [float],
        new_units_charge_unit [string],
        existing_units_refrigerant_capacity [float],
        existing_units_refrigerant_capacity_unit [string],
        existing_units_months_in_used [float],
        disposed_units_refrigerant_capacity [float],
        disposed_units_refrigerant_capacity_unit [string],
        disposed_units_months_in_use [float]


        
## scope2/utilities/owned:

    required: 
        facility_address [string],
        provider_name [string],
        account_number [string],
        begin_date [string],
        end_date [string],
        total_amount [float],
        unit [string],
        activity_type [string]

    allowed: 
        total_cost [float]


        
## scope2/utilities/leased:

    required: 
        facility_address [string],
        pct_occupied [float],
        begin_date [string],
        end_date [string],
        total_amount [float],
        unit [string],
        activity_type [string]

    allowed: 
        provider_name [string],
        account_number [string],
        total_cost [float]


        
## scope3/waste:

    required:
        provider [string],
        account_number [string],
        date [string],
        waste_type [string],
        disposal_method [string],
        total_amount [float],
        unit [string]

    allowed: 
        total_cost [float]


        
## scope3/transportation-and-distribution:

    required: 
        supplier_or_customer [string],
        mode_of_transport [string],
        date [string],
        begin_point [string],
        end_point [string],
        total_weight [float],
        weight_unit [string]

    allowed: 
        vehicle_type [string],
        total_cost [float]


        
## scope3/purchased-packaging/average-data:

    required: 
        supplier [string],
        packaging_type [string],
        packaging_material [string],
        pct_recycled_content [float],
        other_sustainable_certifications [string],
        date [string],
        total_weight [float],
        unit [string]

    allowed: 
        total_cost [float]


        
## scope3/purchased-packaging/average-data-using-key:

    required: 
        sku [string],
        product_name [string],
        supplier [string],
        primary_packaging_type [string],
        primary_packaging_material [string],
        primary_packaging_weight [float],
        primary_packaging_pct_recycled_content [float],
        primary_packaging_sustainable_certs [string]

    allowed: 
        primary_packaging_unit [string],
        secondary_packaging_type [string],
        secondary_packaging_material [string],
        secondary_packaging_weight [float],
        secondary_packaging_unit [string],
        tertiary_packaging_type [string],
        tertiary_packaging_material [string],
        tertiary_packaging_weight [float],
        tertiary_packaging_unit [string]


        
## scope3/purchased-packaging/spend-data:

    required: 
        supplier [string],
        packaging_type [string],
        packaging_material [string],
        date [string],
        total_cost [float]

    allowed: 
        # All allowed fields are required


        
## scope3/purchased-ingredients/average-data:

    required: 
        supplier [string],
        ingredient_name [string],
        country_of_origin [string],
        date [string],
        total_weight [float],
        unit [string]

    allowed: 
        total_cost [float]


        
## scope3/purchased-ingredients/average-component-data-using-key:

    required: 
        sku [string],
        component_name [string],
        primary_ingredient_name [string],
        primary_ingredient_weight [float],
        primary_ingredient_unit [string]

    allowed: 
        secondary_ingredient_name [string],
        secondary_ingredient_weight [float],
        secondary_ingredient_unit [string],
        other_ingredient_name [string],
        other_ingredient_weight [float],
        other_ingredient_unit [string]


        
## scope3/purchased-ingredients/average-product-data-using-key:

    required: 
        sku [string],
        product_name [string],
        primary_ingredient_name [string],
        primary_ingredient_weight [float],
        primary_ingredient_unit [string]

    allowed: 
        secondary_ingredient_name [string],
        secondary_ingredient_weight [float],
        secondary_ingredient_unit [string],
        other_ingredient_name [string],
        other_ingredient_weight [float],
        other_ingredient_unit [string]


        
## scope3/purchased-ingredients/spend-data:

    required: 
        supplier [string],
        ingredient_name [string],
        date [string],
        total_cost [float]

    allowed: 
        # All allowed fields are required


        
## scope3/contract-manufacturers:

    required: 
        cmo_name [string],
        year [integer],
        total_cost [float]

    allowed: 
        # All allowed fields are required



## scope3/business-travel/distance-data:

    required: 
        method_of_travel [string],
        date [string],
        total_distance_traveled [float],
        unit [string]

    allowed: 
        employee_id [string],
        total_cost [float]



## scope3/business-travel/begin-end-data:

    required: 
        method_of_travel [string],
        date [string],
        begin_location [string],
        end_location [string],

    allowed: 
        employee_id [string],
        total_cost [float]



## scope3/business-travel/spend-data:

    required: 
        method_of_travel [string],
        date [string],
        total_cost [float]

    allowed: 
        # All allowed fields are required
