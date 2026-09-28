# Solar-EV-charging-station
# Solar EV Charging Station
# Python Simulation Program

print("======================================")
print("        SOLAR EV CHARGING STATION")
print("======================================")

# Input values
solar_power = float(input("Enter available solar power (kW): "))
ev_battery = float(input("Enter EV battery level (%): "))
battery_capacity = float(input("Enter EV battery capacity (kWh): "))

# Charging power
charging_power = min(solar_power, 7.0)

print("\n--- Charging Station Status ---")
print("Solar Power Available :", solar_power, "kW")
print("EV Battery Level      :", ev_battery, "%")
print("EV Battery Capacity   :", battery_capacity, "kWh")

if solar_power <= 0:
    print("\n🔴 No solar power available.")
    print("EV charging stopped.")

elif ev_battery >= 100:
    print("\n🟢 EV battery is fully charged.")
    print("Charging stopped.")

else:
    # Energy required to fully charge
    energy_required = battery_capacity * (100 - ev_battery) / 100

    # Approximate charging time
    charging_time = energy_required / charging_power

    print("\n🟢 Solar EV Charging ACTIVE")
    print("Charging Power :", charging_power, "kW")
    print("Energy Required:", round(energy_required, 2), "kWh")
    print("Estimated Time :", round(charging_time, 2), "hours")
    print("☀️ Solar energy is being used to charge the EV.")
