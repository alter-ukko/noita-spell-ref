## ![???](images/FUNKY_SPELL.png)??? (FUNKY_SPELL)

* **description**: ???
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [6, 10]
* **spawn_probability**: [0.1, 0.1]
* **price**: 50
* **mana**: 5
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/machinegun_bullet.xml"}
* **spawn_requires_flag**: card_unlocked_funky
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/machinegun_bullet.xml")
      c.fire_rate_wait = c.fire_rate_wait - 3
      c.screenshake = c.screenshake + 0.2
      c.spread_degrees = c.spread_degrees + 2.0
      c.damage_critical_chance = c.damage_critical_chance + 1
    end,
```

## ![Accelerating shot](images/ACCELERATING_SHOT.png)Accelerating shot (ACCELERATING_SHOT)

* **description**: Causes a projectile to accelerate as it flies
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4]
* **spawn_probability**: [0.5, 0.5, 1.0]
* **price**: 190
* **mana**: 20
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/accelerating_shot.xml" }
* **action**:

```lua
 function()
      c.fire_rate_wait    = c.fire_rate_wait + 8
      c.speed_multiplier = c.speed_multiplier * 0.32
      shot_effects.recoil_knockback = shot_effects.recoil_knockback + 10.0
      c.extra_entities = c.extra_entities .. "data/entities/misc/accelerating_shot.xml,"
      
      if ( c.speed_multiplier >= 20 ) then
        c.speed_multiplier = math.min( c.speed_multiplier, 20 )
      elseif ( c.speed_multiplier < 0 ) then
        c.speed_multiplier = 0
      end
      
      draw_actions( 1, true )
    end,
```

## ![Accelerative Homing](images/HOMING_ACCELERATING.png)Accelerative Homing (HOMING_ACCELERATING)

* **description**: A projectile homes towards enemies at an increasing pace
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 2, 3, 4]
* **spawn_probability**: [0.1, 0.3, 0.3, 0.5]
* **price**: 180
* **mana**: 60
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/homing_accelerating.xml", "data/entities/particles/tinyspark_white_small.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/homing_accelerating.xml,data/entities/particles/tinyspark_white_small.xml,"
      draw_actions( 1, true )
    end,
```

## ![Acid](images/MATERIAL_ACID.png)Acid (MATERIAL_ACID)

* **description**: Transmute drops of acid from nothing
* **type**: ACTION_TYPE_MATERIAL
* **spawn_level**: [2, 3, 4, 5, 6]
* **spawn_probability**: [0.4, 0.4, 0.4, 0.4, 0.4]
* **price**: 150
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/material_acid.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/material_acid.xml")
      c.fire_rate_wait = c.fire_rate_wait - 15
      current_reload_time = current_reload_time - ACTION_DRAW_RELOAD_TIME_INCREASE - 10 -- this is a hack to get the cement reload time back to 0
    end,
```

## ![Acid ball](images/ACIDSHOT.png)Acid ball (ACIDSHOT)

* **description**: A terrifying acidic projectile
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [1, 2, 3, 4]
* **spawn_probability**: [1.0, 1.0, 1.0, 1.0]
* **price**: 180
* **mana**: 20
* **max_uses**: 20
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/acidshot.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/acidshot.xml")
      c.fire_rate_wait = c.fire_rate_wait + 10
    end,
```

## ![Acid cloud](images/CLOUD_ACID.png)Acid cloud (CLOUD_ACID)

* **description**: Creates a rain of acid
* **type**: ACTION_TYPE_STATIC_PROJECTILE
* **spawn_level**: [0, 1, 2, 3, 4, 5]
* **spawn_probability**: [0.2, 0.2, 0.2, 0.2, 0.2, 0.2]
* **price**: 180
* **mana**: 90
* **max_uses**: 8
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/cloud_acid.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/cloud_acid.xml")
      c.fire_rate_wait = c.fire_rate_wait + 15
    end,
```

## ![Acid trail](images/ACID_TRAIL.png)Acid trail (ACID_TRAIL)

* **description**: Gives a projectile a trail of acid
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 2, 3, 4, 5]
* **spawn_probability**: [0.3, 0.3, 0.3, 0.3, 0.3]
* **price**: 160
* **mana**: 15
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      c.trail_material = c.trail_material .. "acid,"
      c.trail_material_amount = c.trail_material_amount + 5
      draw_actions( 1, true )
    end,
```

## ![Add expiration trigger](images/ADD_DEATH_TRIGGER.png)Add expiration trigger (ADD_DEATH_TRIGGER)

* **description**: Makes a projectile cast another spell upon expiring
* **type**: ACTION_TYPE_OTHER
* **spawn_level**: [3, 4, 5, 10]
* **spawn_probability**: [0.3, 0.6, 0.6, 1.0]
* **price**: 150
* **mana**: 20
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_mestari
* **related_extra_entities**: 
* **action**:

```lua
 function()
      local data = {}
      
      local how_many = 1
      
      if ( #deck > 0 ) then
        data = deck[1]
      else
        data = nil
      end
      
      if ( data ~= nil ) then
        while ( #deck >= how_many ) and ( ( data.type == ACTION_TYPE_MODIFIER ) or ( data.type == ACTION_TYPE_PASSIVE ) or ( data.type == ACTION_TYPE_OTHER ) or ( data.type == ACTION_TYPE_DRAW_MANY ) ) do
          if ( ( data.uses_remaining == nil ) or ( data.uses_remaining ~= 0 ) ) and ( data.id ~= "ADD_TRIGGER" ) and ( data.id ~= "ADD_TIMER" ) and ( data.id ~= "ADD_DEATH_TRIGGER" ) then
            if ( data.type == ACTION_TYPE_MODIFIER ) then
              dont_draw_actions = true
              data.action()
              dont_draw_actions = false
            end
          end
          how_many = how_many + 1
          data = deck[how_many]
        end
        
        if ( data ~= nil ) and ( data.related_projectiles ~= nil ) and ( ( data.uses_remaining == nil ) or ( data.uses_remaining ~= 0 ) ) then
          local target = data.related_projectiles[1]
          local count = data.related_projectiles[2] or 1
          
          for i=1,how_many do
            data = deck[1]
            table.insert( discarded, data )
            table.remove( deck, 1 )
          end
          
          local valid = false
          
          for i=1,#deck do
            local check = deck[i]
            
            if ( check ~= nil ) and ( ( check.type == ACTION_TYPE_PROJECTILE ) or ( check.type == ACTION_TYPE_STATIC_PROJECTILE ) or ( check.type == ACTION_TYPE_MATERIAL ) or ( check.type == ACTION_TYPE_UTILITY ) ) then
              valid = true
              break
            end
          end
          
          if ( data.uses_remaining ~= nil ) and ( data.uses_remaining > 0 ) then
            data.uses_remaining = data.uses_remaining - 1
            
            local reduce_uses = ActionUsesRemainingChanged( data.inventoryitem_id, data.uses_remaining )
            if not reduce_uses then
              data.uses_remaining = data.uses_remaining + 1 -- cancel the reduction
            end
          end
          
          if valid then
            for i=1,count do
              add_projectile_trigger_death(target, 1)
            end
          else
            dont_draw_actions = true
            data.action()
            dont_draw_actions = false
          end
        end
      end
    end,
```

## ![Add mana](images/MANA_REDUCE.png)Add mana (MANA_REDUCE)

* **description**: Adds 30 mana to the wand
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 2, 3, 4, 5, 6]
* **spawn_probability**: [1.0, 1.0, 1.0, 1.0, 1.0, 1.0]
* **price**: 250
* **mana**: -30
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      c.fire_rate_wait = c.fire_rate_wait + 10
      draw_actions( 1, true )
    end,
```

## ![Add timer](images/ADD_TIMER.png)Add timer (ADD_TIMER)

* **description**: Makes a projectile cast another spell after a short time
* **type**: ACTION_TYPE_OTHER
* **spawn_level**: [3, 4, 5, 10]
* **spawn_probability**: [0.3, 0.6, 0.6, 1.0]
* **price**: 150
* **mana**: 20
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_mestari
* **related_extra_entities**: 
* **action**:

```lua
 function()
      local data = {}
      
      local how_many = 1
      
      if ( #deck > 0 ) then
        data = deck[1]
      else
        data = nil
      end
      
      if ( data ~= nil ) then
        while ( #deck >= how_many ) and ( ( data.type == ACTION_TYPE_MODIFIER ) or ( data.type == ACTION_TYPE_PASSIVE ) or ( data.type == ACTION_TYPE_OTHER ) or ( data.type == ACTION_TYPE_DRAW_MANY ) ) do
          if ( ( data.uses_remaining == nil ) or ( data.uses_remaining ~= 0 ) ) and ( data.id ~= "ADD_TRIGGER" ) and ( data.id ~= "ADD_TIMER" ) and ( data.id ~= "ADD_DEATH_TRIGGER" ) then
            if ( data.type == ACTION_TYPE_MODIFIER ) then
              dont_draw_actions = true
              data.action()
              dont_draw_actions = false
            end
          end
          how_many = how_many + 1
          data = deck[how_many]
        end
        
        if ( data ~= nil ) and ( data.related_projectiles ~= nil ) and ( ( data.uses_remaining == nil ) or ( data.uses_remaining ~= 0 ) ) then
          local target = data.related_projectiles[1]
          local count = data.related_projectiles[2] or 1
          
          for i=1,how_many do
            data = deck[1]
            table.insert( discarded, data )
            table.remove( deck, 1 )
          end
          
          local valid = false
          
          for i=1,#deck do
            local check = deck[i]
            
            if ( check ~= nil ) and ( ( check.type == ACTION_TYPE_PROJECTILE ) or ( check.type == ACTION_TYPE_STATIC_PROJECTILE ) or ( check.type == ACTION_TYPE_MATERIAL ) or ( check.type == ACTION_TYPE_UTILITY ) ) then
              valid = true
              break
            end
          end
          
          if ( data.uses_remaining ~= nil ) and ( data.uses_remaining > 0 ) then
            data.uses_remaining = data.uses_remaining - 1
            
            local reduce_uses = ActionUsesRemainingChanged( data.inventoryitem_id, data.uses_remaining )
            if not reduce_uses then
              data.uses_remaining = data.uses_remaining + 1 -- cancel the reduction
            end
          end
          
          if valid then
            for i=1,count do
              add_projectile_trigger_timer(target, 20, 1)
            end
          else
            dont_draw_actions = true
            data.action()
            dont_draw_actions = false
          end
        end
      end
    end,
```

## ![Add trigger](images/ADD_TRIGGER.png)Add trigger (ADD_TRIGGER)

* **description**: Makes a projectile cast another spell upon collision
* **type**: ACTION_TYPE_OTHER
* **spawn_level**: [3, 4, 5, 10]
* **spawn_probability**: [0.3, 0.6, 0.6, 1.0]
* **price**: 100
* **mana**: 10
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_mestari
* **related_extra_entities**: 
* **action**:

```lua
 function()
      local data = {}
      
      local how_many = 1
      
      if ( #deck > 0 ) then
        data = deck[1]
      else
        data = nil
      end
      
      if ( data ~= nil ) then
        while ( #deck >= how_many ) and ( ( data.type == ACTION_TYPE_MODIFIER ) or ( data.type == ACTION_TYPE_PASSIVE ) or ( data.type == ACTION_TYPE_OTHER ) or ( data.type == ACTION_TYPE_DRAW_MANY ) ) do
          if ( ( data.uses_remaining == nil ) or ( data.uses_remaining ~= 0 ) ) and ( data.id ~= "ADD_TRIGGER" ) and ( data.id ~= "ADD_TIMER" ) and ( data.id ~= "ADD_DEATH_TRIGGER" ) then
            if ( data.type == ACTION_TYPE_MODIFIER ) then
              dont_draw_actions = true
              data.action()
              dont_draw_actions = false
            end
          end
          how_many = how_many + 1
          data = deck[how_many]
        end
        
        if ( data ~= nil ) and ( data.related_projectiles ~= nil ) and ( ( data.uses_remaining == nil ) or ( data.uses_remaining ~= 0 ) ) then
          local target = data.related_projectiles[1]
          local count = data.related_projectiles[2] or 1
          
          for i=1,how_many do
            data = deck[1]
            table.insert( discarded, data )
            table.remove( deck, 1 )
          end
          
          local valid = false
          
          for i=1,#deck do
            local check = deck[i]
            
            if ( check ~= nil ) and ( ( check.type == ACTION_TYPE_PROJECTILE ) or ( check.type == ACTION_TYPE_STATIC_PROJECTILE ) or ( check.type == ACTION_TYPE_MATERIAL ) or ( check.type == ACTION_TYPE_UTILITY ) ) then
              valid = true
              break
            end
          end
          
          if ( data.uses_remaining ~= nil ) and ( data.uses_remaining > 0 ) then
            data.uses_remaining = data.uses_remaining - 1
            
            local reduce_uses = ActionUsesRemainingChanged( data.inventoryitem_id, data.uses_remaining )
            if not reduce_uses then
              data.uses_remaining = data.uses_remaining + 1 -- cancel the reduction
            end
          end
          
          if valid then
            for i=1,count do
              add_projectile_trigger_hit_world(target, 1)
            end
          else
            dont_draw_actions = true
            data.action()
            dont_draw_actions = false
          end
        end
      end
    end,
```

## ![Aiming Arc](images/HOMING_CURSOR.png)Aiming Arc (HOMING_CURSOR)

* **description**: A projectile rotates towards the direction you're aiming
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4, 5, 6]
* **spawn_probability**: [0.7, 0.7, 0.4, 0.4, 1.0]
* **price**: 175
* **mana**: 30
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/homing_cursor.xml", "data/entities/particles/tinyspark_white.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/homing_cursor.xml,data/entities/particles/tinyspark_white.xml,"
      draw_actions( 1, true )
    end,
```

## ![All-seeing eye](images/X_RAY.png)All-seeing eye (X_RAY)

* **description**: See into the unexplored. But not everywhere...
* **type**: ACTION_TYPE_UTILITY
* **spawn_level**: [0, 1, 2, 3, 4, 5, 6]
* **spawn_probability**: [0.8, 1.0, 1.0, 0.8, 0.6, 0.4, 0.2]
* **price**: 230
* **mana**: 100
* **max_uses**: 10
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/xray.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/xray.xml")
    end,
```

## ![Alpha](images/ALPHA.png)Alpha (ALPHA)

* **description**: Casts a copy of the first spell in your wand
* **type**: ACTION_TYPE_OTHER
* **spawn_level**: [5, 6, 10]
* **spawn_probability**: [0.1, 0.1, 1.0]
* **price**: 200
* **mana**: 30
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: true
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_duplicate
* **related_extra_entities**: 
* **action**:

```lua
 function( recursion_level, iteration )
      c.fire_rate_wait = c.fire_rate_wait + 15
      
      local data = {}
      
      if ( #discarded > 0 ) then
        data = discarded[1]
      elseif ( #hand > 0 ) then
        data = hand[1]
      elseif ( #deck > 0 ) then
        data = deck[1]
      else
        data = nil
      end
      
      local rec = check_recursion( data, recursion_level )
      
      if ( data ~= nil ) and ( rec > -1 ) then
        data.action( rec )
      end
      
    end,
```

## ![Anti-gravity](images/GRAVITY_ANTI.png)Anti-gravity (GRAVITY_ANTI)

* **description**: Applies a lifting force to a projectile
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4, 5, 6]
* **spawn_probability**: [0.5, 0.5, 0.5, 0.5, 0.5]
* **price**: 50
* **mana**: 1
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      c.gravity = c.gravity - 600.0
      draw_actions( 1, true )
    end,
```

## ![Arrow](images/ARROW.png)Arrow (ARROW)

* **description**: Summons an arrow
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [1, 2, 4, 5]
* **spawn_probability**: [1.0, 1.0, 1.0, 1.0]
* **price**: 140
* **mana**: 15
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/arrow.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/arrow.xml")
      c.fire_rate_wait = c.fire_rate_wait + 10
      c.spread_degrees = c.spread_degrees - 20
      shot_effects.recoil_knockback = 30.0
    end,
```

## ![Auto-Aim](images/AUTOAIM.png)Auto-Aim (AUTOAIM)

* **description**: Makes a projectile turns towards the nearest visible enemy
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4, 5, 6]
* **spawn_probability**: [0.4, 0.4, 0.4, 0.4, 0.4]
* **price**: 150
* **mana**: 25
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/autoaim.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/autoaim.xml,"
      draw_actions( 1, true )
    end,
```

## ![Avoiding arc](images/AVOIDING_ARC.png)Avoiding arc (AVOIDING_ARC)

* **description**: Makes a projectile shy away from obstacles
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 4, 6]
* **spawn_probability**: [0.4, 0.4, 0.4]
* **price**: 30
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/avoiding_arc.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/avoiding_arc.xml,"
      c.fire_rate_wait    = c.fire_rate_wait + 10
      draw_actions( 1, true )
    end,
```

## ![Ball Lightning](images/BALL_LIGHTNING.png)Ball Lightning (BALL_LIGHTNING)

* **description**: Summons three short range electrical orbs
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [1, 2, 4, 5]
* **spawn_probability**: [0.2, 0.2, 1.0, 1.0]
* **price**: 250
* **mana**: 70
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/ball_lightning.xml",3}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/ball_lightning.xml")
      add_projectile("data/entities/projectiles/deck/ball_lightning.xml")
      add_projectile("data/entities/projectiles/deck/ball_lightning.xml")
      c.fire_rate_wait = c.fire_rate_wait + 50
      shot_effects.recoil_knockback = 120.0
    end,
```

## ![Big magic guard](images/BIG_MAGIC_SHIELD.png)Big magic guard (BIG_MAGIC_SHIELD)

* **description**: Eight guarding lights rotate around you for a time
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [2, 4, 5, 6, 10]
* **spawn_probability**: [0.2, 0.2, 0.5, 0.5, 0.1]
* **price**: 120
* **mana**: 60
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/big_magic_shield_start.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/big_magic_shield_start.xml")
      c.fire_rate_wait = c.fire_rate_wait + 30
    end,
```

## ![Black Hole with Death Trigger](images/BLACK_HOLE_DEATH_TRIGGER.png)Black Hole with Death Trigger (BLACK_HOLE_DEATH_TRIGGER)

* **description**: A slow orb of void that eats through all obstacles and casts another spell as it expires
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [2, 4, 5, 6]
* **spawn_probability**: [0.5, 0.5, 0.5, 0.5]
* **price**: 220
* **mana**: 200
* **max_uses**: 3
* **never_unlimited**: true
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/black_hole.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile_trigger_death("data/entities/projectiles/deck/black_hole.xml", 1)
      c.fire_rate_wait = c.fire_rate_wait + 90
      c.screenshake = c.screenshake + 20
    end,
```

## ![Black hole](images/BLACK_HOLE.png)Black hole (BLACK_HOLE)

* **description**: A slow orb of void that eats through all obstacles
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [0, 2, 4, 5]
* **spawn_probability**: [0.8, 0.8, 0.8, 0.8]
* **price**: 200
* **mana**: 180
* **max_uses**: 3
* **never_unlimited**: true
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/black_hole.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/black_hole.xml")
      c.fire_rate_wait = c.fire_rate_wait + 80
      c.screenshake = c.screenshake + 20
    end,
```

## ![Blood](images/MATERIAL_BLOOD.png)Blood (MATERIAL_BLOOD)

* **description**: Blood blood blood
* **type**: ACTION_TYPE_MATERIAL
* **spawn_level**: [1, 2, 3, 4, 5]
* **spawn_probability**: [0.4, 0.4, 0.4, 0.4, 0.4]
* **price**: 130
* **mana**: 0
* **max_uses**: 250
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/material_blood.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/material_blood.xml")
      c.game_effect_entities = c.game_effect_entities .. "data/entities/misc/effect_apply_bloody.xml,"
      c.fire_rate_wait = c.fire_rate_wait - 15
      current_reload_time = current_reload_time - ACTION_DRAW_RELOAD_TIME_INCREASE - 10 -- this is a hack to get the cement reload time back to 0
    end,
```

## ![Blood cloud](images/CLOUD_BLOOD.png)Blood cloud (CLOUD_BLOOD)

* **description**: Creates a rain of blood
* **type**: ACTION_TYPE_STATIC_PROJECTILE
* **spawn_level**: [0, 1, 2, 3, 4, 5]
* **spawn_probability**: [0.3, 0.3, 0.3, 0.3, 0.3, 0.3]
* **price**: 200
* **mana**: 60
* **max_uses**: 3
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/cloud_blood.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/cloud_blood.xml")
      c.fire_rate_wait = c.fire_rate_wait + 30
    end,
```

## ![Blood magic](images/BLOOD_MAGIC.png)Blood magic (BLOOD_MAGIC)

* **description**: Reduces a spell's mana cost and recharge time greatly, at the costs of four health points
* **type**: ACTION_TYPE_UTILITY
* **spawn_level**: [5, 6, 10]
* **spawn_probability**: [0.1, 0.7, 0.5]
* **price**: 150
* **mana**: -100
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/particles/blood_sparks.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/particles/blood_sparks.xml,"
      c.fire_rate_wait = c.fire_rate_wait - 20
      current_reload_time = current_reload_time - 20
      draw_actions( 1, true )
      
      local entity_id = GetUpdatedEntityID()
      
      local dcomps = EntityGetComponent( entity_id, "DamageModelComponent" )
      
      if ( dcomps ~= nil ) and ( #dcomps > 0 ) then
        for a,b in ipairs( dcomps ) do
          local hp = ComponentGetValue2( b, "hp" )
          hp = math.max( hp - 0.16, 0.04 )
          ComponentSetValue2( b, "hp", hp )
        end
      end
    end,
```

## ![Blood mist](images/MIST_BLOOD.png)Blood mist (MIST_BLOOD)

* **description**: A cloud of blood mist
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [1, 2, 3, 4]
* **spawn_probability**: [0.4, 0.4, 0.4, 0.4]
* **price**: 120
* **mana**: 40
* **max_uses**: 10
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/mist_blood.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/mist_blood.xml")
      c.fire_rate_wait = c.fire_rate_wait + 10
    end,
```

## ![Blood to Power](images/BLOOD_TO_POWER.png)Blood to Power (BLOOD_TO_POWER)

* **description**: A projectile gains additional damage at the cost of 20% of your health
* **type**: ACTION_TYPE_UTILITY
* **spawn_level**: [2, 5, 6, 10]
* **spawn_probability**: [0.2, 0.8, 0.1, 0.5]
* **price**: 150
* **mana**: 20
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/particles/blood_sparks.xml" }
* **action**:

```lua
 function()
      local entity_id = GetUpdatedEntityID()
      
      local dcomp = EntityGetFirstComponent( entity_id, "DamageModelComponent" )
      
      if ( dcomp ~= nil ) then
        local hp = ComponentGetValue2( dcomp, "hp" )
        local damage = math.min( hp * 0.44, 960 )
        local self_damage = hp * 0.2
        
        if ( hp >= 0.4 ) and ( self_damage > 0.2 ) then
          c.extra_entities = c.extra_entities .. "data/entities/particles/blood_sparks.xml,"
          
          EntityInflictDamage( entity_id, self_damage, "DAMAGE_CURSE", "$action_blood_to_power", "NONE", 0, 0, entity_id )
          
          
          c.damage_projectile_add = c.damage_projectile_add + damage
        end
      end
      
      draw_actions( 1, true )
    end,
```

## ![Blood to acid](images/BLOOD_TO_ACID.png)Blood to acid (BLOOD_TO_ACID)

* **description**: Makes any blood within a projectile's range turns into acid
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4]
* **spawn_probability**: [0.3, 0.3, 0.3]
* **price**: 80
* **mana**: 30
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/blood_to_acid.xml", "data/entities/particles/tinyspark_red.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/blood_to_acid.xml,data/entities/particles/tinyspark_red.xml,"
      c.fire_rate_wait = c.fire_rate_wait + 10
      draw_actions( 1, true )
    end,
```

## ![Bloodlust](images/BLOODLUST.png)Bloodlust (BLOODLUST)

* **description**: A projectile gains a hefty damage boost, but is also able to hurt you
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 3, 4, 5, 6]
* **spawn_probability**: [0.2, 0.3, 0.6, 0.6, 0.3]
* **price**: 160
* **mana**: 2
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/particles/tinyspark_red.xml" }
* **action**:

```lua
 function()
      c.damage_projectile_add = c.damage_projectile_add + 1.3
      c.gore_particles    = c.gore_particles + 15
      c.fire_rate_wait    = c.fire_rate_wait + 8
      c.friendly_fire    = true
      shot_effects.recoil_knockback = shot_effects.recoil_knockback + 30.0
      c.spread_degrees = c.spread_degrees + 6
      c.extra_entities    = c.extra_entities .. "data/entities/particles/tinyspark_red.xml,"
      draw_actions( 1, true )
    end,
```

## ![Blue Glimmer](images/COLOUR_BLUE.png)Blue Glimmer (COLOUR_BLUE)

* **description**: Gives a projectile a blue sparkly trail
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4]
* **spawn_probability**: [0.1, 0.1, 0.1]
* **price**: 40
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_paint
* **related_extra_entities**: { "data/entities/particles/tinyspark_red.xml", "data/entities/misc/colour_blue.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/particles/tinyspark_red.xml,data/entities/misc/colour_blue.xml,"
      c.fire_rate_wait = c.fire_rate_wait - 8
      c.screenshake = c.screenshake - 2.5
      if ( c.screenshake < 0 ) then
        c.screenshake = 0
      end
      draw_actions( 1, true )
    end,
```

## ![Bomb](images/BOMB.png)Bomb (BOMB)

* **description**: Summons a bomb that destroys ground very efficiently
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [0, 1, 2, 3, 4, 5, 6]
* **spawn_probability**: [1.0, 1.0, 1.0, 1.0, 1.0, 1.0, 1.0]
* **price**: 200
* **mana**: 25
* **max_uses**: 3
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/bomb.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/bomb.xml")
      c.fire_rate_wait = c.fire_rate_wait + 100
    end,
```

## ![Bomb cart](images/BOMB_CART.png)Bomb cart (BOMB_CART)

* **description**: Summons a self-propeled mine cart loaded with explosives
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [0, 1, 2, 3, 4, 5, 6]
* **spawn_probability**: [0.0, 0.0, 0.6, 0.6, 0.6, 0.6, 0.6]
* **price**: 200
* **mana**: 75
* **max_uses**: 6
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/bomb_cart.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/bomb_cart.xml")
      shot_effects.recoil_knockback = shot_effects.recoil_knockback + 200.0
      c.fire_rate_wait = c.fire_rate_wait + 60
    end,
```

## ![Boomerang](images/HOMING_SHOOTER.png)Boomerang (HOMING_SHOOTER)

* **description**: Gives a projectile a path that curves towards you
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4, 5, 6]
* **spawn_probability**: [0.2, 0.2, 0.2, 0.2, 0.2]
* **price**: 100
* **mana**: 10
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/homing_shooter.xml", "data/entities/particles/tinyspark_white.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/homing_shooter.xml,data/entities/particles/tinyspark_white.xml,"
      draw_actions( 1, true )
    end,
```

## ![Bounce](images/BOUNCE.png)Bounce (BOUNCE)

* **description**: Makes a projectile bounce on impact
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4, 5, 6]
* **spawn_probability**: [1.0, 1.0, 0.4, 0.2, 0.2]
* **price**: 50
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      c.bounces = c.bounces + 10
      draw_actions( 1, true )
    end,
```

## ![Bouncing burst](images/RUBBER_BALL.png)Bouncing burst (RUBBER_BALL)

* **description**: A very bouncy projectile
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [0, 1, 6]
* **spawn_probability**: [1.0, 1.0, 1.0]
* **price**: 60
* **mana**: 5
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/rubber_ball.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/rubber_ball.xml")
      c.fire_rate_wait = c.fire_rate_wait - 2
      c.spread_degrees = c.spread_degrees - 1.0
    end,
```

## ![Bubble spark](images/BUBBLESHOT.png)Bubble spark (BUBBLESHOT)

* **description**: A bouncy, inaccurate spell
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [0, 1, 2, 3]
* **spawn_probability**: [1.0, 1.0, 1.0, 0.5]
* **price**: 100
* **mana**: 5
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/bubbleshot.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/bubbleshot.xml")
      c.fire_rate_wait = c.fire_rate_wait - 5
      c.dampening = 0.1
    end,
```

## ![Bubble spark with trigger](images/BUBBLESHOT_TRIGGER.png)Bubble spark with trigger (BUBBLESHOT_TRIGGER)

* **description**: A bouncy, inaccurate spell that casts another spell upon collision
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [1, 2, 3]
* **spawn_probability**: [0.5, 0.5, 1.0]
* **price**: 120
* **mana**: 16
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/bubbleshot.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      c.fire_rate_wait = c.fire_rate_wait - 5
      c.dampening = 0.1
      add_projectile_trigger_hit_world("data/entities/projectiles/deck/bubbleshot.xml", 1)
    end,
```

## ![Bubbly bounce](images/BOUNCE_SPARK.png)Bubbly bounce (BOUNCE_SPARK)

* **description**: Makes a projectile shoot bubble sparks as it bounces
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 2, 3, 4]
* **spawn_probability**: [0.2, 0.6, 0.6, 0.6]
* **price**: 120
* **mana**: 20
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/bounce_spark.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/bounce_spark.xml,"
      c.bounces = c.bounces + 1
      c.fire_rate_wait = c.fire_rate_wait + 8
      shot_effects.recoil_knockback = shot_effects.recoil_knockback + 5.0
      draw_actions( 1, true )
    end,
```

## ![Burning trail](images/BURN_TRAIL.png)Burning trail (BURN_TRAIL)

* **description**: Gives a projectile a tail of fire
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [0, 1, 2]
* **spawn_probability**: [0.3, 0.3, 0.3]
* **price**: 100
* **mana**: 5
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/burn.xml" }
* **action**:

```lua
 function()
      c.game_effect_entities = c.game_effect_entities .. "data/entities/misc/effect_apply_on_fire.xml,"
      c.extra_entities = c.extra_entities .. "data/entities/misc/burn.xml,"
      draw_actions( 1, true )
    end,
```

## ![Burst of air](images/AIR_BULLET.png)Burst of air (AIR_BULLET)

* **description**: A brittle burst of air capable of greatly pushing objects
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [1, 2]
* **spawn_probability**: [1.0, 1.0]
* **price**: 80
* **mana**: 5
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/light_bullet_air.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/light_bullet_air.xml")
      c.fire_rate_wait = c.fire_rate_wait + 3
      c.spread_degrees = c.spread_degrees - 2.0
    end,
```

## ![Cement](images/MATERIAL_CEMENT.png)Cement (MATERIAL_CEMENT)

* **description**: Transmute drops of wet cement from nothing
* **type**: ACTION_TYPE_MATERIAL
* **spawn_level**: [2, 3, 4, 5, 6]
* **spawn_probability**: [0.4, 0.4, 0.4, 0.4, 0.4]
* **price**: 100
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/material_cement.xml"}
* **spawn_requires_flag**: card_unlocked_material_cement
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/material_cement.xml")
      c.fire_rate_wait = c.fire_rate_wait - 15
      current_reload_time = current_reload_time - ACTION_DRAW_RELOAD_TIME_INCREASE - 10 -- this is a hack to get the cement reload time back to 0
    end,
```

## ![Chain Spell](images/CHAIN_SHOT.png)Chain Spell (CHAIN_SHOT)

* **description**: Causes a projectile to cast a copy of itself upon expiring, up to 5 times
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 4, 5]
* **spawn_probability**: [0.4, 0.6, 0.8]
* **price**: 240
* **mana**: 70
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/chain_shot.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/chain_shot.xml,"
      c.lifetime_add = c.lifetime_add - 30
      c.damage_projectile_add = c.damage_projectile_add - 0.2
      c.explosion_radius = c.explosion_radius - 5.0
      if (c.explosion_radius < 0) then
        c.explosion_radius = 0
      end
      c.spread_degrees = c.spread_degrees + 10.0
      draw_actions( 1, true )
    end,
```

## ![Chain bolt](images/CHAIN_BOLT.png)Chain bolt (CHAIN_BOLT)

* **description**: Fires a mysterious bolt that jumps from enemy to enemy
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [0, 4, 5, 6]
* **spawn_probability**: [1.0, 1.0, 1.0, 1.0]
* **price**: 240
* **mana**: 80
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/chain_bolt.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/chain_bolt.xml")
      c.spread_degrees = c.spread_degrees + 14.0
      c.fire_rate_wait = c.fire_rate_wait + 45
    end,
```

## ![Chainsaw](images/CHAINSAW.png)Chainsaw (CHAINSAW)

* **description**: A good tool for cutting meat. Also has some magical properties...
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [0, 2]
* **spawn_probability**: [1.0, 1.0]
* **price**: 80
* **mana**: 1
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/chainsaw.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/chainsaw.xml")
      c.fire_rate_wait = 0
      c.spread_degrees = c.spread_degrees + 6.0
      current_reload_time = current_reload_time - ACTION_DRAW_RELOAD_TIME_INCREASE - 10 -- this is a hack to get the digger reload time back to 0
    end,
```

## ![Chaos larpa](images/LARPA_CHAOS.png)Chaos larpa (LARPA_CHAOS)

* **description**: Makes a projectile cast copies of itself in random directions
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4, 5, 10]
* **spawn_probability**: [0.1, 0.2, 0.3, 0.4, 0.2]
* **price**: 260
* **mana**: 100
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/larpa_chaos.xml" }
* **action**:

```lua
 function()
      c.fire_rate_wait = c.fire_rate_wait + 15
      c.extra_entities = c.extra_entities .. "data/entities/misc/larpa_chaos.xml,"
      draw_actions( 1, true )
    end,
```

## ![Chaos magic](images/RANDOM_EXPLOSION.png)Chaos magic (RANDOM_EXPLOSION)

* **description**: Makes a projectile launch a random spell (out of a limited selection) when it hits something
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [3, 5, 6]
* **spawn_probability**: [0.3, 0.6, 1.0]
* **price**: 240
* **mana**: 120
* **max_uses**: 30
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/random_explosion.xml", "data/entities/particles/tinyspark_purple_bright.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/random_explosion.xml,data/entities/particles/tinyspark_purple_bright.xml,"
      c.fire_rate_wait = c.fire_rate_wait + 40
      draw_actions( 1, true )
    end,
```

## ![Chaotic path](images/CHAOTIC_ARC.png)Chaotic path (CHAOTIC_ARC)

* **description**: Causes a projectile to chaotically fly wherever it wishes
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 3, 5]
* **spawn_probability**: [0.4, 0.4, 0.4]
* **price**: 10
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/chaotic_arc.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/chaotic_arc.xml,"
      c.speed_multiplier = c.speed_multiplier * 2
      
      if ( c.speed_multiplier >= 20 ) then
        c.speed_multiplier = math.min( c.speed_multiplier, 20 )
      elseif ( c.speed_multiplier < 0 ) then
        c.speed_multiplier = 0
      end
      
      draw_actions( 1, true )
    end,
```

## ![Chaotic transmutation](images/TRANSMUTATION.png)Chaotic transmutation (TRANSMUTATION)

* **description**: Transmutes various liquids and powdery substances within a projectile's range into something else
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4, 5, 6, 10]
* **spawn_probability**: [0.3, 0.3, 0.3, 0.3, 0.3, 0.2]
* **price**: 180
* **mana**: 80
* **max_uses**: 8
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/transmutation.xml", "data/entities/particles/tinyspark_purple_bright.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/transmutation.xml,data/entities/particles/tinyspark_purple_bright.xml,"
      c.fire_rate_wait = c.fire_rate_wait + 20
      draw_actions( 1, true )
    end,
```

## ![Charm on toxic sludge](images/HITFX_TOXIC_CHARM.png)Charm on toxic sludge (HITFX_TOXIC_CHARM)

* **description**: Makes a projectile charm creatures covered in toxic sludge
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 3, 4, 5]
* **spawn_probability**: [0.2, 0.2, 0.2, 0.2]
* **price**: 150
* **mana**: 70
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/hitfx_toxic_charm.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/hitfx_toxic_charm.xml,"
      draw_actions( 1, true )
    end,
```

## ![Chunk of soil](images/SOILBALL.png)Chunk of soil (SOILBALL)

* **description**: Don't soil yourself
* **type**: ACTION_TYPE_MATERIAL
* **spawn_level**: [1, 2, 3, 5]
* **spawn_probability**: [1.0, 1.0, 1.0, 1.0]
* **price**: 10
* **mana**: 5
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/chunk_of_soil.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/chunk_of_soil.xml")
    end,
```

## ![Circle of acid](images/CIRCLE_ACID.png)Circle of acid (CIRCLE_ACID)

* **description**: An expanding circle of dripping acid
* **type**: ACTION_TYPE_MATERIAL
* **spawn_level**: [1, 2, 3, 4]
* **spawn_probability**: [0.4, 0.4, 0.4, 0.4]
* **price**: 180
* **mana**: 40
* **max_uses**: 4
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/circle_acid.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/circle_acid.xml")
      c.fire_rate_wait = c.fire_rate_wait + 20
    end,
```

## ![Circle of buoyancy](images/LEVITATION_FIELD.png)Circle of buoyancy (LEVITATION_FIELD)

* **description**: A field of levitative magic
* **type**: ACTION_TYPE_STATIC_PROJECTILE
* **spawn_level**: [1, 2, 3, 4]
* **spawn_probability**: [0.3, 0.6, 0.6, 0.3]
* **price**: 120
* **mana**: 10
* **max_uses**: 15
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/levitation_field.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/levitation_field.xml")
      c.fire_rate_wait = c.fire_rate_wait + 15
    end,
```

## ![Circle of displacement](images/TELEPORTATION_FIELD.png)Circle of displacement (TELEPORTATION_FIELD)

* **description**: A field of teleportative magic
* **type**: ACTION_TYPE_STATIC_PROJECTILE
* **spawn_level**: [0, 1, 2, 3, 4, 5]
* **spawn_probability**: [0.3, 0.6, 0.3, 0.3, 0.6, 0.3]
* **price**: 150
* **mana**: 30
* **max_uses**: 15
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/teleportation_field.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/teleportation_field.xml")
      c.fire_rate_wait = c.fire_rate_wait + 15
    end,
```

## ![Circle of fervour](images/BERSERK_FIELD.png)Circle of fervour (BERSERK_FIELD)

* **description**: A field of berserk magic
* **type**: ACTION_TYPE_STATIC_PROJECTILE
* **spawn_level**: [2, 3, 4]
* **spawn_probability**: [0.3, 0.6, 0.3]
* **price**: 200
* **mana**: 30
* **max_uses**: 15
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/berserk_field.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/berserk_field.xml")
      c.fire_rate_wait = c.fire_rate_wait + 15
    end,
```

## ![Circle of fire](images/CIRCLE_FIRE.png)Circle of fire (CIRCLE_FIRE)

* **description**: An expanding circle of burning air
* **type**: ACTION_TYPE_MATERIAL
* **spawn_level**: [1, 2, 3, 4]
* **spawn_probability**: [0.4, 0.4, 0.4, 0.4]
* **price**: 170
* **mana**: 20
* **max_uses**: 15
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/circle_fire.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/circle_fire.xml")
      c.fire_rate_wait = c.fire_rate_wait + 20
    end,
```

## ![Circle of oil](images/CIRCLE_OIL.png)Circle of oil (CIRCLE_OIL)

* **description**: An expanding circle of slick oil
* **type**: ACTION_TYPE_MATERIAL
* **spawn_level**: [1, 2, 3, 4]
* **spawn_probability**: [0.4, 0.4, 0.4, 0.4]
* **price**: 160
* **mana**: 20
* **max_uses**: 15
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/circle_oil.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/circle_oil.xml")
      c.fire_rate_wait = c.fire_rate_wait + 20
    end,
```

## ![Circle of shielding](images/SHIELD_FIELD.png)Circle of shielding (SHIELD_FIELD)

* **description**: A field of protective magic
* **type**: ACTION_TYPE_STATIC_PROJECTILE
* **spawn_level**: [2, 3, 4, 5, 6]
* **spawn_probability**: [0.3, 0.3, 0.3, 0.3, 0.3]
* **price**: 160
* **mana**: 20
* **max_uses**: 10
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/shield_field.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/shield_field.xml")
      c.fire_rate_wait = c.fire_rate_wait + 15
    end,
```

## ![Circle of stillness](images/FREEZE_FIELD.png)Circle of stillness (FREEZE_FIELD)

* **description**: A field of freezing magic
* **type**: ACTION_TYPE_STATIC_PROJECTILE
* **spawn_level**: [0, 2, 4, 5]
* **spawn_probability**: [0.3, 0.6, 0.7, 0.3]
* **price**: 200
* **mana**: 50
* **max_uses**: 15
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/freeze_field.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/freeze_field.xml")
      c.fire_rate_wait = c.fire_rate_wait + 15
    end,
```

## ![Circle of thunder](images/ELECTROCUTION_FIELD.png)Circle of thunder (ELECTROCUTION_FIELD)

* **description**: A field of electrifying magic
* **type**: ACTION_TYPE_STATIC_PROJECTILE
* **spawn_level**: [1, 3, 5, 6]
* **spawn_probability**: [0.3, 0.6, 0.8, 0.3]
* **price**: 200
* **mana**: 60
* **max_uses**: 15
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/electrocution_field.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/electrocution_field.xml")
      c.fire_rate_wait = c.fire_rate_wait + 15
    end,
```

## ![Circle of transmogrification](images/POLYMORPH_FIELD.png)Circle of transmogrification (POLYMORPH_FIELD)

* **description**: A field of sheep-like magic
* **type**: ACTION_TYPE_STATIC_PROJECTILE
* **spawn_level**: [0, 1, 2, 3, 4, 5, 6]
* **spawn_probability**: [0.3, 0.3, 0.3, 0.8, 0.8, 0.3, 0.3]
* **price**: 200
* **mana**: 50
* **max_uses**: 5
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/polymorph_field.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/polymorph_field.xml")
      c.fire_rate_wait = c.fire_rate_wait + 15
    end,
```

## ![Circle of unstable metamorphosis](images/CHAOS_POLYMORPH_FIELD.png)Circle of unstable metamorphosis (CHAOS_POLYMORPH_FIELD)

* **description**: A field of transformative magic
* **type**: ACTION_TYPE_STATIC_PROJECTILE
* **spawn_level**: [1, 2, 3, 4, 5, 6]
* **spawn_probability**: [0.3, 0.3, 0.5, 0.6, 0.3, 0.3]
* **price**: 200
* **mana**: 20
* **max_uses**: 10
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/chaos_polymorph_field.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/chaos_polymorph_field.xml")
      c.fire_rate_wait = c.fire_rate_wait + 15
    end,
```

## ![Circle of vigour](images/REGENERATION_FIELD.png)Circle of vigour (REGENERATION_FIELD)

* **description**: A field of regenerative magic
* **type**: ACTION_TYPE_STATIC_PROJECTILE
* **spawn_level**: [1, 2, 3, 4]
* **spawn_probability**: [0.3, 0.3, 0.3, 0.3]
* **price**: 250
* **mana**: 80
* **max_uses**: 2
* **never_unlimited**: true
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/regeneration_field.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/regeneration_field.xml")
      c.fire_rate_wait = c.fire_rate_wait + 15
    end,
```

## ![Circle of water](images/CIRCLE_WATER.png)Circle of water (CIRCLE_WATER)

* **description**: An expanding circle of water
* **type**: ACTION_TYPE_MATERIAL
* **spawn_level**: [1, 2, 3, 4]
* **spawn_probability**: [0.4, 0.4, 0.4, 0.4]
* **price**: 160
* **mana**: 20
* **max_uses**: 15
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/circle_water.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/circle_water.xml")
      c.fire_rate_wait = c.fire_rate_wait + 20
    end,
```

## ![Concentrated Explosion](images/EXPLOSION_TINY.png)Concentrated Explosion (EXPLOSION_TINY)

* **description**: Limits the radius of a projectile's explosion heavily
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 4, 5, 6]
* **spawn_probability**: [0.2, 0.6, 0.7, 0.2]
* **price**: 160
* **mana**: 40
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/explosion_tiny.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/explosion_tiny.xml,"
      c.fire_rate_wait = c.fire_rate_wait + 15
      c.explosion_radius = c.explosion_radius - 30.0
      c.damage_explosion_add = c.damage_explosion_add + 0.8
      draw_actions( 1, true )
    end,
```

## ![Concentrated light](images/LASER.png)Concentrated light (LASER)

* **description**: A pinpointed beam of light
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [1, 2, 4]
* **spawn_probability**: [1.0, 1.0, 1.0]
* **price**: 180
* **mana**: 30
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/laser.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/laser.xml")
      c.fire_rate_wait = c.fire_rate_wait - 22
      c.game_effect_entities = c.game_effect_entities .. "data/entities/misc/effect_disintegrated.xml,"
      shot_effects.recoil_knockback = shot_effects.recoil_knockback + 20.0
    end,
```

## ![Concentrated light bounce](images/BOUNCE_LASER.png)Concentrated light bounce (BOUNCE_LASER)

* **description**: Makes a projectile release a bundle of concentrated light as it bounces
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [3, 4, 5]
* **spawn_probability**: [0.4, 0.8, 0.4]
* **price**: 180
* **mana**: 30
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/bounce_laser.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/bounce_laser.xml,"
      c.bounces = c.bounces + 1
      c.fire_rate_wait = c.fire_rate_wait + 12
      shot_effects.recoil_knockback = shot_effects.recoil_knockback + 5.0
      draw_actions( 1, true )
    end,
```

## ![Copy random spell](images/DRAW_RANDOM.png)Copy random spell (DRAW_RANDOM)

* **description**: Casts a random spell among the spells in your wand
* **type**: ACTION_TYPE_OTHER
* **spawn_level**: [2, 3, 4, 5, 6, 10]
* **spawn_probability**: [0.3, 0.2, 0.2, 0.1, 0.1, 1.0]
* **price**: 150
* **mana**: 20
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: true
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_pyramid
* **related_extra_entities**: 
* **action**:

```lua
 function( recursion_level, iteration )
      SetRandomSeed( GameGetFrameNum() + #deck, GameGetFrameNum() - 325 + #discarded )
      local datasize = #deck + #discarded
      local rnd = Random( 1, datasize )
      
      local data = {}
        
      if ( rnd <= #deck ) then
        data = deck[rnd]
      else
        data = discarded[rnd - #deck]
      end
      
      local checks = 0
      local rec = check_recursion( data, recursion_level )
      
      while ( data ~= nil ) and ( ( rec == -1 ) or ( ( data.uses_remaining ~= nil ) and ( data.uses_remaining == 0 ) ) ) and ( checks < datasize ) do
        rnd = ( rnd % datasize ) + 1
        checks = checks + 1
        
        if ( rnd <= #deck ) then
          data = deck[rnd]
        else
          data = discarded[rnd - #deck]
        end
        
        rec = check_recursion( data, recursion_level )
      end
      
      if ( data ~= nil ) and ( rec > -1 ) and ( ( data.uses_remaining == nil ) or ( data.uses_remaining ~= 0 ) ) then
        data.action( rec )
        
        if ( data.uses_remaining ~= nil ) and ( data.uses_remaining > 0 ) then
          data.uses_remaining = data.uses_remaining - 1
          
          local reduce_uses = ActionUsesRemainingChanged( data.inventoryitem_id, data.uses_remaining )
          if not reduce_uses then
            data.uses_remaining = data.uses_remaining + 1 -- cancel the reduction
          end
        end
      end
    end,
```

## ![Copy random spell thrice](images/DRAW_RANDOM_X3.png)Copy random spell thrice (DRAW_RANDOM_X3)

* **description**: Casts a random spell among the spells in your wand three times!
* **type**: ACTION_TYPE_OTHER
* **spawn_level**: [3, 4, 5, 6, 10]
* **spawn_probability**: [0.1, 0.3, 0.1, 0.1, 1.0]
* **price**: 250
* **mana**: 50
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: true
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_pyramid
* **related_extra_entities**: 
* **action**:

```lua
 function( recursion_level, iteration )
      SetRandomSeed( GameGetFrameNum() + #deck, GameGetFrameNum() - 325 + #discarded )
      local datasize = #deck + #discarded
      local rnd = Random( 1, datasize )
      
      local data = {}
        
      if ( rnd <= #deck ) then
        data = deck[rnd]
      else
        data = discarded[rnd - #deck]
      end
      
      local checks = 0
      local rec = check_recursion( data, recursion_level )
      
      while ( data ~= nil ) and ( ( rec == -1 ) or ( ( data.uses_remaining ~= nil ) and ( data.uses_remaining == 0 ) ) ) and ( checks < datasize ) do
        rnd = ( rnd % datasize ) + 1
        checks = checks + 1
        
        if ( rnd <= #deck ) then
          data = deck[rnd]
        else
          data = discarded[rnd - #deck]
        end
        
        rec = check_recursion( data, recursion_level )
      end
      
      if ( data ~= nil ) and ( rec > -1 ) and ( ( data.uses_remaining == nil ) or ( data.uses_remaining ~= 0 ) ) then
        for i=1,3 do
          data.action( rec )
        end
        
        if ( data.uses_remaining ~= nil ) and ( data.uses_remaining > 0 ) then
          data.uses_remaining = data.uses_remaining - 1
          
          local reduce_uses = ActionUsesRemainingChanged( data.inventoryitem_id, data.uses_remaining )
          if not reduce_uses then
            data.uses_remaining = data.uses_remaining + 1 -- cancel the reduction
          end
        end
      end
    end,
```

## ![Copy three random spells](images/DRAW_3_RANDOM.png)Copy three random spells (DRAW_3_RANDOM)

* **description**: Casts three random spells among the spells in your wand
* **type**: ACTION_TYPE_OTHER
* **spawn_level**: [2, 3, 5, 6, 10]
* **spawn_probability**: [0.1, 0.2, 0.1, 0.1, 1.0]
* **price**: 200
* **mana**: 40
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: true
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_pyramid
* **related_extra_entities**: 
* **action**:

```lua
 function( recursion_level, iteration )
      SetRandomSeed( GameGetFrameNum() + #deck, GameGetFrameNum() - 325 + #discarded )
      local datasize = #deck + #discarded
      
      for i=1,3 do
        local rnd = Random( 1, datasize )
        
        local data = {}
        
        if ( rnd <= #deck ) then
          data = deck[rnd]
        else
          data = discarded[rnd - #deck]
        end
        
        local checks = 0
        local rec = check_recursion( data, recursion_level )
        
        while ( data ~= nil ) and ( ( rec == -1 ) or ( ( data.uses_remaining ~= nil ) and ( data.uses_remaining == 0 ) ) ) and ( checks < datasize ) do
          rnd = ( rnd % datasize ) + 1
          checks = checks + 1
          
          if ( rnd <= #deck ) then
            data = deck[rnd]
          else
            data = discarded[rnd - #deck]
          end
          
          rec = check_recursion( data, recursion_level )
        end
        
        if ( data ~= nil ) and ( rec > -1 ) and ( ( data.uses_remaining == nil ) or ( data.uses_remaining ~= 0 ) ) then
          data.action( rec )
          
          if ( data.uses_remaining ~= nil ) and ( data.uses_remaining > 0 ) then
            data.uses_remaining = data.uses_remaining - 1
            
            local reduce_uses = ActionUsesRemainingChanged( data.inventoryitem_id, data.uses_remaining )
            if not reduce_uses then
              data.uses_remaining = data.uses_remaining + 1 -- cancel the reduction
            end
          end
        end
      end
    end,
```

## ![Copy trail](images/LARPA_CHAOS_2.png)Copy trail (LARPA_CHAOS_2)

* **description**: Makes a projectile leave a trail of copies of itself
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [3, 5, 10]
* **spawn_probability**: [0.1, 0.4, 0.1]
* **price**: 300
* **mana**: 150
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_alchemy
* **related_extra_entities**: { "data/entities/misc/larpa_chaos_2.xml" }
* **action**:

```lua
 function()
      c.fire_rate_wait = c.fire_rate_wait + 20
      c.extra_entities = c.extra_entities .. "data/entities/misc/larpa_chaos_2.xml,"
      draw_actions( 1, true )
    end,
```

## ![Critical Plus](images/CRITICAL_HIT.png)Critical Plus (CRITICAL_HIT)

* **description**: Gives a projectile +15% chance of a critical hit
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 2, 3, 4, 5]
* **spawn_probability**: [0.6, 0.6, 0.6, 0.6, 0.6]
* **price**: 140
* **mana**: 5
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      c.damage_critical_chance = c.damage_critical_chance + 15
      draw_actions( 1, true )
    end,
```

## ![Critical on bloody enemies](images/HITFX_CRITICAL_BLOOD.png)Critical on bloody enemies (HITFX_CRITICAL_BLOOD)

* **description**: Makes a projectile always do a critical hit on bloody enemies
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 3, 4, 5]
* **spawn_probability**: [0.2, 0.2, 0.2, 0.2]
* **price**: 70
* **mana**: 10
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/hitfx_critical_blood.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/hitfx_critical_blood.xml,"
      draw_actions( 1, true )
    end,
```

## ![Critical on burning](images/HITFX_BURNING_CRITICAL_HIT.png)Critical on burning (HITFX_BURNING_CRITICAL_HIT)

* **description**: Makes a projectile always do a critical hit on burning enemies
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 3, 4, 5]
* **spawn_probability**: [0.2, 0.2, 0.2, 0.2]
* **price**: 70
* **mana**: 10
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/particles/freeze_charge.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/hitfx_burning_critical_hit.xml,"
      draw_actions( 1, true )
    end,
```

## ![Critical on oiled enemies](images/HITFX_CRITICAL_OIL.png)Critical on oiled enemies (HITFX_CRITICAL_OIL)

* **description**: Makes a projectile always do a critical hit on oiled enemies
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 3, 4, 5]
* **spawn_probability**: [0.2, 0.2, 0.2, 0.2]
* **price**: 70
* **mana**: 10
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/hitfx_critical_oil.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/hitfx_critical_oil.xml,"
      draw_actions( 1, true )
    end,
```

## ![Critical on wet (water) enemies](images/HITFX_CRITICAL_WATER.png)Critical on wet (water) enemies (HITFX_CRITICAL_WATER)

* **description**: Makes a projectile always do a critical hit on wet (water) enemies
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 3, 4, 5]
* **spawn_probability**: [0.2, 0.2, 0.2, 0.2]
* **price**: 70
* **mana**: 10
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/hitfx_critical_water.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/hitfx_critical_water.xml,"
      draw_actions( 1, true )
    end,
```

## ![Cursed sphere](images/CURSED_ORB.png)Cursed sphere (CURSED_ORB)

* **description**: A projectile that brings bad luck to anyone it hits
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [1, 2, 3]
* **spawn_probability**: [0.3, 0.2, 0.1]
* **price**: 200
* **mana**: 40
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/orb_cursed.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/orb_cursed.xml")
      c.fire_rate_wait = c.fire_rate_wait + 20
      shot_effects.recoil_knockback = 40.0
    end,
```

## ![Damage Plus](images/DAMAGE.png)Damage Plus (DAMAGE)

* **description**: Increases the damage done by a projectile
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 2, 3, 4, 5]
* **spawn_probability**: [0.6, 0.6, 0.6, 0.6, 0.6]
* **price**: 140
* **mana**: 5
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/particles/tinyspark_yellow.xml" }
* **action**:

```lua
 function()
      c.damage_projectile_add = c.damage_projectile_add + 0.4
      c.gore_particles    = c.gore_particles + 5
      c.fire_rate_wait    = c.fire_rate_wait + 5
      c.extra_entities    = c.extra_entities .. "data/entities/particles/tinyspark_yellow.xml,"
      shot_effects.recoil_knockback = shot_effects.recoil_knockback + 10.0
      draw_actions( 1, true )
    end,
```

## ![Damage field](images/AREA_DAMAGE.png)Damage field (AREA_DAMAGE)

* **description**: Gives a projectile an energy field that constantly deals 3.5 damage to nearby creatures
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4, 5, 6]
* **spawn_probability**: [0.5, 0.5, 0.5, 0.5, 0.5]
* **price**: 140
* **mana**: 30
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/area_damage.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/area_damage.xml,"
      draw_actions( 1, true )
    end,
```

## ![Death cross](images/DEATH_CROSS.png)Death cross (DEATH_CROSS)

* **description**: A deadly energy cross that explodes after a short time
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [1, 2, 3, 4, 5, 6]
* **spawn_probability**: [1.0, 0.6, 0.6, 0.6, 0.6, 0.6]
* **price**: 210
* **mana**: 80
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/death_cross.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/death_cross.xml")
      c.fire_rate_wait = c.fire_rate_wait + 40
    end,
```

## ![Decelerating shot](images/DECELERATING_SHOT.png)Decelerating shot (DECELERATING_SHOT)

* **description**: Makes a projectile decelerate as it flies
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4]
* **spawn_probability**: [0.3, 0.3, 0.5]
* **price**: 80
* **mana**: 10
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/decelerating_shot.xml" }
* **action**:

```lua
 function()
      c.fire_rate_wait    = c.fire_rate_wait - 8
      c.speed_multiplier = c.speed_multiplier * 1.68
      shot_effects.recoil_knockback = shot_effects.recoil_knockback - 10.0
      c.extra_entities = c.extra_entities .. "data/entities/misc/decelerating_shot.xml,"
      
      if ( c.speed_multiplier >= 20 ) then
        c.speed_multiplier = math.min( c.speed_multiplier, 20 )
      elseif ( c.speed_multiplier < 0 ) then
        c.speed_multiplier = 0
      end
      
      draw_actions( 1, true )
    end,
```

## ![Delayed spellcast](images/DELAYED_SPELL.png)Delayed spellcast (DELAYED_SPELL)

* **description**: A static, magical phenomenon that casts 3 extra spells after a short while
* **type**: ACTION_TYPE_STATIC_PROJECTILE
* **spawn_level**: [0, 1, 2, 4, 5, 6]
* **spawn_probability**: [1.0, 1.0, 1.0, 1.0, 1.0, 1.0]
* **price**: 240
* **mana**: 20
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/delayed_spell.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile_trigger_death("data/entities/projectiles/deck/delayed_spell.xml", 3)
      c.fire_rate_wait = c.fire_rate_wait + 10
    end,
```

## ![Destruction](images/DESTRUCTION.png)Destruction (DESTRUCTION)

* **description**: Instantly decimates foes around you, at the cost of your HP
* **type**: ACTION_TYPE_STATIC_PROJECTILE
* **spawn_level**: [10]
* **spawn_probability**: [1.0]
* **price**: 600
* **mana**: 600
* **max_uses**: 5
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: true
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/destruction.xml"}
* **spawn_requires_flag**: card_unlocked_destruction
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/destruction.xml")
      c.fire_rate_wait = c.fire_rate_wait + 100
      current_reload_time = current_reload_time + 300
    end,
```

## ![Digging blast](images/POWERDIGGER.png)Digging blast (POWERDIGGER)

* **description**: More powerful digging
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [2, 3, 4]
* **spawn_probability**: [0.5, 1.0, 1.0]
* **price**: 110
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/powerdigger.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/powerdigger.xml")
      c.fire_rate_wait = c.fire_rate_wait + 1
      current_reload_time = current_reload_time - ACTION_DRAW_RELOAD_TIME_INCREASE - 10 -- this is a hack to get the digger reload time back to 0
    end,
```

## ![Digging bolt](images/DIGGER.png)Digging bolt (DIGGER)

* **description**: A bolt that is ideal for mining operations
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [1, 2]
* **spawn_probability**: [1.0, 0.5]
* **price**: 70
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/digger.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/digger.xml")
      c.fire_rate_wait = c.fire_rate_wait + 1
      current_reload_time = current_reload_time - ACTION_DRAW_RELOAD_TIME_INCREASE - 10 -- this is a hack to get the digger reload time back to 0
    end,
```

## ![Disc projectile](images/DISC_BULLET.png)Disc projectile (DISC_BULLET)

* **description**: Summons a sharp disc projectile
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [0, 2, 4]
* **spawn_probability**: [1.0, 1.0, 1.0]
* **price**: 120
* **mana**: 20
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/disc_bullet.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/disc_bullet.xml")
      c.fire_rate_wait = c.fire_rate_wait + 10
      c.spread_degrees = c.spread_degrees + 2.0
      shot_effects.recoil_knockback = 20.0
    end,
```

## ![Divide by 10](images/DIVIDE_10.png)Divide by 10 (DIVIDE_10)

* **description**: Casts the next spell 10 times, but with reduced damage
* **type**: ACTION_TYPE_OTHER
* **spawn_level**: [10]
* **spawn_probability**: [1.0]
* **price**: 400
* **mana**: 200
* **max_uses**: 5
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_divide
* **related_extra_entities**: 
* **action**:

```lua
 function( recursion_level, iteration )
      c.fire_rate_wait = c.fire_rate_wait + 80
      current_reload_time = current_reload_time + 20
      
      local data = {}
      
      local iter = iteration or 1
      local iter_max = iteration or 1
      
      if ( #deck > 0 ) then
        data = deck[iter] or nil
      else
        data = nil
      end
      
      local count = 10
      if ( iter >= 3 ) then
        count = 1
      end
      
      local rec = check_recursion( data, recursion_level )
      
      if ( data ~= nil ) and ( rec > -1 ) and ( ( data.uses_remaining == nil ) or ( data.uses_remaining ~= 0 ) ) then
        local firerate = c.fire_rate_wait
        local reload = current_reload_time
        
        for i=1,count do
          if ( i == 1 ) then
            dont_draw_actions = true
          end
          local imax = data.action( rec, iter + 1 )
          dont_draw_actions = false
          if (imax ~= nil) then
            iter_max = imax
          end
        end
        
        if ( data.uses_remaining ~= nil ) and ( data.uses_remaining > 0 ) then
          data.uses_remaining = data.uses_remaining - 1
          
          local reduce_uses = ActionUsesRemainingChanged( data.inventoryitem_id, data.uses_remaining )
          if not reduce_uses then
            data.uses_remaining = data.uses_remaining + 1 -- cancel the reduction
          end
        end
        
        if (iter == 1) then
          c.fire_rate_wait = firerate
          current_reload_time = reload
          
          for i=1,iter_max do
            if (#deck > 0) then
              local d = deck[1]
              table.insert( discarded, d )
              table.remove( deck, 1 )
            end
          end
        end
      end
      
      c.damage_projectile_add = c.damage_projectile_add - 1.5
      c.explosion_radius = c.explosion_radius - 40.0
      if (c.explosion_radius < 0) then
        c.explosion_radius = 0
      end
      
      c.pattern_degrees = 5
      
      return iter_max
    end,
```

## ![Divide by 2](images/DIVIDE_2.png)Divide by 2 (DIVIDE_2)

* **description**: Casts the next spell twice, but with reduced damage
* **type**: ACTION_TYPE_OTHER
* **spawn_level**: [3, 5, 6, 10]
* **spawn_probability**: [0.2, 0.3, 0.2, 1.0]
* **price**: 200
* **mana**: 35
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_musicbox
* **related_extra_entities**: 
* **action**:

```lua
 function( recursion_level, iteration )
      c.fire_rate_wait = c.fire_rate_wait + 20
      
      local data = {}
      
      local iter = iteration or 1
      local iter_max = iteration or 1
      
      if ( #deck > 0 ) then
        data = deck[iter] or nil
      else
        data = nil
      end
      
      local count = 2
      if ( iter >= 5 ) then
        count = 1
      end
      
      local rec = check_recursion( data, recursion_level )
      
      if ( data ~= nil ) and ( rec > -1 ) and ( ( data.uses_remaining == nil ) or ( data.uses_remaining ~= 0 ) ) then
        local firerate = c.fire_rate_wait
        local reload = current_reload_time
        
        for i=1,count do
          if ( i == 1 ) then
            dont_draw_actions = true
          end
          local imax = data.action( rec, iter + 1 )
          dont_draw_actions = false
          if (imax ~= nil) then
            iter_max = imax
          end
        end
        
        if ( data.uses_remaining ~= nil ) and ( data.uses_remaining > 0 ) then
          data.uses_remaining = data.uses_remaining - 1
          
          local reduce_uses = ActionUsesRemainingChanged( data.inventoryitem_id, data.uses_remaining )
          if not reduce_uses then
            data.uses_remaining = data.uses_remaining + 1 -- cancel the reduction
          end
        end
        
        if (iter == 1) then
          c.fire_rate_wait = firerate
          current_reload_time = reload
          
          for i=1,iter_max do
            if (#deck > 0) then
              local d = deck[1]
              table.insert( discarded, d )
              table.remove( deck, 1 )
            end
          end
        end
      end
      
      c.damage_projectile_add = c.damage_projectile_add - 0.2
      c.explosion_radius = c.explosion_radius - 5.0
      if (c.explosion_radius < 0) then
        c.explosion_radius = 0
      end
      
      c.pattern_degrees = 5
      
      return iter_max
    end,
```

## ![Divide by 3](images/DIVIDE_3.png)Divide by 3 (DIVIDE_3)

* **description**: Casts the next spell 3 times, but with reduced damage
* **type**: ACTION_TYPE_OTHER
* **spawn_level**: [4, 5, 6, 10]
* **spawn_probability**: [0.1, 0.1, 0.2, 1.0]
* **price**: 250
* **mana**: 50
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_musicbox
* **related_extra_entities**: 
* **action**:

```lua
 function( recursion_level, iteration )
      c.fire_rate_wait = c.fire_rate_wait + 35
      
      local data = {}
      
      local iter = iteration or 1
      local iter_max = iteration or 1
      
      if ( #deck > 0 ) then
        data = deck[iter] or nil
      else
        data = nil
      end
      
      local count = 3
      if ( iter >= 4 ) then
        count = 1
      end
      
      local rec = check_recursion( data, recursion_level )
      
      if ( data ~= nil ) and ( rec > -1 ) and ( ( data.uses_remaining == nil ) or ( data.uses_remaining ~= 0 ) ) then
        local firerate = c.fire_rate_wait
        local reload = current_reload_time
        
        for i=1,count do
          if ( i == 1 ) then
            dont_draw_actions = true
          end
          local imax = data.action( rec, iter + 1 )
          dont_draw_actions = false
          if (imax ~= nil) then
            iter_max = imax
          end
        end
        
        if ( data.uses_remaining ~= nil ) and ( data.uses_remaining > 0 ) then
          data.uses_remaining = data.uses_remaining - 1
          
          local reduce_uses = ActionUsesRemainingChanged( data.inventoryitem_id, data.uses_remaining )
          if not reduce_uses then
            data.uses_remaining = data.uses_remaining + 1 -- cancel the reduction
          end
        end
        
        if (iter == 1) then
          c.fire_rate_wait = firerate
          current_reload_time = reload
          
          for i=1,iter_max do
            if (#deck > 0) then
              local d = deck[1]
              table.insert( discarded, d )
              table.remove( deck, 1 )
            end
          end
        end
      end
      
      c.damage_projectile_add = c.damage_projectile_add - 0.4
      c.explosion_radius = c.explosion_radius - 10.0
      if (c.explosion_radius < 0) then
        c.explosion_radius = 0
      end
      
      c.pattern_degrees = 5
      
      return iter_max
    end,
```

## ![Divide by 4](images/DIVIDE_4.png)Divide by 4 (DIVIDE_4)

* **description**: Casts the next spell 4 times, but with reduced damage
* **type**: ACTION_TYPE_OTHER
* **spawn_level**: [5, 6, 10]
* **spawn_probability**: [0.1, 0.1, 1.0]
* **price**: 300
* **mana**: 70
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_musicbox
* **related_extra_entities**: 
* **action**:

```lua
 function( recursion_level, iteration )
      c.fire_rate_wait = c.fire_rate_wait + 50
      
      local data = {}
      
      local iter = iteration or 1
      local iter_max = iteration or 1
      
      if ( #deck > 0 ) then
        data = deck[iter] or nil
      else
        data = nil
      end
      
      local count = 4
      if ( iter >= 4 ) then
        count = 1
      end
      
      local rec = check_recursion( data, recursion_level )
      
      if ( data ~= nil ) and ( rec > -1 ) and ( ( data.uses_remaining == nil ) or ( data.uses_remaining ~= 0 ) ) then
        local firerate = c.fire_rate_wait
        local reload = current_reload_time
        
        for i=1,count do
          if ( i == 1 ) then
            dont_draw_actions = true
          end
          local imax = data.action( rec, iter + 1 )
          dont_draw_actions = false
          if (imax ~= nil) then
            iter_max = imax
          end
        end
        
        if ( data.uses_remaining ~= nil ) and ( data.uses_remaining > 0 ) then
          data.uses_remaining = data.uses_remaining - 1
          
          local reduce_uses = ActionUsesRemainingChanged( data.inventoryitem_id, data.uses_remaining )
          if not reduce_uses then
            data.uses_remaining = data.uses_remaining + 1 -- cancel the reduction
          end
        end
        
        if (iter == 1) then
          c.fire_rate_wait = firerate
          current_reload_time = reload
          
          for i=1,iter_max do
            if (#deck > 0) then
              local d = deck[1]
              table.insert( discarded, d )
              table.remove( deck, 1 )
            end
          end
        end
      end
      
      c.damage_projectile_add = c.damage_projectile_add - 0.6
      c.explosion_radius = c.explosion_radius - 20.0
      if (c.explosion_radius < 0) then
        c.explosion_radius = 0
      end
      
      c.pattern_degrees = 5
      
      return iter_max
    end,
```

## ![Dormant crystal](images/PIPE_BOMB.png)Dormant crystal (PIPE_BOMB)

* **description**: A crystal that explodes when caught in an explosion
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [2, 3, 4]
* **spawn_probability**: [1.0, 1.0, 1.0]
* **price**: 200
* **mana**: 20
* **max_uses**: 20
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/pipe_bomb.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/pipe_bomb.xml")
      c.fire_rate_wait = c.fire_rate_wait + 30
      c.child_speed_multiplier = c.child_speed_multiplier * 0.75
      c.speed_multiplier = c.speed_multiplier * 0.75
      
      if ( c.speed_multiplier >= 20 ) then
        c.speed_multiplier = math.min( c.speed_multiplier, 20 )
      elseif ( c.speed_multiplier < 0 ) then
        c.speed_multiplier = 0
      end
    end,
```

## ![Dormant crystal with trigger](images/PIPE_BOMB_DEATH_TRIGGER.png)Dormant crystal with trigger (PIPE_BOMB_DEATH_TRIGGER)

* **description**: A crystal that explodes and casts another spell when caught in an explosion
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [2, 3, 4, 5]
* **spawn_probability**: [1.0, 1.0, 1.0, 1.0]
* **price**: 230
* **mana**: 20
* **max_uses**: 20
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/pipe_bomb.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      c.fire_rate_wait = c.fire_rate_wait + 30
      c.child_speed_multiplier = c.child_speed_multiplier * 0.75
      c.speed_multiplier = c.speed_multiplier * 0.75
      add_projectile_trigger_death("data/entities/projectiles/deck/pipe_bomb.xml", 1)
      shot_effects.recoil_knockback = shot_effects.recoil_knockback + 60.0
      
      if ( c.speed_multiplier >= 20 ) then
        c.speed_multiplier = math.min( c.speed_multiplier, 20 )
      elseif ( c.speed_multiplier < 0 ) then
        c.speed_multiplier = 0
      end
    end,
```

## ![Double scatter spell](images/SCATTER_2.png)Double scatter spell (SCATTER_2)

* **description**: Simultaneously casts 2 spells with low accuracy
* **type**: ACTION_TYPE_DRAW_MANY
* **spawn_level**: [0, 1, 2]
* **spawn_probability**: [0.8, 0.8, 0.8]
* **price**: 100
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      draw_actions( 2, true )
      c.spread_degrees = c.spread_degrees + 10.0
    end,
```

## ![Double spell](images/BURST_2.png)Double spell (BURST_2)

* **description**: Simultaneously casts 2 spells
* **type**: ACTION_TYPE_DRAW_MANY
* **spawn_level**: [0, 1, 2, 3, 4, 5, 6]
* **spawn_probability**: [0.8, 0.8, 0.8, 0.8, 0.8, 0.8, 0.8]
* **price**: 140
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      draw_actions( 2, true )
    end,
```

## ![Downwards bolt bundle](images/ROCKET_DOWNWARDS.png)Downwards bolt bundle (ROCKET_DOWNWARDS)

* **description**: Makes a projectile separate into a bundle of 5 explosive bolts as soon as it moves downwards
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 2, 3, 4]
* **spawn_probability**: [0.2, 1.0, 1.0, 1.0]
* **price**: 200
* **mana**: 90
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/rocket_downwards.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/rocket_downwards.xml,"
      c.fire_rate_wait = c.fire_rate_wait + 25
      draw_actions( 1, true )
    end,
```

## ![Downwards larpa](images/LARPA_DOWNWARDS.png)Downwards larpa (LARPA_DOWNWARDS)

* **description**: Makes a projectile cast copies of itself with a downwards trajectory
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4, 5, 10]
* **spawn_probability**: [0.1, 0.3, 0.2, 0.2, 0.2]
* **price**: 290
* **mana**: 120
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/larpa_downwards.xml" }
* **action**:

```lua
 function()
      c.fire_rate_wait = c.fire_rate_wait + 15
      c.extra_entities = c.extra_entities .. "data/entities/misc/larpa_downwards.xml,"
      draw_actions( 1, true )
    end,
```

## ![Drilling shot](images/CLIPPING_SHOT.png)Drilling shot (CLIPPING_SHOT)

* **description**: Gives a projectile the power to go through the ground
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4, 5, 6]
* **spawn_probability**: [0.6, 0.6, 0.6, 0.6, 0.6]
* **price**: 200
* **mana**: 160
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/clipping_shot.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/clipping_shot.xml,"
      c.fire_rate_wait = c.fire_rate_wait + 50
      current_reload_time = current_reload_time + 40
      draw_actions( 1, true )
    end,
```

## ![Dropper bolt](images/GRENADE_LARGE.png)Dropper bolt (GRENADE_LARGE)

* **description**: A very heavy explosive bolt
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [0, 1, 2, 3, 4, 5]
* **spawn_probability**: [0.4, 0.4, 0.4, 0.4, 0.4, 0.4]
* **price**: 150
* **mana**: 80
* **max_uses**: 35
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/grenade_large.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/grenade_large.xml")
      c.fire_rate_wait = c.fire_rate_wait + 40
      c.screenshake = c.screenshake + 5.0
      c.child_speed_multiplier = c.child_speed_multiplier * 0.75
      shot_effects.recoil_knockback = 80.0
    end,
```

## ![Dynamite](images/DYNAMITE.png)Dynamite (DYNAMITE)

* **description**: Summons a small explosive
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [0, 1, 2, 3, 4]
* **spawn_probability**: [1.0, 1.0, 1.0, 1.0, 1.0]
* **price**: 160
* **mana**: 50
* **max_uses**: 16
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/tnt.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/tnt.xml")
      c.fire_rate_wait = c.fire_rate_wait + 50
      c.spread_degrees = c.spread_degrees + 6.0
    end,
```

## ![Earthquake](images/CRUMBLING_EARTH.png)Earthquake (CRUMBLING_EARTH)

* **description**: Calls the anger of the earth
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [2, 3, 4, 5, 6]
* **spawn_probability**: [0.6, 0.6, 0.6, 0.6, 0.6]
* **price**: 300
* **mana**: 240
* **max_uses**: 3
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/crumbling_earth.xml"}
* **spawn_requires_flag**: card_unlocked_crumbling_earth
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/crumbling_earth.xml")
    end,
```

## ![Earthquake shot](images/CRUMBLING_EARTH_PROJECTILE.png)Earthquake shot (CRUMBLING_EARTH_PROJECTILE)

* **description**: Makes a projectile crumble the earth it hits
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 2, 3, 4, 5]
* **spawn_probability**: [0.4, 0.4, 0.4, 0.4, 0.4]
* **price**: 200
* **mana**: 45
* **max_uses**: 15
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/crumbling_earth_projectile.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/crumbling_earth_projectile.xml,"
      draw_actions( 1, true )
    end,
```

## ![Eldritch portal](images/TENTACLE_PORTAL.png)Eldritch portal (TENTACLE_PORTAL)

* **description**: Summons a one-way portal to a sinister realm
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [1, 2, 3, 4, 10]
* **spawn_probability**: [0.4, 0.4, 0.4, 0.4, 0.2]
* **price**: 220
* **mana**: 140
* **max_uses**: 5
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/tentacle_portal.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/tentacle_portal.xml")
      c.fire_rate_wait = c.fire_rate_wait + 30
    end,
```

## ![Electric Arc](images/ARC_ELECTRIC.png)Electric Arc (ARC_ELECTRIC)

* **description**: Creates arcs of lightning between projectiles (requires 2 projectile spells)
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4, 5, 6]
* **spawn_probability**: [0.4, 0.4, 0.4, 0.4, 0.8]
* **price**: 170
* **mana**: 15
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/arc_electric.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/arc_electric.xml,"
      draw_actions( 1, true )
    end,
```

## ![Electric Torch](images/TORCH_ELECTRIC.png)Electric Torch (TORCH_ELECTRIC)

* **description**: Gives your wand a bright but very dangerous light!
* **type**: ACTION_TYPE_PASSIVE
* **spawn_level**: [0, 1, 2]
* **spawn_probability**: [1.0, 1.0, 1.0]
* **price**: 150
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      draw_actions( 1, true )
    end,
```

## ![Electric charge](images/ELECTRIC_CHARGE.png)Electric charge (ELECTRIC_CHARGE)

* **description**: Gives a projectile an electric charge, that it will release on impact
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 2, 4, 5]
* **spawn_probability**: [1.0, 1.0, 1.0, 1.0]
* **price**: 150
* **mana**: 8
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/particles/electricity.xml" }
* **action**:

```lua
 function()
      c.lightning_count = c.lightning_count + 1
      c.damage_electricity_add = c.damage_electricity_add + 0.1
      c.extra_entities = c.extra_entities .. "data/entities/particles/electricity.xml,"
      draw_actions( 1, true )
    end,
```

## ![Energy orb](images/SLOW_BULLET.png)Energy orb (SLOW_BULLET)

* **description**: A slow but powerful orb of energy
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [1, 2, 3, 4]
* **spawn_probability**: [1.0, 1.0, 1.0, 1.0]
* **price**: 160
* **mana**: 30
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/bullet_slow.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/bullet_slow.xml")
      c.fire_rate_wait = c.fire_rate_wait + 6
      c.screenshake = c.screenshake + 2
      c.spread_degrees = c.spread_degrees + 3.6
      shot_effects.recoil_knockback = shot_effects.recoil_knockback + 20.0
    end,
```

## ![Energy orb with a timer](images/SLOW_BULLET_TIMER.png)Energy orb with a timer (SLOW_BULLET_TIMER)

* **description**: A slow but powerful orb of energy that casts another spell after a timer runs out
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [1, 2, 3, 4, 5, 6]
* **spawn_probability**: [0.5, 0.5, 0.5, 0.5, 1.0, 1.0]
* **price**: 200
* **mana**: 50
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/bullet_slow.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      c.fire_rate_wait = c.fire_rate_wait + 6
      c.screenshake = c.screenshake + 2
      c.spread_degrees = c.spread_degrees + 3.6
      add_projectile_trigger_timer("data/entities/projectiles/deck/bullet_slow.xml", 100, 1)
      shot_effects.recoil_knockback = shot_effects.recoil_knockback + 20.0
    end,
```

## ![Energy orb with a trigger](images/SLOW_BULLET_TRIGGER.png)Energy orb with a trigger (SLOW_BULLET_TRIGGER)

* **description**: A slow but powerful orb of energy that casts another spell upon collision
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [1, 2, 3, 4, 5]
* **spawn_probability**: [0.5, 0.5, 0.5, 0.5, 1.0]
* **price**: 200
* **mana**: 50
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/bullet_slow.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      c.fire_rate_wait = c.fire_rate_wait + 25
      c.screenshake = c.screenshake + 2
      c.spread_degrees = c.spread_degrees + 10
      add_projectile_trigger_hit_world("data/entities/projectiles/deck/bullet_slow.xml", 1)
      shot_effects.recoil_knockback = shot_effects.recoil_knockback + 20.0
    end,
```

## ![Energy shield](images/ENERGY_SHIELD.png)Energy shield (ENERGY_SHIELD)

* **description**: Deflects incoming projectiles
* **type**: ACTION_TYPE_PASSIVE
* **spawn_level**: [1, 2, 3, 4, 5, 6]
* **spawn_probability**: [0.05, 0.6, 0.6, 0.6, 0.6, 0.6]
* **price**: 220
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      draw_actions( 1, true )
    end,
```

## ![Energy shield sector](images/ENERGY_SHIELD_SECTOR.png)Energy shield sector (ENERGY_SHIELD_SECTOR)

* **description**: Deflects incoming projectiles
* **type**: ACTION_TYPE_PASSIVE
* **spawn_level**: [0, 1, 2, 3, 4, 5]
* **spawn_probability**: [0.05, 0.6, 0.6, 0.6, 0.6, 0.6]
* **price**: 160
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      draw_actions( 1, true )
    end,
```

## ![Energy sphere](images/BOUNCY_ORB.png)Energy sphere (BOUNCY_ORB)

* **description**: A fast, arcing projectile
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [0, 2, 4]
* **spawn_probability**: [1.0, 1.0, 1.0]
* **price**: 120
* **mana**: 20
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/bouncy_orb.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/bouncy_orb.xml")
      c.fire_rate_wait = c.fire_rate_wait + 10
      shot_effects.recoil_knockback = 20.0
    end,
```

## ![Energy sphere with timer](images/BOUNCY_ORB_TIMER.png)Energy sphere with timer (BOUNCY_ORB_TIMER)

* **description**: A fast, arcing projectile that casts another spell after a timer runs out
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [0, 2, 4]
* **spawn_probability**: [0.5, 0.5, 0.5]
* **price**: 150
* **mana**: 50
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/bouncy_orb.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile_trigger_timer("data/entities/projectiles/deck/bouncy_orb.xml",200,1)
      c.fire_rate_wait = c.fire_rate_wait + 10
      shot_effects.recoil_knockback = 20.0
    end,
```

## ![Essence to Power](images/ESSENCE_TO_POWER.png)Essence to Power (ESSENCE_TO_POWER)

* **description**: Increases a projectile's damage based on the number of creatures nearby
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 2, 3, 10]
* **spawn_probability**: [0.2, 0.5, 0.5, 0.1]
* **price**: 120
* **mana**: 110
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/essence_to_power.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/essence_to_power.xml,"
      c.fire_rate_wait    = c.fire_rate_wait + 20
      draw_actions( 1, true )
    end,
```

## ![Expanding Sphere](images/EXPANDING_ORB.png)Expanding Sphere (EXPANDING_ORB)

* **description**: A slow projectile that increases its damage over time
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [2, 3, 4, 5, 6]
* **spawn_probability**: [0.5, 0.5, 1.0, 1.0, 1.0]
* **price**: 200
* **mana**: 70
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/orb_expanding.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/orb_expanding.xml")
      c.fire_rate_wait = c.fire_rate_wait + 30
      shot_effects.recoil_knockback = 20.0
    end,
```

## ![Explosion](images/EXPLOSION.png)Explosion (EXPLOSION)

* **description**: A powerful explosion
* **type**: ACTION_TYPE_STATIC_PROJECTILE
* **spawn_level**: [0, 2, 4, 5]
* **spawn_probability**: [0.5, 1.0, 1.0, 1.0]
* **price**: 160
* **mana**: 80
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: true
* **related_projectiles**: {"data/entities/projectiles/deck/explosion.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/explosion.xml")
      c.fire_rate_wait = c.fire_rate_wait + 3
      c.screenshake = c.screenshake + 2.5
    end,
```

## ![Explosion of brimstone](images/FIRE_BLAST.png)Explosion of brimstone (FIRE_BLAST)

* **description**: A fiery explosion
* **type**: ACTION_TYPE_STATIC_PROJECTILE
* **spawn_level**: [0, 1, 3, 5]
* **spawn_probability**: [0.5, 0.5, 0.6, 0.6]
* **price**: 120
* **mana**: 10
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: true
* **related_projectiles**: {"data/entities/projectiles/deck/fireblast.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/fireblast.xml")
      c.fire_rate_wait = c.fire_rate_wait + 3
      c.screenshake = c.screenshake + 0.5
    end,
```

## ![Explosion of poison](images/POISON_BLAST.png)Explosion of poison (POISON_BLAST)

* **description**: An alchemical explosion
* **type**: ACTION_TYPE_STATIC_PROJECTILE
* **spawn_level**: [1, 2, 4, 6]
* **spawn_probability**: [0.5, 0.6, 0.6, 0.5]
* **price**: 140
* **mana**: 30
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: true
* **related_projectiles**: {"data/entities/projectiles/deck/poison_blast.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/poison_blast.xml")
      c.fire_rate_wait = c.fire_rate_wait + 3
      c.screenshake = c.screenshake + 0.5
    end,
```

## ![Explosion of spirits](images/ALCOHOL_BLAST.png)Explosion of spirits (ALCOHOL_BLAST)

* **description**: An inebriating explosion
* **type**: ACTION_TYPE_STATIC_PROJECTILE
* **spawn_level**: [1, 2, 4, 6]
* **spawn_probability**: [0.5, 0.6, 0.6, 0.5]
* **price**: 140
* **mana**: 30
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: true
* **related_projectiles**: {"data/entities/projectiles/deck/alcohol_blast.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/alcohol_blast.xml")
      c.fire_rate_wait = c.fire_rate_wait + 3
      c.screenshake = c.screenshake + 0.5
    end,
```

## ![Explosion of thunder](images/THUNDER_BLAST.png)Explosion of thunder (THUNDER_BLAST)

* **description**: An electric explosion
* **type**: ACTION_TYPE_STATIC_PROJECTILE
* **spawn_level**: [1, 3, 5, 6, 10]
* **spawn_probability**: [0.5, 0.6, 0.6, 0.5, 0.1]
* **price**: 180
* **mana**: 110
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: true
* **related_projectiles**: {"data/entities/projectiles/deck/thunder_blast.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/thunder_blast.xml")
      c.fire_rate_wait = c.fire_rate_wait + 15
      c.screenshake = c.screenshake + 3.0
      shot_effects.recoil_knockback = shot_effects.recoil_knockback + 30.0
    end,
```

## ![Explosion on drunk enemies](images/HITFX_EXPLOSION_ALCOHOL.png)Explosion on drunk enemies (HITFX_EXPLOSION_ALCOHOL)

* **description**: Makes a projectile explode upon collision with creatures covered in alcohol
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 3, 4, 5]
* **spawn_probability**: [0.2, 0.2, 0.2, 0.2]
* **price**: 140
* **mana**: 20
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/hitfx_explode_alcohol.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/hitfx_explode_alcohol.xml,"
      draw_actions( 1, true )
    end,
```

## ![Explosion on slimy enemies](images/HITFX_EXPLOSION_SLIME.png)Explosion on slimy enemies (HITFX_EXPLOSION_SLIME)

* **description**: Makes a projectile explode upon collision with creatures covered in slime
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 3, 4, 5]
* **spawn_probability**: [0.2, 0.2, 0.2, 0.2]
* **price**: 140
* **mana**: 20
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/hitfx_explode_slime.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/hitfx_explode_slime.xml,"
      draw_actions( 1, true )
    end,
```

## ![Explosive Detonator](images/BOMB_DETONATOR.png)Explosive Detonator (BOMB_DETONATOR)

* **description**: All nearby explosive spells cast by you instantly detonate
* **type**: ACTION_TYPE_STATIC_PROJECTILE
* **spawn_level**: [2, 3, 4, 5, 6]
* **spawn_probability**: [1.0, 1.0, 1.0, 1.0, 1.0]
* **price**: 120
* **mana**: 50
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/bomb_detonator.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/bomb_detonator.xml")
    end,
```

## ![Explosive bounce](images/BOUNCE_EXPLOSION.png)Explosive bounce (BOUNCE_EXPLOSION)

* **description**: Makes a projectile explode as it bounces
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4, 5]
* **spawn_probability**: [0.2, 0.6, 0.8, 0.8]
* **price**: 180
* **mana**: 20
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/bounce_explosion.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/bounce_explosion.xml,"
      c.bounces = c.bounces + 1
      c.fire_rate_wait = c.fire_rate_wait + 25
      shot_effects.recoil_knockback = shot_effects.recoil_knockback + 20.0
      draw_actions( 1, true )
    end,
```

## ![Explosive projectile](images/EXPLOSIVE_PROJECTILE.png)Explosive projectile (EXPLOSIVE_PROJECTILE)

* **description**: Makes a projectile more destructive to the environment
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4]
* **spawn_probability**: [1.0, 1.0, 1.0]
* **price**: 120
* **mana**: 30
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      c.explosion_radius = c.explosion_radius + 15.0
      c.damage_explosion_add = c.damage_explosion_add + 0.2
      c.fire_rate_wait   = c.fire_rate_wait + 40
      c.speed_multiplier = c.speed_multiplier * 0.75
      shot_effects.recoil_knockback = shot_effects.recoil_knockback + 30.0
      
      if ( c.speed_multiplier >= 20 ) then
        c.speed_multiplier = math.min( c.speed_multiplier, 20 )
      elseif ( c.speed_multiplier < 0 ) then
        c.speed_multiplier = 0
      end
      
      draw_actions( 1, true )
    end,
```

## ![Fire Arc](images/ARC_FIRE.png)Fire Arc (ARC_FIRE)

* **description**: Creates arcs of fire between projectiles (requires 2 projectile spells)
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 2, 3, 4, 5]
* **spawn_probability**: [0.4, 0.4, 0.4, 0.4, 0.4]
* **price**: 160
* **mana**: 15
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/arc_fire.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/arc_fire.xml,"
      draw_actions( 1, true )
    end,
```

## ![Fire trail](images/FIRE_TRAIL.png)Fire trail (FIRE_TRAIL)

* **description**: Gives a projectile a trail of fiery particles
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [0, 1, 2, 3, 4]
* **spawn_probability**: [0.3, 0.3, 0.3, 0.3, 0.3]
* **price**: 130
* **mana**: 10
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      c.game_effect_entities = c.game_effect_entities .. "data/entities/misc/effect_apply_on_fire.xml,"
      c.trail_material = c.trail_material .. "fire,"
      c.trail_material_amount = c.trail_material_amount + 10
      draw_actions( 1, true )
    end,
```

## ![Fireball](images/FIREBALL.png)Fireball (FIREBALL)

* **description**: A powerful exploding spell
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [0, 3, 4, 6]
* **spawn_probability**: [1.0, 1.0, 1.0, 1.0]
* **price**: 220
* **mana**: 70
* **max_uses**: 15
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/fireball.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/fireball.xml")
      c.spread_degrees = c.spread_degrees + 4.0
      c.fire_rate_wait = c.fire_rate_wait + 50
      shot_effects.recoil_knockback = shot_effects.recoil_knockback + 20.0
    end,
```

## ![Fireball Orbit](images/ORBIT_FIREBALLS.png)Fireball Orbit (ORBIT_FIREBALLS)

* **description**: Makes four fireballs rotate around a projectile
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [0, 1, 2, 4, 5]
* **spawn_probability**: [0.5, 0.2, 0.8, 0.4, 0.2]
* **price**: 140
* **mana**: 40
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_dragon
* **related_extra_entities**: { "data/entities/misc/orbit_fireballs.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/orbit_fireballs.xml,"
      draw_actions( 1, true )
    end,
```

## ![Fireball thrower](images/FIREBALL_RAY.png)Fireball thrower (FIREBALL_RAY)

* **description**: Makes a projectile cast fireballs in random directions
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 2, 4, 5]
* **spawn_probability**: [0.6, 0.6, 0.4, 0.4]
* **price**: 150
* **mana**: 110
* **max_uses**: 16
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/fireball_ray.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/fireball_ray.xml,"
      draw_actions( 1, true )
    end,
```

## ![Firebolt](images/GRENADE.png)Firebolt (GRENADE)

* **description**: A bouncy, explosive bolt
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [0, 1, 2, 3, 4]
* **spawn_probability**: [1.0, 1.0, 0.5, 0.25, 0.25]
* **price**: 170
* **mana**: 50
* **max_uses**: 25
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/grenade.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/grenade.xml")
      c.fire_rate_wait = c.fire_rate_wait + 30
      c.screenshake = c.screenshake + 4.0
      c.child_speed_multiplier = c.child_speed_multiplier * 0.75
      shot_effects.recoil_knockback = 80.0
    end,
```

## ![Firebolt with trigger](images/GRENADE_TRIGGER.png)Firebolt with trigger (GRENADE_TRIGGER)

* **description**: A bouncy, explosive bolt that that casts another spell upon collision
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [0, 1, 2, 3, 4, 5]
* **spawn_probability**: [0.5, 0.5, 0.5, 0.5, 0.5, 1.0]
* **price**: 210
* **mana**: 50
* **max_uses**: 25
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/grenade.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      c.fire_rate_wait = c.fire_rate_wait + 30
      c.screenshake = c.screenshake + 4.0
      c.child_speed_multiplier = c.child_speed_multiplier * 0.75
      add_projectile_trigger_hit_world("data/entities/projectiles/deck/grenade.xml", 1)
      shot_effects.recoil_knockback = 80.0
    end,
```

## ![Firebomb](images/FIREBOMB.png)Firebomb (FIREBOMB)

* **description**: Slow, fiery bolt
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [1, 2, 3]
* **spawn_probability**: [1.0, 1.0, 1.0]
* **price**: 90
* **mana**: 10
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/firebomb.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/firebomb.xml")
    end,
```

## ![Firecrackers](images/UNSTABLE_GUNPOWDER.png)Firecrackers (UNSTABLE_GUNPOWDER)

* **description**: Makes a projectile release firecrackers when it disappears
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4]
* **spawn_probability**: [0.3, 0.3, 0.3]
* **price**: 140
* **mana**: 15
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      c.material = "gunpowder_unstable"
      c.material_amount = c.material_amount + 10
      draw_actions( 1, true )
    end,
```

## ![Fireworks!](images/FIREWORK.png)Fireworks! (FIREWORK)

* **description**: A fiery, explosive projectile
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [1, 2, 3, 4, 5, 6]
* **spawn_probability**: [1.0, 1.0, 1.0, 1.0, 1.0, 1.0]
* **price**: 220
* **mana**: 70
* **max_uses**: 25
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/fireworks/firework_pink.xml"}
* **spawn_requires_flag**: card_unlocked_firework
* **related_extra_entities**: 
* **action**:

```lua
 function()
      SetRandomSeed( GameGetFrameNum(), GameGetFrameNum() )
      local types = {"pink","green","blue","orange"}
      local rnd = Random(1, #types)
      local firework_name = "firework_" .. tostring(types[rnd]) .. ".xml"
      add_projectile("data/entities/projectiles/deck/fireworks/" .. firework_name)
      c.fire_rate_wait = c.fire_rate_wait + 60
      c.ragdoll_fx = 2
      shot_effects.recoil_knockback = 120.0
    end,
```

## ![Fizzle](images/FIZZLE.png)Fizzle (FIZZLE)

* **description**: Gives a spell a small probability of short-circuiting
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [3, 4, 5]
* **spawn_probability**: [0.1, 0.1, 0.1]
* **price**: 0
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/fizzle.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/fizzle.xml,"
      c.speed_multiplier = c.speed_multiplier * 1.2
      c.fire_rate_wait = c.fire_rate_wait - 10
      
      if ( c.speed_multiplier >= 20 ) then
        c.speed_multiplier = math.min( c.speed_multiplier, 20 )
      elseif ( c.speed_multiplier < 0 ) then
        c.speed_multiplier = 0
      end
      
      draw_actions( 1, true )
    end,
```

## ![Flamethrower](images/FLAMETHROWER.png)Flamethrower (FLAMETHROWER)

* **description**: A stream of fire!!
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [2, 3, 6]
* **spawn_probability**: [1.0, 1.0, 1.0]
* **price**: 220
* **mana**: 20
* **max_uses**: 60
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/flamethrower.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/flamethrower.xml")
      c.spread_degrees = c.spread_degrees + 4.0
    end,
```

## ![Floating arc](images/FLOATING_ARC.png)Floating arc (FLOATING_ARC)

* **description**: Makes a projectile float above the ground
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 3, 5]
* **spawn_probability**: [0.4, 0.4, 0.4]
* **price**: 30
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/floating_arc.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/floating_arc.xml,"
      c.fire_rate_wait    = c.fire_rate_wait + 10
      draw_actions( 1, true )
    end,
```

## ![Flock of Ducks](images/EXPLODING_DUCKS.png)Flock of Ducks (EXPLODING_DUCKS)

* **description**: Summons a chaotic flock of spicy ducks
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [3, 4, 5]
* **spawn_probability**: [0.6, 0.8, 0.6]
* **price**: 200
* **mana**: 100
* **max_uses**: 20
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/duck.xml", 3}
* **spawn_requires_flag**: card_unlocked_exploding_deer
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/duck.xml")
      add_projectile("data/entities/projectiles/deck/duck.xml")
      add_projectile("data/entities/projectiles/deck/duck.xml")
      c.fire_rate_wait = c.fire_rate_wait + 60
      current_reload_time = current_reload_time + 20
    end,
```

## ![Fly downwards](images/FLY_DOWNWARDS.png)Fly downwards (FLY_DOWNWARDS)

* **description**: Causes a projectile to aim straight downwards a short time after casting
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 3, 5]
* **spawn_probability**: [0.4, 0.4, 0.4]
* **price**: 30
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/fly_downwards.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/fly_downwards.xml,"
      draw_actions( 1, true )
      c.fire_rate_wait    = c.fire_rate_wait - 3
    end,
```

## ![Fly upwards](images/FLY_UPWARDS.png)Fly upwards (FLY_UPWARDS)

* **description**: Causes a projectile to aim straight upwards a short time after casting
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 4, 6]
* **spawn_probability**: [0.4, 0.4, 0.4]
* **price**: 20
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/fly_upwards.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/fly_upwards.xml,"
      draw_actions( 1, true )
      c.fire_rate_wait    = c.fire_rate_wait - 3
    end,
```

## ![Formation - above and below](images/T_SHAPE.png)Formation - above and below (T_SHAPE)

* **description**: Casts 3 spells - ahead, above and below the caster
* **type**: ACTION_TYPE_DRAW_MANY
* **spawn_level**: [1, 2, 3, 4, 5]
* **spawn_probability**: [0.4, 0.4, 0.4, 0.4, 0.4]
* **price**: 120
* **mana**: 3
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      draw_actions(3, true)
      c.pattern_degrees = 90
    end,
```

## ![Formation - behind your back](images/I_SHAPE.png)Formation - behind your back (I_SHAPE)

* **description**: Casts two spells: one ahead of and one behind the caster
* **type**: ACTION_TYPE_DRAW_MANY
* **spawn_level**: [1, 2, 3, 4]
* **spawn_probability**: [0.4, 0.4, 0.4, 0.4]
* **price**: 80
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      draw_actions(2, true)
      c.pattern_degrees = 180
    end,
```

## ![Formation - bifurcated](images/Y_SHAPE.png)Formation - bifurcated (Y_SHAPE)

* **description**: Casts 2 spells in a bifurcated pattern
* **type**: ACTION_TYPE_DRAW_MANY
* **spawn_level**: [0, 1, 2, 3, 4]
* **spawn_probability**: [0.8, 0.4, 0.4, 0.4, 0.4]
* **price**: 100
* **mana**: 2
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      draw_actions(2, true)
      c.pattern_degrees = 45
    end,
```

## ![Formation - hexagon](images/CIRCLE_SHAPE.png)Formation - hexagon (CIRCLE_SHAPE)

* **description**: Casts 6 spells in a hexagonal pattern
* **type**: ACTION_TYPE_DRAW_MANY
* **spawn_level**: [1, 2, 3, 4, 5, 6]
* **spawn_probability**: [0.1, 0.2, 0.3, 0.3, 0.3, 0.3]
* **price**: 150
* **mana**: 6
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      draw_actions(6, true)
      c.pattern_degrees = 180
    end,
```

## ![Formation - pentagon](images/PENTAGRAM_SHAPE.png)Formation - pentagon (PENTAGRAM_SHAPE)

* **description**: Casts 5 spells in a pentagonal pattern
* **type**: ACTION_TYPE_DRAW_MANY
* **spawn_level**: [1, 2, 3, 4, 5]
* **spawn_probability**: [0.4, 0.4, 0.3, 0.2, 0.1]
* **price**: 150
* **mana**: 5
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      draw_actions(5, true)
      c.pattern_degrees = 180
    end,
```

## ![Formation - trifurcated](images/W_SHAPE.png)Formation - trifurcated (W_SHAPE)

* **description**: Casts 3 spells in a trifurcated pattern
* **type**: ACTION_TYPE_DRAW_MANY
* **spawn_level**: [2, 3, 4, 5, 6]
* **spawn_probability**: [0.4, 0.3, 0.3, 0.3, 0.3]
* **price**: 160
* **mana**: 3
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      draw_actions(3, true)
      c.pattern_degrees = 20
    end,
```

## ![Freeze charge](images/FREEZE.png)Freeze charge (FREEZE)

* **description**: Gives a projectile a frozen charge, that it will release on impact
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 3, 4, 5]
* **spawn_probability**: [1.0, 1.0, 1.0, 1.0]
* **price**: 140
* **mana**: 10
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/particles/freeze_charge.xml" }
* **action**:

```lua
 function()
      c.damage_ice_add = c.damage_ice_add + 0.2
      c.game_effect_entities = c.game_effect_entities .. "data/entities/misc/effect_frozen.xml,"
      c.extra_entities = c.extra_entities .. "data/entities/particles/freeze_charge.xml,"
      draw_actions( 1, true )
    end,
```

## ![Freezing gaze](images/FREEZING_GAZE.png)Freezing gaze (FREEZING_GAZE)

* **description**: A heart-freezingly sinister aura
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [2, 3, 4]
* **spawn_probability**: [1.0, 1.0, 1.0]
* **price**: 180
* **mana**: 45
* **max_uses**: 20
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/freezing_gaze_beam.xml",12}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/freezing_gaze_beam.xml")
      add_projectile("data/entities/projectiles/deck/freezing_gaze_beam.xml")
      add_projectile("data/entities/projectiles/deck/freezing_gaze_beam.xml")
      add_projectile("data/entities/projectiles/deck/freezing_gaze_beam.xml")
      add_projectile("data/entities/projectiles/deck/freezing_gaze_beam.xml")
      add_projectile("data/entities/projectiles/deck/freezing_gaze_beam.xml")
      add_projectile("data/entities/projectiles/deck/freezing_gaze_beam.xml")
      add_projectile("data/entities/projectiles/deck/freezing_gaze_beam.xml")
      add_projectile("data/entities/projectiles/deck/freezing_gaze_beam.xml")
      add_projectile("data/entities/projectiles/deck/freezing_gaze_beam.xml")
      add_projectile("data/entities/projectiles/deck/freezing_gaze_beam.xml")
      add_projectile("data/entities/projectiles/deck/freezing_gaze_beam.xml")
      c.pattern_degrees = 30
      c.fire_rate_wait = c.fire_rate_wait + 20
    end,
```

## ![Gamma](images/GAMMA.png)Gamma (GAMMA)

* **description**: Casts a copy of the last spell in your wand
* **type**: ACTION_TYPE_OTHER
* **spawn_level**: [5, 6, 10]
* **spawn_probability**: [0.1, 0.1, 1.0]
* **price**: 200
* **mana**: 30
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: true
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_duplicate
* **related_extra_entities**: 
* **action**:

```lua
 function( recursion_level, iteration )
      c.fire_rate_wait = c.fire_rate_wait + 15
      
      local data = {}
      
      if ( #deck > 0 ) then
        data = deck[#deck]
      elseif ( #hand > 0 ) then
        data = hand[#hand]
      else
        data = nil
      end
      
      local rec = check_recursion( data, recursion_level )
      
      if ( data ~= nil ) and ( rec > -1 ) then
        data.action( rec )
      end
      
    end,
```

## ![Giant explosion on drunk enemies](images/HITFX_EXPLOSION_ALCOHOL_GIGA.png)Giant explosion on drunk enemies (HITFX_EXPLOSION_ALCOHOL_GIGA)

* **description**: Makes a projectile explode powerfully upon collision with creatures covered in alcohol
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 3, 4, 5]
* **spawn_probability**: [0.1, 0.1, 0.1, 0.1]
* **price**: 300
* **mana**: 200
* **max_uses**: 20
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/hitfx_explode_alcohol_giga.xml", "data/entities/particles/tinyspark_orange.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/hitfx_explode_alcohol_giga.xml,data/entities/particles/tinyspark_orange.xml,"
      draw_actions( 1, true )
    end,
```

## ![Giant explosion on slimy enemies](images/HITFX_EXPLOSION_SLIME_GIGA.png)Giant explosion on slimy enemies (HITFX_EXPLOSION_SLIME_GIGA)

* **description**: Makes a projectile explode powerfully upon collision with creatures covered in slime
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 3, 4, 5]
* **spawn_probability**: [0.1, 0.1, 0.1, 0.1]
* **price**: 300
* **mana**: 200
* **max_uses**: 20
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/hitfx_explode_slime_giga.xml", "data/entities/particles/tinyspark_purple.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/hitfx_explode_slime_giga.xml,data/entities/particles/tinyspark_purple.xml,"
      draw_actions( 1, true )
    end,
```

## ![Giant firebolt](images/GRENADE_TIER_3.png)Giant firebolt (GRENADE_TIER_3)

* **description**: The most powerful version of Firebolt
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [1, 2, 3, 4, 5]
* **spawn_probability**: [0.25, 0.5, 0.75, 1.0, 1.0]
* **price**: 220
* **mana**: 90
* **max_uses**: 20
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/grenade_tier_3.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/grenade_tier_3.xml")
      c.fire_rate_wait = c.fire_rate_wait + 80
      c.screenshake = c.screenshake + 15.0
      c.child_speed_multiplier = c.child_speed_multiplier * 0.9
      shot_effects.recoil_knockback = 140.0
    end,
```

## ![Giant magic missile](images/ROCKET_TIER_3.png)Giant magic missile (ROCKET_TIER_3)

* **description**: The most powerful version of Magic missile
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [2, 3, 4, 5, 6]
* **spawn_probability**: [0.25, 0.5, 1.0, 1.0, 1.0]
* **price**: 250
* **mana**: 120
* **max_uses**: 6
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/rocket_tier_3.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/rocket_tier_3.xml")
      c.fire_rate_wait = c.fire_rate_wait + 120
      c.ragdoll_fx = 2
      shot_effects.recoil_knockback = 180.0
    end,
```

## ![Giant spitter bolt](images/SPITTER_TIER_3.png)Giant spitter bolt (SPITTER_TIER_3)

* **description**: The most powerful version of Spitter Bolt
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [3, 4, 5, 6]
* **spawn_probability**: [0.8, 0.8, 1.0, 1.0]
* **price**: 240
* **mana**: 40
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/spitter_tier_3.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/spitter_tier_3.xml")
      c.fire_rate_wait = c.fire_rate_wait - 4
      c.screenshake = c.screenshake + 3.1
      c.dampening = 0.3
      c.spread_degrees = c.spread_degrees + 9.0
    end,
```

## ![Giant spitter bolt with timer](images/SPITTER_TIER_3_TIMER.png)Giant spitter bolt with timer (SPITTER_TIER_3_TIMER)

* **description**: The most powerful version of Spitter Bolt that casts another spell after a timer runs out
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [4, 5, 6]
* **spawn_probability**: [0.5, 0.5, 0.5]
* **price**: 260
* **mana**: 45
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/spitter_tier_3.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile_trigger_timer("data/entities/projectiles/deck/spitter_tier_3.xml", 40, 1)
      c.fire_rate_wait = c.fire_rate_wait - 4
      c.screenshake = c.screenshake + 3.1
      c.dampening = 0.3
      c.spread_degrees = c.spread_degrees + 9.0
    end,
```

## ![Giga Holy Bomb](images/BOMB_HOLY_GIGA.png)Giga Holy Bomb (BOMB_HOLY_GIGA)

* **description**: Bigger and therefore holier
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [10]
* **spawn_probability**: [1.0]
* **price**: 600
* **mana**: 600
* **max_uses**: 2
* **never_unlimited**: true
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/bomb_holy_giga.xml"}
* **spawn_requires_flag**: card_unlocked_bomb_holy_giga
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/bomb_holy_giga.xml")
      current_reload_time = current_reload_time + 160
      shot_effects.recoil_knockback = shot_effects.recoil_knockback + 100.0
      c.fire_rate_wait = c.fire_rate_wait + 120
    end,
```

## ![Giga Nuke](images/NUKE_GIGA.png)Giga Nuke (NUKE_GIGA)

* **description**: What do you expect?
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [10]
* **spawn_probability**: [1.0]
* **price**: 800
* **mana**: 500
* **max_uses**: 1
* **never_unlimited**: true
* **spawn_manual_unlock**: true
* **recursive**: true
* **ai_never_uses**: true
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/nuke_giga.xml"}
* **spawn_requires_flag**: card_unlocked_nukegiga
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/nuke_giga.xml")
      c.fire_rate_wait = 50
      c.speed_multiplier = c.speed_multiplier * 0.5
      c.material = "fire"
      c.material_amount = c.material_amount + 80
      c.ragdoll_fx = 2
      c.gore_particles = c.gore_particles + 30
      c.screenshake = c.screenshake + 30.5
      current_reload_time = current_reload_time + 800
      shot_effects.recoil_knockback = shot_effects.recoil_knockback + 300.0
      
      if ( c.speed_multiplier >= 20 ) then
        c.speed_multiplier = math.min( c.speed_multiplier, 20 )
      elseif ( c.speed_multiplier < 0 ) then
        c.speed_multiplier = 0
      end
    end,
```

## ![Giga black hole](images/BLACK_HOLE_BIG.png)Giga black hole (BLACK_HOLE_BIG)

* **description**: A growing orb of negative energy that destroys everything in its reach
* **type**: ACTION_TYPE_STATIC_PROJECTILE
* **spawn_level**: [1, 3, 5, 6, 10]
* **spawn_probability**: [0.8, 0.8, 0.8, 0.8, 0.5]
* **price**: 320
* **mana**: 240
* **max_uses**: 6
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/black_hole_big.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/black_hole_big.xml")
      c.fire_rate_wait = c.fire_rate_wait + 80
      c.screenshake = c.screenshake + 10
    end,
```

## ![Giga death cross](images/DEATH_CROSS_BIG.png)Giga death cross (DEATH_CROSS_BIG)

* **description**: A giant, deadly energy cross that explodes after a short time
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [2, 3, 4, 5, 6, 10]
* **spawn_probability**: [0.4, 0.4, 0.4, 0.4, 0.4, 0.2]
* **price**: 310
* **mana**: 150
* **max_uses**: 8
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/death_cross_big.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/death_cross_big.xml")
      c.fire_rate_wait = c.fire_rate_wait + 70
      shot_effects.recoil_knockback = shot_effects.recoil_knockback + 30.0
    end,
```

## ![Giga disc projectile](images/DISC_BULLET_BIG.png)Giga disc projectile (DISC_BULLET_BIG)

* **description**: Summons a large, serrated disc with a curious flight pattern
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [0, 2, 4, 10]
* **spawn_probability**: [0.6, 0.6, 0.6, 0.1]
* **price**: 180
* **mana**: 38
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/disc_bullet_big.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/disc_bullet_big.xml")
      c.fire_rate_wait = c.fire_rate_wait + 20
      c.spread_degrees = c.spread_degrees + 3.4
      shot_effects.recoil_knockback = shot_effects.recoil_knockback + 20.0
    end,
```

## ![Glitter bomb](images/GLITTER_BOMB.png)Glitter bomb (GLITTER_BOMB)

* **description**: Summons a bomb that explodes into volatile fragments
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [0, 1, 2, 3, 4]
* **spawn_probability**: [0.8, 0.8, 0.8, 0.8, 0.8]
* **price**: 200
* **mana**: 70
* **max_uses**: 16
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/glitter_bomb.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/glitter_bomb.xml")
      c.fire_rate_wait = c.fire_rate_wait + 50
      c.spread_degrees = c.spread_degrees + 12.0
    end,
```

## ![Glittering field](images/PURPLE_EXPLOSION_FIELD.png)Glittering field (PURPLE_EXPLOSION_FIELD)

* **description**: Small explosions appear randomly over a large area
* **type**: ACTION_TYPE_STATIC_PROJECTILE
* **spawn_level**: [0, 1, 2, 4, 5, 6]
* **spawn_probability**: [1.0, 1.0, 1.0, 1.0, 1.0, 1.0]
* **price**: 160
* **mana**: 90
* **max_uses**: 20
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/purple_explosion_field.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/purple_explosion_field.xml")
      c.fire_rate_wait = c.fire_rate_wait + 10
      c.speed_multiplier = c.speed_multiplier - 2
      
      if ( c.speed_multiplier >= 20 ) then
        c.speed_multiplier = math.min( c.speed_multiplier, 20 )
      elseif ( c.speed_multiplier < 0 ) then
        c.speed_multiplier = 0
      end
    end,
```

## ![Glowing lance](images/LANCE.png)Glowing lance (LANCE)

* **description**: A magical lance that cuts through soft materials
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [1, 2, 5, 6]
* **spawn_probability**: [1.0, 1.0, 1.0, 1.0]
* **price**: 180
* **mana**: 30
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/lance.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/lance.xml")
      c.fire_rate_wait = c.fire_rate_wait + 20
      c.spread_degrees = c.spread_degrees - 20
      shot_effects.recoil_knockback = 60.0
    end,
```

## ![Glue Ball](images/GLUE_SHOT.png)Glue Ball (GLUE_SHOT)

* **description**: A projectile that explodes into a sticky mess
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [2, 3, 4, 5]
* **spawn_probability**: [0.6, 0.2, 0.2, 0.6]
* **price**: 140
* **mana**: 25
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/glue_shot.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/glue_shot.xml")
      c.fire_rate_wait = c.fire_rate_wait + 30
      c.spread_degrees = c.spread_degrees + 5.0
    end,
```

## ![Gold to Power](images/MONEY_MAGIC.png)Gold to Power (MONEY_MAGIC)

* **description**: Spends 5% of your current gold and adds damage to a projectile proportional to the amount spent
* **type**: ACTION_TYPE_UTILITY
* **spawn_level**: [3, 5, 6, 10]
* **spawn_probability**: [0.2, 0.8, 0.1, 0.5]
* **price**: 200
* **mana**: 30
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/particles/gold_sparks.xml" }
* **action**:

```lua
 function()
      local entity_id = GetUpdatedEntityID()
      
      local dcomp = EntityGetFirstComponent( entity_id, "WalletComponent" )
      
      if ( dcomp ~= nil ) then
        local money = ComponentGetValue2( dcomp, "money" )
        local moneyspent = ComponentGetValue2( dcomp, "money_spent" )
        local damage = math.min( math.floor( money * 0.05 ), 24000 )
        
        if ( damage > 1 ) and ( money >= 10 ) then
          damage = math.max( damage, 10 )
          
          c.extra_entities = c.extra_entities .. "data/entities/particles/gold_sparks.xml,"
          
          money = money - damage
          moneyspent = moneyspent + damage
          ComponentSetValue2( dcomp, "money", money )
          ComponentSetValue2( dcomp, "money_spent", moneyspent )
          
          
          if ( damage < 120 ) then
            c.damage_projectile_add = c.damage_projectile_add + ( damage / 25 )
          elseif ( damage < 300 ) then
            c.damage_projectile_add = c.damage_projectile_add + ( damage / 35 )
          elseif ( damage < 500 ) then
            c.damage_projectile_add = c.damage_projectile_add + ( damage / 45 )
          else
            c.damage_projectile_add = c.damage_projectile_add + ( damage / 55 )
          end
        end
      end
      
      draw_actions( 1, true )
    end,
```

## ![Gravity](images/GRAVITY.png)Gravity (GRAVITY)

* **description**: Increases the effect gravity has on a projectile
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4, 5, 6]
* **spawn_probability**: [0.5, 0.5, 0.5, 0.5, 0.5]
* **price**: 50
* **mana**: 1
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      c.gravity = c.gravity + 600.0
      draw_actions( 1, true )
    end,
```

## ![Green Glimmer](images/COLOUR_GREEN.png)Green Glimmer (COLOUR_GREEN)

* **description**: Gives a projectile a green sparkly trail
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4]
* **spawn_probability**: [0.1, 0.1, 0.1]
* **price**: 40
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_paint
* **related_extra_entities**: { "data/entities/particles/tinyspark_red.xml", "data/entities/misc/colour_green.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/particles/tinyspark_red.xml,data/entities/misc/colour_green.xml,"
      c.fire_rate_wait = c.fire_rate_wait - 8
      c.screenshake = c.screenshake - 2.5
      if ( c.screenshake < 0 ) then
        c.screenshake = 0
      end
      draw_actions( 1, true )
    end,
```

## ![Ground to sand](images/STATIC_TO_SAND.png)Ground to sand (STATIC_TO_SAND)

* **description**: Makes any hard, solid materials within a projectile's range turn into sand
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4]
* **spawn_probability**: [0.3, 0.3, 0.3]
* **price**: 140
* **mana**: 70
* **max_uses**: 8
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/static_to_sand.xml", "data/entities/particles/tinyspark_yellow.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/static_to_sand.xml,data/entities/particles/tinyspark_yellow.xml,"
      c.fire_rate_wait = c.fire_rate_wait + 60
      draw_actions( 1, true )
    end,
```

## ![Gunpowder Arc](images/ARC_GUNPOWDER.png)Gunpowder Arc (ARC_GUNPOWDER)

* **description**: Creates arcs of gunpowder between projectiles (requires 2 projectile spells)
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 2, 3, 4, 5]
* **spawn_probability**: [0.4, 0.4, 0.4, 0.4, 0.4]
* **price**: 160
* **mana**: 15
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/arc_gunpowder.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/arc_gunpowder.xml,"
      draw_actions( 1, true )
    end,
```

## ![Gunpowder trail](images/GUNPOWDER_TRAIL.png)Gunpowder trail (GUNPOWDER_TRAIL)

* **description**: Gives a projectile a trail of gunpowder
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4]
* **spawn_probability**: [0.3, 0.3, 0.3]
* **price**: 160
* **mana**: 10
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      c.trail_material = c.trail_material .. "gunpowder,"
      c.trail_material_amount = c.trail_material_amount + 20
      draw_actions( 1, true )
    end,
```

## ![Healing bolt](images/HEAL_BULLET.png)Healing bolt (HEAL_BULLET)

* **description**: A magical bolt with rejuvenative powers
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [2, 3, 4]
* **spawn_probability**: [1.0, 1.0, 1.0]
* **price**: 60
* **mana**: 15
* **max_uses**: 20
* **never_unlimited**: true
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/heal_bullet.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/heal_bullet.xml")
      c.fire_rate_wait = c.fire_rate_wait + 4
      c.spread_degrees = c.spread_degrees + 2.0
    end,
```

## ![Heavy Shot](images/HEAVY_SHOT.png)Heavy Shot (HEAVY_SHOT)

* **description**: Greatly increases the damage done by a projectile, at the cost of its speed
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4]
* **spawn_probability**: [0.4, 0.4, 0.4]
* **price**: 150
* **mana**: 7
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/particles/heavy_shot.xml" }
* **action**:

```lua
 function()
      c.damage_projectile_add = c.damage_projectile_add + 1.75
      c.fire_rate_wait    = c.fire_rate_wait + 10
      c.gore_particles    = c.gore_particles + 10
      c.speed_multiplier = c.speed_multiplier * 0.3
      shot_effects.recoil_knockback = shot_effects.recoil_knockback + 50.0
      c.extra_entities = c.extra_entities .. "data/entities/particles/heavy_shot.xml,"
      
      if ( c.speed_multiplier >= 20 ) then
        c.speed_multiplier = math.min( c.speed_multiplier, 20 )
      elseif ( c.speed_multiplier < 0 ) then
        c.speed_multiplier = 0
      end
      
      draw_actions( 1, true )
    end,
```

## ![Heavy spread](images/HEAVY_SPREAD.png)Heavy spread (HEAVY_SPREAD)

* **description**: Gives a projectile a much lower cast delay, but no respect to your aim
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [0, 1, 2, 4, 5, 6]
* **spawn_probability**: [0.8, 0.8, 0.8, 0.8, 0.8, 0.8]
* **price**: 100
* **mana**: 2
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      c.fire_rate_wait = c.fire_rate_wait - 7
      current_reload_time = current_reload_time - 15
      c.spread_degrees = c.spread_degrees + 720
      draw_actions( 1, true )
    end,
```

## ![Holy Bomb](images/BOMB_HOLY.png)Holy Bomb (BOMB_HOLY)

* **description**: Summons a bomb that... well...
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [2, 3, 4, 5, 6, 10]
* **spawn_probability**: [0.2, 0.2, 0.2, 0.2, 0.2, 0.5]
* **price**: 400
* **mana**: 300
* **max_uses**: 2
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/bomb_holy.xml"}
* **spawn_requires_flag**: card_unlocked_bomb_holy
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/bomb_holy.xml")
      current_reload_time = current_reload_time + 80
      shot_effects.recoil_knockback = shot_effects.recoil_knockback + 100.0
      c.fire_rate_wait = c.fire_rate_wait + 40
    end,
```

## ![Homebringer Teleport Bolt](images/TELEPORT_PROJECTILE_CLOSER.png)Homebringer Teleport Bolt (TELEPORT_PROJECTILE_CLOSER)

* **description**: Brings the target hit closer to you
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [0, 1, 2, 4, 5, 6]
* **spawn_probability**: [0.6, 0.6, 0.6, 0.4, 0.4, 0.4]
* **price**: 130
* **mana**: 20
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/teleport_projectile_closer.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/teleport_projectile_closer.xml")
      c.spread_degrees = c.spread_degrees - 2.0
    end,
```

## ![Homing](images/HOMING.png)Homing (HOMING)

* **description**: Makes a projectile accelerate towards your foes
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 2, 3, 4, 5, 6]
* **spawn_probability**: [0.1, 0.4, 0.4, 0.4, 0.4, 0.4]
* **price**: 220
* **mana**: 70
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/homing.xml", "data/entities/particles/tinyspark_white.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/homing.xml,data/entities/particles/tinyspark_white.xml,"
      draw_actions( 1, true )
    end,
```

## ![Horizontal barrier](images/WALL_HORIZONTAL.png)Horizontal barrier (WALL_HORIZONTAL)

* **description**: A thin, horizontal barrier that harms passing creatures, including you
* **type**: ACTION_TYPE_STATIC_PROJECTILE
* **spawn_level**: [0, 1, 2, 4, 5, 6]
* **spawn_probability**: [0.4, 0.4, 0.4, 0.4, 0.4, 0.4]
* **price**: 160
* **mana**: 70
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/wall_horizontal.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/wall_horizontal.xml")
      c.fire_rate_wait = c.fire_rate_wait + 5
    end,
```

## ![Horizontal path](images/HORIZONTAL_ARC.png)Horizontal path (HORIZONTAL_ARC)

* **description**: Forces a projectile on a horizontal path, but increases its damage
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 3, 5]
* **spawn_probability**: [0.4, 0.4, 0.4]
* **price**: 20
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/horizontal_arc.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/horizontal_arc.xml,"
      draw_actions( 1, true )
      c.damage_projectile_add = c.damage_projectile_add + 0.3
      c.fire_rate_wait    = c.fire_rate_wait - 6
    end,
```

## ![Iceball](images/ICEBALL.png)Iceball (ICEBALL)

* **description**: A magical ball of frozen fire
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [2, 3, 4, 6]
* **spawn_probability**: [1.0, 1.0, 1.0, 1.0]
* **price**: 260
* **mana**: 90
* **max_uses**: 15
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/iceball.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/iceball.xml")
      c.spread_degrees = c.spread_degrees + 8.0
      c.fire_rate_wait = c.fire_rate_wait + 80
      shot_effects.recoil_knockback = shot_effects.recoil_knockback + 20.0
    end,
```

## ![Increase lifetime](images/LIFETIME.png)Increase lifetime (LIFETIME)

* **description**: Increases the lifetime of a spell
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [3, 4, 5, 6, 10]
* **spawn_probability**: [0.5, 0.5, 0.5, 0.5, 0.1]
* **price**: 250
* **mana**: 40
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      c.lifetime_add     = c.lifetime_add + 75
      c.fire_rate_wait = c.fire_rate_wait + 13
      draw_actions( 1, true )
    end,
```

## ![Infestation](images/INFESTATION.png)Infestation (INFESTATION)

* **description**: A bunch of magical sparks that fly in every direction
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [2, 3, 4]
* **spawn_probability**: [0.1, 0.3, 0.3]
* **price**: 160
* **mana**: 40
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/infestation.xml",10}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      for i=1,6 do
        add_projectile("data/entities/projectiles/deck/infestation.xml")
      end
      c.fire_rate_wait = c.fire_rate_wait - 2
      c.spread_degrees = c.spread_degrees + 25
    end,
```

## ![Intense concentrated light](images/MEGALASER.png)Intense concentrated light (MEGALASER)

* **description**: A spectral wand is summoned that casts a huge beam of light
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [3, 4, 5, 6, 10]
* **spawn_probability**: [0.6, 0.6, 0.6, 0.6, 0.1]
* **price**: 300
* **mana**: 110
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/megalaser.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/megalaser_beam.xml")
      add_projectile("data/entities/projectiles/deck/megalaser_beam.xml")
      add_projectile("data/entities/projectiles/deck/megalaser_beam.xml")
      add_projectile("data/entities/projectiles/deck/megalaser_beam.xml")
      add_projectile("data/entities/projectiles/deck/megalaser_beam.xml")
      
      add_projectile("data/entities/projectiles/deck/megalaser.xml")
      c.fire_rate_wait = c.fire_rate_wait + 90
      shot_effects.recoil_knockback = shot_effects.recoil_knockback + 20.0
      c.game_effect_entities = c.game_effect_entities .. "data/entities/misc/effect_disintegrated.xml,"
    end,
```

## ![Invisible Spell](images/COLOUR_INVIS.png)Invisible Spell (COLOUR_INVIS)

* **description**: Turns a projectile invisible
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4]
* **spawn_probability**: [0.1, 0.1, 0.1]
* **price**: 40
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_paint
* **related_extra_entities**: { "data/entities/misc/colour_invis.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/colour_invis.xml,"
      c.fire_rate_wait = c.fire_rate_wait - 8
      c.screenshake = c.screenshake - 2.5
      if ( c.screenshake < 0 ) then
        c.screenshake = 0
      end
      draw_actions( 1, true )
    end,
```

## ![Kantele - note A](images/KANTELE_A.png)Kantele - note A (KANTELE_A)

* **description**: Music for your ears!
* **type**: ACTION_TYPE_OTHER
* **spawn_level**: [10]
* **spawn_probability**: [0.0]
* **price**: 10
* **mana**: 1
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/kantele/kantele_a.xml"}
* **spawn_requires_flag**: card_unlocked_kantele
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/kantele/kantele_a.xml")
      c.fire_rate_wait = c.fire_rate_wait + 15
    end,
```

## ![Kantele - note D](images/KANTELE_D.png)Kantele - note D (KANTELE_D)

* **description**: Music for your ears!
* **type**: ACTION_TYPE_OTHER
* **spawn_level**: [10]
* **spawn_probability**: [0.0]
* **price**: 10
* **mana**: 1
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/kantele/kantele_d.xml"}
* **spawn_requires_flag**: card_unlocked_kantele
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/kantele/kantele_d.xml")
      c.fire_rate_wait = c.fire_rate_wait + 15
    end,
```

## ![Kantele - note D#](images/KANTELE_DIS.png)Kantele - note D# (KANTELE_DIS)

* **description**: Music for your ears!
* **type**: ACTION_TYPE_OTHER
* **spawn_level**: [10]
* **spawn_probability**: [0.0]
* **price**: 10
* **mana**: 1
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/kantele/kantele_dis.xml"}
* **spawn_requires_flag**: card_unlocked_kantele
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/kantele/kantele_dis.xml")
      c.fire_rate_wait = c.fire_rate_wait + 15
    end,
```

## ![Kantele - note E](images/KANTELE_E.png)Kantele - note E (KANTELE_E)

* **description**: Music for your ears!
* **type**: ACTION_TYPE_OTHER
* **spawn_level**: [10]
* **spawn_probability**: [0.0]
* **price**: 10
* **mana**: 1
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/kantele/kantele_e.xml"}
* **spawn_requires_flag**: card_unlocked_kantele
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/kantele/kantele_e.xml")
      c.fire_rate_wait = c.fire_rate_wait + 15
    end,
```

## ![Kantele - note G](images/KANTELE_G.png)Kantele - note G (KANTELE_G)

* **description**: Music for your ears!
* **type**: ACTION_TYPE_OTHER
* **spawn_level**: [10]
* **spawn_probability**: [0.0]
* **price**: 10
* **mana**: 1
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/kantele/kantele_g.xml"}
* **spawn_requires_flag**: card_unlocked_kantele
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/kantele/kantele_g.xml")
      c.fire_rate_wait = c.fire_rate_wait + 15
    end,
```

## ![Knockback](images/KNOCKBACK.png)Knockback (KNOCKBACK)

* **description**: Gives a projectile the power to knock back the foes it hits
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [3, 5]
* **spawn_probability**: [0.6, 0.6]
* **price**: 100
* **mana**: 5
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      c.knockback_force = c.knockback_force + 5
      draw_actions( 1, true )
    end,
```

## ![Large firebolt](images/GRENADE_TIER_2.png)Large firebolt (GRENADE_TIER_2)

* **description**: A more powerful version of Firebolt
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [1, 2, 3, 4, 5]
* **spawn_probability**: [0.5, 1.0, 1.0, 1.0, 1.0]
* **price**: 220
* **mana**: 90
* **max_uses**: 20
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/grenade_tier_2.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/grenade_tier_2.xml")
      c.fire_rate_wait = c.fire_rate_wait + 50
      c.screenshake = c.screenshake + 8.0
      c.child_speed_multiplier = c.child_speed_multiplier * 0.75
      shot_effects.recoil_knockback = 120.0
    end,
```

## ![Large magic missile](images/ROCKET_TIER_2.png)Large magic missile (ROCKET_TIER_2)

* **description**: A more powerful version of Magic missile
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [2, 3, 4, 5, 6]
* **spawn_probability**: [0.5, 1.0, 1.0, 1.0, 1.0]
* **price**: 240
* **mana**: 90
* **max_uses**: 8
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/rocket_tier_2.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/rocket_tier_2.xml")
      c.fire_rate_wait = c.fire_rate_wait + 90
      c.ragdoll_fx = 2
      shot_effects.recoil_knockback = 160.0
    end,
```

## ![Large spitter bolt](images/SPITTER_TIER_2.png)Large spitter bolt (SPITTER_TIER_2)

* **description**: A more powerful version of Spitter Bolt
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [2, 3, 4, 5]
* **spawn_probability**: [1.0, 1.0, 1.0, 0.5]
* **price**: 190
* **mana**: 25
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/spitter_tier_2.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/spitter_tier_2.xml")
      c.fire_rate_wait = c.fire_rate_wait - 2
      c.screenshake = c.screenshake + 1.1
      c.dampening = 0.2
      c.spread_degrees = c.spread_degrees + 7.5
    end,
```

## ![Large spitter bolt with timer](images/SPITTER_TIER_2_TIMER.png)Large spitter bolt with timer (SPITTER_TIER_2_TIMER)

* **description**: A more powerful version of Spitter Bolt that casts another spell after a timer runs out
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [2, 3, 4, 5]
* **spawn_probability**: [0.5, 0.5, 0.5, 1.0]
* **price**: 220
* **mana**: 30
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/spitter_tier_2.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile_trigger_timer("data/entities/projectiles/deck/spitter_tier_2.xml", 40, 1)
      c.fire_rate_wait = c.fire_rate_wait - 2
      c.screenshake = c.screenshake + 1.1
      c.dampening = 0.2
      c.spread_degrees = c.spread_degrees + 7.5
    end,
```

## ![Larpa Bounce](images/BOUNCE_LARPA.png)Larpa Bounce (BOUNCE_LARPA)

* **description**: A projectile will launch a copy of itself when it bounces
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [4, 5, 6]
* **spawn_probability**: [0.4, 0.6, 0.4]
* **price**: 250
* **mana**: 80
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/bounce_larpa.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/bounce_larpa.xml,"
      c.bounces = c.bounces + 1
      c.fire_rate_wait = c.fire_rate_wait + 32
      shot_effects.recoil_knockback = shot_effects.recoil_knockback + 10.0
      draw_actions( 1, true )
    end,
```

## ![Larpa Explosion](images/LARPA_DEATH.png)Larpa Explosion (LARPA_DEATH)

* **description**: A projectile will shoot out 8 copies of itself when it expires or hits the ground
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4, 5, 10]
* **spawn_probability**: [0.1, 0.1, 0.3, 0.2, 0.2]
* **price**: 150
* **mana**: 90
* **max_uses**: 30
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/larpa_death.xml" }
* **action**:

```lua
 function()
      c.fire_rate_wait = c.fire_rate_wait + 15
      c.extra_entities = c.extra_entities .. "data/entities/misc/larpa_death.xml,"
      draw_actions( 1, true )
    end,
```

## ![Lava to blood](images/LAVA_TO_BLOOD.png)Lava to blood (LAVA_TO_BLOOD)

* **description**: Makes any lava within a projectile's range turn into blood
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4]
* **spawn_probability**: [0.3, 0.3, 0.3]
* **price**: 80
* **mana**: 30
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/lava_to_blood.xml", "data/entities/particles/tinyspark_orange.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/lava_to_blood.xml,data/entities/particles/tinyspark_orange.xml,"
      c.fire_rate_wait = c.fire_rate_wait + 10
      draw_actions( 1, true )
    end,
```

## ![Light](images/LIGHT.png)Light (LIGHT)

* **description**: Makes a projectile illuminate its surroundings
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [0, 1, 2, 3, 4]
* **spawn_probability**: [1.0, 0.8, 0.6, 0.4, 0.2]
* **price**: 20
* **mana**: 1
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/light.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/light.xml,"
      draw_actions( 1, true )
    end,
```

## ![Light shot](images/LIGHT_SHOT.png)Light shot (LIGHT_SHOT)

* **description**: Makes a projectile move considerably faster, but deal less damage
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4]
* **spawn_probability**: [0.4, 0.4, 0.4]
* **price**: 60
* **mana**: 5
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/particles/light_shot.xml" }
* **action**:

```lua
 function()
      c.damage_projectile_add = c.damage_projectile_add - 1.0
      c.explosion_radius = c.explosion_radius - 10.0
      if (c.explosion_radius < 0) then
        c.explosion_radius = 0
      end
      c.fire_rate_wait    = c.fire_rate_wait - 3
      c.speed_multiplier = c.speed_multiplier * 7.5
      c.spread_degrees = c.spread_degrees - 6
      shot_effects.recoil_knockback = shot_effects.recoil_knockback - 10.0
      c.extra_entities = c.extra_entities .. "data/entities/particles/light_shot.xml,"
      
      if ( c.speed_multiplier >= 20 ) then
        c.speed_multiplier = math.min( c.speed_multiplier, 20 )
      elseif ( c.speed_multiplier < 0 ) then
        c.speed_multiplier = 0
      end
      
      draw_actions( 1, true )
    end,
```

## ![Lightning bolt](images/LIGHTNING.png)Lightning bolt (LIGHTNING)

* **description**: The primordial force of nature
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [1, 2, 5, 6]
* **spawn_probability**: [1.0, 1.0, 1.0, 1.0]
* **price**: 250
* **mana**: 70
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/lightning.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/lightning.xml")
      c.fire_rate_wait = c.fire_rate_wait + 50
      shot_effects.recoil_knockback = 180.0
    end,
```

## ![Lightning thrower](images/LIGHTNING_RAY.png)Lightning thrower (LIGHTNING_RAY)

* **description**: Makes a projectile cast lightning in random directions
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 2, 3, 4, 5]
* **spawn_probability**: [0.0, 0.0, 0.4, 0.4, 0.4]
* **price**: 180
* **mana**: 110
* **max_uses**: 16
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/lightning_ray.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/lightning_ray.xml,"
      draw_actions( 1, true )
    end,
```

## ![Linear arc](images/LINE_ARC.png)Linear arc (LINE_ARC)

* **description**: Makes a projectile fly only in cardinal or diagonal lines
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 3, 5]
* **spawn_probability**: [0.4, 0.4, 0.4]
* **price**: 30
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/line_arc.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/line_arc.xml,"
      draw_actions( 1, true )
      c.damage_projectile_add = c.damage_projectile_add + 0.2
      c.fire_rate_wait    = c.fire_rate_wait - 4
    end,
```

## ![Liquid Detonation](images/LIQUID_TO_EXPLOSION.png)Liquid Detonation (LIQUID_TO_EXPLOSION)

* **description**: Converts nearby nonmagical liquids into explosive gunpowder
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4]
* **spawn_probability**: [0.3, 0.3, 0.3]
* **price**: 120
* **mana**: 40
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/liquid_to_explosion.xml", "data/entities/particles/tinyspark_red.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/liquid_to_explosion.xml,data/entities/particles/tinyspark_red.xml,"
      c.fire_rate_wait = c.fire_rate_wait + 20
      draw_actions( 1, true )
    end,
```

## ![Liquid Vacuum Field](images/VACUUM_LIQUID.png)Liquid Vacuum Field (VACUUM_LIQUID)

* **description**: Sucks liquid materials nearby and releases them upon expiring
* **type**: ACTION_TYPE_STATIC_PROJECTILE
* **spawn_level**: [2, 3, 5, 6]
* **spawn_probability**: [0.3, 1.0, 0.3, 0.3]
* **price**: 150
* **mana**: 40
* **max_uses**: 20
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/vacuum_liquid.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/vacuum_liquid.xml")
      c.fire_rate_wait = c.fire_rate_wait + 10
    end,
```

## ![Long-distance cast](images/LONG_DISTANCE_CAST.png)Long-distance cast (LONG_DISTANCE_CAST)

* **description**: Casts a spell some distance away from the caster
* **type**: ACTION_TYPE_UTILITY
* **spawn_level**: [0, 1, 2, 4, 5, 6]
* **spawn_probability**: [0.6, 0.6, 0.6, 0.6, 0.6, 0.6]
* **price**: 90
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/long_distance_cast.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile_trigger_death("data/entities/projectiles/deck/long_distance_cast.xml", 1)
      c.fire_rate_wait = c.fire_rate_wait - 5
    end,
```

## ![Luminous drill](images/LUMINOUS_DRILL.png)Luminous drill (LUMINOUS_DRILL)

* **description**: A pinpointed, short-ranged beam of concentrated light
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [0, 2]
* **spawn_probability**: [1.0, 1.0]
* **price**: 150
* **mana**: 10
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/luminous_drill.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/luminous_drill.xml")
      c.fire_rate_wait = c.fire_rate_wait - 35
      current_reload_time = current_reload_time - ACTION_DRAW_RELOAD_TIME_INCREASE - 10 -- this is a hack to get the digger reload time back to 0
    end,
```

## ![Luminous drill with timer](images/LASER_LUMINOUS_DRILL.png)Luminous drill with timer (LASER_LUMINOUS_DRILL)

* **description**: A pinpointed, short-ranged beam of concentrated light that casts another spell after a timer runs out
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [0, 2]
* **spawn_probability**: [1.0, 1.0]
* **price**: 220
* **mana**: 30
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/luminous_drill.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile_trigger_timer("data/entities/projectiles/deck/luminous_drill.xml",4,1)
      c.fire_rate_wait = c.fire_rate_wait - 35
      current_reload_time = current_reload_time - ACTION_DRAW_RELOAD_TIME_INCREASE - 10 -- this is a hack to get the digger reload time back to 0
    end,
```

## ![Magic arrow](images/BULLET.png)Magic arrow (BULLET)

* **description**: A handy magical arrow
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [1, 2, 3, 4, 5]
* **spawn_probability**: [1.0, 1.0, 1.0, 1.0, 1.0]
* **price**: 150
* **mana**: 20
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/bullet.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/bullet.xml")
      c.fire_rate_wait = c.fire_rate_wait + 4
      c.screenshake = c.screenshake + 2
      c.spread_degrees = c.spread_degrees + 2.0
      c.damage_critical_chance = c.damage_critical_chance + 5
      shot_effects.recoil_knockback = shot_effects.recoil_knockback + 23.0
    end,
```

## ![Magic arrow with timer](images/BULLET_TIMER.png)Magic arrow with timer (BULLET_TIMER)

* **description**: A magical arrow that casts another spell after a timer runs out
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [2, 3, 4, 5, 6]
* **spawn_probability**: [0.5, 0.5, 0.5, 0.5, 0.5]
* **price**: 190
* **mana**: 35
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/bullet.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      c.fire_rate_wait = c.fire_rate_wait + 4
      c.screenshake = c.screenshake + 2
      c.spread_degrees = c.spread_degrees + 2.0
      c.damage_critical_chance = c.damage_critical_chance + 5
      add_projectile_trigger_timer("data/entities/projectiles/deck/bullet.xml", 10, 1)
      shot_effects.recoil_knockback = shot_effects.recoil_knockback + 23.0
    end,
```

## ![Magic arrow with trigger](images/BULLET_TRIGGER.png)Magic arrow with trigger (BULLET_TRIGGER)

* **description**: A magical arrow that casts another spell upon collision
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [1, 2, 3, 4, 5]
* **spawn_probability**: [0.5, 0.5, 0.5, 0.5, 0.5]
* **price**: 190
* **mana**: 35
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/bullet.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      c.fire_rate_wait = c.fire_rate_wait + 4
      c.screenshake = c.screenshake + 2
      c.spread_degrees = c.spread_degrees + 2.0
      c.damage_critical_chance = c.damage_critical_chance + 5
      add_projectile_trigger_hit_world("data/entities/projectiles/deck/bullet.xml", 1)
      shot_effects.recoil_knockback = shot_effects.recoil_knockback + 23.0
    end,
```

## ![Magic bolt](images/HEAVY_BULLET.png)Magic bolt (HEAVY_BULLET)

* **description**: A powerful magical bolt
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [1, 2, 3, 4, 5, 6]
* **spawn_probability**: [0.5, 1.0, 1.0, 1.0, 1.0, 1.0]
* **price**: 200
* **mana**: 30
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/bullet_heavy.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/bullet_heavy.xml")
      c.fire_rate_wait = c.fire_rate_wait + 7
      c.screenshake = c.screenshake + 2.5
      c.spread_degrees = c.spread_degrees + 5.0
      c.damage_critical_chance = c.damage_critical_chance + 5
      shot_effects.recoil_knockback = shot_effects.recoil_knockback + 50.0
    end,
```

## ![Magic bolt with timer](images/HEAVY_BULLET_TIMER.png)Magic bolt with timer (HEAVY_BULLET_TIMER)

* **description**: A powerful magical bolt that casts another spell after a timer runs out
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [2, 3, 4, 5, 6]
* **spawn_probability**: [0.5, 0.5, 0.5, 0.5, 0.5]
* **price**: 240
* **mana**: 40
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/bullet_heavy.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      c.fire_rate_wait = c.fire_rate_wait + 7
      c.screenshake = c.screenshake + 2.5
      c.spread_degrees = c.spread_degrees + 5.0
      c.damage_critical_chance = c.damage_critical_chance + 5
      add_projectile_trigger_timer("data/entities/projectiles/deck/bullet_heavy.xml", 10, 1)
      shot_effects.recoil_knockback = shot_effects.recoil_knockback + 50.0
    end,
```

## ![Magic bolt with trigger](images/HEAVY_BULLET_TRIGGER.png)Magic bolt with trigger (HEAVY_BULLET_TRIGGER)

* **description**: A powerful magical bolt that casts another spell upon collision
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [2, 3, 4, 5, 6]
* **spawn_probability**: [0.5, 0.5, 0.5, 0.5, 0.5]
* **price**: 240
* **mana**: 40
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/bullet_heavy.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      c.fire_rate_wait = c.fire_rate_wait + 7
      c.screenshake = c.screenshake + 2.5
      c.spread_degrees = c.spread_degrees + 5.0
      c.damage_critical_chance = c.damage_critical_chance + 5
      add_projectile_trigger_hit_world("data/entities/projectiles/deck/bullet_heavy.xml", 1)
      shot_effects.recoil_knockback = shot_effects.recoil_knockback + 50.0
    end,
```

## ![Magic guard](images/MAGIC_SHIELD.png)Magic guard (MAGIC_SHIELD)

* **description**: Four guarding lights rotate around you for a time
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [2, 4, 5, 6]
* **spawn_probability**: [0.5, 0.5, 1.0, 1.0]
* **price**: 100
* **mana**: 40
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/magic_shield_start.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/magic_shield_start.xml")
      c.fire_rate_wait = c.fire_rate_wait + 20
    end,
```

## ![Magic missile](images/ROCKET.png)Magic missile (ROCKET)

* **description**: A fiery, explosive projectile
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [1, 2, 3, 4, 5]
* **spawn_probability**: [1.0, 1.0, 1.0, 0.5, 0.5]
* **price**: 220
* **mana**: 70
* **max_uses**: 10
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/rocket.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/rocket.xml")
      c.fire_rate_wait = c.fire_rate_wait + 60
      c.ragdoll_fx = 2
      shot_effects.recoil_knockback = 120.0
    end,
```

## ![Magical Explosion](images/EXPLOSION_LIGHT.png)Magical Explosion (EXPLOSION_LIGHT)

* **description**: A large explosion that doesn't damage the ground
* **type**: ACTION_TYPE_STATIC_PROJECTILE
* **spawn_level**: [2, 3, 5, 6]
* **spawn_probability**: [0.5, 1.0, 1.0, 1.0]
* **price**: 160
* **mana**: 80
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: true
* **related_projectiles**: {"data/entities/projectiles/deck/explosion_light.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/explosion_light.xml")
      c.fire_rate_wait = c.fire_rate_wait + 3
      c.screenshake = c.screenshake + 2.5
    end,
```

## ![Mana To Damage](images/DAMAGE_FOREVER.png)Mana To Damage (DAMAGE_FOREVER)

* **description**: If the wand has more than 50 mana, all mana over that is converted into additional damage
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4, 5, 6]
* **spawn_probability**: [0.2, 0.4, 0.6, 0.4, 0.2]
* **price**: 240
* **mana**: 0
* **max_uses**: 20
* **never_unlimited**: true
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/particles/tinyspark_red.xml" }
* **action**:

```lua
 function()
      if ( mana > 50 ) then
        local manaforspell = mana - 50
        c.damage_projectile_add = c.damage_projectile_add + 0.025 * manaforspell
        mana = 50
      end
      
      c.gore_particles    = c.gore_particles + 15
      c.fire_rate_wait    = c.fire_rate_wait + 15
      current_reload_time = current_reload_time + 10
      c.extra_entities    = c.extra_entities .. "data/entities/particles/tinyspark_red.xml,"
      shot_effects.recoil_knockback = shot_effects.recoil_knockback + 10.0
      draw_actions( 1, true )
    end,
```

## ![Matosade](images/WORM_RAIN.png)Matosade (WORM_RAIN)

* **description**: Alea iacta est
* **type**: ACTION_TYPE_STATIC_PROJECTILE
* **spawn_level**: [6, 10]
* **spawn_probability**: [0.1, 1.0]
* **price**: 300
* **mana**: 225
* **max_uses**: 2
* **never_unlimited**: true
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/animals/worm_big.xml"}
* **spawn_requires_flag**: card_unlocked_rain
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/worm_rain.xml")
      c.fire_rate_wait = c.fire_rate_wait + 100
      current_reload_time = current_reload_time + 60
    end,
```

## ![Matter eater](images/MATTER_EATER.png)Matter eater (MATTER_EATER)

* **description**: Makes a projectile eat the environment as it flies
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 2, 4, 5, 10]
* **spawn_probability**: [0.1, 1.0, 0.1, 0.1, 0.2]
* **price**: 280
* **mana**: 120
* **max_uses**: 10
* **never_unlimited**: true
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/matter_eater.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/matter_eater.xml,"
      draw_actions( 1, true )
    end,
```

## ![Meteor](images/METEOR.png)Meteor (METEOR)

* **description**: A destructive projectile from the skies!
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [4, 5, 6, 10]
* **spawn_probability**: [0.6, 0.6, 0.6, 0.5]
* **price**: 280
* **mana**: 150
* **max_uses**: 10
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/meteor.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/meteor.xml")
    end,
```

## ![Meteorisade](images/METEOR_RAIN.png)Meteorisade (METEOR_RAIN)

* **description**: Alea iacta est
* **type**: ACTION_TYPE_STATIC_PROJECTILE
* **spawn_level**: [6, 10]
* **spawn_probability**: [0.1, 1.0]
* **price**: 300
* **mana**: 225
* **max_uses**: 2
* **never_unlimited**: true
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: { "data/entities/projectiles/deck/meteor_rain_meteor.xml" }
* **spawn_requires_flag**: card_unlocked_rain
* **related_extra_entities**: { "data/entities/misc/effect_meteor_rain.xml" }
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/meteor_rain.xml")
      c.extra_entities = c.extra_entities .. "data/entities/misc/effect_meteor_rain.xml,"
      c.fire_rate_wait = c.fire_rate_wait + 100
      current_reload_time = current_reload_time + 60
    end,
```

## ![Mu](images/MU.png)Mu (MU)

* **description**: Every modifier-type spell in the current wand is applied to a projectile
* **type**: ACTION_TYPE_OTHER
* **spawn_level**: [5, 6, 10]
* **spawn_probability**: [0.1, 0.1, 1.0]
* **price**: 500
* **mana**: 120
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: true
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_duplicate
* **related_extra_entities**: 
* **action**:

```lua
 function( recursion_level, iteration )
      c.fire_rate_wait = c.fire_rate_wait + 50
      
      local firerate = c.fire_rate_wait
      local reload = current_reload_time
      local mana_ = mana
      
      if ( discarded ~= nil ) then
        for i,data in ipairs( discarded ) do
          local rec = check_recursion( data, recursion_level )
          if ( data ~= nil ) and ( data.type == 2 ) and ( rec > -1 ) then
            dont_draw_actions = true
            data.action( rec )
            dont_draw_actions = false
          end
        end
      end
      
      if ( hand ~= nil ) then
        for i,data in ipairs( hand ) do
          local rec = check_recursion( data, recursion_level )
          if ( data ~= nil ) and ( data.type == 2 ) and ( rec > -1 ) then
            dont_draw_actions = true
            data.action( rec )
            dont_draw_actions = false
          end
        end
      end
      
      if ( deck ~= nil ) then
        for i,data in ipairs( deck ) do
          local rec = check_recursion( data, recursion_level )
          if ( data ~= nil ) and ( data.type == 2 ) and ( rec > -1 ) then
            dont_draw_actions = true
            data.action( rec )
            dont_draw_actions = false
          end
        end
      end
      
      c.fire_rate_wait = firerate
      current_reload_time = reload
      mana = mana_
      
      draw_actions( 1, true )
    end,
```

## ![Myriad Spell](images/BURST_X.png)Myriad Spell (BURST_X)

* **description**: Simultaneously casts as many spells as you have left uncast in your wand
* **type**: ACTION_TYPE_DRAW_MANY
* **spawn_level**: [5, 6, 10]
* **spawn_probability**: [0.1, 0.1, 0.5]
* **price**: 500
* **mana**: 50
* **max_uses**: 30
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_musicbox
* **related_extra_entities**: 
* **action**:

```lua
 function()
      if ( #deck > 0 ) then
        draw_actions( #deck, true )
      end
    end,
```

## ![Necromancy](images/NECROMANCY.png)Necromancy (NECROMANCY)

* **description**: Makes corpses of creatures killed by a projectile rise to your aid
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4, 5]
* **spawn_probability**: [0.6, 0.6, 0.6, 0.6]
* **price**: 80
* **mana**: 20
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_necromancy
* **related_extra_entities**: 
* **action**:

```lua
 function()
      c.game_effect_entities = c.game_effect_entities .. "data/entities/misc/effect_necromancy.xml,"
      c.fire_rate_wait = c.fire_rate_wait + 10
      draw_actions( 1, true )
    end,
```

## ![Nolla](images/NOLLA.png)Nolla (NOLLA)

* **description**: The duration of a projectile is set to zero
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 4, 5, 6, 10]
* **spawn_probability**: [0.2, 0.2, 0.5, 0.5, 1.0]
* **price**: 50
* **mana**: 1
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_pyramid
* **related_extra_entities**: { "data/entities/misc/nolla.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/nolla.xml,"
      c.fire_rate_wait = c.fire_rate_wait - 15
      draw_actions( 1, true )
    end,
```

## ![Nuke](images/NUKE.png)Nuke (NUKE)

* **description**: Take cover!
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [1, 5, 6, 10]
* **spawn_probability**: [0.3, 1.0, 1.0, 0.2]
* **price**: 400
* **mana**: 200
* **max_uses**: 1
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/nuke.xml"}
* **spawn_requires_flag**: card_unlocked_nuke
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/nuke.xml")
      c.fire_rate_wait = 20
      c.speed_multiplier = c.speed_multiplier * 0.75
      c.material = "fire"
      c.material_amount = c.material_amount + 60
      c.ragdoll_fx = 2
      c.gore_particles = c.gore_particles + 10
      c.screenshake = c.screenshake + 10.5
      current_reload_time = current_reload_time + 600
      shot_effects.recoil_knockback = shot_effects.recoil_knockback + 300.0
      
      if ( c.speed_multiplier >= 20 ) then
        c.speed_multiplier = math.min( c.speed_multiplier, 20 )
      elseif ( c.speed_multiplier < 0 ) then
        c.speed_multiplier = 0
      end
    end,
```

## ![Nuke Orbit](images/ORBIT_NUKES.png)Nuke Orbit (ORBIT_NUKES)

* **description**: Makes four??? nukes(?!) rotate around a projectile
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 4, 5, 6, 10]
* **spawn_probability**: [0.1, 0.1, 0.1, 0.2, 1.0]
* **price**: 400
* **mana**: 250
* **max_uses**: 3
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: true
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_dragon
* **related_extra_entities**: { "data/entities/misc/orbit_nukes.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/orbit_nukes.xml,"
      draw_actions( 1, true )
    end,
```

## ![Ocarina - note A](images/OCARINA_A.png)Ocarina - note A (OCARINA_A)

* **description**: Music for your ears!
* **type**: ACTION_TYPE_OTHER
* **spawn_level**: [10]
* **spawn_probability**: [0.0]
* **price**: 10
* **mana**: 1
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/ocarina/ocarina_a.xml"}
* **spawn_requires_flag**: card_unlocked_ocarina
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/ocarina/ocarina_a.xml")
      c.fire_rate_wait = c.fire_rate_wait + 15
    end,
```

## ![Ocarina - note A2](images/OCARINA_A2.png)Ocarina - note A2 (OCARINA_A2)

* **description**: Music for your ears!
* **type**: ACTION_TYPE_OTHER
* **spawn_level**: [10]
* **spawn_probability**: [0.0]
* **price**: 10
* **mana**: 1
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/ocarina/ocarina_a2.xml"}
* **spawn_requires_flag**: card_unlocked_ocarina
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/ocarina/ocarina_a2.xml")
      c.fire_rate_wait = c.fire_rate_wait + 15
    end,
```

## ![Ocarina - note B](images/OCARINA_B.png)Ocarina - note B (OCARINA_B)

* **description**: Music for your ears!
* **type**: ACTION_TYPE_OTHER
* **spawn_level**: [10]
* **spawn_probability**: [0.0]
* **price**: 10
* **mana**: 1
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/ocarina/ocarina_b.xml"}
* **spawn_requires_flag**: card_unlocked_ocarina
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/ocarina/ocarina_b.xml")
      c.fire_rate_wait = c.fire_rate_wait + 15
    end,
```

## ![Ocarina - note C](images/OCARINA_C.png)Ocarina - note C (OCARINA_C)

* **description**: Music for your ears!
* **type**: ACTION_TYPE_OTHER
* **spawn_level**: [10]
* **spawn_probability**: [0.0]
* **price**: 10
* **mana**: 1
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/ocarina/ocarina_c.xml"}
* **spawn_requires_flag**: card_unlocked_ocarina
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/ocarina/ocarina_c.xml")
      c.fire_rate_wait = c.fire_rate_wait + 15
    end,
```

## ![Ocarina - note D](images/OCARINA_D.png)Ocarina - note D (OCARINA_D)

* **description**: Music for your ears!
* **type**: ACTION_TYPE_OTHER
* **spawn_level**: [10]
* **spawn_probability**: [0.0]
* **price**: 10
* **mana**: 1
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/ocarina/ocarina_d.xml"}
* **spawn_requires_flag**: card_unlocked_ocarina
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/ocarina/ocarina_d.xml")
      c.fire_rate_wait = c.fire_rate_wait + 15
    end,
```

## ![Ocarina - note E](images/OCARINA_E.png)Ocarina - note E (OCARINA_E)

* **description**: Music for your ears!
* **type**: ACTION_TYPE_OTHER
* **spawn_level**: [10]
* **spawn_probability**: [0.0]
* **price**: 10
* **mana**: 1
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/ocarina/ocarina_e.xml"}
* **spawn_requires_flag**: card_unlocked_ocarina
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/ocarina/ocarina_e.xml")
      c.fire_rate_wait = c.fire_rate_wait + 15
    end,
```

## ![Ocarina - note F](images/OCARINA_F.png)Ocarina - note F (OCARINA_F)

* **description**: Music for your ears!
* **type**: ACTION_TYPE_OTHER
* **spawn_level**: [10]
* **spawn_probability**: [0.0]
* **price**: 10
* **mana**: 1
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/ocarina/ocarina_f.xml"}
* **spawn_requires_flag**: card_unlocked_ocarina
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/ocarina/ocarina_f.xml")
      c.fire_rate_wait = c.fire_rate_wait + 15
    end,
```

## ![Ocarina - note G#](images/OCARINA_GSHARP.png)Ocarina - note G# (OCARINA_GSHARP)

* **description**: Music for your ears!
* **type**: ACTION_TYPE_OTHER
* **spawn_level**: [10]
* **spawn_probability**: [0.0]
* **price**: 10
* **mana**: 1
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/ocarina/ocarina_gsharp.xml"}
* **spawn_requires_flag**: card_unlocked_ocarina
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/ocarina/ocarina_gsharp.xml")
      c.fire_rate_wait = c.fire_rate_wait + 15
    end,
```

## ![Octagonal bolt bundle](images/ROCKET_OCTAGON.png)Octagonal bolt bundle (ROCKET_OCTAGON)

* **description**: Makes a projectile launch 8 magical bolts if it moves slowly enough
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4]
* **spawn_probability**: [0.5, 0.5, 0.5]
* **price**: 200
* **mana**: 100
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/rocket_octagon.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/rocket_octagon.xml,"
      c.fire_rate_wait = c.fire_rate_wait + 20
      draw_actions( 1, true )
    end,
```

## ![Octuple spell](images/BURST_8.png)Octuple spell (BURST_8)

* **description**: Simultaneously cast 8 spells
* **type**: ACTION_TYPE_DRAW_MANY
* **spawn_level**: [5, 6, 10]
* **spawn_probability**: [0.1, 0.1, 0.5]
* **price**: 300
* **mana**: 30
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_musicbox
* **related_extra_entities**: 
* **action**:

```lua
 function()
      draw_actions( 8, true )
    end,
```

## ![Odd Firebolt](images/GRENADE_ANTI.png)Odd Firebolt (GRENADE_ANTI)

* **description**: A somewhat peculiar bouncy, explosive bolt
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [0, 1, 2, 3, 4, 5]
* **spawn_probability**: [0.4, 0.4, 0.4, 0.4, 0.4, 0.4]
* **price**: 170
* **mana**: 50
* **max_uses**: 25
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/grenade_anti.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/grenade_anti.xml")
      c.fire_rate_wait = c.fire_rate_wait + 30
      c.screenshake = c.screenshake + 4.0
      c.child_speed_multiplier = c.child_speed_multiplier * 0.75
      shot_effects.recoil_knockback = 80.0
    end,
```

## ![Oil](images/MATERIAL_OIL.png)Oil (MATERIAL_OIL)

* **description**: Transmute drops of oil from nothing
* **type**: ACTION_TYPE_MATERIAL
* **spawn_level**: [1, 2, 3, 4, 5]
* **spawn_probability**: [0.4, 0.4, 0.4, 0.4, 0.4]
* **price**: 140
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/material_oil.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/material_oil.xml")
      c.game_effect_entities = c.game_effect_entities .. "data/entities/misc/effect_apply_oiled.xml,"
      c.fire_rate_wait = c.fire_rate_wait - 15
      current_reload_time = current_reload_time - ACTION_DRAW_RELOAD_TIME_INCREASE - 10 -- this is a hack to get the cement reload time back to 0
    end,
```

## ![Oil cloud](images/CLOUD_OIL.png)Oil cloud (CLOUD_OIL)

* **description**: Creates a rain of oil
* **type**: ACTION_TYPE_STATIC_PROJECTILE
* **spawn_level**: [0, 1, 2, 3, 4, 5]
* **spawn_probability**: [0.4, 0.4, 0.4, 0.4, 0.4, 0.4]
* **price**: 100
* **mana**: 20
* **max_uses**: 15
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/cloud_oil.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/cloud_oil.xml")
      c.fire_rate_wait = c.fire_rate_wait + 15
    end,
```

## ![Oil trail](images/OIL_TRAIL.png)Oil trail (OIL_TRAIL)

* **description**: Gives a projectile a trail of oil
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4]
* **spawn_probability**: [0.3, 0.3, 0.3]
* **price**: 160
* **mana**: 10
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      c.game_effect_entities = c.game_effect_entities .. "data/entities/misc/effect_apply_oiled.xml,"
      c.trail_material = c.trail_material .. "oil,"
      c.trail_material_amount = c.trail_material_amount + 20
      draw_actions( 1, true )
    end,
```

## ![Omega](images/OMEGA.png)Omega (OMEGA)

* **description**: Casts copies of every spell in your wand
* **type**: ACTION_TYPE_OTHER
* **spawn_level**: [5, 6, 10]
* **spawn_probability**: [0.1, 0.1, 1.0]
* **price**: 600
* **mana**: 300
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: true
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_duplicate
* **related_extra_entities**: 
* **action**:

```lua
 function( recursion_level, iteration )
      c.fire_rate_wait = c.fire_rate_wait + 50
      
      if ( discarded ~= nil ) then
        for i,data in ipairs( discarded ) do
          local rec = check_recursion( data, recursion_level )
          if ( data ~= nil ) and ( rec > -1 ) and ( data.id ~= "RESET" ) then
            dont_draw_actions = true
            data.action( rec )
            dont_draw_actions = false
          end
        end
      end
      
      if ( hand ~= nil ) then
        for i,data in ipairs( hand ) do
          local rec = check_recursion( data, recursion_level )
          if ( data ~= nil ) and ( ( data.recursive == nil ) or ( data.recursive == false ) ) then
            dont_draw_actions = true
            data.action( rec )
            dont_draw_actions = false
          end
        end
      end
      
      if ( deck ~= nil ) then
        for i,data in ipairs( deck ) do
          local rec = check_recursion( data, recursion_level )
          if ( data ~= nil ) and ( rec > -1 ) and ( data.id ~= "RESET" ) then
            dont_draw_actions = true
            data.action( rec )
            dont_draw_actions = false
          end
        end
      end
    end,
```

## ![Omega Black Hole](images/BLACK_HOLE_GIGA.png)Omega Black Hole (BLACK_HOLE_GIGA)

* **description**: Even light dies eventually...
* **type**: ACTION_TYPE_STATIC_PROJECTILE
* **spawn_level**: [10]
* **spawn_probability**: [1.0]
* **price**: 600
* **mana**: 500
* **max_uses**: 6
* **never_unlimited**: true
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/black_hole_giga.xml"}
* **spawn_requires_flag**: card_unlocked_black_hole
* **related_extra_entities**: 
* **action**:

```lua
 function()
      local black_holes = EntityGetWithTag( "black_hole_giga" )
      
      if ( #black_holes < 3 ) then
        add_projectile("data/entities/projectiles/deck/black_hole_giga.xml")
        c.fire_rate_wait = c.fire_rate_wait + 120
        current_reload_time = current_reload_time + 100
        c.screenshake = c.screenshake + 40
      end
    end,
```

## ![Orange Glimmer](images/COLOUR_ORANGE.png)Orange Glimmer (COLOUR_ORANGE)

* **description**: Gives a projectile a orange sparkly trail
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4]
* **spawn_probability**: [0.1, 0.1, 0.1]
* **price**: 40
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_paint
* **related_extra_entities**: { "data/entities/particles/tinyspark_red.xml", "data/entities/misc/colour_orange.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/particles/tinyspark_red.xml,data/entities/misc/colour_orange.xml,"
      c.fire_rate_wait = c.fire_rate_wait - 8
      c.screenshake = c.screenshake - 2.5
      if ( c.screenshake < 0 ) then
        c.screenshake = 0
      end
      draw_actions( 1, true )
    end,
```

## ![Orbit Larpa](images/ORBIT_LARPA.png)Orbit Larpa (ORBIT_LARPA)

* **description**: Makes four copies of a projectile rotate around it
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [3, 4, 6, 10]
* **spawn_probability**: [0.2, 0.2, 0.8, 0.1]
* **price**: 240
* **mana**: 90
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_dragon
* **related_extra_entities**: { "data/entities/misc/orbit_larpa.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/orbit_larpa.xml,"
      draw_actions( 1, true )
    end,
```

## ![Orbiting Arc](images/ORBIT_SHOT.png)Orbiting Arc (ORBIT_SHOT)

* **description**: A projectile orbits the point of its origin
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 2, 3, 4]
* **spawn_probability**: [0.2, 0.3, 0.4, 0.1]
* **price**: 30
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/spiraling_shot.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/spiraling_shot.xml,"
      draw_actions( 1, true )
      c.damage_projectile_add = c.damage_projectile_add + 0.1
      c.fire_rate_wait    = c.fire_rate_wait - 6
      c.lifetime_add     = c.lifetime_add + 25
    end,
```

## ![Path of dark flame](images/DARKFLAME.png)Path of dark flame (DARKFLAME)

* **description**: A trail of dark, deadly flames
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [3, 5, 6]
* **spawn_probability**: [1.0, 1.0, 1.0]
* **price**: 180
* **mana**: 90
* **max_uses**: 60
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/darkflame.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/darkflame.xml")
      c.fire_rate_wait = c.fire_rate_wait + 20
    end,
```

## ![Personal fireball thrower](images/FIREBALL_RAY_ENEMY.png)Personal fireball thrower (FIREBALL_RAY_ENEMY)

* **description**: Makes a projectile turn the creatures it hits into living fireball throwers
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 2, 4, 5]
* **spawn_probability**: [0.6, 0.6, 0.4, 0.4]
* **price**: 100
* **mana**: 90
* **max_uses**: 20
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/hitfx_fireball_ray_enemy.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/hitfx_fireball_ray_enemy.xml,"
      draw_actions( 1, true )
    end,
```

## ![Personal gravity field](images/GRAVITY_FIELD_ENEMY.png)Personal gravity field (GRAVITY_FIELD_ENEMY)

* **description**: Makes creatures hit by a projectile gain a temporary gravity well that draws projectiles in
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 2, 4, 5]
* **spawn_probability**: [0.6, 0.6, 0.4, 0.4]
* **price**: 250
* **mana**: 110
* **max_uses**: 20
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/hitfx_gravity_field_enemy.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/hitfx_gravity_field_enemy.xml,"
      draw_actions( 1, true )
    end,
```

## ![Personal lightning caster](images/LIGHTNING_RAY_ENEMY.png)Personal lightning caster (LIGHTNING_RAY_ENEMY)

* **description**: Makes a projectile turn the creatures it hits into living thunderstorms
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 2, 3, 4, 5]
* **spawn_probability**: [0.0, 0.0, 0.4, 0.4, 0.4]
* **price**: 150
* **mana**: 90
* **max_uses**: 20
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/hitfx_lightning_ray_enemy.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/hitfx_lightning_ray_enemy.xml,"
      draw_actions( 1, true )
    end,
```

## ![Personal tentacler](images/TENTACLE_RAY_ENEMY.png)Personal tentacler (TENTACLE_RAY_ENEMY)

* **description**: Makes creatures hit by a projectile grow tentacles in a chaotic manner
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 2, 3, 4, 5]
* **spawn_probability**: [0.0, 0.0, 0.4, 0.4, 0.4]
* **price**: 150
* **mana**: 90
* **max_uses**: 20
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/hitfx_tentacle_ray_enemy.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/hitfx_tentacle_ray_enemy.xml,"
      draw_actions( 1, true )
    end,
```

## ![Petrify](images/HITFX_PETRIFY.png)Petrify (HITFX_PETRIFY)

* **description**: Turns a wounded enemy into stone
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 5, 6]
* **spawn_probability**: [0.2, 0.2, 0.2, 0.2]
* **price**: 140
* **mana**: 10
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/hitfx_petrify.xml,"
      draw_actions( 1, true )
    end,
```

## ![Phasing Arc](images/PHASING_ARC.png)Phasing Arc (PHASING_ARC)

* **description**: Makes a projectile fly much slower, but teleport short distances over its flight
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4, 5]
* **spawn_probability**: [0.2, 0.3, 0.6, 0.1]
* **price**: 170
* **mana**: 2
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/phasing_arc.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/phasing_arc.xml,"
      draw_actions( 1, true )
      c.fire_rate_wait    = c.fire_rate_wait - 12
      c.lifetime_add     = c.lifetime_add + 80
      c.speed_multiplier  = c.speed_multiplier * 0.33
      c.child_speed_multiplier  = c.child_speed_multiplier * 0.33
      
      if ( c.speed_multiplier >= 20 ) then
        c.speed_multiplier = math.min( c.speed_multiplier, 20 )
      elseif ( c.speed_multiplier < 0 ) then
        c.speed_multiplier = 0
      end
    end,
```

## ![Phi](images/PHI.png)Phi (PHI)

* **description**: Casts a copy of every projectile-type spell in the current wand
* **type**: ACTION_TYPE_OTHER
* **spawn_level**: [5, 6, 10]
* **spawn_probability**: [0.1, 0.1, 1.0]
* **price**: 500
* **mana**: 120
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: true
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_duplicate
* **related_extra_entities**: 
* **action**:

```lua
 function( recursion_level, iteration )
      c.fire_rate_wait = c.fire_rate_wait + 50
      
      local firerate = c.fire_rate_wait
      local reload = current_reload_time
      local mana_ = mana
      
      if ( discarded ~= nil ) then
        for i,data in ipairs( discarded ) do
          local rec = check_recursion( data, recursion_level )
          if ( data ~= nil ) and ( data.type == 0 ) and ( rec > -1 ) then
            dont_draw_actions = true
            data.action( rec )
            dont_draw_actions = false
          end
        end
      end
      
      if ( hand ~= nil ) then
        for i,data in ipairs( hand ) do
          local rec = check_recursion( data, recursion_level )
          if ( data ~= nil ) and ( data.type == 0 ) and ( rec > -1 ) then
            dont_draw_actions = true
            data.action( rec )
            dont_draw_actions = false
          end
        end
      end
      
      if ( deck ~= nil ) then
        for i,data in ipairs( deck ) do
          local rec = check_recursion( data, recursion_level )
          if ( data ~= nil ) and ( data.type == 0 ) and ( rec > -1 ) then
            dont_draw_actions = true
            data.action( rec )
            dont_draw_actions = false
          end
        end
      end
      
      c.fire_rate_wait = firerate
      current_reload_time = reload
      mana = mana_
    end,
```

## ![Piercing shot](images/PIERCING_SHOT.png)Piercing shot (PIERCING_SHOT)

* **description**: Makes a projectile fly through enemies, but harmful to the caster
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4, 5, 6]
* **spawn_probability**: [0.6, 0.6, 0.6, 0.6, 0.6]
* **price**: 190
* **mana**: 140
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/piercing_shot.xml" }
* **action**:

```lua
 function()
      c.damage_projectile_add = c.damage_projectile_add - 0.6
      c.extra_entities = c.extra_entities .. "data/entities/misc/piercing_shot.xml,"
      c.friendly_fire    = true
      draw_actions( 1, true )
    end,
```

## ![Ping-pong path](images/PINGPONG_PATH.png)Ping-pong path (PINGPONG_PATH)

* **description**: Makes a projectile fly back and forth
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 3, 5]
* **spawn_probability**: [0.4, 0.4, 0.4]
* **price**: 20
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/pingpong_path.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/pingpong_path.xml,"
      c.lifetime_add = c.lifetime_add + 25
      draw_actions( 1, true )
    end,
```

## ![Pinpoint of light](images/GLOWING_BOLT.png)Pinpoint of light (GLOWING_BOLT)

* **description**: An extremely concentrated point of light that explodes after a moment
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [3, 4, 5, 10]
* **spawn_probability**: [1.0, 1.0, 1.0, 0.1]
* **price**: 220
* **mana**: 65
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/glowing_bolt.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/glowing_bolt.xml")
      c.fire_rate_wait = c.fire_rate_wait + 40
      c.spread_degrees = c.spread_degrees + 6.0
    end,
```

## ![Plasma Beam Bounce](images/BOUNCE_LASER_EMITTER.png)Plasma Beam Bounce (BOUNCE_LASER_EMITTER)

* **description**: A projectile launches a plasma beam upon bouncing
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [3, 4, 5]
* **spawn_probability**: [0.4, 0.8, 0.4]
* **price**: 180
* **mana**: 40
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/bounce_laser_emitter.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/bounce_laser_emitter.xml,"
      c.bounces = c.bounces + 1
      c.fire_rate_wait = c.fire_rate_wait + 12
      shot_effects.recoil_knockback = shot_effects.recoil_knockback + 5.0
      draw_actions( 1, true )
    end,
```

## ![Plasma Beam Cross](images/LASER_EMITTER_FOUR.png)Plasma Beam Cross (LASER_EMITTER_FOUR)

* **description**: Four deadly plasma beams in a cross-shape. Look out, they can hurt you as well!
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [1, 2, 3, 4, 5]
* **spawn_probability**: [0.2, 1.0, 0.2, 0.5, 1.0]
* **price**: 200
* **mana**: 80
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/orb_laseremitter.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/orb_laseremitter_four.xml")
      shot_effects.recoil_knockback = shot_effects.recoil_knockback + 30.0
      c.fire_rate_wait = c.fire_rate_wait + 15
      c.game_effect_entities = c.game_effect_entities .. "data/entities/misc/effect_disintegrated.xml,"
    end,
```

## ![Plasma Beam Enhancer](images/LASER_EMITTER_WIDER.png)Plasma Beam Enhancer (LASER_EMITTER_WIDER)

* **description**: Makes plasma beam spell's beam wider
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4]
* **spawn_probability**: [0.3, 0.3, 0.3]
* **price**: 40
* **mana**: 10
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/laser_emitter_wider.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/laser_emitter_wider.xml,"
      draw_actions( 1, true )
    end,
```

## ![Plasma Beam Orbit](images/ORBIT_LASERS.png)Plasma Beam Orbit (ORBIT_LASERS)

* **description**: Makes four plasma beams rotate around a projectile
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 2, 4, 5, 10]
* **spawn_probability**: [0.2, 0.8, 0.4, 0.2, 0.2]
* **price**: 200
* **mana**: 100
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_dragon
* **related_extra_entities**: { "data/entities/misc/orbit_lasers.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/orbit_lasers.xml,"
      draw_actions( 1, true )
    end,
```

## ![Plasma Beam Thrower](images/LASER_EMITTER_RAY.png)Plasma Beam Thrower (LASER_EMITTER_RAY)

* **description**: A projectile fires plasma beams in all directions!
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 2, 3, 4, 5]
* **spawn_probability**: [0.0, 0.0, 0.4, 0.4, 0.4]
* **price**: 150
* **mana**: 110
* **max_uses**: 16
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/laser_emitter_ray.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/laser_emitter_ray.xml,"
      draw_actions( 1, true )
    end,
```

## ![Plasma Cutter](images/LASER_EMITTER_CUTTER.png)Plasma Cutter (LASER_EMITTER_CUTTER)

* **description**: A plasma beam specialized in cutting materials!
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [0, 1, 2, 3, 4]
* **spawn_probability**: [0.2, 0.3, 1.0, 0.5, 0.1]
* **price**: 120
* **mana**: 40
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/orb_laseremitter_cutter.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/orb_laseremitter_cutter.xml")
      current_reload_time = current_reload_time + 10
      c.game_effect_entities = c.game_effect_entities .. "data/entities/misc/effect_disintegrated.xml,"
    end,
```

## ![Plasma beam](images/LASER_EMITTER.png)Plasma beam (LASER_EMITTER)

* **description**: An instantaneous, dangerous beam of light
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [1, 2, 3, 4]
* **spawn_probability**: [0.2, 1.0, 1.0, 0.5]
* **price**: 180
* **mana**: 60
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/orb_laseremitter.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/orb_laseremitter.xml")
      shot_effects.recoil_knockback = shot_effects.recoil_knockback + 20.0
      c.fire_rate_wait = c.fire_rate_wait + 6
      c.game_effect_entities = c.game_effect_entities .. "data/entities/misc/effect_disintegrated.xml,"
    end,
```

## ![Poison Arc](images/ARC_POISON.png)Poison Arc (ARC_POISON)

* **description**: Creates arcs of poison between projectiles (requires 2 projectile spells)
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 2, 3, 4, 5]
* **spawn_probability**: [0.4, 0.4, 0.4, 0.4, 0.4]
* **price**: 160
* **mana**: 15
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/arc_poison.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/arc_poison.xml,"
      draw_actions( 1, true )
    end,
```

## ![Poison trail](images/POISON_TRAIL.png)Poison trail (POISON_TRAIL)

* **description**: Gives a projectile a trail of poison
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4]
* **spawn_probability**: [0.3, 0.3, 0.3]
* **price**: 160
* **mana**: 10
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      c.game_effect_entities = c.game_effect_entities .. "data/entities/misc/effect_apply_poison.xml,"
      c.trail_material = c.trail_material .. "poison,"
      c.trail_material_amount = c.trail_material_amount + 9
      draw_actions( 1, true )
    end,
```

## ![Pollen](images/POLLEN.png)Pollen (POLLEN)

* **description**: A small, floating projectile that homes towards nearby creatures
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [0, 1, 3, 4]
* **spawn_probability**: [0.6, 1.0, 1.0, 0.8]
* **price**: 110
* **mana**: 10
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/pollen.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/pollen.xml")
      c.fire_rate_wait = c.fire_rate_wait + 2
      c.spread_degrees = c.spread_degrees + 20
    end,
```

## ![Powder Vacuum Field](images/VACUUM_POWDER.png)Powder Vacuum Field (VACUUM_POWDER)

* **description**: Sucks powder-like materials nearby and releases them upon expiring
* **type**: ACTION_TYPE_STATIC_PROJECTILE
* **spawn_level**: [2, 3, 5, 6]
* **spawn_probability**: [0.3, 1.0, 0.3, 0.3]
* **price**: 150
* **mana**: 40
* **max_uses**: 20
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/vacuum_powder.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/vacuum_powder.xml")
      c.fire_rate_wait = c.fire_rate_wait + 10
    end,
```

## ![Prickly Spore Pod](images/SPORE_POD.png)Prickly Spore Pod (SPORE_POD)

* **description**: Summons a spore pod that attaches to a surface and then grows and explodes into spikes
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [1, 2, 3, 4, 5]
* **spawn_probability**: [0.8, 0.8, 0.8, 0.8, 0.8]
* **price**: 200
* **mana**: 20
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/spore_pod.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/spore_pod.xml")
      c.fire_rate_wait = c.fire_rate_wait + 40
      shot_effects.recoil_knockback = shot_effects.recoil_knockback + 30.0
    end,
```

## ![Projectile Area Teleport](images/HOMING_AREA.png)Projectile Area Teleport (HOMING_AREA)

* **description**: If a valid target appears somewhere in the proximity of a projectile, the projectile will teleport right on top of the target
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4, 5, 6]
* **spawn_probability**: [0.2, 0.4, 0.6, 0.7, 0.4]
* **price**: 175
* **mana**: 60
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/homing_area.xml", "data/entities/particles/tinyspark_white.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/homing_area.xml,data/entities/particles/tinyspark_white.xml,"
      c.fire_rate_wait    = c.fire_rate_wait + 8
      c.spread_degrees = c.spread_degrees + 6
      c.speed_multiplier  = c.speed_multiplier * 0.75
      
      if ( c.speed_multiplier >= 20 ) then
        c.speed_multiplier = math.min( c.speed_multiplier, 20 )
      elseif ( c.speed_multiplier < 0 ) then
        c.speed_multiplier = 0
      end
      
      draw_actions( 1, true )
    end,
```

## ![Projectile energy shield](images/ENERGY_SHIELD_SHOT.png)Projectile energy shield (ENERGY_SHIELD_SHOT)

* **description**: Gives a projectile a shield that deflects other projectiles
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4, 5, 6]
* **spawn_probability**: [0.3, 0.3, 0.3, 0.3, 0.3]
* **price**: 180
* **mana**: 5
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/energy_shield_shot.xml" }
* **action**:

```lua
 function()
      c.speed_multiplier = c.speed_multiplier * 0.4
      c.extra_entities = c.extra_entities .. "data/entities/misc/energy_shield_shot.xml,"
      
      if ( c.speed_multiplier >= 20 ) then
        c.speed_multiplier = math.min( c.speed_multiplier, 20 )
      elseif ( c.speed_multiplier < 0 ) then
        c.speed_multiplier = 0
      end
      
      draw_actions( 1, true )
    end,
```

## ![Projectile gravity field](images/PROJECTILE_GRAVITY_FIELD.png)Projectile gravity field (PROJECTILE_GRAVITY_FIELD)

* **description**: Projectiles caught within the field are attracted towards its center
* **type**: ACTION_TYPE_STATIC_PROJECTILE
* **spawn_level**: [2, 5, 6]
* **spawn_probability**: [0.3, 0.3, 0.3]
* **price**: 250
* **mana**: 120
* **max_uses**: 6
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/projectile_gravity_field.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/projectile_gravity_field.xml")
      c.fire_rate_wait = c.fire_rate_wait + 15
    end,
```

## ![Projectile thunder field](images/PROJECTILE_THUNDER_FIELD.png)Projectile thunder field (PROJECTILE_THUNDER_FIELD)

* **description**: Projectiles caught within the field transform into blasts of lightning
* **type**: ACTION_TYPE_STATIC_PROJECTILE
* **spawn_level**: [3, 4, 5, 6]
* **spawn_probability**: [0.3, 0.3, 0.3, 0.3]
* **price**: 300
* **mana**: 140
* **max_uses**: 6
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/projectile_thunder_field.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/projectile_thunder_field.xml")
      c.fire_rate_wait = c.fire_rate_wait + 15
    end,
```

## ![Projectile transmutation field](images/PROJECTILE_TRANSMUTATION_FIELD.png)Projectile transmutation field (PROJECTILE_TRANSMUTATION_FIELD)

* **description**: Projectiles caught within the field transform into harmless critters
* **type**: ACTION_TYPE_STATIC_PROJECTILE
* **spawn_level**: [2, 3, 4, 5, 6]
* **spawn_probability**: [0.3, 0.3, 0.3, 0.3, 0.3]
* **price**: 250
* **mana**: 120
* **max_uses**: 6
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/projectile_transmutation_field.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/projectile_transmutation_field.xml")
      c.fire_rate_wait = c.fire_rate_wait + 15
    end,
```

## ![Propane tank](images/PROPANE_TANK.png)Propane tank (PROPANE_TANK)

* **description**: Summons a propane tank. Be careful what you wish for.
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [0, 1, 2, 3, 4, 5, 6]
* **spawn_probability**: [0.0, 0.0, 1.0, 1.0, 1.0, 1.0, 1.0]
* **price**: 200
* **mana**: 75
* **max_uses**: 10
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/propane_tank.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/propane_tank.xml")
      c.fire_rate_wait = c.fire_rate_wait + 100
    end,
```

## ![Purple Glimmer](images/COLOUR_PURPLE.png)Purple Glimmer (COLOUR_PURPLE)

* **description**: Gives a projectile a purple sparkly trail
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4]
* **spawn_probability**: [0.1, 0.1, 0.1]
* **price**: 40
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_paint
* **related_extra_entities**: { "data/entities/particles/tinyspark_red.xml", "data/entities/misc/colour_purple.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/particles/tinyspark_red.xml,data/entities/misc/colour_purple.xml,"
      c.fire_rate_wait = c.fire_rate_wait - 8
      c.screenshake = c.screenshake - 2.5
      if ( c.screenshake < 0 ) then
        c.screenshake = 0
      end
      draw_actions( 1, true )
    end,
```

## ![Quadruple scatter spell](images/SCATTER_4.png)Quadruple scatter spell (SCATTER_4)

* **description**: Simultaneously casts 4 spells with low accuracy
* **type**: ACTION_TYPE_DRAW_MANY
* **spawn_level**: [1, 2, 3, 4, 5, 6]
* **spawn_probability**: [0.6, 0.6, 0.7, 0.8, 0.8, 0.8]
* **price**: 140
* **mana**: 2
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      draw_actions( 4, true )
      c.spread_degrees = c.spread_degrees + 40.0
    end,
```

## ![Quadruple spell](images/BURST_4.png)Quadruple spell (BURST_4)

* **description**: Simultaneously casts 4 spells
* **type**: ACTION_TYPE_DRAW_MANY
* **spawn_level**: [2, 3, 4, 5, 6]
* **spawn_probability**: [0.6, 0.6, 0.6, 0.6, 0.6]
* **price**: 180
* **mana**: 5
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      draw_actions( 4, true )
    end,
```

## ![Quantum Split](images/QUANTUM_SPLIT.png)Quantum Split (QUANTUM_SPLIT)

* **description**: Makes a projectile split into three projectiles whose existences are entangled
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4, 5, 6]
* **spawn_probability**: [0.5, 0.5, 0.5, 0.5, 1.0]
* **price**: 200
* **mana**: 10
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/quantum_split.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/quantum_split.xml,"
      c.fire_rate_wait = c.fire_rate_wait + 5
      draw_actions( 1, true )
    end,
```

## ![Rain cloud](images/CLOUD_WATER.png)Rain cloud (CLOUD_WATER)

* **description**: Creates a watery weather phenomenon
* **type**: ACTION_TYPE_STATIC_PROJECTILE
* **spawn_level**: [0, 1, 2, 3, 4, 5]
* **spawn_probability**: [0.4, 0.4, 0.4, 0.4, 0.4, 0.4]
* **price**: 140
* **mana**: 30
* **max_uses**: 10
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/cloud_water.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/cloud_water.xml")
      c.fire_rate_wait = c.fire_rate_wait + 15
    end,
```

## ![Rainbow Glimmer](images/COLOUR_RAINBOW.png)Rainbow Glimmer (COLOUR_RAINBOW)

* **description**: Gives a projectile a randomly colored sparkly trail
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4]
* **spawn_probability**: [0.1, 0.1, 0.1]
* **price**: 40
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_paint
* **related_extra_entities**: { "data/entities/particles/tinyspark_red.xml", "data/entities/misc/colour_rainbow.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/particles/tinyspark_red.xml,data/entities/misc/colour_rainbow.xml,"
      c.fire_rate_wait = c.fire_rate_wait - 8
      c.screenshake = c.screenshake - 2.5
      if ( c.screenshake < 0 ) then
        c.screenshake = 0
      end
      draw_actions( 1, true )
    end,
```

## ![Rainbow trail](images/RAINBOW_TRAIL.png)Rainbow trail (RAINBOW_TRAIL)

* **description**: Gives a projectile a trail of rainbow
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [10]
* **spawn_probability**: [0.0]
* **price**: 100
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_rainbow_trail
* **related_extra_entities**: 
* **action**:

```lua
 function()
      c.game_effect_entities = c.game_effect_entities .. "data/entities/misc/effect_rainbow_farts.xml,"
      c.trail_material = c.trail_material .. "material_rainbow,"
      c.trail_material_amount = c.trail_material_amount + 20
      draw_actions( 1, true )
    end,
```

## ![Random damage](images/DAMAGE_RANDOM.png)Random damage (DAMAGE_RANDOM)

* **description**: Randomly increases or lowers the damage done by projectiles
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [3, 4, 5]
* **spawn_probability**: [0.6, 0.6, 0.6]
* **price**: 200
* **mana**: 15
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_pyramid
* **related_extra_entities**: { "data/entities/particles/tinyspark_yellow.xml" }
* **action**:

```lua
 function()
      SetRandomSeed( GameGetFrameNum(), GameGetFrameNum() + 253 )
      local multiplier = 0
      multiplier = Random( -3, 4 ) * Random( 0, 2 )
      local result = 0
      result = c.damage_projectile_add + 0.4 * multiplier
      c.damage_projectile_add = result
      c.gore_particles    = c.gore_particles + 5 * multiplier
      c.fire_rate_wait    = c.fire_rate_wait + 5
      c.extra_entities    = c.extra_entities .. "data/entities/particles/tinyspark_yellow.xml,"
      shot_effects.recoil_knockback = shot_effects.recoil_knockback + 10.0 * multiplier
      draw_actions( 1, true )
    end,
```

## ![Random modifier spell](images/RANDOM_MODIFIER.png)Random modifier spell (RANDOM_MODIFIER)

* **description**: Casts one random modifier spell
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [4, 5, 6, 10]
* **spawn_probability**: [0.3, 0.1, 0.1, 0.5]
* **price**: 120
* **mana**: 20
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: true
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_pyramid
* **related_extra_entities**: 
* **action**:

```lua
 function( recursion_level, iteration )
      SetRandomSeed( GameGetFrameNum() + #deck, GameGetFrameNum() + 133 )
      local rnd = Random( 1, #actions )
      local data = actions[rnd]
      
      local safety = 0
      local rec = check_recursion( data, recursion_level )
      
      while ( safety < 100 ) and ( ( data.type ~= 2 ) or ( rec == -1 ) ) do
        rnd = Random( 1, #actions )
        data = actions[rnd]
        rec = check_recursion( data, recursion_level )
        
        safety = safety + 1
      end
      
      data.action( rec )
    end,
```

## ![Random projectile spell](images/RANDOM_PROJECTILE.png)Random projectile spell (RANDOM_PROJECTILE)

* **description**: Casts one random projectile spell
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [2, 4, 5, 6, 10]
* **spawn_probability**: [0.2, 0.4, 0.1, 0.1, 0.5]
* **price**: 150
* **mana**: 20
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: true
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_pyramid
* **related_extra_entities**: 
* **action**:

```lua
 function( recursion_level, iteration )
      SetRandomSeed( GameGetFrameNum() + #deck, GameGetFrameNum() + 203 )
      local rnd = Random( 1, #actions )
      local data = actions[rnd]
      
      local safety = 0
      local rec = check_recursion( data, recursion_level )
      
      while ( safety < 100 ) and ( ( data.type ~= 0 ) or ( rec == -1 ) ) do
        rnd = Random( 1, #actions )
        data = actions[rnd]
        rec = check_recursion( data, recursion_level )
        
        safety = safety + 1
      end
      
      data.action( rec )
    end,
```

## ![Random spell](images/RANDOM_SPELL.png)Random spell (RANDOM_SPELL)

* **description**: Casts a spell, any spell, at random!
* **type**: ACTION_TYPE_OTHER
* **spawn_level**: [3, 4, 5, 6, 10]
* **spawn_probability**: [0.2, 0.3, 0.1, 0.1, 0.5]
* **price**: 100
* **mana**: 5
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: true
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_pyramid
* **related_extra_entities**: 
* **action**:

```lua
 function( recursion_level, iteration )
      SetRandomSeed( GameGetFrameNum() + #deck, GameGetFrameNum() + 263 )
      local rnd = Random( 1, #actions )
      local data = actions[rnd]
      
      local safety = 0
      local rec = check_recursion( data, recursion_level )
      
      while ( safety < 100 ) and ( rec == -1 ) do
        rnd = Random( 1, #actions )
        data = actions[rnd]
        rec = check_recursion( data, recursion_level )
        
        safety = safety + 1
      end
      
      data.action( rec )
    end,
```

## ![Random static projectile spell](images/RANDOM_STATIC_PROJECTILE.png)Random static projectile spell (RANDOM_STATIC_PROJECTILE)

* **description**: Casts one random static projectile spell
* **type**: ACTION_TYPE_STATIC_PROJECTILE
* **spawn_level**: [3, 5, 6, 10]
* **spawn_probability**: [0.2, 0.1, 0.1, 0.5]
* **price**: 160
* **mana**: 20
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: true
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_pyramid
* **related_extra_entities**: 
* **action**:

```lua
 function( recursion_level, iteration )
      SetRandomSeed( GameGetFrameNum() + #deck, GameGetFrameNum() + 253 )
      local rnd = Random( 1, #actions )
      local data = actions[rnd]
      
      local safety = 0
      local rec = check_recursion( data, recursion_level )
      
      while ( safety < 100 ) and ( ( data.type ~= 1 ) or ( rec == -1 ) ) do
        rnd = Random( 1, #actions )
        data = actions[rnd]
        rec = check_recursion( data, recursion_level )
        
        safety = safety + 1
      end
      
      data.action( rec )
    end,
```

## ![Recoil](images/RECOIL.png)Recoil (RECOIL)

* **description**: Increases the recoil when casting spells
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 4]
* **spawn_probability**: [0.6, 0.6]
* **price**: 100
* **mana**: 5
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      shot_effects.recoil_knockback = shot_effects.recoil_knockback + 200.0
      draw_actions( 1, true )
    end,
```

## ![Recoil Damper](images/RECOIL_DAMPER.png)Recoil Damper (RECOIL_DAMPER)

* **description**: Reduces the recoil when casting spells
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [3, 6]
* **spawn_probability**: [0.6, 0.6]
* **price**: 100
* **mana**: 5
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      shot_effects.recoil_knockback = shot_effects.recoil_knockback - 200
      draw_actions( 1, true )
    end,
```

## ![Red Glimmer](images/COLOUR_RED.png)Red Glimmer (COLOUR_RED)

* **description**: Gives a projectile a red sparkly trail
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 2, 3, 4, 5, 6]
* **spawn_probability**: [0.2, 0.2, 0.2, 0.2, 0.2, 0.2]
* **price**: 40
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_paint
* **related_extra_entities**: { "data/entities/particles/tinyspark_red.xml", "data/entities/misc/colour_red.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/particles/tinyspark_red.xml,data/entities/misc/colour_red.xml,"
      c.fire_rate_wait = c.fire_rate_wait - 8
      c.screenshake = c.screenshake - 2.5
      if ( c.screenshake < 0 ) then
        c.screenshake = 0
      end
      draw_actions( 1, true )
    end,
```

## ![Reduce lifetime](images/LIFETIME_DOWN.png)Reduce lifetime (LIFETIME_DOWN)

* **description**: Reduces the lifetime of a spell
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [3, 4, 5, 6, 10]
* **spawn_probability**: [0.5, 0.5, 0.5, 0.5, 0.1]
* **price**: 90
* **mana**: 10
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      c.lifetime_add     = c.lifetime_add - 42
      c.fire_rate_wait = c.fire_rate_wait - 15
      draw_actions( 1, true )
    end,
```

## ![Reduce recharge time](images/RECHARGE.png)Reduce recharge time (RECHARGE)

* **description**: Reduces the time between spellcasts
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 2, 3, 4, 5, 6]
* **spawn_probability**: [1.0, 1.0, 1.0, 1.0, 1.0, 1.0]
* **price**: 200
* **mana**: 12
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      c.fire_rate_wait    = c.fire_rate_wait - 10
      current_reload_time = current_reload_time - 20
      draw_actions( 1, true )
    end,
```

## ![Reduce spread](images/SPREAD_REDUCE.png)Reduce spread (SPREAD_REDUCE)

* **description**: Reduces the spread of a spell
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 2, 3, 4, 5, 6]
* **spawn_probability**: [0.8, 0.8, 0.8, 0.8, 0.8, 0.8]
* **price**: 100
* **mana**: 1
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      c.spread_degrees = c.spread_degrees - 60.0
      draw_actions( 1, true )
    end,
```

## ![Remove Bounce](images/REMOVE_BOUNCE.png)Remove Bounce (REMOVE_BOUNCE)

* **description**: A normally bouncy projectile stops doing so
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4, 5, 6]
* **spawn_probability**: [0.2, 0.2, 1.0, 1.0, 1.0]
* **price**: 50
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/remove_bounce.xml,"
      c.bounces = 0
      draw_actions( 1, true )
    end,
```

## ![Remove Explosion](images/EXPLOSION_REMOVE.png)Remove Explosion (EXPLOSION_REMOVE)

* **description**: Makes a projectile no longer explode
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 4, 5, 6]
* **spawn_probability**: [0.2, 0.6, 0.7, 0.2]
* **price**: 50
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/explosion_remove.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/explosion_remove.xml,"
      c.fire_rate_wait = c.fire_rate_wait - 15
      c.explosion_radius = c.explosion_radius - 30.0
      c.damage_explosion_add = c.damage_explosion_add - 0.8
      draw_actions( 1, true )
    end,
```

## ![Requirement - Endpoint](images/IF_END.png)Requirement - Endpoint (IF_END)

* **description**: Any Requirement spells before this will skip all spells between them and this spell
* **type**: ACTION_TYPE_OTHER
* **spawn_level**: [10]
* **spawn_probability**: [1.0]
* **price**: 10
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_maths
* **related_extra_entities**: 
* **action**:

```lua
 function( recursion_level, iteration ) 
      draw_actions( 1, true )
    end,
```

## ![Requirement - Enemies](images/IF_ENEMY.png)Requirement - Enemies (IF_ENEMY)

* **description**: The next spell is skipped if there are less than 15 enemies nearby
* **type**: ACTION_TYPE_OTHER
* **spawn_level**: [10]
* **spawn_probability**: [1.0]
* **price**: 100
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_maths
* **related_extra_entities**: 
* **action**:

```lua
 function( recursion_level, iteration )
      local endpoint = -1
      local elsepoint = -1
      local x,y = EntityGetTransform( GetUpdatedEntityID() )
      local enemies = EntityGetInRadiusWithTag( x, y, 240, "homing_target" )
      
      local doskip = false
      if ( #enemies < 15 ) then
        doskip = true
      end
      
      if ( #deck > 0 ) then
        for i,v in ipairs( deck ) do
          if ( v ~= nil ) then
            if ( string.sub( v.id, 1, 3 ) == "IF_" ) and ( v.id ~= "IF_END" ) and ( v.id ~= "IF_ELSE" ) then
              endpoint = -1
              break
            end
            
            if ( v.id == "IF_ELSE" ) then
              endpoint = i
              elsepoint = i
            end
            
            if ( v.id == "IF_END" ) then
              endpoint = i
              break
            end
          end
        end
        
        local envelope_min = 1
        local envelope_max = 1
          
        if doskip then
          if ( elsepoint > 0 ) then
            envelope_max = elsepoint
          elseif ( endpoint > 0 ) then
            envelope_max = endpoint
          end
          
          for i=envelope_min,envelope_max do
            local v = deck[envelope_min]
            
            if ( v ~= nil ) then
              table.insert( discarded, v )
              table.remove( deck, envelope_min )
            end
          end
        else
          if ( elsepoint > 0 ) then
            envelope_min = elsepoint
            
            if ( endpoint > 0 ) then
              envelope_max = endpoint
            else
              envelope_max = #deck
            end
            
            for i=envelope_min,envelope_max do
              local v = deck[envelope_min]
              
              if ( v ~= nil ) then
                table.insert( discarded, v )
                table.remove( deck, envelope_min )
              end
            end
          end
        end
      end
      
      draw_actions( 1, true )
    end,
```

## ![Requirement - Every Other](images/IF_HALF.png)Requirement - Every Other (IF_HALF)

* **description**: The next spell is skipped every other time this spell is cast
* **type**: ACTION_TYPE_OTHER
* **spawn_level**: [10]
* **spawn_probability**: [1.0]
* **price**: 100
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_maths
* **related_extra_entities**: 
* **action**:

```lua
 function( recursion_level, iteration )
      local endpoint = -1
      local elsepoint = -1
      local doskip = false
      
      if ( reflecting == false ) then
        local status = tonumber( GlobalsGetValue( "GUN_ACTION_IF_HALF_STATUS", "0" ) ) or 0
        
        if ( status == 1 ) then
          doskip = true
        end
        
        status = 1 - status
        GlobalsSetValue( "GUN_ACTION_IF_HALF_STATUS", tostring( status ) )
      end
      
      if ( #deck > 0 ) then
        for i,v in ipairs( deck ) do
          if ( v ~= nil ) then
            if ( string.sub( v.id, 1, 3 ) == "IF_" ) and ( v.id ~= "IF_END" ) and ( v.id ~= "IF_ELSE" ) then
              endpoint = -1
              break
            end
            
            if ( v.id == "IF_ELSE" ) then
              endpoint = i
              elsepoint = i
            end
            
            if ( v.id == "IF_END" ) then
              endpoint = i
              break
            end
          end
        end
        
        local envelope_min = 1
        local envelope_max = 1
        
        if doskip then
          if ( elsepoint > 0 ) then
            envelope_max = elsepoint
          elseif ( endpoint > 0 ) then
            envelope_max = endpoint
          end
          
          for i=envelope_min,envelope_max do
            local v = deck[envelope_min]
          
            if ( v ~= nil ) then
              table.insert( discarded, v )
              table.remove( deck, envelope_min )
            end
          end
        else
          if ( elsepoint > 0 ) then
            envelope_min = elsepoint
            
            if ( endpoint > 0 ) then
              envelope_max = endpoint
            else
              envelope_max = #deck
            end
            
            for i=envelope_min,envelope_max do
              local v = deck[envelope_min]
              
              if ( v ~= nil ) then
                table.insert( discarded, v )
                table.remove( deck, envelope_min )
              end
            end
          end
        end
      end
      
      draw_actions( 1, true )
    end,
```

## ![Requirement - Low Health](images/IF_HP.png)Requirement - Low Health (IF_HP)

* **description**: The next spell is skipped if you have more than 25% health left
* **type**: ACTION_TYPE_OTHER
* **spawn_level**: [10]
* **spawn_probability**: [1.0]
* **price**: 100
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_maths
* **related_extra_entities**: 
* **action**:

```lua
 function( recursion_level, iteration )
      local endpoint = -1
      local elsepoint = -1
      local entity_id = GetUpdatedEntityID()
      local comp = EntityGetFirstComponent( entity_id, "DamageModelComponent" )
      local hpdiff = 1.0
      
      if ( comp ~= nil ) then
        local hp = ComponentGetValue2( comp, "hp" )
        local max_hp = ComponentGetValue2( comp, "max_hp" )
        
        hpdiff = hp / max_hp
      end
      
      local doskip = false
      if ( hpdiff > 0.25 ) then
        doskip = true
      end
      
      if ( #deck > 0 ) then
        for i,v in ipairs( deck ) do
          if ( v ~= nil ) then
            if ( string.sub( v.id, 1, 3 ) == "IF_" ) and ( v.id ~= "IF_END" ) and ( v.id ~= "IF_ELSE" ) then
              endpoint = -1
              break
            end
            
            if ( v.id == "IF_ELSE" ) then
              endpoint = i
              elsepoint = i
            end
            
            if ( v.id == "IF_END" ) then
              endpoint = i
              break
            end
          end
        end
        
        local envelope_min = 1
        local envelope_max = 1
          
        if doskip then
          if ( elsepoint > 0 ) then
            envelope_max = elsepoint
          elseif ( endpoint > 0 ) then
            envelope_max = endpoint
          end
          
          for i=envelope_min,envelope_max do
            local v = deck[envelope_min]
            
            if ( v ~= nil ) then
              table.insert( discarded, v )
              table.remove( deck, envelope_min )
            end
          end
        else
          if ( elsepoint > 0 ) then
            envelope_min = elsepoint
            
            if ( endpoint > 0 ) then
              envelope_max = endpoint
            else
              envelope_max = #deck
            end
            
            for i=envelope_min,envelope_max do
              local v = deck[envelope_min]
              
              if ( v ~= nil ) then
                table.insert( discarded, v )
                table.remove( deck, envelope_min )
              end
            end
          end
        end
      end
      
      draw_actions( 1, true )
    end,
```

## ![Requirement - Otherwise](images/IF_ELSE.png)Requirement - Otherwise (IF_ELSE)

* **description**: If a Requirement spell before this succeeds, the next spell is skipped
* **type**: ACTION_TYPE_OTHER
* **spawn_level**: [10]
* **spawn_probability**: [1.0]
* **price**: 10
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_maths
* **related_extra_entities**: 
* **action**:

```lua
 function( recursion_level, iteration ) 
      draw_actions( 1, true )
    end,
```

## ![Requirement - Projectile Spells](images/IF_PROJECTILE.png)Requirement - Projectile Spells (IF_PROJECTILE)

* **description**: The next spell is skipped if there are less than 20 projectiles nearby
* **type**: ACTION_TYPE_OTHER
* **spawn_level**: [10]
* **spawn_probability**: [1.0]
* **price**: 100
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_maths
* **related_extra_entities**: 
* **action**:

```lua
 function( recursion_level, iteration )
      local endpoint = -1
      local elsepoint = -1
      local x,y = EntityGetTransform( GetUpdatedEntityID() )
      local enemies = EntityGetInRadiusWithTag( x, y, 160, "projectile" )
      
      local doskip = false
      if ( #enemies < 20 ) then
        doskip = true
      end
      
      if ( #deck > 0 ) then
        for i,v in ipairs( deck ) do
          if ( v ~= nil ) then
            if ( string.sub( v.id, 1, 3 ) == "IF_" ) and ( v.id ~= "IF_END" ) and ( v.id ~= "IF_ELSE" ) then
              endpoint = -1
              break
            end
            
            if ( v.id == "IF_ELSE" ) then
              endpoint = i
              elsepoint = i
            end
            
            if ( v.id == "IF_END" ) then
              endpoint = i
              break
            end
          end
        end
        
        local envelope_min = 1
        local envelope_max = 1
          
        if doskip then
          if ( elsepoint > 0 ) then
            envelope_max = elsepoint
          elseif ( endpoint > 0 ) then
            envelope_max = endpoint
          end
          
          for i=envelope_min,envelope_max do
            local v = deck[envelope_min]
            
            if ( v ~= nil ) then
              table.insert( discarded, v )
              table.remove( deck, envelope_min )
            end
          end
        else
          if ( elsepoint > 0 ) then
            envelope_min = elsepoint
            
            if ( endpoint > 0 ) then
              envelope_max = endpoint
            else
              envelope_max = #deck
            end
            
            for i=envelope_min,envelope_max do
              local v = deck[envelope_min]
              
              if ( v ~= nil ) then
                table.insert( discarded, v )
                table.remove( deck, envelope_min )
              end
            end
          end
        end
      end
      
      draw_actions( 1, true )
    end,
```

## ![Return](images/TELEPORT_PROJECTILE_STATIC.png)Return (TELEPORT_PROJECTILE_STATIC)

* **description**: After a period of time, you'll be returned to where you cast this spell
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [0, 1, 2, 4, 5, 6]
* **spawn_probability**: [0.6, 0.6, 0.6, 0.4, 0.4, 0.4]
* **price**: 90
* **mana**: 40
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/teleport_projectile_static.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/teleport_projectile_static.xml")
      c.fire_rate_wait = c.fire_rate_wait + 3
      c.spread_degrees = c.spread_degrees - 2.0
    end,
```

## ![Rock](images/SUMMON_ROCK.png)Rock (SUMMON_ROCK)

* **description**: Create a mighty rock out of thin air
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [0, 1, 2, 3, 4, 5, 6]
* **spawn_probability**: [0.8, 0.8, 0.8, 0.8, 0.8, 0.8, 0.8]
* **price**: 160
* **mana**: 100
* **max_uses**: 3
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/rock.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/rock.xml")
    end,
```

## ![Rotate towards foes](images/HOMING_ROTATE.png)Rotate towards foes (HOMING_ROTATE)

* **description**: Makes a projectile turn towards your foes
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4, 5, 6]
* **spawn_probability**: [0.4, 0.4, 0.4, 0.4, 0.4]
* **price**: 175
* **mana**: 40
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/homing_rotate.xml", "data/entities/particles/tinyspark_white.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/homing_rotate.xml,data/entities/particles/tinyspark_white.xml,"
      draw_actions( 1, true )
    end,
```

## ![Sawblade Orbit](images/ORBIT_DISCS.png)Sawblade Orbit (ORBIT_DISCS)

* **description**: Makes four sawblades rotate around a projectile
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 2, 4, 5]
* **spawn_probability**: [0.2, 0.8, 0.4, 0.2]
* **price**: 200
* **mana**: 70
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_dragon
* **related_extra_entities**: { "data/entities/misc/orbit_discs.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/orbit_discs.xml,"
      draw_actions( 1, true )
    end,
```

## ![Sea of acid](images/SEA_ACID.png)Sea of acid (SEA_ACID)

* **description**: Summons a large body of acid below the caster
* **type**: ACTION_TYPE_MATERIAL
* **spawn_level**: [0, 4, 5, 6]
* **spawn_probability**: [0.2, 0.2, 0.2, 0.2]
* **price**: 350
* **mana**: 140
* **max_uses**: 3
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/sea_acid.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/sea_acid.xml")
      c.fire_rate_wait = c.fire_rate_wait + 15
    end,
```

## ![Sea of alcohol](images/SEA_ALCOHOL.png)Sea of alcohol (SEA_ALCOHOL)

* **description**: Summons a large body of tasty alcohol below the caster
* **type**: ACTION_TYPE_MATERIAL
* **spawn_level**: [0, 4, 5, 6]
* **spawn_probability**: [0.3, 0.3, 0.3, 0.3]
* **price**: 350
* **mana**: 140
* **max_uses**: 3
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/sea_alcohol.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/sea_alcohol.xml")
      c.fire_rate_wait = c.fire_rate_wait + 15
    end,
```

## ![Sea of flammable gas](images/SEA_ACID_GAS.png)Sea of flammable gas (SEA_ACID_GAS)

* **description**: Summons a large body of flammable gas below the caster
* **type**: ACTION_TYPE_MATERIAL
* **spawn_level**: [0, 4, 5, 6]
* **spawn_probability**: [0.3, 0.3, 0.3, 0.3]
* **price**: 200
* **mana**: 140
* **max_uses**: 3
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/sea_acid_gas.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/sea_acid_gas.xml")
      c.fire_rate_wait = c.fire_rate_wait + 15
    end,
```

## ![Sea of lava](images/SEA_LAVA.png)Sea of lava (SEA_LAVA)

* **description**: Summons a large body of lava below the caster
* **type**: ACTION_TYPE_MATERIAL
* **spawn_level**: [0, 4, 5, 6]
* **spawn_probability**: [0.2, 0.2, 0.2, 0.2]
* **price**: 350
* **mana**: 140
* **max_uses**: 3
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/sea_lava.xml"}
* **spawn_requires_flag**: card_unlocked_sea_lava
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/sea_lava.xml")
      c.fire_rate_wait = c.fire_rate_wait + 15
    end,
```

## ![Sea of oil](images/SEA_OIL.png)Sea of oil (SEA_OIL)

* **description**: Summons a large body of oil below the caster
* **type**: ACTION_TYPE_MATERIAL
* **spawn_level**: [0, 4, 5, 6]
* **spawn_probability**: [0.3, 0.3, 0.3, 0.3]
* **price**: 350
* **mana**: 140
* **max_uses**: 3
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/sea_oil.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/sea_oil.xml")
      c.fire_rate_wait = c.fire_rate_wait + 15
    end,
```

## ![Sea of water](images/SEA_WATER.png)Sea of water (SEA_WATER)

* **description**: Summons a large body of water below the caster
* **type**: ACTION_TYPE_MATERIAL
* **spawn_level**: [0, 4, 5, 6]
* **spawn_probability**: [0.4, 0.4, 0.4, 0.4]
* **price**: 350
* **mana**: 140
* **max_uses**: 3
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/sea_water.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/sea_water.xml")
      c.fire_rate_wait = c.fire_rate_wait + 15
    end,
```

## ![Short-range Homing](images/HOMING_SHORT.png)Short-range Homing (HOMING_SHORT)

* **description**: A projectile flies towards targets when near them
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 2, 3, 4, 5, 6]
* **spawn_probability**: [0.4, 0.8, 1.0, 0.4, 0.1, 0.1]
* **price**: 160
* **mana**: 40
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/homing_short.xml", "data/entities/particles/tinyspark_white_weak.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/homing_short.xml,data/entities/particles/tinyspark_white_weak.xml,"
      draw_actions( 1, true )
    end,
```

## ![Sigma](images/SIGMA.png)Sigma (SIGMA)

* **description**: Copies every static projectile -type spell in the wand when cast
* **type**: ACTION_TYPE_OTHER
* **spawn_level**: [4, 5, 10]
* **spawn_probability**: [0.1, 0.1, 1.0]
* **price**: 500
* **mana**: 120
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: true
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_duplicate
* **related_extra_entities**: 
* **action**:

```lua
 function( recursion_level, iteration )
      c.fire_rate_wait = c.fire_rate_wait + 30
      
      local firerate = c.fire_rate_wait
      local reload = current_reload_time
      local mana_ = mana
      
      if ( discarded ~= nil ) then
        for i,data in ipairs( discarded ) do
          local rec = check_recursion( data, recursion_level )
          if ( data ~= nil ) and ( data.type == 1 ) and ( rec > -1 ) then
            dont_draw_actions = true
            data.action( rec )
            dont_draw_actions = false
          end
        end
      end
      
      if ( hand ~= nil ) then
        for i,data in ipairs( hand ) do
          local rec = check_recursion( data, recursion_level )
          if ( data ~= nil ) and ( data.type == 1 ) and ( rec > -1 ) then
            dont_draw_actions = true
            data.action( rec )
            dont_draw_actions = false
          end
        end
      end
      
      if ( deck ~= nil ) then
        for i,data in ipairs( deck ) do
          local rec = check_recursion( data, recursion_level )
          if ( data ~= nil ) and ( data.type == 1 ) and ( rec > -1 ) then
            dont_draw_actions = true
            data.action( rec )
            dont_draw_actions = false
          end
        end
      end
      
      c.fire_rate_wait = firerate
      current_reload_time = reload
      mana = mana_
      
      draw_actions( 1, true )
    end,
```

## ![Slime mist](images/MIST_SLIME.png)Slime mist (MIST_SLIME)

* **description**: A cloud of slimy mist
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [1, 2, 3, 4]
* **spawn_probability**: [0.4, 0.4, 0.4, 0.4]
* **price**: 80
* **mana**: 40
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/mist_slime.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/mist_slime.xml")
      c.fire_rate_wait = c.fire_rate_wait + 10
    end,
```

## ![Slimeball](images/SLIMEBALL.png)Slimeball (SLIMEBALL)

* **description**: A dripping ball of poisonous slime
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [0, 3, 4]
* **spawn_probability**: [1.0, 1.0, 1.0]
* **price**: 130
* **mana**: 20
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/slime.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/slime.xml")
      c.spread_degrees = c.spread_degrees + 4.0
      c.fire_rate_wait = c.fire_rate_wait + 10
      c.speed_multiplier = c.speed_multiplier * 1.1
      
      if ( c.speed_multiplier >= 20 ) then
        c.speed_multiplier = math.min( c.speed_multiplier, 20 )
      elseif ( c.speed_multiplier < 0 ) then
        c.speed_multiplier = 0
      end
    end,
```

## ![Slithering path](images/SINEWAVE.png)Slithering path (SINEWAVE)

* **description**: Makes a projectile move rapidly in a slithering manner, like a snake
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 4, 6]
* **spawn_probability**: [0.4, 0.4, 0.4]
* **price**: 10
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/sinewave.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/sinewave.xml,"
      c.speed_multiplier = c.speed_multiplier * 2
      
      if ( c.speed_multiplier >= 20 ) then
        c.speed_multiplier = math.min( c.speed_multiplier, 20 )
      elseif ( c.speed_multiplier < 0 ) then
        c.speed_multiplier = 0
      end
      
      draw_actions( 1, true )
    end,
```

## ![Slow But Steady](images/SLOW_BUT_STEADY.png)Slow But Steady (SLOW_BUT_STEADY)

* **description**: The reload time of the wand is set to exactly 1.5 seconds
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [3, 4, 5, 6, 10]
* **spawn_probability**: [0.1, 0.2, 0.3, 0.4, 0.4]
* **price**: 50
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_maths
* **related_extra_entities**: 
* **action**:

```lua
 function()
      current_reload_time = 90
      shot_effects.recoil_knockback = shot_effects.recoil_knockback - 80.0
      draw_actions( 1, true )
    end,
```

## ![Small Teleport Bolt](images/TELEPORT_PROJECTILE_SHORT.png)Small Teleport Bolt (TELEPORT_PROJECTILE_SHORT)

* **description**: A shortlived magical bolt that moves you wherever it ends up flying
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [0, 1, 2, 4, 5, 6]
* **spawn_probability**: [0.6, 0.6, 0.6, 0.4, 0.4, 0.4]
* **price**: 130
* **mana**: 20
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/teleport_projectile_short.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/teleport_projectile_short.xml")
      c.spread_degrees = c.spread_degrees - 2.0
    end,
```

## ![Spark bolt](images/LIGHT_BULLET.png)Spark bolt (LIGHT_BULLET)

* **description**: A weak but enchanting sparkling projectile
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [0, 1, 2]
* **spawn_probability**: [2.0, 1.0, 0.5]
* **price**: 100
* **mana**: 5
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/light_bullet.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/light_bullet.xml")
      c.fire_rate_wait = c.fire_rate_wait + 3
      c.screenshake = c.screenshake + 0.5
      c.spread_degrees = c.spread_degrees - 1.0
      c.damage_critical_chance = c.damage_critical_chance + 5
    end,
```

## ![Spark bolt with double trigger](images/LIGHT_BULLET_TRIGGER_2.png)Spark bolt with double trigger (LIGHT_BULLET_TRIGGER_2)

* **description**: A spark bolt that casts two new spells upon collision
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [2, 3, 5, 6, 10]
* **spawn_probability**: [1.0, 0.5, 1.0, 1.0, 0.2]
* **price**: 250
* **mana**: 15
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/light_bullet_blue.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      c.fire_rate_wait = c.fire_rate_wait + 4
      c.screenshake = c.screenshake + 1
      c.damage_critical_chance = c.damage_critical_chance + 5
      add_projectile_trigger_hit_world("data/entities/projectiles/deck/light_bullet_blue.xml", 2)
    end,
```

## ![Spark bolt with timer](images/LIGHT_BULLET_TIMER.png)Spark bolt with timer (LIGHT_BULLET_TIMER)

* **description**: A spark bolt that casts another spell after a timer runs out
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [1, 2, 3]
* **spawn_probability**: [0.5, 0.5, 0.5]
* **price**: 140
* **mana**: 10
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/light_bullet.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      c.fire_rate_wait = c.fire_rate_wait + 3
      c.screenshake = c.screenshake + 0.5
      c.damage_critical_chance = c.damage_critical_chance + 5
      add_projectile_trigger_timer("data/entities/projectiles/deck/light_bullet.xml", 10, 1)
    end,
```

## ![Spark bolt with trigger](images/LIGHT_BULLET_TRIGGER.png)Spark bolt with trigger (LIGHT_BULLET_TRIGGER)

* **description**: A spark bolt that casts another spell upon collision
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [0, 1, 2, 3]
* **spawn_probability**: [1.0, 0.5, 0.5, 0.5]
* **price**: 140
* **mana**: 10
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/light_bullet.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      c.fire_rate_wait = c.fire_rate_wait + 3
      c.screenshake = c.screenshake + 0.5
      c.damage_critical_chance = c.damage_critical_chance + 5
      add_projectile_trigger_hit_world("data/entities/projectiles/deck/light_bullet.xml", 1)
    end,
```

## ![Speed Up](images/SPEED.png)Speed Up (SPEED)

* **description**: Increases the speed at which a projectile flies through the air
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 2, 3]
* **spawn_probability**: [1.0, 0.5, 0.5]
* **price**: 100
* **mana**: 3
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      c.speed_multiplier = c.speed_multiplier * 2.5
      
      if ( c.speed_multiplier >= 20 ) then
        c.speed_multiplier = math.min( c.speed_multiplier, 20 )
      elseif ( c.speed_multiplier < 0 ) then
        c.speed_multiplier = 0
      end
      
      draw_actions( 1, true )
    end,
```

## ![Spell duplication](images/DUPLICATE.png)Spell duplication (DUPLICATE)

* **description**: Duplicates every spell cast before it
* **type**: ACTION_TYPE_OTHER
* **spawn_level**: [5, 6, 10]
* **spawn_probability**: [0.1, 0.1, 1.0]
* **price**: 250
* **mana**: 250
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: true
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_mestari
* **related_extra_entities**: 
* **action**:

```lua
 function( recursion_level, iteration )
      local hand_count = #hand
      
      for i,v in ipairs( hand ) do
        local rec = check_recursion( v, recursion_level )
        if ( v.id ~= "DUPLICATE" ) and ( i <= hand_count ) and ( rec > -1 ) then
          v.action( rec )
        end
      end
      
      c.fire_rate_wait = c.fire_rate_wait + 20
      current_reload_time = current_reload_time + 20
      
      draw_actions( 1, true )
    end,
```

## ![Spells to Power](images/SPELLS_TO_POWER.png)Spells to Power (SPELLS_TO_POWER)

* **description**: Converts any nearby projectiles cast by you into extra damage
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4, 5, 6, 10]
* **spawn_probability**: [0.5, 0.5, 0.5, 0.5, 0.5, 0.1]
* **price**: 140
* **mana**: 110
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/spells_to_power.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/spells_to_power.xml,"
      c.fire_rate_wait    = c.fire_rate_wait + 40
      draw_actions( 1, true )
    end,
```

## ![Spells to acid](images/ALL_ACID.png)Spells to acid (ALL_ACID)

* **description**: Transforms every projectile currently in the air into a pool of acid
* **type**: ACTION_TYPE_UTILITY
* **spawn_level**: [4, 6, 10]
* **spawn_probability**: [0.1, 0.05, 1.0]
* **price**: 600
* **mana**: 200
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_alchemy
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/all_acid.xml")
      c.fire_rate_wait = c.fire_rate_wait + 100
      current_reload_time = current_reload_time + 100
    end,
```

## ![Spells to black holes](images/ALL_BLACKHOLES.png)Spells to black holes (ALL_BLACKHOLES)

* **description**: Transforms every projectile currently in the air into a black hole
* **type**: ACTION_TYPE_UTILITY
* **spawn_level**: [3, 6, 10]
* **spawn_probability**: [0.1, 0.05, 1.0]
* **price**: 500
* **mana**: 200
* **max_uses**: 10
* **never_unlimited**: true
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_alchemy
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/all_blackholes.xml")
      c.fire_rate_wait = c.fire_rate_wait + 100
      current_reload_time = current_reload_time + 100
    end,
```

## ![Spells to death crosses](images/ALL_DEATHCROSSES.png)Spells to death crosses (ALL_DEATHCROSSES)

* **description**: Transforms every projectile currently in the air into a death cross
* **type**: ACTION_TYPE_UTILITY
* **spawn_level**: [2, 6, 10]
* **spawn_probability**: [0.1, 0.05, 1.0]
* **price**: 350
* **mana**: 80
* **max_uses**: 15
* **never_unlimited**: true
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_alchemy
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/all_deathcrosses.xml")
      c.fire_rate_wait = c.fire_rate_wait + 40
      current_reload_time = current_reload_time + 40
    end,
```

## ![Spells to giga sawblades](images/ALL_DISCS.png)Spells to giga sawblades (ALL_DISCS)

* **description**: Transforms every projectile currently in the air into a giant sawblade
* **type**: ACTION_TYPE_UTILITY
* **spawn_level**: [0, 6, 10]
* **spawn_probability**: [0.1, 0.05, 1.0]
* **price**: 400
* **mana**: 100
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_alchemy
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/all_discs.xml")
      c.fire_rate_wait = c.fire_rate_wait + 50
      current_reload_time = current_reload_time + 50
    end,
```

## ![Spells to magic missiles](images/ALL_ROCKETS.png)Spells to magic missiles (ALL_ROCKETS)

* **description**: Transforms every projectile currently in the air into a magic missile
* **type**: ACTION_TYPE_UTILITY
* **spawn_level**: [1, 6, 10]
* **spawn_probability**: [0.1, 0.05, 1.0]
* **price**: 400
* **mana**: 100
* **max_uses**: 10
* **never_unlimited**: true
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_alchemy
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/all_rockets.xml")
      c.fire_rate_wait = c.fire_rate_wait + 50
      current_reload_time = current_reload_time + 50
    end,
```

## ![Spells to nukes](images/ALL_NUKES.png)Spells to nukes (ALL_NUKES)

* **description**: Transforms every projectile currently in the air into a nuke; not a good idea
* **type**: ACTION_TYPE_UTILITY
* **spawn_level**: [6, 10]
* **spawn_probability**: [0.1, 1.0]
* **price**: 600
* **mana**: 600
* **max_uses**: 2
* **never_unlimited**: true
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: true
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_alchemy
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/all_nukes.xml")
      c.fire_rate_wait = c.fire_rate_wait + 100
      current_reload_time = current_reload_time + 100
    end,
```

## ![Spiral Arc](images/SPIRALING_SHOT.png)Spiral Arc (SPIRALING_SHOT)

* **description**: A projectile flies in a spiralling pattern
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 2, 3, 4]
* **spawn_probability**: [0.2, 0.3, 0.4, 0.1]
* **price**: 30
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/orbit_shot.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/orbit_shot.xml,"
      draw_actions( 1, true )
      c.damage_projectile_add = c.damage_projectile_add + 0.1
      c.fire_rate_wait    = c.fire_rate_wait - 6
      c.lifetime_add     = c.lifetime_add + 50
    end,
```

## ![Spiral shot](images/SPIRAL_SHOT.png)Spiral shot (SPIRAL_SHOT)

* **description**: A mystical whirlwind of magic sparks
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [4, 5, 6]
* **spawn_probability**: [1.0, 1.0, 1.0]
* **price**: 190
* **mana**: 50
* **max_uses**: 15
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/spiral_shot.xml"}
* **spawn_requires_flag**: card_unlocked_spiral_shot
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/spiral_shot.xml")
      c.fire_rate_wait = c.fire_rate_wait + 20
    end,
```

## ![Spitter bolt](images/SPITTER.png)Spitter bolt (SPITTER)

* **description**: A short-lived magical bolt
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [0, 1, 2, 3]
* **spawn_probability**: [1.0, 1.0, 1.0, 0.5]
* **price**: 110
* **mana**: 5
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/spitter.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/spitter.xml")
      c.fire_rate_wait = c.fire_rate_wait - 1
      c.screenshake = c.screenshake + 0.1
      c.dampening = 0.1
      c.spread_degrees = c.spread_degrees + 6.0
    end,
```

## ![Spitter bolt with timer](images/SPITTER_TIMER.png)Spitter bolt with timer (SPITTER_TIMER)

* **description**: A short-lived magical bolt that casts another spell after a timer runs out
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [0, 1, 2, 3]
* **spawn_probability**: [0.5, 0.5, 0.5, 1.0]
* **price**: 140
* **mana**: 10
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/spitter.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      c.fire_rate_wait = c.fire_rate_wait - 1
      c.screenshake = c.screenshake + 0.1
      c.dampening = 0.1
      c.spread_degrees = c.spread_degrees + 6.0
      add_projectile_trigger_timer("data/entities/projectiles/deck/spitter.xml", 40, 1)
    end,
```

## ![Square barrier](images/WALL_SQUARE.png)Square barrier (WALL_SQUARE)

* **description**: A thin, square-shaped barrier that harms passing creatures, including you
* **type**: ACTION_TYPE_STATIC_PROJECTILE
* **spawn_level**: [0, 1, 2, 4, 5, 6]
* **spawn_probability**: [0.4, 0.4, 0.4, 0.4, 0.4, 0.4]
* **price**: 160
* **mana**: 70
* **max_uses**: 20
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/wall_square.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/wall_square.xml")
      c.fire_rate_wait = c.fire_rate_wait + 20
    end,
```

## ![Summon Explosive Box](images/TNTBOX.png)Summon Explosive Box (TNTBOX)

* **description**: Summons a box of explosive matter
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [1, 2, 3, 4, 5]
* **spawn_probability**: [0.8, 0.8, 0.8, 0.8, 0.8]
* **price**: 150
* **mana**: 40
* **max_uses**: 15
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/tntbox.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/tntbox.xml")
      c.fire_rate_wait = c.fire_rate_wait + 30
    end,
```

## ![Summon Firebug swarm](images/SWARM_FIREBUG.png)Summon Firebug swarm (SWARM_FIREBUG)

* **description**: Summons four fire bugs to aid you in battle
* **type**: ACTION_TYPE_STATIC_PROJECTILE
* **spawn_level**: [2, 4, 5, 6]
* **spawn_probability**: [0.2, 0.2, 0.5, 0.5]
* **price**: 100
* **mana**: 80
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/swarm_firebug.xml",4}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/swarm_firebug.xml")
      add_projectile("data/entities/projectiles/deck/swarm_firebug.xml")
      add_projectile("data/entities/projectiles/deck/swarm_firebug.xml")
      add_projectile("data/entities/projectiles/deck/swarm_firebug.xml")
      c.spread_degrees = c.spread_degrees + 12.0
      c.fire_rate_wait = c.fire_rate_wait + 60
      current_reload_time = current_reload_time + 20
    end,
```

## ![Summon Friendly fly](images/FRIEND_FLY.png)Summon Friendly fly (FRIEND_FLY)

* **description**: Summons a friendly fly that attacks your enemies!
* **type**: ACTION_TYPE_STATIC_PROJECTILE
* **spawn_level**: [4, 5, 6]
* **spawn_probability**: [0.2, 0.5, 0.5]
* **price**: 160
* **mana**: 120
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/friend_fly.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/friend_fly.xml")
      c.spread_degrees = c.spread_degrees + 24.0
      c.fire_rate_wait = c.fire_rate_wait + 80
      current_reload_time = current_reload_time + 40
    end,
```

## ![Summon Large Explosive Box](images/TNTBOX_BIG.png)Summon Large Explosive Box (TNTBOX_BIG)

* **description**: Summons a large box of explosive matter
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [1, 2, 3, 4, 5]
* **spawn_probability**: [0.8, 0.8, 0.8, 0.8, 0.8]
* **price**: 170
* **mana**: 40
* **max_uses**: 15
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/tntbox_big.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/tntbox_big.xml")
      c.fire_rate_wait = c.fire_rate_wait + 30
    end,
```

## ![Summon Omega Sawblade](images/DISC_BULLET_BIGGER.png)Summon Omega Sawblade (DISC_BULLET_BIGGER)

* **description**: That's a lot of sawblade
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [2, 3, 5, 10]
* **spawn_probability**: [0.1, 0.6, 1.0, 0.1]
* **price**: 270
* **mana**: 70
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/disc_bullet_bigger.xml"}
* **spawn_requires_flag**: card_unlocked_everything
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/disc_bullet_bigger.xml")
      c.fire_rate_wait = c.fire_rate_wait + 40
      c.spread_degrees = c.spread_degrees + 6.4
      shot_effects.recoil_knockback = shot_effects.recoil_knockback + 30.0
      c.damage_projectile_add = c.damage_projectile_add + 0.2
    end,
```

## ![Summon Platform](images/TEMPORARY_PLATFORM.png)Summon Platform (TEMPORARY_PLATFORM)

* **description**: Summons a shortlived bit of ground
* **type**: ACTION_TYPE_UTILITY
* **spawn_level**: [0, 1, 2, 4, 5, 6]
* **spawn_probability**: [0.1, 0.1, 0.3, 0.4, 0.2, 0.1]
* **price**: 90
* **mana**: 30
* **max_uses**: 20
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/temporary_platform.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/temporary_platform.xml")
      c.fire_rate_wait = c.fire_rate_wait + 40
    end,
```

## ![Summon Taikasauva](images/SUMMON_WANDGHOST.png)Summon Taikasauva (SUMMON_WANDGHOST)

* **description**: Summons a possessed wand to aid you
* **type**: ACTION_TYPE_UTILITY
* **spawn_level**: [2, 4, 5, 6, 10]
* **spawn_probability**: [0.08, 0.1, 0.1, 0.1, 0.1]
* **price**: 420
* **mana**: 300
* **max_uses**: 1
* **never_unlimited**: true
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/wand_ghost_player.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/wand_ghost_player.xml")
      add_projectile("data/entities/particles/image_emitters/wand_effect.xml")
    end,
```

## ![Summon Tentacle](images/TENTACLE.png)Summon Tentacle (TENTACLE)

* **description**: Calls a terrifying appendage from another dimension
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [3, 4, 5, 6]
* **spawn_probability**: [1.0, 1.0, 1.0, 1.0]
* **price**: 200
* **mana**: 20
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/tentacle.xml"}
* **spawn_requires_flag**: card_unlocked_tentacle
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/tentacle.xml")
      c.fire_rate_wait = c.fire_rate_wait + 40
    end,
```

## ![Summon Tentacle with timer](images/TENTACLE_TIMER.png)Summon Tentacle with timer (TENTACLE_TIMER)

* **description**: Calls a terrifying appendage from another dimension! Comes with a timer
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [3, 4, 5, 6]
* **spawn_probability**: [0.6, 0.6, 0.6, 0.6]
* **price**: 250
* **mana**: 20
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/tentacle.xml"}
* **spawn_requires_flag**: card_unlocked_tentacle
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile_trigger_timer("data/entities/projectiles/deck/tentacle.xml",20,1)
      c.fire_rate_wait = c.fire_rate_wait + 40
    end,
```

## ![Summon Tiny Ghost](images/TINY_GHOST.png)Summon Tiny Ghost (TINY_GHOST)

* **description**: Summons a tiny ethereal being to your help. It may cast stronger spells depending on how much damage you have suffered.
* **type**: ACTION_TYPE_PASSIVE
* **spawn_level**: [1, 2, 3, 4, 5, 6]
* **spawn_probability**: [0.1, 0.5, 1.0, 1.0, 1.0, 1.0]
* **price**: 160
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      draw_actions( 1, true )
    end,
```

## ![Summon Wall](images/TEMPORARY_WALL.png)Summon Wall (TEMPORARY_WALL)

* **description**: Summons a shortlived obstacle
* **type**: ACTION_TYPE_UTILITY
* **spawn_level**: [0, 1, 2, 4, 5, 6]
* **spawn_probability**: [0.1, 0.1, 0.3, 0.4, 0.2, 0.1]
* **price**: 100
* **mana**: 40
* **max_uses**: 20
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/temporary_wall.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/temporary_wall.xml")
      c.fire_rate_wait = c.fire_rate_wait + 40
    end,
```

## ![Summon Wasp swarm](images/SWARM_WASP.png)Summon Wasp swarm (SWARM_WASP)

* **description**: Summon six wasps to aid you in battle
* **type**: ACTION_TYPE_STATIC_PROJECTILE
* **spawn_level**: [2, 4, 5, 6]
* **spawn_probability**: [0.2, 0.2, 0.5, 0.5]
* **price**: 120
* **mana**: 90
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/swarm_wasp.xml",6}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/swarm_wasp.xml")
      add_projectile("data/entities/projectiles/deck/swarm_wasp.xml")
      add_projectile("data/entities/projectiles/deck/swarm_wasp.xml")
      add_projectile("data/entities/projectiles/deck/swarm_wasp.xml")
      add_projectile("data/entities/projectiles/deck/swarm_wasp.xml")
      add_projectile("data/entities/projectiles/deck/swarm_wasp.xml")
      c.spread_degrees = c.spread_degrees + 24.0
      c.fire_rate_wait = c.fire_rate_wait + 60
      current_reload_time = current_reload_time + 20
    end,
```

## ![Summon deercoy](images/EXPLODING_DEER.png)Summon deercoy (EXPLODING_DEER)

* **description**: Summons a seemingly-innocuous deer
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [3, 4, 5]
* **spawn_probability**: [0.6, 0.6, 0.6]
* **price**: 170
* **mana**: 120
* **max_uses**: 10
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/exploding_deer.xml"}
* **spawn_requires_flag**: card_unlocked_exploding_deer
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/exploding_deer.xml")
      c.fire_rate_wait = c.fire_rate_wait + 80
    end,
```

## ![Summon egg](images/SUMMON_EGG.png)Summon egg (SUMMON_EGG)

* **description**: Summons an egg that houses a friendly creature
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [0, 1, 2, 3, 4, 5, 6]
* **spawn_probability**: [0.8, 0.8, 0.8, 0.8, 0.8, 0.8, 0.8]
* **price**: 220
* **mana**: 100
* **max_uses**: 2
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/items/pickup/egg_monster.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      SetRandomSeed( GameGetFrameNum(), GameGetFrameNum() )
      local types = {"monster","slime","red","fire"}
      local rnd = Random(1, #types)
      local egg_name = "egg_" .. tostring(types[rnd]) .. ".xml"
      add_projectile("data/entities/items/pickup/" .. egg_name)
    end,
```

## ![Summon fly swarm](images/SWARM_FLY.png)Summon fly swarm (SWARM_FLY)

* **description**: Summons five flies to aid you in battle
* **type**: ACTION_TYPE_STATIC_PROJECTILE
* **spawn_level**: [2, 4, 5, 6]
* **spawn_probability**: [0.2, 0.2, 0.5, 0.5]
* **price**: 90
* **mana**: 70
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/swarm_fly.xml",5}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/swarm_fly.xml")
      add_projectile("data/entities/projectiles/deck/swarm_fly.xml")
      add_projectile("data/entities/projectiles/deck/swarm_fly.xml")
      add_projectile("data/entities/projectiles/deck/swarm_fly.xml")
      add_projectile("data/entities/projectiles/deck/swarm_fly.xml")
      c.spread_degrees = c.spread_degrees + 6.0
      c.fire_rate_wait = c.fire_rate_wait + 60
      current_reload_time = current_reload_time + 20
    end,
```

## ![Summon hollow egg](images/SUMMON_HOLLOW_EGG.png)Summon hollow egg (SUMMON_HOLLOW_EGG)

* **description**: Summons an otherwise empty egg that casts a spell upon cracking open
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [0, 1, 2, 3, 4, 5, 6]
* **spawn_probability**: [0.8, 0.8, 0.8, 0.8, 0.8, 0.8, 0.8]
* **price**: 140
* **mana**: 30
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/items/pickup/egg_hollow.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile_trigger_death("data/entities/items/pickup/egg_hollow.xml", 1)
      c.fire_rate_wait = c.fire_rate_wait - 12
    end,
```

## ![Summon missile](images/MISSILE.png)Summon missile (MISSILE)

* **description**: A missile!!!
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [1, 2, 3, 5]
* **spawn_probability**: [0.5, 0.5, 1.0, 1.0]
* **price**: 200
* **mana**: 60
* **max_uses**: 20
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/rocket_player.xml")
      current_reload_time = current_reload_time + 30
      c.spread_degrees = c.spread_degrees + 3.0
      shot_effects.recoil_knockback = shot_effects.recoil_knockback + 60.0
    end,
```

## ![Summon portal](images/SUMMON_PORTAL.png)Summon portal (SUMMON_PORTAL)

* **description**: Summons a strange portal
* **type**: ACTION_TYPE_OTHER
* **spawn_level**: [10]
* **spawn_probability**: [0.0]
* **price**: 100
* **mana**: 50
* **max_uses**: 7
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/summon_portal.xml")
      c.fire_rate_wait = c.fire_rate_wait + 80
    end,
```

## ![Summon rock spirit](images/PEBBLE.png)Summon rock spirit (PEBBLE)

* **description**: Summons an autonomous rock ally
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [1, 2, 4, 6]
* **spawn_probability**: [1.0, 1.0, 1.0, 1.0]
* **price**: 200
* **mana**: 120
* **max_uses**: 10
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/pebble_player.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/pebble_player.xml")
      c.fire_rate_wait = c.fire_rate_wait + 80
    end,
```

## ![Swapper](images/SWAPPER_PROJECTILE.png)Swapper (SWAPPER_PROJECTILE)

* **description**: It was theorized that the source of qualia would be transferred ???But it turns out it was the whole body all along.
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [0, 1, 2, 4, 5, 6]
* **spawn_probability**: [0.05, 0.05, 0.05, 0.05, 0.05, 0.05]
* **price**: 100
* **mana**: 5
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/swapper.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/swapper.xml")
      c.fire_rate_wait = c.fire_rate_wait + 3
      c.screenshake = c.screenshake + 0.5
      c.spread_degrees = c.spread_degrees - 2.0
      c.damage_critical_chance = c.damage_critical_chance + 5
    end,
```

## ![Tau](images/TAU.png)Tau (TAU)

* **description**: Copies the two following spells in the wand when cast
* **type**: ACTION_TYPE_OTHER
* **spawn_level**: [5, 6, 10]
* **spawn_probability**: [0.1, 0.1, 1.0]
* **price**: 200
* **mana**: 80
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: true
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_duplicate
* **related_extra_entities**: 
* **action**:

```lua
 function( recursion_level, iteration )
      c.fire_rate_wait = c.fire_rate_wait + 35
      
      local data1 = {}
      local data2 = {}
      
      local s1 = ""
      local s2 = ""
      
      if ( #deck > 0 ) then
        s1 = "deck"
        data1 = deck[1]
      else
        data1 = nil
      end
      
      if ( #deck > 0 ) then
        s2 = "deck 2"
        data2 = deck[2]
      else
        data2 = nil
      end
      
      local rec1 = check_recursion( data1, recursion_level )
      local rec2 = check_recursion( data2, recursion_level )
      
      if ( data1 ~= nil ) and ( rec1 > -1 ) then
        data1.action( rec1 )
      end
      
      if ( data2 ~= nil ) and ( rec2 > -1 ) then
        data2.action( rec2 )
      end
      
    end,
```

## ![Teleport bolt](images/TELEPORT_PROJECTILE.png)Teleport bolt (TELEPORT_PROJECTILE)

* **description**: A magical bolt that moves you wherever it ends up flying
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [0, 1, 2, 4, 5, 6]
* **spawn_probability**: [0.6, 0.6, 0.6, 0.4, 0.4, 0.4]
* **price**: 130
* **mana**: 40
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/teleport_projectile.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/teleport_projectile.xml")
      c.fire_rate_wait = c.fire_rate_wait + 3
      c.spread_degrees = c.spread_degrees - 2.0
    end,
```

## ![Teleporting cast](images/TELEPORT_CAST.png)Teleporting cast (TELEPORT_CAST)

* **description**: Casts a spell from the closest enemy
* **type**: ACTION_TYPE_UTILITY
* **spawn_level**: [0, 1, 2, 4, 5, 6]
* **spawn_probability**: [0.6, 0.6, 0.6, 0.6, 0.6, 0.6]
* **price**: 190
* **mana**: 100
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/teleport_cast.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile_trigger_death("data/entities/projectiles/deck/teleport_cast.xml", 1)
      c.fire_rate_wait = c.fire_rate_wait + 20
      c.spread_degrees = c.spread_degrees + 24
    end,
```

## ![Tentacler](images/TENTACLE_RAY.png)Tentacler (TENTACLE_RAY)

* **description**: Makes a projectile cast tentacles in random directions
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 2, 3, 4, 5]
* **spawn_probability**: [0.0, 0.0, 0.4, 0.4, 0.4]
* **price**: 150
* **mana**: 110
* **max_uses**: 16
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/tentacle_ray.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/tentacle_ray.xml,"
      draw_actions( 1, true )
    end,
```

## ![The end of everything](images/ALL_SPELLS.png)The end of everything (ALL_SPELLS)

* **description**: You're heavily advised not to cast this spell.
* **type**: ACTION_TYPE_OTHER
* **spawn_level**: [10]
* **spawn_probability**: [1.0]
* **price**: 1000
* **mana**: 600
* **max_uses**: 1
* **never_unlimited**: true
* **spawn_manual_unlock**: true
* **recursive**: true
* **ai_never_uses**: true
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_everything
* **related_extra_entities**: 
* **action**:

```lua
 function()
      local players = EntityGetWithTag( "player_unit" )
      for i,v in ipairs( players ) do
        local x,y = EntityGetTransform( v )
        local eid = EntityLoad("data/entities/projectiles/deck/all_spells_loader.xml", x, y)
      end
      c.fire_rate_wait = c.fire_rate_wait + 100
      current_reload_time = current_reload_time + 100
    end,
```

## ![Thunder charge](images/THUNDERBALL.png)Thunder charge (THUNDERBALL)

* **description**: A projectile with immense stored electricity
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [2, 4, 6, 10]
* **spawn_probability**: [1.0, 1.0, 1.0, 0.2]
* **price**: 300
* **mana**: 120
* **max_uses**: 3
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/thunderball.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/thunderball.xml")
      c.fire_rate_wait = c.fire_rate_wait + 120
    end,
```

## ![Thundercloud](images/CLOUD_THUNDER.png)Thundercloud (CLOUD_THUNDER)

* **description**: Creates a stormy cloud
* **type**: ACTION_TYPE_STATIC_PROJECTILE
* **spawn_level**: [0, 1, 2, 3, 4, 5]
* **spawn_probability**: [0.3, 0.3, 0.3, 0.3, 0.3, 0.3]
* **price**: 190
* **mana**: 90
* **max_uses**: 5
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/cloud_thunder.xml"}
* **spawn_requires_flag**: card_unlocked_cloud_thunder
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/cloud_thunder.xml")
      c.fire_rate_wait = c.fire_rate_wait + 30
    end,
```

## ![Torch](images/TORCH.png)Torch (TORCH)

* **description**: Lights your wand right up!
* **type**: ACTION_TYPE_PASSIVE
* **spawn_level**: [0, 1, 2]
* **spawn_probability**: [1.0, 1.0, 1.0]
* **price**: 100
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      draw_actions( 1, true )
    end,
```

## ![Touch of Blood](images/TOUCH_BLOOD.png)Touch of Blood (TOUCH_BLOOD)

* **description**: Transmutes everything in a short radius into blood, including walls, creatures... and you
* **type**: ACTION_TYPE_MATERIAL
* **spawn_level**: [1, 2, 3, 4, 5, 6, 7, 10]
* **spawn_probability**: [0.0, 0.0, 0.0, 0.0, 0.1, 0.1, 0.1, 0.5]
* **price**: 390
* **mana**: 270
* **max_uses**: 3
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/touch_blood.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/touch_blood.xml")
    end,
```

## ![Touch of Gold](images/TOUCH_GOLD.png)Touch of Gold (TOUCH_GOLD)

* **description**: Transmutes everything in a short radius into gold, including walls, creatures... and you
* **type**: ACTION_TYPE_MATERIAL
* **spawn_level**: [1, 2, 3, 4, 5, 6, 7, 10]
* **spawn_probability**: [0.0, 0.0, 0.0, 0.0, 0.1, 0.1, 0.1, 0.5]
* **price**: 480
* **mana**: 300
* **max_uses**: 1
* **never_unlimited**: true
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/touch_gold.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/touch_gold.xml")
    end,
```

## ![Touch of Oil](images/TOUCH_OIL.png)Touch of Oil (TOUCH_OIL)

* **description**: Transmutes everything in a short radius into oil, including walls, creatures... and you
* **type**: ACTION_TYPE_MATERIAL
* **spawn_level**: [1, 2, 3, 4, 5, 6, 7, 10]
* **spawn_probability**: [0.0, 0.0, 0.0, 0.0, 0.1, 0.1, 0.1, 0.1]
* **price**: 380
* **mana**: 260
* **max_uses**: 5
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/touch_oil.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/touch_oil.xml")
    end,
```

## ![Touch of Smoke](images/TOUCH_SMOKE.png)Touch of Smoke (TOUCH_SMOKE)

* **description**: Transmutes everything in a short radius into smoke, including walls, creatures... and you
* **type**: ACTION_TYPE_MATERIAL
* **spawn_level**: [1, 2, 3, 4, 5, 6, 7, 10]
* **spawn_probability**: [0.0, 0.0, 0.0, 0.0, 0.1, 0.1, 0.1, 0.1]
* **price**: 350
* **mana**: 230
* **max_uses**: 5
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/touch_smoke.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/touch_smoke.xml")
    end,
```

## ![Touch of Spirits](images/TOUCH_ALCOHOL.png)Touch of Spirits (TOUCH_ALCOHOL)

* **description**: Transmutes everything in a short radius into alcohol, including walls, creatures... and you
* **type**: ACTION_TYPE_MATERIAL
* **spawn_level**: [1, 2, 3, 4, 5, 6, 7, 10]
* **spawn_probability**: [0.0, 0.0, 0.0, 0.0, 0.1, 0.1, 0.1, 0.1]
* **price**: 360
* **mana**: 240
* **max_uses**: 5
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/touch_alcohol.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/touch_alcohol.xml")
    end,
```

## ![Touch of Water](images/TOUCH_WATER.png)Touch of Water (TOUCH_WATER)

* **description**: Transmutes everything in a short radius into water, including walls, creatures... and you
* **type**: ACTION_TYPE_MATERIAL
* **spawn_level**: [1, 2, 3, 4, 5, 6, 7, 10]
* **spawn_probability**: [0.0, 0.0, 0.0, 0.0, 0.1, 0.1, 0.1, 0.1]
* **price**: 420
* **mana**: 280
* **max_uses**: 5
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/touch_water.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/touch_water.xml")
    end,
```

## ![Toxic mist](images/MIST_RADIOACTIVE.png)Toxic mist (MIST_RADIOACTIVE)

* **description**: A cloud of toxic mist
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [1, 2, 3, 4]
* **spawn_probability**: [0.4, 0.4, 0.4, 0.4]
* **price**: 80
* **mana**: 40
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/mist_radioactive.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/mist_radioactive.xml")
      c.fire_rate_wait = c.fire_rate_wait + 10
    end,
```

## ![Toxic sludge to acid](images/TOXIC_TO_ACID.png)Toxic sludge to acid (TOXIC_TO_ACID)

* **description**: Makes any toxic sludge within a projectile's range turn into acid
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4]
* **spawn_probability**: [0.3, 0.3, 0.3]
* **price**: 120
* **mana**: 50
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/toxic_to_acid.xml", "data/entities/particles/tinyspark_green.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/toxic_to_acid.xml,data/entities/particles/tinyspark_green.xml,"
      c.fire_rate_wait = c.fire_rate_wait + 10
      draw_actions( 1, true )
    end,
```

## ![Triple scatter spell](images/SCATTER_3.png)Triple scatter spell (SCATTER_3)

* **description**: Simultaneously casts 3 spells with low accuracy
* **type**: ACTION_TYPE_DRAW_MANY
* **spawn_level**: [0, 1, 2, 3]
* **spawn_probability**: [0.7, 0.7, 0.7, 0.8]
* **price**: 120
* **mana**: 1
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      draw_actions( 3, true )
      c.spread_degrees = c.spread_degrees + 20.0
    end,
```

## ![Triple spell](images/BURST_3.png)Triple spell (BURST_3)

* **description**: Simultaneously casts 3 spells
* **type**: ACTION_TYPE_DRAW_MANY
* **spawn_level**: [1, 2, 3, 4, 5, 6]
* **spawn_probability**: [0.7, 0.7, 0.7, 0.7, 0.7, 0.7]
* **price**: 160
* **mana**: 2
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      draw_actions( 3, true )
    end,
```

## ![Triplicate bolt](images/BUCKSHOT.png)Triplicate bolt (BUCKSHOT)

* **description**: A formation of three small, fast bolts
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [0, 1, 2, 3, 4]
* **spawn_probability**: [1.0, 1.0, 1.0, 1.0, 1.0]
* **price**: 160
* **mana**: 25
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/buckshot_player.xml",3}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/buckshot_player.xml")
      add_projectile("data/entities/projectiles/deck/buckshot_player.xml")
      add_projectile("data/entities/projectiles/deck/buckshot_player.xml")
      c.fire_rate_wait = c.fire_rate_wait + 8
      c.spread_degrees = c.spread_degrees + 14.0
    end,
```

## ![Two-way fireball thrower](images/FIREBALL_RAY_LINE.png)Two-way fireball thrower (FIREBALL_RAY_LINE)

* **description**: Makes a projectile fire small fireballs perpendicular to its trajectory
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4, 5, 6]
* **spawn_probability**: [0.6, 0.4, 0.4, 0.4, 1.0]
* **price**: 120
* **mana**: 130
* **max_uses**: 20
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/fireball_ray_line.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/fireball_ray_line.xml,"
      draw_actions( 1, true )
    end,
```

## ![Unstable crystal](images/MINE.png)Unstable crystal (MINE)

* **description**: A crystal that explodes when someone comes nearby
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [1, 3, 4, 6]
* **spawn_probability**: [1.0, 1.0, 1.0, 1.0]
* **price**: 200
* **mana**: 20
* **max_uses**: 15
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/mine.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/mine.xml")
      c.fire_rate_wait = c.fire_rate_wait + 30
      c.child_speed_multiplier = c.child_speed_multiplier * 0.75
      c.speed_multiplier = c.speed_multiplier * 0.75
      shot_effects.recoil_knockback = 60.0
      
      if ( c.speed_multiplier >= 20 ) then
        c.speed_multiplier = math.min( c.speed_multiplier, 20 )
      elseif ( c.speed_multiplier < 0 ) then
        c.speed_multiplier = 0
      end
    end,
```

## ![Unstable crystal with trigger](images/MINE_DEATH_TRIGGER.png)Unstable crystal with trigger (MINE_DEATH_TRIGGER)

* **description**: A crystal that explodes and casts another spell when someone comes nearby
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [2, 6]
* **spawn_probability**: [1.0, 1.0]
* **price**: 240
* **mana**: 20
* **max_uses**: 15
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/mine.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile_trigger_death("data/entities/projectiles/deck/mine.xml", 1)
      c.fire_rate_wait = c.fire_rate_wait + 30
      c.child_speed_multiplier = c.child_speed_multiplier * 0.75
      c.speed_multiplier = c.speed_multiplier * 0.75
      shot_effects.recoil_knockback = 60.0
      
      if ( c.speed_multiplier >= 20 ) then
        c.speed_multiplier = math.min( c.speed_multiplier, 20 )
      elseif ( c.speed_multiplier < 0 ) then
        c.speed_multiplier = 0
      end
    end,
```

## ![Upwards larpa](images/LARPA_UPWARDS.png)Upwards larpa (LARPA_UPWARDS)

* **description**: Makes a projectile cast copies of itself with an upwards trajectory
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4, 5, 10]
* **spawn_probability**: [0.1, 0.1, 0.2, 0.4, 0.2]
* **price**: 290
* **mana**: 120
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/larpa_upwards.xml" }
* **action**:

```lua
 function()
      c.fire_rate_wait = c.fire_rate_wait + 15
      c.extra_entities = c.extra_entities .. "data/entities/misc/larpa_upwards.xml,"
      draw_actions( 1, true )
    end,
```

## ![Vacuum Field](images/VACUUM_ENTITIES.png)Vacuum Field (VACUUM_ENTITIES)

* **description**: Sucks nearby projectiles and creatures into the middle of the field instantaneously
* **type**: ACTION_TYPE_STATIC_PROJECTILE
* **spawn_level**: [2, 3, 5, 6]
* **spawn_probability**: [0.3, 1.0, 0.3, 0.3]
* **price**: 200
* **mana**: 50
* **max_uses**: 20
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/vacuum_liquid.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/vacuum_entities.xml")
      c.fire_rate_wait = c.fire_rate_wait + 10
    end,
```

## ![Venomous Curse](images/CURSE.png)Venomous Curse (CURSE)

* **description**: Imbues a projectile with a curse that makes the target hit by the projectile to waste away
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 5]
* **spawn_probability**: [0.6, 0.8, 0.4]
* **price**: 140
* **mana**: 30
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/hitfx_curse.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/hitfx_curse.xml,"
      draw_actions( 1, true )
    end,
```

## ![Vertical barrier](images/WALL_VERTICAL.png)Vertical barrier (WALL_VERTICAL)

* **description**: A thin, vertical barrier that harms passing creatures, including you
* **type**: ACTION_TYPE_STATIC_PROJECTILE
* **spawn_level**: [0, 1, 2, 4, 5, 6]
* **spawn_probability**: [0.4, 0.4, 0.4, 0.4, 0.4, 0.4]
* **price**: 160
* **mana**: 70
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/wall_vertical.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/wall_vertical.xml")
      c.fire_rate_wait = c.fire_rate_wait + 5
    end,
```

## ![Wand Refresh](images/RESET.png)Wand Refresh (RESET)

* **description**: Reloads the wand immediately
* **type**: ACTION_TYPE_UTILITY
* **spawn_level**: [10]
* **spawn_probability**: [1.0]
* **price**: 120
* **mana**: 20
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: true
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_mestari
* **related_extra_entities**: 
* **action**:

```lua
 function()
      current_reload_time = current_reload_time - 25
      
      for i,v in ipairs( hand ) do
        table.insert( discarded, v )
      end
      
      for i,v in ipairs( deck ) do
        table.insert( discarded, v )
      end
      
      hand = {}
      deck = {}
      
      if ( force_stop_draws == false ) then
        force_stop_draws = true
        move_discarded_to_deck()
        order_deck()
      end
    end,
```

## ![Warp cast](images/SUPER_TELEPORT_CAST.png)Warp cast (SUPER_TELEPORT_CAST)

* **description**: Makes a spell immediately jump a long distance, stopped by walls
* **type**: ACTION_TYPE_UTILITY
* **spawn_level**: [0, 1, 2, 4, 5, 6]
* **spawn_probability**: [0.2, 0.2, 0.2, 0.6, 0.6, 0.6]
* **price**: 160
* **mana**: 20
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/super_teleport_cast.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile_trigger_death("data/entities/projectiles/deck/super_teleport_cast.xml", 1)
      c.fire_rate_wait = c.fire_rate_wait + 10
      c.spread_degrees = c.spread_degrees - 6
    end,
```

## ![Water](images/MATERIAL_WATER.png)Water (MATERIAL_WATER)

* **description**: Transmute drops of water from nothing
* **type**: ACTION_TYPE_MATERIAL
* **spawn_level**: [1, 2, 3, 4, 5]
* **spawn_probability**: [0.4, 0.4, 0.4, 0.4, 0.4]
* **price**: 110
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/material_water.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/material_water.xml")
      c.game_effect_entities = c.game_effect_entities .. "data/entities/misc/effect_apply_wet.xml,"
      c.fire_rate_wait = c.fire_rate_wait - 15
      current_reload_time = current_reload_time - ACTION_DRAW_RELOAD_TIME_INCREASE - 10 -- this is a hack to get the cement reload time back to 0
    end,
```

## ![Water to poison](images/WATER_TO_POISON.png)Water to poison (WATER_TO_POISON)

* **description**: Makes any water within a projectile's range turns into poison
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4]
* **spawn_probability**: [0.3, 0.3, 0.3]
* **price**: 80
* **mana**: 30
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/water_to_poison.xml", "data/entities/particles/tinyspark_purple.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/water_to_poison.xml,data/entities/particles/tinyspark_purple.xml,"
      c.fire_rate_wait = c.fire_rate_wait + 10
      draw_actions( 1, true )
    end,
```

## ![Water trail](images/WATER_TRAIL.png)Water trail (WATER_TRAIL)

* **description**: Gives a projectile a trail of water
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 2, 3, 4]
* **spawn_probability**: [0.3, 0.3, 0.3, 0.3]
* **price**: 160
* **mana**: 10
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      c.game_effect_entities = c.game_effect_entities .. "data/entities/misc/effect_apply_wet.xml,"
      c.trail_material = c.trail_material .. "water,"
      c.trail_material_amount = c.trail_material_amount + 20
      draw_actions( 1, true )
    end,
```

## ![Weakening Curse - Electricity](images/CURSE_WITHER_ELECTRICITY.png)Weakening Curse - Electricity (CURSE_WITHER_ELECTRICITY)

* **description**: Target hit by a projectile takes 25% extra electricity damage for a time
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [1, 4, 5, 6]
* **spawn_probability**: [0.2, 0.4, 0.9, 0.9]
* **price**: 100
* **mana**: 50
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/hitfx_curse_wither_electricity.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/hitfx_curse_wither_electricity.xml,"
      draw_actions( 1, true )
    end,
```

## ![Weakening Curse - Explosives](images/CURSE_WITHER_EXPLOSION.png)Weakening Curse - Explosives (CURSE_WITHER_EXPLOSION)

* **description**: Target hit by a projectile takes 25% extra explosion damage for a time
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4, 5]
* **spawn_probability**: [0.2, 0.4, 0.9, 0.9]
* **price**: 100
* **mana**: 50
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/hitfx_curse_wither_explosion.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/hitfx_curse_wither_explosion.xml,"
      draw_actions( 1, true )
    end,
```

## ![Weakening Curse - Melee](images/CURSE_WITHER_MELEE.png)Weakening Curse - Melee (CURSE_WITHER_MELEE)

* **description**: Target hit by a projectile takes 25% extra melee damage for a time
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [3, 4, 5, 6]
* **spawn_probability**: [0.2, 0.4, 0.9, 0.9]
* **price**: 100
* **mana**: 50
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/hitfx_curse_wither_melee.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/hitfx_curse_wither_melee.xml,"
      draw_actions( 1, true )
    end,
```

## ![Weakening Curse - Projectiles](images/CURSE_WITHER_PROJECTILE.png)Weakening Curse - Projectiles (CURSE_WITHER_PROJECTILE)

* **description**: Target hit by a projectile takes 25% extra projectile damage for a time
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [3, 4, 5, 6]
* **spawn_probability**: [0.2, 0.4, 0.9, 0.9]
* **price**: 100
* **mana**: 50
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: 
* **related_extra_entities**: { "data/entities/misc/hitfx_curse_wither_projectile.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/misc/hitfx_curse_wither_projectile.xml,"
      draw_actions( 1, true )
    end,
```

## ![Worm Launcher](images/WORM_SHOT.png)Worm Launcher (WORM_SHOT)

* **description**: Summons a giant worm to cause havoc for a moment!
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [3, 4, 5]
* **spawn_probability**: [0.6, 0.8, 0.6]
* **price**: 200
* **mana**: 150
* **max_uses**: 10
* **never_unlimited**: true
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/worm_shot.xml"}
* **spawn_requires_flag**: card_unlocked_exploding_deer
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/worm_shot.xml")
      c.fire_rate_wait = c.fire_rate_wait + 80
      current_reload_time = current_reload_time + 40
      c.spread_degrees = c.spread_degrees + 20
    end,
```

## ![Yellow Glimmer](images/COLOUR_YELLOW.png)Yellow Glimmer (COLOUR_YELLOW)

* **description**: Gives a projectile a yellow sparkly trail
* **type**: ACTION_TYPE_MODIFIER
* **spawn_level**: [2, 3, 4]
* **spawn_probability**: [0.1, 0.1, 0.1]
* **price**: 40
* **mana**: 0
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_paint
* **related_extra_entities**: { "data/entities/particles/tinyspark_red.xml", "data/entities/misc/colour_yellow.xml" }
* **action**:

```lua
 function()
      c.extra_entities = c.extra_entities .. "data/entities/particles/tinyspark_red.xml,data/entities/misc/colour_yellow.xml,"
      c.fire_rate_wait = c.fire_rate_wait - 8
      c.screenshake = c.screenshake - 2.5
      if ( c.screenshake < 0 ) then
        c.screenshake = 0
      end
      draw_actions( 1, true )
    end,
```

## ![Zeta](images/ZETA.png)Zeta (ZETA)

* **description**: Copies a random spell in another wand you're holding
* **type**: ACTION_TYPE_OTHER
* **spawn_level**: [1, 2, 3, 10]
* **spawn_probability**: [0.2, 0.8, 0.6, 0.1]
* **price**: 200
* **mana**: 10
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: true
* **recursive**: true
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: 
* **spawn_requires_flag**: card_unlocked_duplicate
* **related_extra_entities**: 
* **action**:

```lua
 function( recursion_level, iteration )
      local entity_id = GetUpdatedEntityID()
      local x, y = EntityGetTransform( entity_id )
      local options = {}
      
      local children = EntityGetAllChildren( entity_id )
      local inventory = EntityGetFirstComponent( entity_id, "Inventory2Component" )
      
      if ( children ~= nil ) and ( inventory ~= nil ) then
        local active_wand = ComponentGetValue2( inventory, "mActiveItem" )
        
        for i,child_id in ipairs( children ) do
          if ( EntityGetName( child_id ) == "inventory_quick" ) then
            local wands = EntityGetAllChildren( child_id )
            
            if ( wands ~= nil ) then
              for k,wand_id in ipairs( wands ) do
                if ( wand_id ~= active_wand ) and EntityHasTag( wand_id, "wand" ) then
                  local spells = EntityGetAllChildren( wand_id )
                  
                  if ( spells ~= nil ) then
                    for j,spell_id in ipairs( spells ) do
                      local comp = EntityGetFirstComponentIncludingDisabled( spell_id, "ItemActionComponent" )
                      
                      if ( comp ~= nil ) then
                        local action_id = ComponentGetValue2( comp, "action_id" )
                        
                        table.insert( options, action_id )
                      end
                    end
                  end
                end
              end
            end
          end
        end
      end
      
      if ( #options > 0 ) then
        SetRandomSeed( x + GameGetFrameNum(), y + 251 )
        
        local rnd = Random( 1, #options )
        local action_id = options[rnd]
        
        for i,data in ipairs( actions ) do
          if ( data.id == action_id ) then
            local rec = check_recursion( data, recursion_level )
            if ( rec > -1 ) then
              dont_draw_actions = true
              data.action( rec )
              dont_draw_actions = false
            end
            break
          end
        end
      end
      
      draw_actions( 1, true )
    end,
```

## ![mist of spirits](images/MIST_ALCOHOL.png)mist of spirits (MIST_ALCOHOL)

* **description**: A cloud of potent alcohol
* **type**: ACTION_TYPE_PROJECTILE
* **spawn_level**: [1, 2, 3, 4]
* **spawn_probability**: [0.4, 0.4, 0.4, 0.4]
* **price**: 80
* **mana**: 40
* **max_uses**: 0
* **never_unlimited**: false
* **spawn_manual_unlock**: false
* **recursive**: false
* **ai_never_uses**: false
* **is_dangerous_blast**: false
* **related_projectiles**: {"data/entities/projectiles/deck/mist_alcohol.xml"}
* **spawn_requires_flag**: 
* **related_extra_entities**: 
* **action**:

```lua
 function()
      add_projectile("data/entities/projectiles/deck/mist_alcohol.xml")
      c.fire_rate_wait = c.fire_rate_wait + 10
    end,
```

