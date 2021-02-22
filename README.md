# catwareLUA

**CREDIT TO 
https://github.com/ZaUserA**

<a name="-1"></a>

|Contents|
|--------|
|[Global](#0)|
|[Menu](#1)|
|[Game](#2)|
|[Render](#3)|
|[Convar](#4)|
|[Event](#5)|
|[Trace](#6)|
|[User CMD](#7)|
|[Sound](#8)|
|[Local](#9)|
|[Cheat](#q)|
|[Input](#w)|
|[World](#e)|
|[AntiAim](#r)|
|[Exploit](#a)|
|[RageBot](#s)|
|[Material](#d)|

---

## <a name="0"></a>Global
|-------------------------------|

[ **RegisterCallBack** ]
Usage: Global.RegisterCallBack([EventName: string, Function: string])  
Used to call the functions you write.
```lua
local function paint_traverse()
Render.DrawText(font, 0, 0, color.new(255, 255, 255, 255), "Hi")
end

Global.RegisterCallBack("PaintTraverse", paint_traverse)
```

[ **LoadLUA** ]
Usage: Global.LoadLUA([Name: string])  
Used to load another LUA you type inside of LoadLUA.
```lua
Global.LoadLUA("HitList")
```

[ **UnloadLUA** ]
Usage: Global.UnloadLUA([Name: string])  
Used to unload another LUA you type inside of UnloadLUA
```lua
Global.UnloadLUA("HitList")
```

[ **AddLog** ]
Usage: Global.AddLog([Text: string])  
Add the text you write inside AddLog into the cheat eventlogger
```lua
local function paint_traverse()
Global.AddLog("Hi from the event logger")
end

Global.RegisterCallBack("PaintTraverse", paint_traverse)
```

[ **Username** ]
Syntax: Global.Username
Used to get forum username.
```lua
Global.Username()
```

[back to Contents](#-1)

## <a name="1"></a>Menu
|-------------------------------|

  [ **IsVisible** ]
Syntax: Menu.IsVisible() 
True if the menu is open, false otherwise. 
```lua
if (Menu.IsVisible() == true)
Global.AddLog("Menu is open!")
end
```

  [ **NextLine** ]
Syntax: Menu.NextLine()   
Skip last menu line.
```lua
Menu.AddCheckbox("Enable Hit list") // this will be skipped
Menu.AddCheckbox("Enable Spectator List") // this is from another LUA.
Menu.NextLine()   
menu.AddColorPicker("Hit list Color")
```

  [ **AddCheckBox** ]
Syntax: Menu.AddCheckBox([Name: string])   
Create a checkbox in LUA tab.
```lua
Menu.AddCheckBox("Checkbox")   
```

  [ **AddComboBox** ]
Syntax: Menu.AddComboBox([Name: string], [Labels: string vector])   
Create a combobox in LUa tab. 
```lua
Menu.AddComboBox("Combobox", { "Selection 1", "Selection 2" })   
```


  [ **AddSliderInt** ]
Syntax: Menu.AddSliderInt([Name: string], [Min: integer], [Max: integer])    
Create a slider (integer).  
```lua
Menu.AddSliderInt("Int", 0, 100) 
```

  [ **AddSliderFloat** ]
Syntax: Menu.AddSliderFloat([Name: string], [Min: float], [Max: float])
Create a slider (float). 
```lua
Menu.AddSliderFloat("Float", 0.0, 100.0) 
```

  [ **AddColorPicker** ]
Syntax: Menu.AddColorPicker([Name: string])  
Create a Color Picker.
```lua
Menu.AddColorPicker("Color Picker") 
```

  [ **GetBool** ]
Syntax: Menu.GetBool([Name: string])  
Get bool statement of LUA item and Config items.  
```lua
Menu.AddCheckBox("Checkbox") 

local function paint_traverse()
if Menu.GetBool("Checkbox") then
Global.AddLog("This bool is currently active!")
end
else
Global.AddLog("This bool is currently disabled!")
end

Global.RegisterCallBack("PaintTraverse", paint_traverse)
```

  [ **GetInt** ]
Syntax: Menu.GetInt([Name: string])  
Get integer statement of LUA items and Config items. Can be Combo Box or Slider Int!  
```lua
Menu.AddSliderInt("Slider", 0, 1) 

local function paint_traverse()
if Menu.GetInt("Slider") > 0 then
Global.AddLog("This int is currently 1!")
end
else
Global.AddLog("This int is currently 0!")
end

Global.RegisterCallBack("PaintTraverse", paint_traverse)
```

  [ **GetFloat** ]
Syntax: Menu.GetFloat([Name: string])  
Get float statement of LUA items and Config items. Only Float Slider.  
```lua
Menu.AddSliderFloat("Slider", 0, 1) 

local function paint_traverse()
if Menu.GetFloat("Slider") > 0.1 then
Global.AddLog("This int is currently higher than 0!")
end
else
Global.AddLog("This int is currently 0!")
end

Global.RegisterCallBack("PaintTraverse", paint_traverse)
```

  [ **GetColor** ]
Syntax: Menu.GetColor([Name: string])  
Get color of LUA items and Config items.
```lua
local function paint_traverse()
local color = Menu.GetColor("Hit list Color")
render.draw_rect_filled(0, 0, 1366, 768, color) 
end

Global.RegisterCallBack("PaintTraverse", paint_traverse)
```

  [ **GetKeyState** ]
Syntax: Menu.GetKeyState([Keybind: integer])
Get current state of Keybind.   
```lua
local function paint_traverse()
if menu.get_key_bind_state(key_binds.double_tap) then
Global.AddLog("Doubletap is currently active!")
end
end

Global.RegisterCallBack("PaintTraverse", paint_traverse)
```

  [ **GetKeyMode** ]
Syntax: Menu.GetKeyMode([Keybind: integer])
Get current mode of Keybind. 

**MODE:**
Hold will return 0.
Toggle will return 1.

```lua
local type = Menu.GetKeyMode(key_binds.body_aim)
```

  [ **SetBool** ]
Syntax: Menu.SetBool([Name: string], [Value: boolean])  
Force set boolean of an items.
```lua
Menu.SetBool("Player.enable", true)  
```

  [ **SetInt** ]
Syntax: Menu.SetInt([Name: string], [Value: integer])  
Force set integer of an items.
```lua
Menu.SetInt("Esp.viewmodel_fov", 100)  
```

  [ **SetFloat** ]
Syntax: Menu.SetBool([Name: string], [Value: float])  
Force set float of an items.
```lua
Menu.SetFloat("Esp.aspect_ratio_amount", 2.0)  
```

  [ **SetColor** ]
Syntax: Menu.SetBool([Name: string], [Value: color])  
Force set color of an items.
```lua
Menu.SetColor("Esp.projectiles_color", color.new(0, 0, 0, 0))  
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

## <a name="3"></a>RENDER
|-------------------------------|

  [ **FILLEDCIRCLE** ]
Syntax:Render.FilledCircle(x, y, r, color)  
Draws a filled circle with the given position, radius, and RGBA color.  
**Returns**  true on success or false on failure.  
```java
function drawCircle()
{
   Render.FilledCircle( 150, 150, 50, [ 255, 255, 255, 255 ] );
}

Cheat.RegisterCallback("Draw", "drawCircle")
// This function will draw filled circle on screen.
```

  [ **TEXTUREDRECT** ]
Syntax:Render.TexturedRect( x, y, width, height, texture );    
Draws a textured rectangle with the given position, size, and texture.  
**Returns**  true on success or false on failure.  
```java
function drawTexture()
{
    forumBG = Render.AddTexture("ot/scripts/forumclr.png");
    Render.TexturedRect( 300, 300, 100, 100, forumBG );
}
Cheat.RegisterCallback("Draw", "drawTexture");
```

  [ **TEXTUREDRECT** ]
Syntax:Render.TexturedRect( x, y, width, height, texture );    
Draws a textured rectangle with the given position, size, and texture.  
**Returns**  true on success or false on failure.  
```java
function drawTexture()
{
    forumBG = Render.AddTexture("ot/scripts/forumclr.png");
    Render.TexturedRect( 300, 300, 100, 100, forumBG );
}
Cheat.RegisterCallback("Draw", "drawTexture");
```

  [ **ADDTEXTURE** ]
Syntax:Render.AddTexture( path );    
Adds a texture.  
**Returns** texture identifier.  

**Notes:**
- Path is relative to CSGO folder, so you don't need full path.  
- Supports the following formats:  
.bmp  
.dds  
.dib  
.hdr  
.jpg  
.pfm  
.png  
.ppm  
.tga  

```java
function drawTexture()
{
    forumBG = Render.AddTexture("ot/scripts/forumclr.png");
    Render.TexturedRect( 300, 300, 100, 100, forumBG );
}
Cheat.RegisterCallback("Draw", "drawTexture");
```


  [ **TEXTSIZECUSTOM** ]
Syntax:Render.TextSizeCustom( string text, font );  
Finds the text width size of the given string with custom font.  
**Returns** given text height and width.  
```java
function getTextSize()
{
    font = Render.AddFont( "Comic Sans MS", 15, 400);
    textSize = Render.TextSizeCustom("Hello", font);
    Cheat.Print("Text width: " + textSize[0] + "height: " + textSize[1] + "\n");
}

Cheat.RegisterCallback("Draw", "getTextSize")
```

  [ **STRINGCUSTOM** ]
Syntax:Render.StringCustom( int x, int y, int align, string text, [ color ], font )  
Draws a string with custom font.  
**Returns** true on success or false on failure.  
```java
function comicSans()
{
    font = Render.AddFont( "Comic Sans MS", 15, 100);
    Render.StringCustom( 100, 100, 0, "This is Comic Sans Text", [ 255, 255, 255, 255 ], font );
   
}
Cheat.RegisterCallback("Draw", "comicSans")
```
  [ **FINDFONT** ]
Syntax:Render.FindFont( string name, int size, int weight );  
Searches for custom font.  
**Returns** font identifier.  
```java
function getIdentifier()
{
    font = Render.AddFont( "Comic Sans MS", 15, 100);
    identifier = Render.FindFont( "Comic Sans MS", 15, 100 );
    Cheat.Print("Font identifier is: " + identifier + "\n");
   
}
Cheat.RegisterCallback("Draw", "getIdentifier")
```

  [ **ADDFONT** ]
Syntax:Render.AddFont( string name, int size, int weight );  
Adds a custom font.  
**Returns** font identifier.  

Argument weight defines from thickness.
100	Lightest.
200	Bolder than 100, lighter than 300.
300	Bolder than 200, lighter than 400.
400	Bolder than 300, lighter than 500. Equivalent of normal.
500	Bolder than 400, lighter than 600.
600	Bolder than 500, lighter than 700.
700	Bolder than 600, lighter than 800. Equivalent of bold.
800	Bolder than 700, lighter than 900.
900	Boldest.

```java
function comicSans()
{
    font = Render.AddFont( "Comic Sans MS", 15, 100);
    Render.StringCustom( 100, 100, 0, "This is Comic Sans Text", [ 255, 255, 255, 255 ], font );
   
}
Cheat.RegisterCallback("Draw", "comicSans")
```

  [ **FINDFONT** ]
Syntax:Render.FindFont( string name, int size, int weight );  
Searches for custom font.  
**Returns** font identifier.  
```java
function getIdentifier()
{
    font = Render.AddFont( "Comic Sans MS", 15, 100);
    identifier = Render.FindFont( "Comic Sans MS", 15, 100 );
    Cheat.Print("Font identifier is: " + identifier + "\n");
   
}
Cheat.RegisterCallback("Draw", "getIdentifier")
```


  [ **POLYGON** ]
Syntax:Render.Polygon( [ [ x, y ], [ x1, y1 ], [ x2, y2 ] ], [ R, G, B, A ] );  
Draws a polygon with shape based on arguments passed.  
```java
function drawPolygon()
{
    Render.Polygon( [ [ 10.0, 200.0 ], [ 100.0, 10.0 ], [ 200.0, 160.0 ] ], [ 255, 0, 0, 255 ] );
}
Cheat.RegisterCallback("Draw", "drawPolygon");
```

  [ **GRADIENTRECT** ]
Syntax:Render.GradientRect( x, y, w, h, dir, [ col1 ], [ col2 ] );  
Draws a gradient rectangle with the given position, size, and RGBA color.  
**Returns** true on success or false on failure.  
```java
function drawGradient()
{

    Render.GradientRect( 100, 100, 100, 100, 0, [ 255, 0, 0, 255 ], [ 255, 255, 255, 255 ]);
    Render.GradientRect( 210, 100, 100, 100, 1, [ 255, 0, 0, 255 ], [ 255, 255, 255, 255 ]);
}
Cheat.RegisterCallback("Draw", "drawGradient")
```

  [ **TEXTSIZE** ]
Syntax:Render.TextSize(string, int size [optional]);  
Finds the text width size of the given string.  
**Returns** 0 - default, 1 - bold, 2 - small, 3 - small bold, 4 - large, 5 - icon, 6 - small icon, 8 to 48 regular font with specific size.  
```java
var text_width = Render.TextSize("Hello");
var screen_size = Global.GetScreenSize();
var screen_height = screen_size[0];
var screen_width = screen_size[1];

Render.String( screen_width - text_width[1], 100, 0, "Hello", [255, 255, 255, 255], 4 );
```

  [ **GETSCREENSIZE** ]
Syntax:Render.GetScreenSize()  
Returns width and height of your screen.  
```java
function getScreenSize()
{
    var screen_size = Render.GetScreenSize();
    Cheat.Print( "Height of screen is: " + screen_size[0] + "\n");
    Cheat.Print( "Width of screen is: " + screen_size[1] + "\n");
}
Cheat.RegisterCallback("Draw", "getScreenSize")
// This function will print your screen height and width in in-game console.
```

  [ **WORLDTOSCREEN** ]
Syntax:Render.WorldToScreen([x, y, z])  
Finds the world position for the given screen position.  
Returns the value of the parameter or false.  
```java
function drawDuckAmount( )
{
    players = Entity.GetEnemies( );

    for ( i = 0; i < players.length; i++ )
    {
      if ( Entity.IsAlive( players[i] ) )
      {
        world = Entity.GetRenderOrigin( players[i] );

        screen_bot = Render.WorldToScreen( world );

        duckamount = Entity.GetProp( players[i], "DT_BasePlayer", "m_flDuckAmount" );
    
        world_top = world;
        world_top[2] = world_top[2] + ( 64 * ( 1 - duckamount ) );

        screen_top = Render.WorldToScreen( world_top );
      
        if ( screen_bot[2] == 1 && screen_top[2] == 1 )
        {
            Render.Line( screen_bot[0], screen_bot[1], screen_top[0], screen_top[1], [ 0, 0, 255, 255 ] );
        }
    }
  }
}
Cheat.RegisterCallback("Draw", "drawDuckAmount");
// This script will draw a line on enemy players which represents their duck amount.
```


  [ **CIRCLE** ]
Syntax:Render.Circle(x, y, r, color)  
Draws a circle with the given position, radius, and RGBA color.  
**Returns** true on success or false on failure.  
```java
function drawCircle()
{
   Render.Circle( 150, 150, 50, [ 255, 255, 255, 255 ] );
}

Cheat.RegisterCallback("Draw", "drawCircle")
// This function will draw a circle on screen.
```

  [ **FILLEDRECT** ]
Syntax:Render.FilledRect(x, y, width, height, color)  
Draws a circle with the given position, radius, and RGBA color.  
**Returns** true on success or false on failure.   
```java
function drawFilledRect()
{
Render.FilledRect( 100, 100, 150, 150, [ 255, 0, 0, 180 ] );
}

Cheat.RegisterCallback("Draw", "drawFilledRect")
// This function will draw a filled rectangle on screen.
```

  [ **RECT** ]
Syntax:Render.Rect(x, y, width, height, color)  
Draws a rectangle with the given position, size, and RGBA color.    
**Returns** true on success or false on failure.  
```java
function drawRect()
{
Render.Rect( 100, 100, 150, 150, [ 255, 0, 0, 255 ] );
}

Cheat.RegisterCallback("Draw", "drawRect")
// This function will draw a rectangle on screen.
```

  [ **LINE** ]
Syntax:Render.Line(x, y, x1, y1, color)  
Draws a line with the given position RGBA color.    
**Returns** true on success or false on failure.  
```java
function drawLine()
{
Render.Line( 100, 200, 300, 200, [ 255, 0, 0, 255 ] );
}

Cheat.RegisterCallback("Draw", "drawLine")
// This function will draw a line on your screen.
```

  [ **STRING** ]
Syntax:Render.String(x, y, align, message, color, int size [optional])  
Draws a string with the given position, align, RGBA color, and size.  
**Returns** true on success or false on failure.  

**Size values**  
0 - default font  
1 - bold font  
2 - small font  
3 - small bold font  
4 - BIG font  
5 - icons  
6 - small icons  
even numbers from 8 to 48 are regular font with a more specific size  


```java
function drawString()
{
Render.String( 100, 100, 0, "Hello", [ 255, 255, 255, 255 ] );
}

Cheat.RegisterCallback("Draw", "drawString")
// This script will draw a string Hello on your screen
```

[back to Contents](#-1)


## <a name="4"></a>Convar
|-------------------------------|

  [ **SETSTRING** ]
Syntax:Convar.SetString("cmd", string)  
Sets the string value of the given console command.      
**Returns** true on success or false on failure.  
```java
Convar.SetString ("r_aspectratio", "1");
```

  [ **GETSTRING** ]
Syntax:Convar.GetString("cmd")  
Finds the string value of the given console command.   
**Returns** the value of the parameter or false.   
```java
var name = Convar.GetString("name");
Cheat.Print(name);
```

  [ **SETFLOAT** ]
Syntax:Convar.SetFloat ("cmd", value)  
Sets the float value of the given console command.  
**Returns** true on success or false on failure.  
```java
Convar.SetFloat("cl_ragdoll_gravity", 100.00);
```

  [ **GETFLOAT** ]
Syntax:Convar.GetFloat("cmd")   
Finds the float value of the given console command.  
**Returns** the value of the parameter or false.  
```java
var sv_gravity_value = Convar.GetFloat("cl_ragdoll_gravity");
Cheat.Print(sv_gravity_value);
```

  [ **SETINT** ]
Syntax:Convar.SetInt("cmd", value)  
Sets the integer value of the given console command.  
**Returns** true on success or false on failure.  
```java
Convar.SetInt("cl_ragdoll_gravity", 100);
```

  [ **GETINT** ]
Syntax:Convar.GetInt("cmd")
Finds the integer value of the given console command.  
**Returns** the value of the parameter or false.   
```java
var sv_gravity_value = Convar.GetInt("cl_ragdoll_gravity");
Cheat.Print(sv_gravity_value);
```

[back to Contents](#-1)

## <a name="5"></a>Event
|-------------------------------|

  [ **RAGEBOT_FIRE** ]
Syntax:ragebot_fire  
**Returns** information on ragebot_fire event.  

Following arguments can be used with Event.GetInt for the ragebot_fire event  
target_index  
hitbox  
hitchance  
safepoint  
exploit  
0 = no exploit    
1 = hide shots/1st shot from doubletap  
2 = second shot from doubletap  

```java
function getHitboxName(index)
{
    var hitboxName = "";
    switch (index)
    {
        case 0:
            hitboxName = "Head";
            break;
        case 1:
            hitboxName = "Neck";
            break;
        case 2:
            hitboxName = "Pelvis";
            break;
        case 3:
            hitboxName = "Body";
            break;
        case 4:
            hitboxName = "Thorax";
            break;
        case 5:
            hitboxName = "Chest";
            break;
        case 6:
            hitboxName = "Upper chest";
            break;
        case 7:
            hitboxName = "Left thigh";
            break;
        case 8:
            hitboxName = "Right thigh";
            break;
        case 9:
            hitboxName = "Left calf";
            break;
        case 10:
            hitboxName = "Right calf";
            break;
        case 11:
            hitboxName = "Left foot";
            break;
        case 12:
            hitboxName = "Right foot";
            break;
        case 13:
            hitboxName = "Left hand";
            break;
        case 14:
            hitboxName = "Right hand";
            break;
        case 15:
            hitboxName = "Left upper arm";
            break;
        case 16:
            hitboxName = "Left forearm";
            break;
        case 17:
            hitboxName = "Right upper arm";
            break;
        case 18:
            hitboxName = "Right forearm";
            break;
        default:
            hitboxName = "Generic";
    }

    return hitboxName;
}
function ragebotLogs()
{
  
    ragebot_target = Event.GetInt("target_index");
    ragebot_target_hitbox = Event.GetInt("hitbox");
    ragebot_target_hitchance = Event.GetInt("hitchance");
    ragebot_target_safepoint = Event.GetInt("safepoint");
    ragebot_target_exploit = Event.GetInt("exploit");
    targetName = Entity.GetName(ragebot_target);
  
    Cheat.Print("[onetap] TARGET: " + targetName + " HITBOX: " + getHitboxName(ragebot_target_hitbox) + " HC: " + ragebot_target_hitchance + " SAFEPOINT: " + ragebot_target_safepoint + " EXPLOIT: " + ragebot_target_exploit + " \n");

}

Cheat.RegisterCallback("ragebot_fire", "ragebotLogs");
```

  [ **GETSTRING** ]
Syntax:Event.GetString(string)
Finds the string value of the given game event.  
**Returns** the value of the parameter or false.   
```java
var weapon_name = Event.GetString("weaponname");
```

  [ **GETFLOAT** ]
Syntax:Event.GetFloat(float)  
Finds the float value of the given game event.  
**Returns** the value of the parameter or false.  
```java
pos_x = Event.GetFloat("x");
```

  [ **GETINT** ]
Syntax:Event.GetInt(int)  
Finds the int value of the given game event.  
**Returns** the value of the parameter or false.  
```java
userid = Event.GetInt("userid");
```

[back to Contents](#-1)

## <a name="6"></a>Trace
|-------------------------------|

  [ **RAWLINE** ]
Syntax:Trace.RawLine( int skip_index, vec3 start, vec3 end, unsigned int mask, int type )  
Used for advanced line tracing.  
**Returns** entity index and number fraction.  
**Fraction info:**  
1.0 means it didnt hit anything, 0.5 means it hit something half way through, 0.1 is hit  
**Skip index:**  
skips a certain entity, can be 0 to not skip any entity.  
**Mask:**  
filters what should and shouldn't be taken into consideration when tracing  
masks can be combined, example below:  
A bullet would be 0x4600400b ( CONTENTS_SOLID + CONTENTS_WINDOW + CONTENTS_GRATE + CONTENTS_MOVEABLE + CONTENTS_MONSTER + CONTENTS_DEBRIS + CONTENTS_HITBOX )  
**Type:**  
0 = TRACE_EVERYTHING  
1 = TRACE_WORLD_ONLY  
2 = TRACE_ENTITIES_ONLY  
```java
  CONTENTS_SOLID                    0x1
        CONTENTS_WINDOW                       0x2
        CONTENTS_AUX                      0x4
        CONTENTS_GRATE                      0x8
        CONTENTS_SLIME                      0x10
        CONTENTS_WATER                      0x20
        CONTENTS_BLOCKLOS                  0x40
        CONTENTS_OPAQUE                      0x80
        CONTENTS_TESTFOGVOLUME              0x100
        CONTENTS_UNUSED                      0x200
        CONTENTS_BLOCKLIGHT                  0x400
        CONTENTS_TEAM1                      0x800
        CONTENTS_TEAM2                      0x1000
        CONTENTS_IGNORE_NODRAW_OPAQUE     0x2000
        CONTENTS_MOVEABLE                  0x4000
        CONTENTS_AREAPORTAL                  0x8000
        CONTENTS_PLAYERCLIP                  0x10000
        CONTENTS_MONSTERCLIP              0x20000
        CONTENTS_ORIGIN                      0x1000000
        CONTENTS_MONSTER                  0x2000000
        CONTENTS_DEBRIS                      0x4000000
        CONTENTS_DETAIL                      0x8000000
        CONTENTS_TRANSLUCENT              0x10000000
        CONTENTS_LADDER                      0x20000000
        CONTENTS_HITBOX                      0x40000000
```


 **IN OT V3 CRACK NOT WORKS** [ **SMOKE** ]
Syntax:Trace.Smoke(array start, array end)  
Used to check if smoke is between two points.  
**Returns** 1 if there was smoke.  
```java
function isBehindSmoke(entity_index)
{
    eyepos = Entity.GetEyePosition(Entity.GetLocalPlayer());
        if (Entity.IsValid(entity_index) && Entity.IsAlive(entity_index) && !Entity.IsDormant(entity_index)){
            hitbox_pos = Entity.GetHitboxPosition(entity_index, 0);
            result = Trace.Smoke(eyepos, hitbox_pos);
                if (result == 1)
                {
                    return true
                }
                else
                {
                    return false
                }
        }       
}
function main()
{
    enemies = Entity.GetEnemies()
    for (i=0; i < enemies.length; i++)
    {
        if (isBehindSmoke(enemies[i]))
        {
            Cheat.Print("Enemy: " + Entity.GetName(enemies[i])+ " is behind smoke\n")
        }
    }
}
Cheat.RegisterCallback("CreateMove", "main");
```


  [ **BULLET** ]
Syntax:Trace.Bullet(int ent_index, int target, array start, array end);  
Used to trace bullet between two entities.  
**Returns** entity index, damage, visibility, and hitbox.  
```java
function isVisible()
{

    localPlayer_index = Entity.GetLocalPlayer();
    localPlayer_eyepos = Entity.GetEyePosition(localPlayer_index);
    enemies = Entity.GetEnemies();
    for ( i = 0; i < enemies.length; i++)
    {
        if (Entity.IsValid(enemies[i]) == true && Entity.IsAlive(enemies[i]) && Entity.IsDormant(enemies[i]) == false)
        {
        hitbox_pos = Entity.GetHitboxPosition(localPlayer_index, 0);
        bot_eyepos = Entity.GetEyePosition(enemies[i])
        
        w2s_s = Render.WorldToScreen(bot_eyepos)
        w2s_e = Render.WorldToScreen(hitbox_pos)
        Render.Line(w2s_s[0], w2s_s[1], w2s_e[0], w2s_e[1], [255, 255, 255, 255])
        Render.String(w2s_s[0], w2s_s[1], 0, "START", [255, 0, 0, 255])
        Render.String(w2s_e[0], w2s_e[1], 0, "END", [255, 0, 0, 255])
        }
    }
}

function cm()
{
    localPlayer_index = Entity.GetLocalPlayer();
    localPlayer_eyepos = Entity.GetEyePosition(localPlayer_index);
    enemies = Entity.GetEnemies();
    for ( i = 0; i < enemies.length; i++)
    {
       if (Entity.IsValid(enemies[i]) == true && Entity.IsAlive(enemies[i]) && Entity.IsDormant(enemies[i]) == false)
        {
        hitbox_pos = Entity.GetHitboxPosition(localPlayer_index, 0);
        bot_eyepos = Entity.GetEyePosition(enemies[i])
        result = Trace.Bullet(enemies[i], localPlayer_index, bot_eyepos, hitbox_pos);
        Cheat.Print("Trace result:: " + Entity.GetName(enemies[i]) + " can see player: " + Entity.GetName(result[0]) + " damage:: " + result[1] + " visible:: " + result[2] + " hitbox :: " + result[3] + "\n")
        }
    }

}
Cheat.RegisterCallback("Draw", "isVisible");
Cheat.RegisterCallback("CreateMove", "cm");
```

  [ **LINE** ]
Syntax:Trace.Line(int ent_index, array start, array end);  
Used to trace line between point A and B.  
**Returns** entity index and number fraction.  
Fraction info: 1.0 means it didnt hit anything, 0.5 means it hit something half way through, 0.1 is hit  
```java
function isVisible()
{

    localPlayer_index = Entity.GetLocalPlayer();
    localPlayer_eyepos = Entity.GetEyePosition(localPlayer_index);
    enemies = Entity.GetEnemies();
    for ( i = 0; i < enemies.length; i++)
    {
        hitbox_pos = Entity.GetHitboxPosition(enemies[i], 0);
        result = Trace.Line(localPlayer_index, localPlayer_eyepos, hitbox_pos);
        Cheat.Print("Entity: " + Entity.GetName(result[0]) + " fraction: " + result[1] + "\n");
    }

}

Cheat.RegisterCallback("Draw", "isVisible");
// This function will trace line from localplayer eye position to enemy head hitbox position and return whether the enemy is visible or not.
```


[back to Contents](#-1)

## <a name="7"></a>UserCMD
|-------------------------------|


  [ **GETMOVEMENT** ]
Syntax:UserCMD.GetMovement();  
Used to obtain movement values.  
**Returns** an array object with forward move, side move, and up move.  
```java
function onCreateMove()
{
    var movement = UserCMD.GetMovement();

    forward = movement[0];
    side = movement[1];
    up = movement[2];

    Cheat.Print("Forward: " + forward + "\nSide: " + side + "\nUp: " +  up + "\n");
}
Cheat.RegisterCallback("CreateMove", "onCreateMove");
```


**IN OT V3 CRACK NOT WORKS**  [ **SETVIEWANGLES** ]
Syntax:UserCMD.SetViewAngles( [x,y,z], bool silent );  
Control user angles.  
```java
function setAngle()
{
    curAngle = Local.GetViewAngles();
    UserCMD.SetViewAngles([curAngle[0], 180, curAngle[2]], true) ;
}
Cheat.RegisterCallback("CreateMove", "setAngle");
```

**IN OT V3 CRACK NOT WORKS**  [ **SEND** ]
Syntax:UserCMD.Send()  
Please note that this function may be overruled by internal processing related to, but not limited to, shot handling, anti-aim, and exploits.

**IN OT V3 CRACK NOT WORKS**  [ **CHOKE** ]
Syntax:UserCMD.Choke()  
Please note that this function may be overruled by internal processing related to, but not limited to, shot handling, anti-aim, and exploits.


**IN OT V3 CRACK NOT WORKS**  [ **SETBUTTONS** ]
Syntax:UUserCMD.SetButtons();  
Used to set buttons.  
```java
function forceJump()
{
    var buttons = UserCMD.GetButtons();
    UserCMD.SetButtons(buttons | (1 << 1));
    
}
Cheat.RegisterCallback("CreateMove", "forceJump")
```


**IN OT V3 CRACK NOT WORKS**  [ **SETBUTTONS** ]
Syntax:UserCMD.GetButtons();  
Used to set buttons.  
**Returns** buttons.  
```java
function forceJump()
{
    var buttons = UserCMD.GetButtons();
    UserCMD.SetButtons(buttons | (1 << 1));
    
}
Cheat.RegisterCallback("CreateMove", "forceJump")
```

  [ **SETMOVEMENT** ]
Syntax:UserCMD.SetMovement([forwardmove, sidemove, upmove]);  
Control user movement.  
```java
function moveForward()
{
    UserCMD.SetMovement( [ 450, 0, 0 ] );
}
Cheat.RegisterCallback("CreateMove", "moveForward");
```

[back to Contents](#-1)

## <a name="8"></a>Sound
|-------------------------------|

  [ **STOPMICROPHONE** ]
Syntax:Sound.StopMicrophone( );  
Used to stop Sound.PlayMicrophone  
```java
Sound.StopMicrophone( );
```

  [ **PLAYMICROPHONE** ]
Syntax:Sound.PlayMicrophone(path)  
Plays a sound on microphone.  
```java
Sound.PlayMicrophone(path);
```

  [ **PLAY** ]
Syntax:Sound.Play( string path )  
Plays a sound.  
```java
function playSoundOnKill()
{
    localplayer_index = Entity.GetLocalPlayer();
    attacker = Event.GetInt("attacker");
    attacker_index = Entity.GetEntityFromUserID(attacker);

    if (attacker_index == localplayer_index)
    {
        Sound.Play("C:\\Program Files (x86)\\Steam\\steamapps\\common\\Counter-Strike Global Offensive\\ot\\scripts\\headshot.wav");
    }

}

Cheat.RegisterCallback("player_death", "playSoundOnKill");
```


[back to Contents](#-1)

## <a name="9"></a>Local
|-------------------------------|


  [ **GETINACCURACY** ]
Syntax:Local.GetInaccuracy();  
**Returns** inaccuracy.  
```java
inaccuracy = Local.GetInaccuracy();
Cheat.Print(inaccuracy + "\n");
```

  [ **GETSPREAD** ]
Syntax:Local.GetSpread();  
**Returns** spread.  
```java
spread = Local.GetSpread();
Cheat.Print(spread + "\n");
```

  [ **GETFAKEYAW** ]
Syntax:Local.GetFakeYaw();   
**Returns** fake yaw angle.  
```java
fakeyaw = Local.GetFakeYaw();
Cheat.Print(fakeyaw + "\n");
```

  [ **GETREALYAW** ]
Syntax:Local.GetRealYaw();  
**Returns** real yaw angle.   
```java
realyaw = Local.GetRealYaw();
Cheat.Print(realyaw + "\n");
```

  [ **SETCLANTAG** ]
Syntax:Local.SetClanTag(string text);    
```java
Local.SetClanTag("onetap.su");
```

  [ **SETVIEWANGLES** ]
Syntax:Local.SetViewAngles(array)  
Sets user-defined view angles.  
```java
    viewAngles = Local.GetViewAngles();
    Cheat.Print("PITCH: " + viewAngles[0] + " YAW: " + viewAngles[1] + " ROLL: " + viewAngles[2] + "\n");
    Local.SetViewAngles([ 89, 180, 0 ]);
    newAngles = Local.GetViewAngles();
    Cheat.Print("PITCH: " + newAngles[0] + " YAW: " + newAngles[1] + " ROLL: " + newAngles[2] + "\n")
```


  [ **GETVIEWANGLES** ]
Syntax:Local.GetViewAngles();  
**Returns** array object with pitch, yaw and roll of your local view.  
```java
var viewAngles = Local.GetViewAngles();
Cheat.Print("Current view angles: " + viewAngles);
```


  [ **LATENCY** ]
Syntax:Local.Latency()  
**Returns** local player ping to the server.  
```java
var myPing = Local.Latency();
Cheat.Print("Your ping is : " + myPing);
```


[back to Contents](#-1)


## <a name="q"></a>Cheat
|-------------------------------|

  [ **GETUSERNAME** ]
Syntax:Cheat.GetUsername()  
**Returns** forum username.  
```java
username = Cheat.GetUsername();
Cheat.Print(username + "\n");
```

  [ **PRINTCHAT** ]
Syntax:Cheat.PrintChat(string text)  
Prints a message in in-game chat.  
```java
Cheat.PrintChat("printing in chat :-)" + "\n");
```

  [ **REGISTERCALLBACK** ]
Syntax:Cheat.RegisterCallback(callback, function)  
Callback: any function/event listed below  
Function: function to be invoked  

**Currently available**  
"CreateMove" useful for adjusting antiaim/ragebot settings with a script before antiaim/ragebot runs  
"Draw" the only place in a script u can call Render functions, is inside a "Draw" callbacks  
"Unload" called when script is unloaded  
"Material" called before materials are applied. Material functions (except Create and Destroy) must be called in this callback  
"ragebot_fire"  
FRAME_START  
FRAME_RENDER_START  
FRAME_RENDER_END  
FRAME_NET_UPDATE_START  
FRAME_NET_UPDATE_END  
FRAME_NET_UPDATE_POSTDATAUPDATE_START  
FRAME_NET_UPDATE_POSTDATAUPDATE_END  
Other game events  
list can be found HERE  https://wiki.alliedmods.net/Counter-Strike:_Global_Offensive_Events
```java
function test()
{
    Cheat.Print("hi from test function\n");
}

Cheat.RegisterCallback("round_start", "test");
// This function prints the text to the in-game console every time "round_start" event is called.
```


  [ **EXECUTECOMMAND** ]
Syntax:Cheat.ExecuteCommand(cmd)  
Prints a message in in-game chat.  
```java
Cheat.ExecuteCommand( "say hello" );
// This function will say hello in chat when script is loaded.
```

  [ **PRINTCOLOR** ]
Syntax:Cheat.PrintColor([ r, g, b, a ], "Text")  
Cheat.PrintColor is used for same purpose(s) as Cheat.Print, in addition you can make your console outputs in different colors.  
```java
Cheat.PrintColor( [ 255, 0, 0, 255 ], "This is red text" );
```

  [ **PRINT** ]
Syntax:Cheat.Print(message)  
Used to print out wide ranges of information to your console, as well as simple messages.  
```java
Cheat.Print( 'hello' );
```

[back to Contents](#-1)


## <a name="w"></a>Input
|-------------------------------|


  [ **GETCURSORPOSITION** ]
Syntax:Input.GetCursorPosition()  
**Returns** an array object with X, Y for cursor position.  
```java
function getCursorPosition()
{
    var cursor_pos = Input.GetCursorPosition();
    Cheat.Print( "Cursor pos X is: " + cursor_pos[0] + "\n");
    Cheat.Print( "Cursor pos Y is: " + cursor_pos[1] + "\n");
}
Cheat.RegisterCallback("Draw", "getCursorPosition")
// This function will print your cursor position x and y in in-game console.
```


  [ **ISKEYPRESSED** ]
Syntax:Input.IsKeyPressed(VK_KEY)  
**Returns** boolean value whether or not a key was pressed.  
```java
if (Input.IsKeyPressed(0x01))
{
   Cheat.ExecuteCommand("say hello");
}
```
A full list of virtual keys can be found HERE. https://docs.microsoft.com/en-us/windows/win32/inputdev/virtual-key-codes  

[back to Contents](#-1)

## <a name="e"></a>World
|-------------------------------|

  [ **GETCURSORPOSITION** ]
Syntax:World.GetServerString();  
**Returns** server IP.  
```java
server = World.GetServerString();
Cheat.Print(server + '\n')
```

  [ **GETMAPNAME** ]
Syntax:World.GetMapName();  
**Returns** current map name.  
```java
current_map = World.GetMapName();
```


[back to Contents](#-1)

## <a name="r"></a>AntiAim
|-------------------------------|

  [ **SETLBYOFFSET** ]
Syntax:AntiAim.SetLBYOffset(int degree);  
Sets the LBY offset of your fake angle.  
```java
// The following code-block will put your real to the left, your fake backwards, and create an LBY similar to the "opposite" option.

AntiAim.SetOverride(1);
AntiAim.SetFakeOffset(30);
AntiAim.SetRealOffset(-30);
AntiAim.SetLBYOffset(90); // <----- This will offset your Fake LBY similar to the "opposite" setting.
```

  [ **SETREALOFFSET** ]
Syntax:AntiAim.SetRealOffset(int degree);  
Sets the offset of your Real angle. Your Real angle is relative to your Fake.  
```java
// The following code-block will put your real to the left, your fake backwards, and create an LBY similar to the "opposite" option.

AntiAim.SetOverride(1);
AntiAim.SetFakeOffset(30);
AntiAim.SetRealOffset(-30); // <----- This will set your real to -30 degrees (RELATIVE TO YOUR FAKE OFFSET OF 30 THAT WAS SETUP ABOVE).
AntiAim.SetLBYOffset(90);
```

  [ **SETFAKEOFFSET** ]
Syntax:AntiAim.SetFakeOffset(int degree);  
Sets the offset of your Fake angle. Fake is the master offset of the AntiAim functions, your Real and LBY are relative to the fake offset.  
```java
// The following code-block will put your real to the left, your fake backwards, and create an LBY similar to the "opposite" option.

AntiAim.SetOverride(1);
AntiAim.SetFakeOffset(30); // <----- This will setup your fake offset.
AntiAim.SetRealOffset(-30);
AntiAim.SetLBYOffset(90);
```

  [ **GETOVERRIDE** ]
Syntax:AntiAim.GetOverride();  
**Returns** the anti-aim override state.  
```java
// The following code-block will print true.

AntiAim.SetOverride(1);

Cheat.Print(AntiAim.GetOverride() + "\n");
```

  [ **GETOVERRIDE** ]
Syntax:AntiAim.SetOverride(int state);  
Enables/disables anti-aim overriding.  
The values used by AA are updated AFTER each send to the server, you can edit them mid cycle, but they wont apply until the next.  
It is recommended to update values in CreateMove callback.  
Spamming SetOverride with alternating values is undefined behavior, just spamming it with 1 or 0 is totally fine though.  
After disabling a script that uses SetOverride, it will not revert back to the original state, you need to change it before the script is disabled.  
The values are offsets to your base yaw, base yaw is affected by the following settings.  
Yaw offset  
Jitter offset (and thus jitter)  
At targets  
Auto direction  
Manual direction  
It is therefor recommended to pay attention and handle this accordingly, disable these settings if your script takes control of it.  
**Understanding Anti-Aim** 
Your fake will be used as a master angle, every other setting is relative to your fake angle.  
The maximum possible angle between your final fake angle and final real angle is 60°.  
SetFakeOffset's default value (0) will set your head backwards, angles are based off 0° being your origin angle.  

```java
// The following code-block will put your real to the left, your fake backwards, and create an LBY similar to the "opposite" setting.

AntiAim.SetOverride(1); // <----- This will enable anti-aim overriding.
AntiAim.SetFakeOffset(30);
AntiAim.SetRealOffset(-30);
AntiAim.SetLBYOffset(90);
```

[back to Contents](#-1)

## <a name="a"></a>Exploit
|-------------------------------|


**IN OT V3 CRACK NOT WORKS**  [ **OVERRIDETOLERANCE** ]
Syntax:Exploit.OverrideTolerance(int value);  
Lower value results in faster double-tap.   
Default value: 2  
Maximum value is clamped to 8.  
```java
UI.AddSliderInt("Shift", 0, 14)
UI.AddSliderInt("Tolerance", 0, 8)
function on_createmove()
{
    Exploit.OverrideShift(UI.GetValue("Script items", "Shift"))
    Exploit.OverrideTolerance(UI.GetValue("Script items", "Tolerance"))
}
Cheat.RegisterCallback("CreateMove", "on_createmove")
```

**IN OT V3 CRACK NOT WORKS**  [ **OVERRIDESHIFT** ]
Syntax:Exploit.OverrideShift(int value);  
Higher value results in faster double-tap.  
Default value: 12  
Maximum value is clamped to 14.  
```java
UI.AddSliderInt("Shift", 0, 14)
UI.AddSliderInt("Tolerance", 0, 8)
function on_createmove()
{
    Exploit.OverrideShift(UI.GetValue("Script items", "Shift"))
    Exploit.OverrideTolerance(UI.GetValue("Script items", "Tolerance"))
}
Cheat.RegisterCallback("CreateMove", "on_createmove")
```

  [ **ENABLERECHARGE** ]
Syntax:Exploit.EnableRecharge();  
Enable automatic recharge  
```java
function on_cm()
{
    Exploit.EnableRecharge()
}
Cheat.RegisterCallback("CreateMove", "on_cm")
```

  [ **DISABLERECHARGE** ]
Syntax:Exploit.DisableRecharge();  
Disables automatic recharging  
```java
function on_cm()
{
    Exploit.DisableRecharge()
}
Cheat.RegisterCallback("CreateMove", "on_cm")
```

  [ **RECHARGE** ]
Syntax:Exploit.Recharge();  
Forces a recharge.  
```java
function on_cm()
{
    Exploit.Recharge()
}
Cheat.RegisterCallback("CreateMove", "on_cm")
```

  [ **GETCHARGE** ]
Syntax:Exploit.GetCharge();   
**Returns** a fraction (0 to 1).  
```java
function on_cm()
{
    chargestate = Exploit.GetCharge()
    Cheat.Print(chargestate + "\n")
}
Cheat.RegisterCallback("CreateMove", "on_cm")
```

[back to Contents](#-1)


## <a name="s"></a>Ragebot
|-------------------------------|

  [ **IGNORETARGET** ]
Syntax:Ragebot.IgnoreTarget( entity_index );  
Ignores a target for 1 tick  

This example will force ragebot to ignore target player with name "llama" if possible.  
You can change the name in code and use this as a whitelist for your friends on HVH servers.  

**Note:** ForceTarget is only active for 1 tick and must be called on CreateMove callback.  
```java
var target = 0
function cm()
{
    target = Ragebot.GetTarget()
    if (Entity.GetName(target) == "llama")
    {
        Ragebot.IgnoreTarget(target)
    }
}

Cheat.RegisterCallback("CreateMove", "cm")
```

  [ **FORCEHITBOXSAFETY** ]
Syntax:Ragebot.ForceHitboxSafety( hitbox_index );  
Forces safety on a specific hitbox  

**Hitboxes:**
0 = head ( 4x damage )  
1 = neck ( legacy in CSGO, does not actually register damage )  
2 = pelvis ( 1.25x damage )  
3 = body ( 1.25x damage )  
4 = thorax  
5 = chest  
6 = upper chest  
7 = left thigh  
8 = right thigh  
9 = left calf  
10 = right calf  
11 = left foot  
12 = right foot  

This example will force ragebot to target only safe point of the hitbox if target velocity is less or equal to 90.  
**Note:** ForceHitboxSafety is only active for 1 tick and must be called on CreateMove callback.  

```java
var target = 0
function cm()
{
    target = Ragebot.GetTarget()
    if (GetVelocity(target) <= 90)
    {
        Ragebot.ForceHitboxSafety(0)
    }
}
function GetVelocity(index) {
    var velocity = Entity.GetProp(index, "CBasePlayer", "m_vecVelocity[0]");
    return Math.sqrt(velocity[0] * velocity[0] + velocity[1] * velocity[1]);
}
Cheat.RegisterCallback("CreateMove", "cm")
```

  [ **FORCETARGETMINIMUMDAMAGE** ]
Syntax:Ragebot.ForceTargetMinimumDamage(entity_index, value);  
Overrides minimum damage on a specific target  
This example will force ragebot's minimum damage to 80 if target velocity is less or equal to 90.  
**Note:** ForceTargetMinimumDamage is only active for 1 tick and must be called on CreateMove callback.  

```java
var target = 0
function cm()
{
    target = Ragebot.GetTarget()
    if (GetVelocity(target) <= 90)
    {
        Ragebot.ForceTargetMinimumDamage(target, 80)
    }
}
function GetVelocity(index) {
    var velocity = Entity.GetProp(index, "CBasePlayer", "m_vecVelocity[0]");
    return Math.sqrt(velocity[0] * velocity[0] + velocity[1] * velocity[1]);
}
Cheat.RegisterCallback("CreateMove", "cm")
```

  [ **FORCETARGETHITCHANCE** ]
Syntax:Ragebot.ForceTargetHitchance( entity_index, value);  
Overrides hitchance on a specific target  
This example will force ragebot's hitchance to 80 if target velocity is less or equal to 90.  
**Note:** ForceTargetHitchance is only active for 1 tick and must be called on CreateMove callback.  

```java
var target = 0
function cm()
{
    target = Ragebot.GetTarget()
    if (GetVelocity(target) <= 90)
    {
        Ragebot.ForceTargetHitchance(target, 80)
    }
}
function GetVelocity(index) {
    var velocity = Entity.GetProp(index, "CBasePlayer", "m_vecVelocity[0]");
    return Math.sqrt(velocity[0] * velocity[0] + velocity[1] * velocity[1]);
}
Cheat.RegisterCallback("CreateMove", "cm")
```

  [ **FORCETARGETSAFETY** ]
Syntax:Ragebot.ForceTargetSafety(entity_index);  
Forces safety on a specific target.  
This example will force ragebot safety on target if the target's name is "edeen".  
**Note:** ForceTargetSafety is only active for 1 tick and must be called on CreateMove callback.   

```java
var target = 0
function cm()
{
    target = Ragebot.GetTarget()
    if (Entity.GetName(target) == "edeen")
    {
        Ragebot.ForceTargetSafety(target)
    }
}
Cheat.RegisterCallback("CreateMove", "cm")
```

  [ **FORCETARGET** ]
Syntax:Ragebot.ForceTarget(entity_index);  
Forces the rage-bot to target a specific entity.  
This example will force ragebot to target player with name "edeen" if possible.  
**Note:** ForceTarget is only active for 1 tick and must be called on CreateMove callback.  
 

```java
var target = 0
function cm()
{
    target = Ragebot.GetTarget()
    if (Entity.GetName(target) == "edeen")
    {
        Ragebot.ForceTargetSafety(target)
    }
}
Cheat.RegisterCallback("CreateMove", "cm")
```

  [ **GETTARGET** ]
Syntax:Ragebot.GetTarget();  
Used to get ragebot target.  


```java
var target = 0
function onCM(){
    target = Ragebot.GetTarget()
}
function onDraw(){
    var pos = Entity.GetRenderBox(target)
    var font = Render.AddFont("Verdana", 8, 400)
    var a = pos[3] - pos[1]
    a /= 2
    a += pos[1]
    Render.StringCustom(a,pos[2] - 30,1,"TARGET", [255,255,255,255], font)
}
Cheat.RegisterCallback("CreateMove", "onCM")
Cheat.RegisterCallback("Draw", "onDraw")
```




[back to Contents](#-1)


## <a name="d"></a>Material
|-------------------------------|


  [ **REFRESH** ]
Syntax:Material.Refresh( material_index );  
Used to apply new set key values.  
**Returns** if the operation succeeded.  
Note: This function can only be used in functions with Material callback.  
More keys and values can be found below:  
https://developer.valvesoftware.com/wiki/Category:List_of_Shader_Parameters  
https://developer.valvesoftware.com/wiki/VertexLitGeneric  
```java
Material.Create("testmaterial");
function updateMaterials()
{
    mat_index = Material.Get("testmaterial");
    if (mat_index > 0)
    {
        Material.SetKeyValue(mat_index, "$baseTexture", "vgui/white");
        Material.SetKeyValue(mat_index, "$envmap", "models/effects/cube_white");
        Material.SetKeyValue(mat_index, "$envmapfresnel", "1");
        Material.SetKeyValue(mat_index, "$envmapfresnelminmaxexp", "[0 1 2]");
        Material.SetKeyValue(mat_index, "$color", "[1.0 1.0 1.0]");
        Material.SetKeyValue(mat_index, "$envmaptint", "[1.0 1.0 1.0]");
        Material.Refresh(mat_index);
    }
}
Cheat.RegisterCallback("Material", "updateMaterials")
```

  [ **SETKEYVALUE** ]
Syntax:Material.SetKeyValue( material_index, key, value );  
Used to set key values.    
**Returns** if the operation succeeded.  
Note: This function can only be used in functions with Material callback.  
More keys and values can be found below:  
https://developer.valvesoftware.com/wiki/Category:List_of_Shader_Parameters  
https://developer.valvesoftware.com/wiki/VertexLitGeneric  
```java
Material.Create("testmaterial");
function updateMaterials()
{
    mat_index = Material.Get("testmaterial");
    if (mat_index > 0)
    {
        Material.SetKeyValue(mat_index, "$baseTexture", "vgui/white");
        Material.SetKeyValue(mat_index, "$envmap", "models/effects/cube_white");
        Material.SetKeyValue(mat_index, "$envmapfresnel", "1");
        Material.SetKeyValue(mat_index, "$envmapfresnelminmaxexp", "[0 1 2]");
        Material.SetKeyValue(mat_index, "$color", "[1.0 1.0 1.0]");
        Material.SetKeyValue(mat_index, "$envmaptint", "[1.0 1.0 1.0]");
        Material.Refresh(mat_index);
    }
}
Cheat.RegisterCallback("Material", "updateMaterials")
```

  [ **GET** ]
Syntax:Material.Get( name );  
Used to get material index.  
**Returns** 0 if material doesn't exist.  
**Note:** This function can only be used in functions with Material callback.  
```java
Material.Create("testmaterial");
function updateMaterials()
{
    mat_index = Material.Get("testmaterial");
    if (mat_index > 0)
    {
        Material.SetKeyValue(mat_index, "$baseTexture", "vgui/white");
        Material.SetKeyValue(mat_index, "$envmap", "models/effects/cube_white");
        Material.SetKeyValue(mat_index, "$envmapfresnel", "1");
        Material.SetKeyValue(mat_index, "$envmapfresnelminmaxexp", "[0 1 2]");
        Material.SetKeyValue(mat_index, "$color", "[1.0 1.0 1.0]");
        Material.SetKeyValue(mat_index, "$envmaptint", "[1.0 1.0 1.0]");
        Material.Refresh(mat_index);
    }
}
Cheat.RegisterCallback("Material", "updateMaterials")
```

  [ **DESTROY** ]
Syntax:Material.Destroy( name );    
**Returns** true if material was destroyed successfully.  
```java
Material.Destroy("cool material")
```

  [ **CREATE** ]
Syntax:Material.Create( name );  
**Returns** true if material was created successfully or false otherwise.   
```java
Material.Create("cool material")
```



[back to Contents](#-1)
