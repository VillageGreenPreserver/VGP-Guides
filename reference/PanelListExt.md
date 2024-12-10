An extension of the panel list, for niche one off panels

## CBaseLoadoutPanel

Derives from EditablePanel

Parameter | Default Value | Data Type | Info
--------- | ------------- | --------- | ----
item_xpos_offcenter_a | "0" | int
item_xpos_offcenter_b | "0" | int
item_ypos | "0" | int
item_ydelta | "0" | int
button_xpos_offcenter | "0" | int
button_ypos | "0" | int
button_ydelta | "0" | int
item_backpack_offcenter_x | "0" | int
item_backpack_xdelta | "0" | int
item_backpack_ydelta | "0" | int
items_only | "0" | bool | Hides "CaratLabel" & "ClassLabel"
force_show_backpack_rarities | "0" | bool
button_override_delete_xpos | "0" | int
modelpanels_kv{} | | ControlName: CItemModelPanel


## CClassLoadoutPanel

Derives from CBaseLoadoutPanel

Res file: "resource/ui/ClassLoadoutPanel.res"

Parameter | Default Value | Data Type | Info
--------- | ------------- | --------- | ----
itemoptionpanels_kv{} | | ControlName: CExButton

Default scheme values
Font | Color | Border
---- | ----  | ------
 | Econ.Button.PresetDefaultColorFg
 | Econ.Button.PresetArmedColorFg
 | Econ.Button.PresetDepressedColorFg
 | Econ.Button.PresetDefaultColorBg
 | Econ.Button.PresetArmedColorBg
 | Econ.Button.PresetDepressedColorBg
 | Button.TextColor
 | Button.ArmedTextColor
 | Button.DepressedTextColor
 | Button.BgColor
 | Button.ArmedBgColor
 | Button.DepressedBgColor
 
Commands | Info
-------- | ----
characterloadout |
tauntloadout |
change* | * = slot number
options* | ditto


## CLoadoutItemOptionsPanel

Derives from EditablePanel

Res file: "resource/ui/ItemOptionsPanel.res"

Commands | Info
-------- | ----
particle_button_clicked |
particle_use_head_clicked |
set_style |


## CBackpackPanel

Derives from CBaseLoadoutPanel

Res file: "resource/ui/econ/BackpackPanel.res"

Parameter | Default Value | Data Type
--------- | ------------- | ---------
page_button_y | "0" | int
page_button_x_delta | "0" | int
page_button_y_delta | "0" | int
page_button_per_row | "20" | int
page_button_height | "0" | int
pagebuttons_kv{} | | ControlName: EditablePanel


Commands | Info
-------- | ----
goto_page_* | * = page number
nextpage
prevpage
showbackpackitems
showbaseitems
canceltool
show_explanations
showdetails
Context_CraftUpCollection
Context_CraftCommonStatClock
equipclass* | * = class number
paint* | etc.
market_paint*
store_paint*
strangepart_*
market_strangepart_*


Page Button Colors
Color | Info
----- | ----
"TanDarker" | Empty Page FgColor
"170 161 137 255" | Partial Page FgColor, hardcoded
"TanLight" | Full Page FgColor
"TFOrange" | Selected Page BgColor



