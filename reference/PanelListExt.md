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

Commands | Info
-------- | ----
characterloadout |
tauntloadout |
change* | * = slot number
options* | `=||=`
