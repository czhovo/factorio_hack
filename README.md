# factorio
覆盖 Factorio/data/base/prototypes 路径下的同名文件即可完成修改

##

### entity/entities.lua
full_resistances()移至开头并添加  
      {
        type = "acid",
        percent = 100
      },
      {
        type = "laser",
        percent = 100
      }

type = "inserter", name = "fast-inserter", extension_speed = 0.1 -> 1.25, rotation_speed = 0.04 -> 0.5, energy_per_movement = "7kJ" -> "7J", energy_per_rotation = "7kJ" -> "7J",
type = "inserter", name = "long-handed-inserter", extension_speed = 0.05 -> 0.625, rotation_speed = 0.02 -> 0.25, energy_per_movement = "5kJ" -> "5J", energy_per_rotation = "5kJ" -> "5J",

type = "character", name = "character", collision_box = {{-0.2, -0.2}, {0.2, 0.2}} -> {{-0., -0.}, {0., 0.}}, inventory_size = 80 -> 2000, mining_speed = 0.5 -> 50, running_speed = 0.15 -> 0.9, 添加resistances = full_resistances(),
    build_distance = 10 ->100,                    
    drop_item_distance = 10 -> 100,
    reach_distance = 10 -> 100,
    item_pickup_distance = 1 -> 5,
    loot_pickup_distance = 2,
    enter_vehicle_distance = 3 -> 100,
    reach_resource_distance = 2.7 -> 100,
    grounded_landing_search_radius = 5 -> 100,


type = "container", name = "iron-chest", inventory_size = 32 -> 2000,



type = "furnace", name = "stone-furnace", crafting_speed = 1 -> 30,
type = "assembling-machine",  name = "assembling-machine-1", crafting_speed = 0.5 -> 15,
type = "assembling-machine",  name = "assembling-machine-2", crafting_speed = 0.75 -> 22.5,
type = "furnace", name = "electric-furnace", crafting_speed = 2 -> 60,
type = "furnace", name = "steel-furnace", crafting_speed = 2 -> 60,
type = "assembling-machine",  name = "assembling-machine-3", crafting_speed = 1.25 -> 37.5,
type = "assembling-machine", name = "oil-refinery", crafting_speed = 1 -> 30,
type = "assembling-machine", name = "chemical-plant", crafting_speed = 1 -> 30,
type = "assembling-machine", name = "centrifuge", crafting_speed = 1 -> 30,



type = "solar-panel", name = "solar-panel", production = "60kW" -> "600MW"
type = "accumulator", name = "accumulator", buffer_capacity = "5MJ" -> "5GJ", input_flow_limit = "300kW" -> "300MW", output_flow_limit = "300kW" -> "300MW"
type = "radar", name = "radar", max_distance_of_sector_revealed = 14 -> 150, max_distance_of_nearby_sector_revealed = 3 -> 50,
type = "electric-pole", name = "small-electric-pole", 添加light = {intensity = 0.9, size = 40, color = {1, 1, 0.75}},

type = "car", name = "tank",  
    resistances =
    {
      {
        type = "fire",
        decrease = 15,
        percent = 60
      },
      {
        type = "physical",
        decrease = 15,
        percent = 60
      },
      {
        type = "impact",
        decrease = 50,
        percent = 80
      },
      {
        type = "explosion",
        decrease = 15,
        percent = 70
      },
      {
        type = "acid",
        decrease = 0,
        percent = 70
      }
    }, 改为full_resistance() 
braking_power = "800kW" -> "800MW", consumption = "600kW" -> "600MW",

    
### recipe.lua
全部的 enabled = false 替换为 enabled = true



### entity/transport-belts.lua
type = "transport-belt", name = "transport-belt", speed = 0.03125 -> 0.625,
type = "underground-belt", name = "underground-belt", speed = 0.03125 -> 0.625,
type = "splitter", name = "splitter", speed = 0.03125 -> 0.625,



### entity/mining-drill.lua
type = "mining-drill", name = "electric-mining-drill", mining_speed = 0.5 -> 50(在大约1200行之后),
type = "mining-drill", name = "pumpjack", mining_speed = 1 -> 60,



### item.lua
type = "item", name = "coal", fuel_value = "4MJ" -> "400GJ",
type = "gun", name = "submachine-gun", cooldown = 6 -> 0.1, movement_slow_down_factor = 0.7 -> 0, range = 18 -> 100,
type = "ammo", name = "firearm-magazine", damage = {amount = 5 -> 5000, type = "physical"}



### entity/resource.lua
local function resource(resource_parameters, autoplace_parameters), autoplace = resource_autoplace.resource_autoplace_settings, base_density = autoplace_parameters.base_density 添加*27, 添加additional_richness = 1000000,



### entity/trains.lua
type = "locomotive", name = "locomotive", max_speed = 1.2 -> 12,  max_power = "600kW" -> "6000kW",  braking_force = 10 -> 1000,
type = "cargo-wagon", name = "cargo-wagon", max_speed = 1.5 -> 6,
type = "fluid-wagon", name = "fluid-wagon", max_speed = 1.5 -> 6,


### technology.lua
type = "technology", name = "uranium-mining", prerequisites = {"chemical-science-pack", "concrete"} -> {},



### entity/flying-robots.lua
type = "logistic-robot", name = "logistic-robot", max_payload_size = 1 -> 20, speed = 0.05 -> 1,