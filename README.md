# catwareLUA

**CREDIT TO    
https://github.com/ZaUserA**

<a name="-1"></a>

|Contents|
|--------|
|[Global](#0)|
|[Menu](#1)|
|[Game](#2)|
|[Engine](#3)|
|[Render](#4)|
|[Console](#5)|
|[Event](#6)|
|[Entity List](#7)|
|[User CMD](#8)|
|[Utils](#9)|
|[Indicators](#q)|
|[HTTP](#w)|

---

**HITBOXES ENUMERATION:** (usage example: Hitboxes.HITBOX_HEAD)     
- HITBOX_HEAD,   
- HITBOX_NECK,    
- HITBOX_PELVIS,     
- HITBOX_STOMACH,     
- HITBOX_LOWER_CHEST,     
- HITBOX_CHEST,      
- HITBOX_UPPER_CHEST,       
- HITBOX_RIGHT_THIGH,       
- HITBOX_LEFT_THIGH,     
- HITBOX_RIGHT_CALF,     
- HITBOX_LEFT_CALF,       
- HITBOX_RIGHT_FOOT,     
- HITBOX_LEFT_FOOT,    
- HITBOX_RIGHT_HAND,          
- HITBOX_LEFT_HAND,                 
- HITBOX_RIGHT_UPPER_ARM,              
- HITBOX_RIGHT_FOREARM,            
- HITBOX_LEFT_UPPER_ARM,            
- HITBOX_LEFT_FOREARM          

---

**KEY_BINDS ENUMERATION:** (usage example: Key_binds.double_tap)         
- legit_automatic_fire - *LEGIT AUTO FIRE KEY*      
- legit_enable - *LEGIT ENABLE KEY*    
- double_tap - *DOUBLE TAP KEY*   
- safe_points - *SAFE POINTS KEY*    
- damage_override - *DAMAGE OVERRIDE KEY*   
- hide_shots - *HIDE SHOTS KEY*    
- manual_back - *MANUAL AA BACK KEY*   
- manual_left - *MANUAL AA LEFT KEY*    
- manual_right - *MANUAL AA RIGHT KEY*   
- flip_desync - *FLIP DESYNC KEY*    
- thirdperson - *THIRDPERSON KEY*   
- automatic_peek - *AUTO PEEK KEY*   
- edge_jump - *EDGE JUMP KEY*    
- fakeduck - *FAKE DUCK KEY*    
- slowwalk - *SLOW WALK KEY*   
- body_aim - *BODY AIM KEY*   

---

**KEY_BIND_MODE ENUMERATION:** (usage example: Key_bind_mode.hold)            
- key_bind_mode.hold - *MODE HOLD*              
- key_bind_mode.toggle - *MODE TOGGLE*            
    
---

**BUTTONS ENUMERATION:** (usage example: Buttons.IN_ATTACK)  
- IN_ATTACK,
- IN_JUMP,
- IN_DUCK,
- IN_FORWARD,
- IN_BACK,
- IN_USE,
- IN_CANCEL,
- IN_LEFT,
- IN_RIGHT,
- IN_MOVELEFT,
- IN_MOVERIGHT,
- IN_ATTACK2,
- IN_RUN,
- IN_RELOAD,
- IN_ALT1,
- IN_ALT2,
- IN_SCORE,
- IN_SPEED,
- IN_WALK,
- IN_ZOOM,
- IN_WEAPON1,
- IN_WEAPON2,
- IN_BULLRUSH,
- IN_GRENADE1,
- IN_GRENADE2,
- IN_LOOKSPIN

---

**GRADIENTTYPE ENUMERATION:**                 
- GRADIENT_HORIZONTAL       
- GRADIENT_VERTICAL   

---

**CSGO GAME EVENT LIST**                   
*https://wiki.alliedmods.net/Counter-Strike:_Global_Offensive_Events*        

**GAME_EVENT STRUCTS:**           
- GetBool([keyName: char]) **(bool)** - *Get Bool*        
- GetInt([keyName: char]) **(integer)** - *Get Int*               
- GetFloat([keyName: char]) **(float)** - *Get Float*                  
- GetString([keyName: char]) **(char)** - *Get String*                    
- SetBool([keyName: char], [Value: bool]) **(bool)** - *Set Bool*                           
- SetInt([keyName: char], [Value: int]) **(integer)** - *Set Int*                            
- SetFloat([keyName: char], [Value: float]) **(float)** - *Set Float*                        
- SetString([keyName: char], [Value: char]) **(char)** - *Set String*                                       

---

**COLOR STRUCTS:**       
- r **(integer)** - *red*                   
- g **(integer)** - *green*   
- b **(integer)** - *blue*    
- a **(integer)** - *alpha*    

---

**RAGEBOT_INFO STRUCTS:** (usage example: Ragebot_info.hitchance) 
- target_name **(string)** - *Returns target name*
- result **(string)** - *Returns shot result. RESULT : ("Spread", "Resolver", "Hit")*
- client_hitbox **(string)** - *Returns client hitbox*
- server_hitbox **(string)** - *Returns server hitbox*
- client_damage **(integer)** - *Returns client damage*
- server_damage **(integer)** - *Returns server damage*
- hitchance **(integer)** - *Returns hitchance*
- backtrack_ticks **(integer)** - *Returns backtrack ticks*
- aim_point **(Vector)** - *Returns aimpoint*

---

**ENTITY STRUCTS:**
- GetPropInt([Table: string], [Var: string]) **(int)** - *Get integer property*
- GetPropFloat([Table: string], [Var: string]) **(float)** - *Get float property*
- GetPropBool([Table: string], [Var: string]) **(boolean)** - *Get boolean property*
- GetPropString([Table: string], [Var: string]) **(string)** - *Get string property*
- SetPropInt([Table: string], [Var: string], [Value: int]) **(void)** - *Set integer property*
- SetPropFloat([Table: string], [Var: string], [Value: float]) **(void)** - *Set float property*
- SetPropBool([Table: string], [Var: string], [Value: bool]) **(void)** - *Set boolean property*
- SetPropString([Table: string], [Var: string], [Value: string]) **(void)** - *Set string property*

---

**WEAPON STRUCTS:**
- IsEmpty **(boolean)** - *Returns true if the weapon is empty (no ammo at all), or else not.*
- CanFire(bool revolver_check) **(boolean)** - *Checks if you can really fire the gun.*
- IsNonAim **(boolean)** - *Checks if the weapon you use is suitable for aimbot or not.*
- CanDoubleTap **(bool)** - *Checks if your weapon can doubletapping or not.*
- GetName **(string)** - *Obtain your weapon name.*
- GetInaccuracy **(float)** - *Obtain your weapon inaccuracy.*
- GetSpread **(float)** - *Obtain your weapon spread.*
- GetPropInt([Table: string], [Var: string]) **(int)** - *Get integer property*
- GetPropFloat([Table: string], [Var: string]) **(float)** - *Get float property*
- GetPropBool([Table: string], [Var: string]) **(boolean)** - *Get boolean property*
- GetPropString([Table: string], [Var: string]) **(string)** - *Get string property*
- SetPropInt([Table: string], [Var: string], [Value: int]) **(void)** - *Set integer property*
- SetPropFloat([Table: string], [Var: string], [Value: float]) **(void)** - *Set float property*
- SetPropBool([Table: string], [Var: string], [Value: bool]) **(void)** - *Set boolean property*
- SetPropString([Table: string], [Var: string], [Value: string]) **(void)** - *Set string property*

---

**PLAYER STRUCTS:**
- EntIndex **(int)** - *Obtain player index.*
- IsDormant **(boolean)** - *Obtain player dormancy.*
- IsAlive **(boolean)** - *Will be true if the player alive, or else it'll not.*
- GetPropInt([Table: string], [Var: string]) **(int)** - *Get integer property*
- GetPropFloat([Table: string], [Var: string]) **(float)** - *Get float property*
- GetPropBool([Table: string], [Var: string]) **(boolean)** - *Get boolean property*
- GetPropString([Table: string], [Var: string]) **(string)** - *Get string property*
- SetPropInt([Table: string], [Var: string], [Value: int]) **(void)** - *Set integer property*
- SetPropFloat([Table: string], [Var: string], [Value: float]) **(void)** - *Set float property*
- SetPropBool([Table: string], [Var: string], [Value: bool]) **(void)** - *Set boolean property*
- SetPropString([Table: string], [Var: string], [Value: string]) **(void)** - *Set string property*

---

**VECTOR STRUCTS:**     
- x **(float)**     
- y **(float)**   
- z **(float)**      
- Length **(float)** - *Returns the euclidean length.*      
- LengthSqr **(float)** - *Returns the squared length of the vector.*          
- Length2D **(float)** - *Returns the length of the vector in two dimensions, without the Z axis.*         
- Length2DSqr **(float)** - *Returns the squared length of the vectors x and y value.*        
- IsZero **(boolean)** - *Checks whenever all fields of the vector are 0.*       
- IsValid **(boolean)** - *Checks when the vector is all valid.*    
- Zero **(void)** - *Sets x, y and z to 0.*          
- DistTo([Target: Vector]) **(float)** - *Returns the euclidean distance between the vector an the other vector.*     
- DistToSqr **(float)** - *Returns the squared distance of 2 vectors*       
- CrossProduct([Target: Vector]) **(Vector)** - *Calculates the cross product of this vector and the passed one.*      
- Normalize **(float)** - *Normalizes the given vector. This changes the vector you call it on.*      

---

**PLAYER_INFO STRUCTS:**        
- fakeplayer **(boolean)** - *Checks whether a player is a bot or not.*        
- szName[128] **(integer)** - *Get Player Name*        
- szSteamID[20] **(char)** - *STEAM:X:Y:Z*       

---

## <a name="0"></a>Global
|-------------------------------|

[ **RegisterCallBack** ]       
Syntax: Global.RegisterCallBack([EventName: string, Function: function])     
**Used** to call the functions you write.    
```lua
local function paint_traverse()
Render.DrawText(font, 0, 0, Color.new(255, 255, 255, 255), "Hi")
end

Global.RegisterCallBack("PaintTraverse", paint_traverse)
```

[ **LoadLUA** ]              
Syntax: Global.LoadLUA([Name: string])      
**Used** to load another LUA you type inside of LoadLUA.       
```lua
Global.LoadLUA("HitList")
```

[ **UnloadLUA** ]              
Syntax: Global.UnloadLUA([Name: string])        
**Used** to unload another LUA you type inside of UnloadLUA       
```lua
Global.UnloadLUA("HitList")
```

[ **AddLog** ]           
Syntax: Global.AddLog([Text: string])         
**Add** the text you write inside AddLog into the cheat eventlogger        
```lua
local function draw()
Global.AddLog("Hi from the event logger")
end

Global.RegisterCallBack("PaintTraverse", draw)
```

[ **Username** ]          
Syntax: Global.Username()             
**Returns** forum username.               
```lua
local function draw()
local font =  Render.CreateFont("Verdana", 12, 600, true, true, true)
Render.DrawText(font, 100, 100, Color.new(255, 0, 0), tostring(Global.Username()))
end

Global.RegisterCallBack("PaintTraverse", draw)
```

[back to Contents](#-1)

## <a name="1"></a>Menu
|-------------------------------|

  [ **IsVisible** ]         
Syntax: Menu.IsVisible()          
**True** if the menu is open, false otherwise.               
```lua
if (Menu.IsVisible() == true)
Global.AddLog("Menu is open!")
end
```

  [ **NextLine** ]              
Syntax: Menu.NextLine()                 
**Skip** last menu line.           
```lua
Menu.AddCheckbox("Enable Hit list") // this will be skipped
Menu.AddCheckbox("Enable Spectator List") // this is from another LUA.
Menu.NextLine()   
menu.AddColorPicker("Hit list Color")
```

  [ **AddCheckBox** ]
Syntax: Menu.AddCheckBox([Name: string])   
**Create** a checkbox in LUA tab.
```lua
Menu.AddCheckBox("Checkbox")   
```

  [ **AddComboBox** ]             
Syntax: Menu.AddComboBox([Name: string], [Labels: string vector])                  
**Create** a combobox in LUA tab.           
```lua
Menu.AddComboBox("Combobox", { "Selection 1", "Selection 2" })   
```


  [ **AddSliderInt** ]               
Syntax: Menu.AddSliderInt([Name: string], [Min: integer], [Max: integer])                          
**Create** a slider *(integer)*.  
```lua
Menu.AddSliderInt("Int", 0, 100) 
```

  [ **AddSliderFloat** ]                    
Syntax: Menu.AddSliderFloat([Name: string], [Min: float], [Max: float])             
**Create** a slider *(float)*.              
```lua
Menu.AddSliderFloat("Float", 0.0, 100.0) 
```

  [ **AddColorPicker** ]              
Syntax: Menu.AddColorPicker([Name: string])                 
**Create** a Color Picker.               
```lua
Menu.AddColorPicker("Color Picker") 
```

  [ **GetBool** ]              
Syntax: Menu.GetBool([Name: string])                
**Get** bool statement of LUA item and Config items.         
```lua
Menu.AddCheckBox("Checkbox") 

local function draw()
if Menu.GetBool("Checkbox") then
Global.AddLog("This bool is currently active!")
end
else
Global.AddLog("This bool is currently disabled!")
end

Global.RegisterCallBack("PaintTraverse", draw)
```

  [ **GetInt** ]          
Syntax: Menu.GetInt([Name: string])                       
**Get** integer statement of LUA items and Config items. *Can be Combo Box or Slider Int!*                   
```lua
Menu.AddSliderInt("Slider", 0, 1) 

local function draw()
if Menu.GetInt("Slider") > 0 then
Global.AddLog("This int is currently 1!")
end
else
Global.AddLog("This int is currently 0!")
end

Global.RegisterCallBack("PaintTraverse", draw)
```

  [ **GetFloat** ]                 
Syntax: Menu.GetFloat([Name: string])               
**Get** float statement of LUA items and Config items. *Only Float Slider*.            
```lua
Menu.AddSliderFloat("Slider", 0, 1) 

local function draw()
if Menu.GetFloat("Slider") > 0.1 then
Global.AddLog("This int is currently higher than 0!")
end
else
Global.AddLog("This int is currently 0!")
end

Global.RegisterCallBack("PaintTraverse", draw)
```

  [ **GetColor** ]                      
Syntax: Menu.GetColor([Name: string])                 
**Get** color of LUA items and Config items.               
```lua
local function draw()
local color = Menu.GetColor("Hit list Color")
render.draw_rect_filled(0, 0, 1366, 768, color) 
end

Global.RegisterCallBack("PaintTraverse", draw)
```

  [ **GetKeyState** ]                  
Syntax: Menu.GetKeyState([Keybind: integer])                  
**Get** current state of Keybind.                
```lua
local function draw()
if menu.get_key_bind_state(key_binds.double_tap) then
Global.AddLog("Doubletap is currently active!")
end
end

Global.RegisterCallBack("PaintTraverse", draw)
```

  [ **GetKeyMode** ]                 
Syntax: Menu.GetKeyMode([Keybind: integer])               
**Get** current mode of Keybind.                    
         
**MODE:**          
Hold will return 0.               
Toggle will return 1.          

```lua
local type = Menu.GetKeyMode(key_binds.body_aim)
```

  [ **SetBool** ]              
Syntax: Menu.SetBool([Name: string], [Value: boolean])            
**Force** set boolean of an items.               
```lua
Menu.SetBool("Player.enable", true)  
```

  [ **SetInt** ]               
Syntax: Menu.SetInt([Name: string], [Value: integer])               
**Force** set integer of an items.              
```lua
Menu.SetInt("Esp.viewmodel_fov", 100)  
```

  [ **SetFloat** ]                
Syntax: Menu.SetBool([Name: string], [Value: float])               
**Force** set float of an items.         
```lua
Menu.SetFloat("Esp.aspect_ratio_amount", 2.0)  
```

  [ **SetColor** ]               
Syntax: Menu.SetBool([Name: string], [Value: color])              
**Force** set color of an items.            
```lua
Menu.SetColor("Esp.projectiles_color", Color.new(0, 0, 0, 0))  
```

[back to Contents](#-1)


## <a name="2"></a>Game
|-------------------------------|

  [ **Framerate** ]                    
Syntax: Game.Framerate()                
**Returns** framerate.                 
```lua
Game.Framerate()
```

  [ **Ping** ]       
Syntax: Game.Ping()              
**Returns** ping.       
```lua
Game.Ping()
```

  [ **ServerIPAddress** ]          
Syntax: Game.ServerIPAddress()          
**Returns** Server IP Address.          
```lua
Game.ServerIPAddress()
```

  [ **Time** ]             
Syntax: Game.Time()              
**Returns** windows current time.             
```lua
Game.Time()
```

  [ **Realtime** ]              
Syntax: Game.Realtime()            
**Returns** realtime.          
```lua
Game.Realtime()
```

  [ **Curtime** ]         
Syntax: Game.Curtime()          
**Returns** curtime.             
```lua
Game.Curtime()
```

  [ **Frametime** ]        
Syntax: Game.Frametime()            
**Returns** frametime.               
```lua
Game.Frametime() 
```


  [ **Tickcount** ]        
Syntax: Game.Tickcount()           
**Returns** tickcount.           
```lua
Game.Tickcount()
```

  [ **Framecount** ]             
Syntax: Game.Framecount()             
**Returns** framecount.            
```lua
Game.Framecount()
```

  [ **IntervalPerTick** ]         
Syntax: Game.IntervalPerTick()              
**Returns** interval per tick.                  
```lua
Game.IntervalPerTick()
```

  [ **MaxClients** ]                
Syntax: Game.MaxClients()              
**Returns** max clients.                     
```lua
Game.MaxClients()
```

[back to Contents](#-1)

## <a name="3"></a>Engine
|-------------------------------|

  [ **ScreenWidth** ]               
Syntax: Engine.ScreenWidth()               
**Returns** screen width.                  
```lua
Menu.AddSliderInt("Screen Width", 0, Engine.ScreenWidth())
```

  [ **ScreenHeight** ]          
Syntax: Engine.ScreenHeight()             
**Returns** screen height.           
```lua
Menu.AddSliderInt("Screen Height", 0, Engine.ScreenHeight())
```

  [ **GetPlayerInfo** ]             
Syntax: Engine.GetPlayerInfo([Index: integer])              
**Returns** player info.              
```lua
Engine.GetPlayerInfo()
```

  [ **GetPlayerForUserID** ]                
Syntax: Engine.GetPlayerForUserID([Index: integer])          
**Returns** player for userid.            
```lua
local function draw()
local player = Engine.GetPlayerForUserID(1)
local me = Engine.GetLocalPlayerIndex()
if player == me then
Global.AddLog("I'm local player!")
end
end

Global.RegisterCallBack("PaintTraverse", draw)
```

  [ **GetLocalPlayerIndex** ]          
Syntax: Engine.GetLocalPlayerIndex()              
**Returns** local player index.                     
```lua
local function draw()
local player = Engine.GetPlayerForUserID(1)
local me = Engine.GetLocalPlayerIndex()
if player == me then
Global.AddLog("I'm local player!")
end
end

Global.RegisterCallBack("PaintTraverse", draw)
```

  [ **GetViewAngles** ]             
Syntax: Engine.GetViewAngles()              
**Returns** local player viewangles.            
```lua
local function cm()
local viewangles = Engine.GetViewAngles()
end

Global.RegisterCallBack("CreateMove", cm)
```

  [ **SetViewAngles** ]             
Syntax: Engine.SetViewAngles([Aim_Angles: vector])              
**Sets** local player viewangles.            
```lua
local function cm()
local viewangles = engine.GetViewAngles()
Engine.SetViewAngles(Vector.new(viewangles.x, viewangles.y + 180.0, viewangles.z))
end

Global.RegisterCallBack("CreateMove", cm)
```

  [ **IsInGame** ]              
Syntax: Engine.IsInGame()           
**Returns** true as if we are in game and will return false if we are not.               
```lua
local function draw()
if Engine.IsInGame() then
Global.AddLog("You are in game!")
else
Global.AddLog("You are not in game!")
end

Global.RegisterCallBack("PaintTraverse", draw)
```

  [ **IsConnected** ]              
Syntax: Engine.IsConnected()           
**Returns** true as if we are connected and will return false if we are not.               
```lua
local function draw()
if Engine.IsConnected() then
Global.AddLog("You are in connect!")
else
Global.AddLog("You are not connected!")
end

Global.RegisterCallBack("PaintTraverse", draw)
```

  [ **LevelName** ]          
Syntax: Engine.LevelName()              
**Returns** level name.              
```lua
local function draw()
local font =  Render.CreateFont("Verdana", 12, 600, true, true, true)
Render.DrawText(font, 100, 100, Color.new(255, 0, 0), tostring(Engine.LevelName()))
end

Global.RegisterCallBack("PaintTraverse", draw)
```

  [ **LevelNameShort** ]              
Syntax: Engine.LevelNameShort()           
**Returns** short level name.               
```lua
local function draw()
local font =  Render.CreateFont("Verdana", 12, 600, true, true, true)
Render.DrawText(font, 100, 100, Color.new(255, 0, 0), tostring(Engine.LevelNameShort()))
end

Global.RegisterCallBack("PaintTraverse", draw)
```

  [ **MapGroupName** ]              
Syntax: Engine.MapGroupName()                
**Returns** map group name.                    
```lua
local function draw()
local font =  Render.CreateFont("Verdana", 12, 600, true, true, true)
Render.DrawText(font, 100, 100, Color.new(255, 0, 0), tostring(Engine.MapGroupName()))
end

Global.RegisterCallBack("PaintTraverse", draw)
```

  [ **IsPlayingDemo** ]              
Syntax: Engine.IsPlayingDemo()           
**Returns** true as if we are playing demo and will return false if we are not.               
```lua
local function draw()
if Engine.IsPlayingDemo() then
Global.AddLog("You are playing demo!")
else
Global.AddLog("You are not playing demo!")
end

Global.RegisterCallBack("PaintTraverse", draw)
```

  [ **IsRecordingDemo** ]              
Syntax: Engine.IsRecordingDemo()           
**Returns** true as if we are recording demo and will return false if we are not.               
```lua
local function draw()
if Engine.IsRecordingDemo() then
Global.AddLog("You are recording demo!")
else
Global.AddLog("You are not recording demo!")
end

Global.RegisterCallBack("PaintTraverse", draw)
```

  [ **IsPaused** ]              
Syntax: Engine.IsPaused()           
**Returns** true as if we are pause the game and will return false if we are not.               
```lua
local function draw()
if Engine.IsPaused() then
Global.AddLog("The game is paused!")
else
Global.AddLog("The game is not paused!")
end

Global.RegisterCallBack("PaintTraverse", draw)
```

  [ **IsTakingScreenshot** ]              
Syntax: Engine.IsTakingScreenshot()           
**Returns** true as if we are taking screenshot and will return false if we are not.               
```lua
local function draw()
if Engine.IsTakingScreenshot() then
Global.AddLog("You are taking screenshot!")
else
Global.AddLog("You are not taking screenshot!")
end

Global.RegisterCallBack("PaintTraverse", draw)
```

  [ **IsHLTV** ]              
Syntax: Engine.IsHLTV()           
**Returns** true as if hltv and will return false if it's not.               
```lua
local function draw()
if Engine.IsHLTV() then
Global.AddLog("HLTV!")
else
Global.AddLog("not HLTV!")
end

Global.RegisterCallBack("PaintTraverse", draw)
```

[back to Contents](#-1)


## <a name="4"></a>Render
|-------------------------------|

  [ **WorldToScreen** ]          
Syntax: Render.WorldToScreen([World: Vector])        
**Transform** world position to screen position. *(non-Z)*         
```lua
local function draw()
local font =  Render.CreateFont("Verdana", 12, 600, true, true, true)
local random_origin = Render.WorldToScreen(Vector.new(1400, 600, 200))
Render.DrawText(font, random_origin.x , random_origin.y , Color.new(255, 0, 0), tostring(engine.get_level_name))
end

Global.RegisterCallBack("PaintTraverse", draw)
```

  [ **GetTextWidth** ]
Syntax: Render.GetTextWidth([Font: font], [Text: string])  
**Returns** the width value.
```lua
local function draw()
local font =  Render.CreateFont("Verdana", 12, 600, true, true, true)
local padding = Render.GetTextWidth(font, "Hello")
end

Global.RegisterCallBack("PaintTraverse", draw)
```

  [ **CreateFont** ]          
Syntax: Render.CreateFont([Font Name: string], [Size: float], [Weight: float], [AntiAliasing: boolean], [DropShadow: boolean], [Outline: boolean])        
**Create** font.                    
```lua
local font = Render.CreateFont("Verdana", 12, 500, true, true, true)
```

  [ **DrawText** ]          
Syntax: Render.CreateFont([Font: font], [x: float], [y: float], [Color: color], [Text: string])        
**Draw** text.           
```lua
local font = Render.CreateFont("Verdana", 12, 500, true, true, true)

local function draw()
Render.DrawText(font, 0, 0, Color.new(255, 255, 255), "Hi")
end

Global.RegisterCallBack("PaintTraverse", draw)
```

  [ **DrawCenteredText** ]          
Syntax: Render.DrawCenteredText([Font: font], [x: float], [y: float], [Color: color], [Centered X: boolean], [Centered Y: boolean], [Text: string])        
**Draw** centered text.         
```lua
local function draw()
local font = Render.CreateFont("Verdana", 12, 600, true, true, true)
Render.DrawCenteredText(font, 100, 100, Color.new(255, 0, 0), true, true, "Hello!")
end

Global.RegisterCallBack("PaintTraverse", draw)
```

  [ **DrawLine** ]          
Syntax: Render.DrawLine([X: float], [Y: float], [X2: float], [Y2: float], [Color: color])        
**Draw** line.     
```lua
local function draw()
    Render.DrawLine(10, 10, 150, 150, Color.new(0, 0, 255))
end

Global.RegisterCallBack("PaintTraverse", draw)
```

  [ **DrawRect** ]          
Syntax: Render.DrawRect([X: float], [Y: float], [W: float], [H: float], [Color: color])        
**Draw** rectangle.     
```lua
local function draw() 
Render.DrawRect(10, 10, 100, 100, Color.new(150, 150, 200)) 
end 

Global.RegisterCallBack("PaintTraverse", draw)
```

  [ **DrawFilledRect** ]          
Syntax: Render.DrawRect([X: float], [Y: float], [W: float], [H: float], [Color: color])        
**Draw** filled rectangle.     
```lua
local function draw() 
Render.DrawFilledRect(10, 10, 100, 100, Color.new(150, 150, 200)) 
end 

Global.RegisterCallBack("PaintTraverse", draw)
```

  [ **DrawFilledRectGradient** ]          
Syntax: Render.DrawFilledRectGradient([X: float], [Y: float], [W: float], [H: float], [Color: color], [Color2: color], [GradientType: integer])        
**Draw** gradient filled rectangle.     
```lua
local function draw() 
Render.DrawFilledRectGradient(10, 10, 100, 100, Color.new(150, 150, 200), Color.new(255, 255, 255)) 
end 

Global.RegisterCallBack("PaintTraverse", draw)
```

  [ **DrawCircle** ]          
Syntax: Render.DrawCircle([X: float], [Y: float], [Points: float], [Radius: float], [Color: color])        
**Draw** circle.     
```lua
local function draw() 
Render.DrawCircle(100, 20, 60, 20, Color.new(255, 255, 255)) 
end 

Global.RegisterCallBack("PaintTraverse", draw)
```

  [ **DrawFilledCircle** ]          
Syntax: Render.DrawFilledCircle([X: float], [Y: float], [Points: float], [Radius: float], [Color: color])        
**Draw** circle.     
```lua
local function draw() 
Render.DrawFilledCircle(100, 20, 60, 20, Color.new(255, 255, 255)) 
end 

Global.RegisterCallBack("PaintTraverse", draw)
```

  [ **DrawFilledCircle** ]          
Syntax: Render.DrawTriangle([X: float], [Y: float], [X2: float], [Y2: float], [X3: float], [Y3: float], [Color: color])        
**Draw** filled circle.     
```lua
local function draw() 
Render.DrawTriangle(100, 20, 60, 20, 80, 40, Color.new(255, 255, 255)) 
end 

Global.RegisterCallBack("PaintTraverse", draw)
```

[back to Contents](#-1)

## <a name="5"></a>Console
|-------------------------------|

  [ **Execute** ]
Syntax: Console.Execute([Command: string])    
**Execute** command.      
```lua 
local function shot(Ragebot_info)
    local result = Ragebot_info.result
    if result == "Hit" and Ragebot_info.server_damage >= 100 then
       Console.Execute("say 1")
    end
end

Global.RegisterCallBack("Ragebot_Shot", shot)
```

  [ **GetInt** ]
Syntax: Console.GetInt([Convar Name: string])  
Finds the int value of the given console command.  
**Returns** the value of the parameter or false.  
```lua
local sv_gravity = Console.GetInt("sv_gravity");
```

  [ **GetFloat** ]
Syntax: Console.GetFloat([Convar Name: string])  
Finds the float value of the given console command.  
**Returns** the value of the parameter or false.  
```lua
local host_timescale = Console.GetFloat("host_timescale");
```

  [ **GetString** ]
Syntax: Console.GetString([Convar Name: string])  
Finds the string value of the given console command.  
**Returns** the value of the parameter or false.  
```lua
local bot_kick = Console.GetString("bot_kick");
```

  [ **SetInt** ]
Syntax: Console.GetInt([Convar Name: string])  
Change the int value of the given console command.  
**Returns** the value of the parameter or false.  
```lua
local sv_gravity = Console.GetInt("sv_gravity", 100);
```

  [ **SetFloat** ]
Syntax: Console.GetFloat([Convar Name: string])  
Change the float value of the given console command.  
**Returns** the value of the parameter or false.  
```lua
local host_timescale = Console.GetFloat("host_timescale", 0.1);
```

  [ **SetString** ]
Syntax: Console.GetString([Convar Name: string])  
Change the string value of the given console command.  
**Returns** the value of the parameter or false.  
```lua
local bot_kick = Console.GetString("bot_kick", "all");
```

[back to Contents](#-1)

## <a name="6"></a>Event
|-------------------------------|

  [ **RegisterSelf** ]        
Syntax: Event.RegisterSelf([Event Name: string], [Function: function])            
**Used** to call event functions you write.            
```lua
local function hurt(event)
Global.AddLog("Player hurt")
end

Event.RegisterSelf("player_hurt", hurt)
```

[back to Contents](#-1)

## <a name="7"></a>Entity List
|-------------------------------|

  [ **GetLocalPlayer** ]        
Syntax: EntityList.GetLocalPlayer();     
**Used** to obtain localplayer.      
```lua
local function cm()
local localplayer = EntityList.GetLocalPlayer()
local health = localplayer:GetPropInt("CBasePlayer", "m_iHealth")
end

Global.RegisterCallBack("CreateMove", cm)
```

  [ **GetPlayerByIndex** ]         
Syntax: EntityList.GetPlayerByIndex([Index: integer]);           
**Used** to obtain player from it's index.              
```lua
local function test()
for i = 0, 64 do
local e = EntityList.GetPlayerByIndex(i)
if e ~= nil and e:IsAlive() then
Global.AddLog("index " .. tostring(i) .. " is alive!" )
end
end
end

Global.RegisterCallBack("CreateMove", test)
```

  [ **GetWeaponByPlayer** ]           
Syntax: EntityList.GetWeaponByPlayer([Player: entity]);      
**Used** to obtain gun from a player.          
```lua
local function test()
for i = 0, 64 do
local e = EntityList.GetPlayerByIndex(i)
if e ~= nil and e:IsAlive() then
local weapon = EntityList.GetWeaponByPlayer(e)
local weapon_name = weapon:GetPropInt("CWeaponCSBaseGun", "m_iClip1")
Global.AddLog("index " .. tostring(i) .. " has" .. "ammo!")
end
end
end

Global.RegisterCallBack("CreateMove", test)
```

[back to Contents](#-1)

## <a name="8"></a>User CMD
|-------------------------------|

  [ **GetSendPacket** ]     
Syntax: UserCMD.GetSendPacket()       
**Used** to get send packet.         
```lua
UserCMD.GetSendPacket()
```

  [ **SetSendPacket** ]
Syntax: UserCMD.SetSendPacket([SendPacket: boolean])  
**Used** to force send packet to desired value.    
```lua
UserCMD.SetSendPacket(15)
```

  [ **GetChoke** ]
Syntax: UserCMD.GetChoke()  
**Used** to get current choked commands number. 
```lua
UserCMD.GetChoke()  
```

  [ **GetButton** ]
Syntax: UserCMD.GetButton([Button: integer])  
**Used** to get current active button. (ex: IN_ATTACK) 
```lua
local function attack()
if UserCMD.GetButton(Buttons.IN_ATTACK) then
Global.AddLog("You are currently holding attack button!")
end

Global.RegisterCallBack("CreateMove", attack)
```

  [ **SetButton** ]
Syntax: UserCMD.SetButton()  
**Used** to set buttons. 
```lua
local function attack()
  UserCMD.SetButton(Buttons.in_duck, true)
end

Global.RegisterCallBack("CreateMove", attack)
```


[back to Contents](#-1)

## <a name="9"></a>Utils
|-------------------------------|


  [ **FindSignature** ]
Syntax: Utils.FindSignature([Module: string], [Signature: string]);  
**Used** to find signature.  
```lua
local ffi = require("ffi")

ffi.cdef[[
typedef int(__fastcall* clantag_t)(const char*, const char*);
]]

local fn_change_clantag
local set_clantag

local function clantag()
  if (fn_change_clantag == nil) then
    fn_change_clantag = Utils.FindSignature("engine.dll", "53 56 57 8B DA 8B F9 FF 15")
  end

  if ((set_clantag == nil) and (fn_change_clantag ~= nil)) then
     set_clantag =  ffi.cast("clantag_t", fn_change_clantag)
  end

  local choke = cmd.get_choke()

  if (choke == 0) then
    set_clantag("132", "312")
  end
end

Global.RegisterCallBack("on_createmove", clantag)
```

[back to Contents](#-1)


## <a name="q"></a>Indicators
|-------------------------------|

  [ **Add** ]       
Syntax: Indicators.Add([Text: string], [Color: color])       
**Add** new items on indicators.      
```lua
Indicators.Add("HEY", Color.new(255, 255, 255))
```

  [ **AddWithPosition** ]
Syntax: Indicators.AddWithPosition([Text: string], [Color: color], [Position: integer])  
**Add** new items on indicators with position. 
```lua
Indicators.AddWithPosition("Hello World", Color.new(255, 255, 255), 15)  
```

[back to Contents](#-1)


## <a name="w"></a>HTTP
|-------------------------------|

  [ **Get** ]
Syntax: HTTP.Get([Link: string])  
**Get** request.
```lua
HTTP.Get("www.example.com")  
```


  [ **Post** ]
Syntax: HTTP.Post([Link: string], [Parameters: string])  
**Post** request.
```lua
HTTP.Get("www.example.com", "") 
```

[back to Contents](#-1)
