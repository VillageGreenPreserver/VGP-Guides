# Panel list

This is a list of panel types and their parameters.


## Panel
The most basic panel, all other panels derive from this

Parent | Creatable | Res File
------ |:---------:| --------
N/A | 🟩 |

Parameter | Default Value | Data Type | Info
--------- | ------------- | --------- | ----
fieldName | NULL | string | Renames the panel
xpos | "0" | pos |Position of the panel in the X axis
ypos | "0" | pos | Position of the panel in the Y axis
zpos | "0" | int | Render priority of the panel
wide | "28" | size | Size of the panel in the X axis
tall | "10" | size | Size of the panel in the Y axis
visible | "1" | bool | Visibility of the panel
enabled | "1" | bool | Changes the colour of labels and disables interaction with buttons, sliders, text boxes etc.
proportionalToParent | "0" | bool | Position & size values relative to the parent size, instead of screen size
fgcolor_override | "Panel.FgColor" | color | Foreground colour
bgcolor_override | "Panel.BgColor" | color | Background colour
alpha | "255" | int | Opacity of the panel 0-255
paintbackground | "-1" | bool | Should the background be painted
PaintBackgroundType | "0" | int | How the background should be painted. Textures can be changed with Texture*</br>0 = Square corners</br>1 = Textured (Uses Texture1)</br>2 = Rounded corners</br>3 = Rounded Corners with horizontal fade
Texture1 | "vgui/hud/800corner1" | material | Image in the top left of PaintBackgroundType 2 & image of PaintBackgroundType 1, path starts in root/materials/
Texture2 | "vgui/hud/800corner2" | material | Top Right
Texture3 | "vgui/hud/800corner3" | material | Botttom Right
Texture4 | "vgui/hud/800corner4" | material | Bottom Left
RoundedCorners | "-1" | int | Which corners are rounded, values 0-15
paintborder | "-1" | bool | Should the panel have a border
border | "" | border | What border to use
pin_to_sibling | NULL | string | Pin the panel's position to another panel on the same level in the hierarchy
pin_corner_to_sibling | "0" | int | Which corner should be pinned to the sibling
pin_to_sibling_corner | "0" | int | To which corner of the sibling should the panel be pinned
mouseinputenabled | "1" | bool | Should the panel listen for mouse inputs
keyboardinputenabled | NULL | bool | Should the panel listen for keyboard inputs
tooltiptext | NULL | string | Text to display when hovering over the panel
actionsignallevel | "-1" |  int | Allows nested child buttons to add their distant parents as action signal targets
IgnoreScheme | "0" | int
usetitlesafe | "0" | int
ForceStereoRenderToFrameBuffer | "0" | bool
tabPosition | "0" | int | The order when selecting with tab
autoResize | "0" | int | Should the panel resize if the parent resizes, 0 = Off, 1 = Horizontal, 2 = Vertical, 3 = Both
PinCorner | "0" | int | Which corner to stick to if the parent resizes, 0 = north-west, 1 = north-east, 2 = south-west, 3 = south-east
PinnedCornerOffSetX | NULL | int
PinnedCornerOffSetY | NULL | int
UnpinnedCornerOffSetX | NULL | int
UnpinnedCornerOffSetY | NULL | int
navUp | NULL | string
navDown | NULL | string
navLeft | NULL | string
navRight | NULL | string
navToRelay | NULL | string
navActivate | NULL | string
navBack | NULL | string

Default scheme values
Font | Color | Border
---- | ----  | ------
  | Panel.FgColor
  | Panel.BgColor 

Commands | Info
-------- | ----
performlayout |
reloadscheme |

## EditablePanel
A panel that can have other panels inside of it

Parent | Creatable | Res File
------ |:---------:| --------
[Panel](/reference/PanelList.md#panel) | 🟩 |

Parameter | Default Value | Data Type
--------- | ------------- | ---------
skip_autoresize | "0" | bool


## Frame
Parent | Creatable | Res File
------ |:---------:| --------
[EditablePanel](/reference/PanelList.md#EditablePanel) | 🟥 |

Parameter | Default Value | Data Type
--------- | ------------- | ---------
setclosebuttonvisible | "1" | bool
settitlebarvisible | "1" | bool
title | "" | string
title_font | "FrameTitleBar.Font" | font
clientinsetx_override | Frame.ClientInsetX | int
titletextinsetX | "0" | int
titletextinsetY | "0" | int
infocus_bgcolor_override | "Frame.BGColor" | color
outoffocus_bgcolor_override | "Frame.OutOfFocusBgColor" | color
titlebarbgcolor_override | "FrameTitleBar.BgColor" | color
titlebardisabledbgcolor_override | "FrameTitleBar.DisabledBgColor" | color
titlebarfgcolor_override | "FrameTitleBar.TextColor" | color
titlebardisabledfgcolor_override | "FrameTitleBar.DisabledTextColor" | color
frame_topGrip{} | | ControlName: GripPanel
frame_bottomGrip{} | | ControlName: GripPanel
frame_leftGrip{} | | ControlName: GripPanel
frame_rightGrip{} | | ControlName: GripPanel
frame_tlGrip{} | | ControlName: GripPanel
frame_trGrip{} | | ControlName: GripPanel
frame_blGrip{} | | ControlName: GripPanel
frame_brGrip{} | | ControlName: GripPanel
frame_caption{} | | ControlName: CaptionGripPanel
frame_minimize{} | | ControlName: FrameButton
frame_maximize{} | | ControlName: FrameButton
frame_mintosystray{} | | ControlName: FrameButton
frame_close{} | | ControlName: FrameButton
frame_menu{} | | ControlName: FrameSystemButton

Default scheme values
Font | Color | Border | Other
---- | ----  | ------ | -----
FrameTitleBar.SmallFont | FrameTitleBar.TextColor | FrameBorder | Frame.TransitionEffectTime
FrameTitleBar.Font | FrameTitleBar.BgColor | | Frame.FocusTransitionEffectTime
 MarlettSmall | FrameTitleBar.DisabledTextColor | | Frame.ClientInsetX
 Marlett | FrameTitleBar.DisabledBgColor | | Frame.ClientInsetY
   | Frame.BgColor | | Frame.TitleTextInsetX
   | Frame.OutOfFocusBgColor

Commands | Info
-------- | ----
Close |
CloseModal |
Minimize |
MinimizeToSysTray |

<details>
<summary><h3>GripPanel</h3></summary>
<br>
	
Parent | Creatable | Res File
------ |:---------:| --------
[Panel](/reference/PanelList.md#Panel) | 🟥 |

Default scheme values
Font | Color | Border | Other
---- | ----  | ------ | -----
MarlettSmall | FrameGrip.Color1 |   | Frame.AutoSnapRange
Marlett | FrameGrip.Color2
   | FrameTitleBar.DisabledTextColor
   | FrameTitleBar.DisabledBgColor
</details>

<details>
<summary><h3>FrameButton</h3></summary>
<br>
	
Parent | Creatable | Res File
------ |:---------:| --------
[Button](/reference/PanelList.md#Button) | 🟥 |


Default scheme values
Font | Color | Border | Other
---- | ----  | ------ | -----
   | FrameTitleButton.FgColor | TitleButtonBorder
   | FrameTitleButton.BgColor | TitleButtonDepressedBorder
   | FrameTitleButton.DisabledFgColor | TitleButtonDisabledBorder
   | FrameTitleButton.DisabledBgColor
</details>

<details>
<summary><h3>FrameSystemButton</h3></summary>
<br>
	
Parent | Creatable | Res File
------ |:---------:| --------
[MenuButton](/reference/PanelList.md#MenuButton) | 🟥 |

Default scheme values
Font | Color | Border | Other
---- | ----  | ------ | -----
   | FrameSystemButton.FgColor |  | FrameSystemButton.Icon
   | FrameSystemButton.BgColor | | FrameSystemButton.DisabledIcon
</details>

## PropertyDialog
Parent | Creatable | Res File
------ |:---------:| --------
[Frame](/reference/PanelList.md#Frame) | 🟥 |

Parameter | Default Value | Data Type
--------- | ------------- | ---------
sheetinset_bottom | "32" | int

Commands | Info
-------- | ----
OK |
Cancel |
Apply

### PropertySheet
Parent | Creatable | Res File
------ |:---------:| --------
[EditablePanel](/reference/PanelList.md#EditablePanel) | 🟥 |

Parameter | Default Value | Data Type
--------- | ------------- | ---------
tabxindent | "0" | int
tabxdelta | "0" | int
tabxfittotext | "1" | bool
tabheight | "28" | int
tabheight_small | "14" | int
tabwidth | "64" | int
transition_time | "0.0" | float
yoffset | "0" | int
tabskv{} | | Controlname: PageTab

Default scheme values
Font | Color | Border | Other
---- | ----  | ------ | -----
DefaultVerySmall |  | PropertySheetBorder | PropertySheet.TransitionEffectTime
Default |


<details>
<summary><h3>PageTab</h3></summary>
<br>
	
Parent | Creatable | Res File
------ |:---------:| --------
[Button](/reference/PanelList.md#Button) | 🟥 |

Parameter | Default Value | Data Type
--------- | ------------- | ---------
selectedcolor | "PropertySheet.SelectedTextColor" | color
unselectedcolor | "PropertySheet.TextColor" | color
activeborder_override | "TabActiveBorder" | border
normalborder_override | "TabBorder" | border

Default scheme values
Font | Color | Border | Other
---- | ----  | ------ | -----
DefaultVerySmall | PropertySheet.SelectedTextColor | TabActiveBorder | PropertySheet.TransitionEffectTime
Default | PropertySheet.TextColor | TabBorder

Commands | Info
-------- | ----
ShowContextMenu |
</details>
	
## ScrollableEditablePanel
Parent | Creatable | Res File
------ |:---------:| --------
[EditablePanel](/reference/PanelList.md#EditablePanel) | 🟥 |

Parameter | Data Type
--------- | ---------
ScrollBar{} | ControlName: ScrollBar


## CExScrollingEditablePanel
A panel that can have other panels inside of it and can be scrolled

Parent | Creatable | Res File
------ |:---------:| --------
[EditablePanel](/reference/PanelList.md#EditablePanel) | 🟩 |

Parameter | Default Value | Data Type | Info
--------- | ------------- | --------- | ----
allow_mouse_wheel_to_scroll | "1" | bool | Only allow scrolling by dragging the slider
scroll_step | "10" | int | How much the scroll wheel scrolls
bottom_buffer | "0" | int | How much space to leave at the bottom
restrict_width | "1" | bool | Make the contents fit inside the panel
ScrollBar{} | | ControlName: CExScrollBar


## CScrollableList
Parent | Creatable | Res File
------ |:---------:| --------
[CExScrollingEditablePanel](/reference/PanelList.md#CExScrollingEditablePanel) | 🟩 |


## CExpandablePanel
Parent | Creatable | Res File
------ |:---------:| --------
[EditablePanel](/reference/PanelList.md#EditablePanel) | 🟥 |

Parameter | Default Value | Data Type | Info
--------- | ------------- | --------- | ----
resize_time | "0.4" | float | How quickly to resize panel
collapsed_height | "17" | int | How tall when collapsed
expanded_height | "50" | int | How tall when expanded
expand_direction | "down" | string | up, down, left, right

Commands | Info
-------- | ----
toggle_collapse |


## CMatchHistoryEntryPanel
Parent | Creatable | Res File
------ |:---------:| --------
[CExpandablePanel](/reference/PanelList.md#CExpandablePanel) | 🟩 | resource/ui/MatchHistoryEntryPanel.res




## ListPanel
Parent | Creatable | Res File
------ |:---------:| --------
[Panel](/reference/PanelList.md#Panel) | 🟩 |

Default scheme values
Font | Color | Border
---- | ----  | ------
Default | ListPanel.BgColor | ButtonDepressedBorder
  | ListPanel.TextColor
   | ListPanel.DisabledTextColor
   | ListPanel.SelectedTextColor
   | ListPanel.DisabledSelectedTextColor
   | ListPanel.EmptyListInfoTextColor


## SectionedListPanel
Parent | Creatable | Res File
------ |:---------:| --------
[Panel](/reference/PanelList.md#Panel) | 🟩 |

Parameter | Data Type | Info
--------- | --------- | ----
show_columns | bool
linespacing | int
sectiongap | int
linegap | int

Default scheme values
Font | Color | Border
---- | ----  | ------
DefaultVerySmall | SectionedListPanel.HeaderTextColor | ButtonDepressedBorder
SectionedListPanel.Font | SectionedListPanel.DividerColor
   | SectionedListPanelHeader.BgColor
   | SectionedListPanel.BrightTextColor
   | SectionedListPanel.SelectedTextColor
   | SectionedListPanel.OutOfFocusSelectedTextColor
   | SectionedListPanel.SelectedBgColor
   | SectionedListPanel.TextColor
   | SectionedListPanel.BgColor
   | SectionedListPanel.OutOfFocusSelectedBgColor
   | SectionedListPanel.Font


## TFSectionedListPanel
Parent | Creatable | Res File
------ |:---------:| --------
[SectionedListPanel](/reference/PanelList.md#SectionedListPanel) | 🟩 |

Parameter | Default Value | Data Type | Info
--------- | ------------- | --------- | ----
medal_width | "s.05" | size
avatar_width | "s.1" | size
spacer | "s.1" | size
name_width | "s.1" | size
class_width | "s.1" | size
award_width | "s.1" | size
stats_width | "s.1" | size
horiz_inset | "5" | int


## PanelListPanel
Parent | Creatable | Res File
------ |:---------:| --------
[EditablePanel](/reference/PanelList.md#EditablePanel) | 🟩 |

Parameter | Default Value | Data Type
--------- | ------------- | ---------
autohide_scrollbar | "0" | bool

Default scheme values
Font | Color | Border
---- | ----  | ------
  | ListPanel.BgColor | ButtonDepressedBorder


## CBaseASyncPanel
Parent | Creatable | Res File
------ |:---------:| --------
[EditablePanel](/reference/PanelList.md#EditablePanel) | 🟥 |

Parameter | Default Value | Data Type | Info
--------- | ------------- | --------- | ----
refresh_delay | "-1.0" | float
asynchandling | NULL | string | "content" or "loading", doesn't look on the panel but rather on the panel's child


## CTFLeaderboardPanel
Parent | Creatable | Res File
------ |:---------:| --------
[CBaseASyncPanel](/reference/PanelList.md#CBaseASyncPanel) | 🟥 | Resource/UI/econ/LeaderboardPanel.res<br>Resource/UI/LeaderboardSpreadEntry.res


Parameter | Default Value | Data Type
--------- | ------------- | ---------
entry_step | "5" | int
EvenTextColor | NULL | color
OddTextColor | NULL | color
LocalPlayerTextColor | NULL | color
ScoresContainer{} | | ControlName: EditablePanel


## CLadderLobbyLeaderboard
Parent | Creatable | Res File
------ |:---------:| --------
[CTFLeaderboardPanel](/reference/PanelList.md#CTFLeaderboardPanel) | 🟥 | Resource/UI/econ/LobbyLeaderboard.res<br>Resource/UI/LeaderboardEntryRank.res

Commands | Info
-------- | ----
stream |
global |
local |


## Menu
Parent | Creatable | Res File
------ |:---------:| --------
[Panel](/reference/PanelList.md#Panel) | 🟩 |

Default scheme values
Font | Color | Border
---- | ----  | ------
  | Menu.TextColor | MenuBorder
  | Menu.BgColor | 
  | BorderDark


### MenuSeparator
Parent | Creatable | Res File
------ |:---------:| --------
[Panel](/reference/PanelList.md#Panel) | 🟥 |

Default scheme values
Font | Color | Border
---- | ----  | ------
  | Menu.SeparatorColor | 
  | Menu.BgColor | 


## MenuItem
Parent | Creatable | Res File
------ |:---------:| --------
[Button](/reference/PanelList.md#Button) | 🟩 |

Default scheme values
Font | Color | Border | Other
---- | ----  | ------ | -----
Marlett | Menu.TextColor |   | Menu.TextInset
Default | Menu.BgColor | 
  | Menu.ArmedTextColor | 
  | Menu.ArmedBgColor | 


## MenuButton
Parent | Creatable | Res File
------ |:---------:| --------
[Button](/reference/PanelList.md#Button) | 🟩 |


## MenuBar
Parent | Creatable | Res File
------ |:---------:| --------
[Panel](/reference/PanelList.md#Panel) | 🟩 |

Default scheme values
Font | Color | Border
---- | ----  | ------
  | MenuBar.BgColor | ButtonBorder



## Label
A panel with text

Parent | Creatable | Res File
------ |:---------:| --------
[Panel](/reference/PanelList.md#Panel) | 🟩 |

Parameter | Default Value | Data Type | Info
--------- | ------------- | --------- | ----
labelText | "Label" | string | Text to display
font | "Default" | font | What font to use
textAlignment | "west" | string | Where the text should align
textinsetx | "0" | int | Move text in X axis
textinsety | "0" | int | Move text in Y axis
use_proportional_insets | "0" | bool | Insets are proportional to screen size
wrap | "0" | bool | Should the text wrap when exceeding panel bounds
centerwrap | "0" | bool |Same as above but centered
auto_wide_tocontents | "0" | bool | The panel's wide value is automatically changed to fit the text
auto_tall_tocontents | "0" | bool | The panel's tall value is automatically changed to fit the text
allcaps | "0" | bool | Use only uppercase letters
disabledfgcolor2_override | "Label.DisabledFgColor2" | color | Foreground colour when enabled == 0
dulltext | "0" | bool | Should the text use dull colours
brighttext | "0" | bool | Should the text use bright colours
associate | "" | string

Default scheme values
Font | Color | Border
---- | ----  | ------
Default | Label.DisabledFgColor1
   | Label.DisabledFgColor2
   | Label.BgColor
   | Label.TextDullColor
   | Label.TextBrightColor
   | Label.TextColor
   | Label.SelectedTextColor


## CExLabel
Parent | Creatable | Res File
------ |:---------:| --------
[Label](/reference/PanelList.md#Label) | 🟩 |

Parameter | Default Value | Data Type | Info
--------- | ------------- | --------- | ----
fgcolor | "Label.TextColor" | color | Foreground colour


## Button
A panel that can fire a command when activated

Parent | Creatable | Res File
------ |:---------:| --------
[Label](/reference/PanelList.md#Label) | 🟩 |

Parameter | Default Value | Data Type | Info
--------- | ------------- | --------- | ----
command | "" | string | Command of the button
selected | "-1" | int | Draw selected by default
stayselectedonclick | "0" | bool | When clicked on, sets selected to 1
stay_armed_on_click | "0" | bool | Don't revert back to default state when clicked
button_activation_type | "2" | int | How the button behaves</br>0 = When pressed sets depressed colours and activates command when released</br>1 = Activates command when pressed</br>2 = Activates command when released, doesn't set selected colours
sound_armed | "" | sound | Sound when hovered over
sound_depressed | "" | sound | Sound when pressing button
sound_released | "" | sound | Sound when releasing button
defaultFgColor_override | "Button.TextColor" | color | Foreground colour
defaultBgColor_override | "Button.BgColor" | color |Background colour
armedFgColor_override | "Button.ArmedTextColor" | color | Foreground colour when hovered
armedBgColor_override | "Button.ArmedBgColor" | color | Background colour when hovered
depressedFgColor_override | "Button.DepressedTextColor" | color | Foreground colour when clicked on
depressedBgColor_override | "Button.DepressedBgColor" | color | Background colour when clicked on
selectedFgColor_override | "Button.SelectedTextColor" | color | Foreground colour when selected
selectedBgColor_override | "Button.SelectedBgColor" | color | Background colour when selected
keyboardFocusColor_override | "Button.FocusBorderColor" | color
blinkFgColor_override | "Button.BlinkColor" | color
default | "0" | bool

Default scheme values
Font | Color | Border
---- | ----  | ------
   | Button.TextColor | ButtonBorder
   | Button.BgColor | ButtonDepressedBorder
   | Button.ArmedTextColor | ButtonKeyFocusBorder
   | Button.ArmedBgColor
   | Button.SelectedTextColor
   | Button.SelectedBgColor
   | Button.DepressedTextColor
   | Button.DepressedBgColor
   | Button.FocusBorderColor
   | Button.BlinkColor


## CExButton
Parent | Creatable | Res File
------ |:---------:| --------
[Button](/reference/PanelList.md#Button) | 🟩 |

Parameter | Default Value | Data Type | Info
--------- | ------------- | --------- | ----
fgcolor | "Button.TextColor" | color | Foreground colour
border_default | "" | border | Default border
border_armed | "" | border | Border when hovered
border_disabled | "" | border | Border when enabled == 0
border_selected | "" | border | Border when selected == 1


## CExImageButton
A button that displays an image

Parent | Creatable | Res File
------ |:---------:| --------
[CExButton](/reference/PanelList.md#CExButton) | 🟩 |

Parameter | Default Value | Data Type | Info
--------- | ------------- | --------- | ----
image_drawcolor | "255 255 255 255" | color | What colour to draw the image by default, can't use clientscheme entries
image_armedcolor | "255 255 255 255" | color | What colour to draw the image when hovered, can't use clientscheme entries
image_depressedcolor | "255 255 255 255" | color | What colour to draw the image when pressed, can't use clientscheme entries
image_disabledcolor | "255 255 255 255" | color | What colour to draw the image when enabled == 0, can't use clientscheme entries
image_selectedcolor | "255 255 255 255" | color | What colour to draw the image when selected == 1, can't use clientscheme entries
image_default | NULL | material | What image to use by default
image_armed | NULL | material | What image to use when hovered
image_selected | NULL | material | What image to use when selected == 1
SubImage{} | | ControlName: ImagePanel


## CImageButton
A button that displays an image

Parent | Creatable | Res File
------ |:---------:| --------
[Button](/reference/PanelList.md#Button) | 🟩 |

Parameter | Default Value | Data Type | Info
--------- | ------------- | --------- | ----
scaleImage | "0" | bool | Whether to scale the image
inactiveimage | NULL | material | Image to use by default
activeimage | NULL | material | Image to use when hovered
inactivedrawcolor | "255 255 255 255" | color | What colour to draw the image by default
activedrawcolor | "255 255 255 255" | color | What colour to draw the image when hovered

Default scheme values
Font | Color | Border
---- | ----  | ------
   | Button.TextColor | NoBorder
   | Button.ArmedTextColor
   | Button.DepressedTextColor


## ToggleButton
A button that can be toggled on and off

Parent | Creatable | Res File
------ |:---------:| --------
[Button](/reference/PanelList.md#Button) | 🟩 |

Default scheme values
Font | Color | Border
---- | ----- | ------
   | ToggleButton.SelectedTextColor |


## RadioButton
Parent | Creatable | Res File
------ |:---------:| --------
[ToggleButton](/reference/PanelList.md#ToggleButton) | 🟩 |

Parameter | Default Value | Data Type | Info
--------- | ------------- | --------- | ----
SubTabPosition | "0" | int | Which radio buttons are linked

Default scheme values
Font | Color | Border
---- | ----  | ------
MarlettSmall | CheckButton.BgColor
 | CheckButton.Border1
 | CheckButton.Border2
 | CheckButton.Check
 | RadioButton.TextColor
 | RadioButton.SelectedTextColor
 | RadioButton.ArmedTextColor


## CheckButton
A button that looks like a checkbox

Parent | Creatable | Res File
------ |:---------:| --------
[ToggleButton](/reference/PanelList.md#ToggleButton) | 🟩 |

Parameter | Default Value | Data Type | Info
--------- | ------------- | --------- | ----
smallcheckimage | "0" | bool | Use a smaller check image

Default scheme values
Font | Color | Border
---- | ----  | ------
 MarlettSmall | CheckButton.TextColor | ButtonBorder
 Marlett | CheckButton.BgColor | ButtonDepressedBorder
   | CheckButton.Border1 | ButtonKeyFocusBorder
   | CheckButton.Border2
   | CheckButton.Check
   | CheckButton.SelectedTextColor
   | CheckButton.DisabledFgColor
   | CheckButton.DisabledBgColor
   | CheckButton.ArmedBgColor
   | CheckButton.DepressedBgColor
   | CheckButton.HighlightFgColor


## CvarToggleCheckButton
A checkbutton that displays the value of a cvar

Parent | Creatable | Res File
------ |:---------:| --------
[CheckButton](/reference/PanelList.md#CheckButton) | 🟩 |

Parameter | Default Value | Data Type | Info
--------- | ------------- | --------- | ----
cvar_name | "" | string
cvar_value | "1" | bool


## CExCheckButton 
Parent | Creatable | Res File
------ |:---------:| --------
[CheckButton](/reference/PanelList.md#CheckButton) | 🟩 |


## ExpandButton
A button that looks like an arrow

Parent | Creatable | Res File
------ |:---------:| --------
[ToggleButton](/reference/PanelList.md#ToggleButton) | 🟩 |

Default scheme values
Font | Color | Border
---- | ----  | ------
 Marlett | ExpandButton.Color


## CTFTeamButton
A button that animates a model

Animation events: idle_enabled, idle_disabled, enter_enabled, enter_disabled, exit_enabled, exit_disabled, hover_disabled

Parent | Creatable | Res File
------ |:---------:| --------
[CExButton](/reference/PanelList.md#CExButton) | 🟥 |

Parameter | Default Value | Data Type | Info
--------- | ------------- | --------- | ----
associated_model | "" | string | What model to animate
team | "0" | int
hover | "-1" | float | Delay before animation


## CAutoFittingLabel
A label that changes the font to fit in the boundaries of the panel and can change color in the middle of a string using unicode symbols

Parent | Creatable | Res File
------ |:---------:| --------
[Label](/reference/PanelList.md#Label) | 🟩 |

Parameter | Data Type | Info
--------- | --------- | ----
fonts{}
colors{}
```
"Example"
{
  "ControlName" "CAutoFittingLabel"
  "labelText" "[0x1] This uses color 1 [0x2] and this uses color 2" //Make sure to replace the [0x1] with the actual unicode symbol for it to work
  "fonts"
  {
    "1"
    {
      "font"  "large_font"
    }
    "2"
    {
      "font"  "medium_font"
    }
    "3"
    {
      "font"  "small_font"
    }
  }

  "colors"
  {
    "1"  "255 0 0 255"
    "2"  "0 255 0 255"
    "3"  "0 0 255 255"
  }
}
```


## URLLabel
A button that opens a web page

Parent | Creatable | Res File
------ |:---------:| --------
[Label](/reference/PanelList.md#Label) | 🟩 |

Parameter | Default Value | Data Type | Info
--------- | ------------- | --------- | ----
URLText | NULL | string | URL to the web page

Default scheme values
Font | Color | Border
---- | ----  | ------
 DefaultUnderline 


## RichText
A panel with text that can scroll and can use a text file for its contents

Parent | Creatable | Res File
------ |:---------:| --------
[Panel](/reference/PanelList.md#Panel) | 🟩 |

Parameter | Default Value | Data Type | Info
--------- | ------------- | --------- | ----
text | "" | string | Text to display
textfile | NULL | path | A text file to display eg. "resource/text.txt"
scrollbar | "1" | bool | Should the scrollbar be enabled
maxchars | "-1" | int
ScrollBar{} | | ControlName: ScrollBar

Default scheme values
Font | Color | Border | Other
---- | ----  | ------ | -----
 Default | RichText.TextColor |   | RichText.InsetX
 DefaultUnderline | RichText.BgColor |   | RichText.InsetY
   | RichText.SelectedTextColor | 
   | RichText.SelectedBgColor | 


## CExRichText
Parent | Creatable | Res File
------ |:---------:| --------
[RichText](/reference/PanelList.md#RichText) | 🟩 |

Parameter | Default Value | Data Type | Info
--------- | ------------- | --------- | ----
font | "Default" | font | What font to use
fgcolor | "RichText.FgColor" | color | Foreground colour
image_up_arrow | "chalkboard_scroll_up" | material | Image for the scrollbar's up arrow
image_down_arrow | "chalkboard_scroll_down" | material | Image for the scrollbar's down arrow
image_line | "chalkboard_scroll_line" | material | Image for the scrollbar slider's background 
image_box | "chalkboard_scroll_box" | material | Image for the scrollbar slider
image_up_arrow_mouseover | NULL | material | Image for the scrollbar's up arrow when hovered
image_down_arrow_mouseover | NULL | material | Image for the scrollbar's down arrow when hovered
Line{} | | ControlName: ImagePanel
Box{} | | ControlName: ImagePanel
UpArrow{} | | ControlName: CExImageButton
DownArrow{} | | ControlName: CExImageButton
ScrollBar{} | | ControlName: ScrollBar

Default scheme values
Font | Color | Border
---- | ----  | ------
   | Blank | NoBorder


## CRichTextWithScrollbarBorders
Uses borders instead of images for image_line & image_box. "Line" & "Box" are Panels instead of ImagePanels

Parent | Creatable | Res File
------ |:---------:| --------
[CExRichText](/reference/PanelList.md#CExRichText) | 🟩 |


## CEconItemDetailsRichText
Rich text control that knows how to fill itself with information that describes a specific item definition

Parent | Creatable | Res File
------ |:---------:| --------
[CRichTextWithScrollbarBorders](/reference/PanelList.md#CRichTextWithScrollbarBorders) | 🟩 |

Parameter | Default Value | Data Type | Info
--------- | ------------- | --------- | ----
highlight_color | "Orange" | color
itemset_color | "Blue" | color
link_color | "LightOrange" | color

Default scheme values
Font | Color | Border
---- | ----  | ------
 Link | |


## ScrollBar
Parent | Creatable | Res File
------ |:---------:| --------
[Panel](/reference/PanelList.md#Panel) | 🟩 |

Parameter | Default Value | Data Type | Info
--------- | ------------- | --------- | ----
nobuttons | "0" | bool | Removes up & down buttons
autohide_buttons | "0" | bool | Automatically removes up & down buttons when not needed
Slider{} | | ControlName: ScrollBarSlider
UpButton{} | | ControlName: ScrollBarButton
DownButton{} | | ControlName: ScrollBarButton

Default scheme values
Font | Color | Border | Other
---- | ----  | ------ | -----
   |   |   | ScrollBar.Wide


## Scrollbar_Horizontal
Parent | Creatable | Res File
------ |:---------:| --------
[ScrollBar](/reference/PanelList.md#ScrollBar) | 🟩 |


## Scrollbar_Vertical
Parent | Creatable | Res File
------ |:---------:| --------
[ScrollBar](/reference/PanelList.md#ScrollBar) | 🟩 |


### ScrollBarSlider
Parent | Creatable | Res File
------ |:---------:| --------
[Panel](/reference/PanelList.md#Panel) | 🟥 |

Parameter | Default Value | Data Type | Info
--------- | ------------- | --------- | ----
ButtonBorder | NULL | border | Border of the slider. Only works with IgnoreScheme 1

Default scheme values
Font | Color | Border
---- | ----  | ------
   | ScrollBarSlider.FgColor | ScrollBarSliderBorder
   | ScrollBarSlider.BgColor | ButtonBorder


### ScrollBarButton
Parent | Creatable | Res File
------ |:---------:| --------
[Button](/reference/PanelList.md#Button) | 🟥 |

Default scheme values
Font | Color | Border
---- | ----  | ------
 Marlett | ScrollBarButton.FgColor | ScrollBarButtonBorder
   | ScrollBarButton.BgColor | ScrollBarButtonDepressedBorder
   | ScrollBarButton.ArmedFgColor | 
   | ScrollBarButton.ArmedBgColor | 
   | ScrollBarButton.DepressedFgColor | 
   | ScrollBarButton.DepressedBgColor | 


## CExScrollBar
"A scroll bar that can have specified width" (?)
Parent | Creatable | Res File
------ |:---------:| --------
[ScrollBar](/reference/PanelList.md#ScrollBar) | 🟥 |


## ImagePanel
A panel that displays an image

Parent | Creatable | Res File
------ |:---------:| --------
[Panel](/reference/PanelList.md#Panel) | 🟩 |

Parameter | Default Value | Data Type | Info
--------- | ------------- | --------- | ----
image | "" | material | The image to display
fillcolor | "0 0 0 0" | color | Background colour
fillcolor_override | "0 0 0 0" | color | Background colour
drawcolor | "255 255 255 255" | color | What colour to draw the image with
drawcolor_override | "255 255 255 255" | color | Override
scaleImage | "0" | bool | Whether to scale the image
scaleAmount | "0.0" | float | How much to scale the image, set to 0 for full size
scaleProportional | "0" | bool
tileImage | "0" | bool | Repeat the image endlessly
tileHorizontally | "0" | bool | Repeat the image endlessly in the X axis
tileVertically | "0" | bool | Repeat the image endlessly in the Y axis
rotation | "0" | int | Rotate image in 90 degree increments
positionImage | "1" | bool


## ScalableImagePanel
A panel that displays an image. Can have scalable corners & sides

Parent | Creatable | Res File
------ |:---------:| --------
[Panel](/reference/PanelList.md#Panel) | 🟩 |

Parameter | Default Value | Data Type | Info
--------- | ------------- | --------- | ----
image | "" | material | The image to display
drawcolor | "255 255 255 255" | color | What colour to draw the image with
src_corner_width | "0" | int | How big the texture's corners are in the X axis
src_corner_height | "0" | int | How big the texture's corners are in the Y axis
draw_corner_width | "0" | int | How big to draw the corners in the X axis
draw_corner_height | "0" | int | How big to draw the corners in the Y axis


## CTFImagePanel
An image panel that can be team coloured

Parent | Creatable | Res File
------ |:---------:| --------
[ScalableImagePanel](/reference/PanelList.md#ScalableImagePanel) | 🟩 |

Parameter | Default Value | Data Type | Info
--------- | ------------- | --------- | ----
teambg_0 | "" | material | Image when unassigned
teambg_1 | "" | material | Image on spectate
teambg_2 | "" | material | Image on RED
teambg_3 | "" | material | Image on BLU


## CSlideshowPanel
A panel that cycles image every 3 seconds

Parent | Creatable | Res File
------ |:---------:| --------
[EditablePanel](/reference/PanelList.md#EditablePanel) | 🟩 |

Parameter | Default Value | Data Type | Info
--------- | ------------- | --------- | ----
default_index | "0" | int
scaleimage | "0" | bool
scaleamount | "1.0" | float
image_* | NULL | material | replace * with number starting from 0

```
"SlideShow"
{
	"ControlName"			"CSlideshowPanel"

	"scaleimage"			"1"
	"image_0"				"replay/thumbnails/an_image"
	"image_1"				"replay/thumbnails/another_image"
	"image_2"				"replay/thumbnails/yet_another_image"
}
```

## CIconPanel
A panel that displays an icon from scripts/mod_textures.txt

Parent | Creatable | Res File
------ |:---------:| --------
[Panel](/reference/PanelList.md#Panel) | 🟩 |

Parameter | Default Value | Data Type | Info
--------- | ------------- | --------- | ----
icon | "" | icon | What icon to use
iconColor | "255 255 255 255" | color | What colour to draw the icon with
scaleImage | "0" | bool | Should the icon scale with the panel


## CAvatarImagePanel
Parent | Creatable | Res File
------ |:---------:| --------
[Panel](/reference/PanelList.md#Panel) | 🟩 |

Parameter | Default Value | Data Type | Info
--------- | ------------- | --------- | ----
scaleImage | "0" | bool
color_outline | "Black" | color


## CBitmapPanel
Parent | Creatable | Res File
------ |:---------:| --------
[Panel](/reference/PanelList.md#Panel) | 🟩 |

Parameter | Default Value | Data Type | Info
--------- | ------------- | --------- | ----
material | "" | material | Looks in materials/ instead of materials/vgui/
color | "255 255 255 255" | color


## CBitmapImagePanel
An image that can maintain its aspect ratio when resized

Parent | Creatable | Res File
------ |:---------:| --------
[Panel](/reference/PanelList.md#Panel) | 🟩 |

Parameter | Default Value | Data Type | Info
--------- | ------------- | --------- | ----
image | "BitmapImagePanel" | material | The image to display
imagecolor | "255 255 255 255" | color | What colour to draw the image with
imageAlignment | "center" | string | Where the image should align, uses same values as textAlignment
preserveAspectRatio | "0" | bool | Should the aspect ratio be maintained
filtered | "0" | bool


## CTFLogoPanel
A rotating TF logo

Parent | Creatable | Res File
------ |:---------:| --------
[Panel](/reference/PanelList.md#Panel) | 🟩 |

Parameter | Default Value | Data Type | Info
--------- | ------------- | --------- | ----
radius | "5" | int | Size of the logo
velocity | "0.0" | float | Speed of the logo



## TextEntry
A panel you can type text in.

Parent | Creatable | Res File
------ |:---------:| --------
[Panel](/reference/PanelList.md#Panel) | 🟩 |

Parameter | Data Type | Info
--------- | --------- | ----
font | font | What font to use
textHidden | bool | Censor the text
editable | bool | Allow the user to change the text
maxchars | int | Maximum amount of characters allowed
NumericInputOnly | bool | Only allow numbers
selectallonfirstfocus | bool
unicode | bool
disabledFgColor_override | color
disabledBgColor_override | color
selectionColor_override | color
selectionTextColor_override | color
defaultSelectionBG2Color_override | color

Default scheme values
Font | Color | Border
---- | ----  | ------
 Default | TextEntry.TextColor | ButtonDepressedBorder
 DefaultVerySmall | TextEntry.BgColor | 
   | TextEntry.CursorColor | 
   | TextEntry.DisabledTextColor | 
   | TextEntry.DisabledBgColor | 
   | TextEntry.SelectedTextColor | 
   | TextEntry.SelectedBgColor | 
   | TextEntry.OutOfFocusSelectedBgColor | 
   | TextEntry.FocusEdgeColor | 


## ComboBox
A panel with a drop down list.

Parent | Creatable | Res File
------ |:---------:| --------
[TextEntry](/reference/PanelList.md#TextEntry) | 🟩 |

Parameter | Data Type | Info
--------- | --------- | ----
border_override | border | Changes the border
Button{} | ControlName: ComboBoxButton

Default scheme values
Font | Color | Border
---- | ----  | ------
   |   | ComboBoxBorder

### ComboBoxButton
Parent | Creatable | Res File
------ |:---------:| --------
[Button](/reference/PanelList.md#Button) | 🟥 |

Default scheme values
Font | Color | Border
---- | ----  | ------
 Marlett | ComboBoxButton.ArrowColor | ScrollBarButtonBorder
   | ComboBoxButton.BgColor | 
   | ComboBoxButton.ArmedArrowColor | 
   | ComboBoxButton.DisabledBgColor | 
   


## Slider
A panel with a movable slider.

Parent | Creatable | Res File
------ |:---------:| --------
[Panel](/reference/PanelList.md#Panel) | 🟩 |

Parameter | Data Type | Info
--------- | --------- | ----
leftText | string | Text on the left
rightText | string | Text on the right
thumbwidth | int | Width of the slider
numTicks | int | Number of lines along the slider
rangeMin | int | What value the slider starts at
rangeMax | int | What value the slider ends at

Default scheme values
Font | Color | Border
---- | ----  | ------
 DefaultVerySmall | Slider.NobColor | ButtonBorder
   | Slider.TextColor | ButtonDepressedBorder
   | Slider.TrackColor | 
   | Slider.DisabledTextColor1 | 
   | Slider.DisabledTextColor2 | 


## CCVarSlider
A slider that can change a cvar.

Parent | Creatable | Res File
------ |:---------:| --------
[Slider](/reference/PanelList.md#Slider) | 🟩 |

Parameter | Data Type | Info
--------- | --------- | ----
minvalue | float | Minimum value allowed
maxvalue | float | Maximum value allowed
cvar_name | string | Cvar to change
use_convar_minmax | bool | Use the minvalue & maxvalue of the cvar instead
allowoutofrange


## ProgressBar
A segmented progress bar.

Parent | Creatable | Res File
------ |:---------:| --------
[Panel](/reference/PanelList.md#Panel) | 🟩 |

Parameter | Data Type | Info
--------- | --------- | ----
variable | string | What to measure
progress | float


## ContinuousProgressBar
Parent | Creatable | Res File
------ |:---------:| --------
[ProgressBar](/reference/PanelList.md#ProgressBar) | 🟩 |


## CBuildingHealthBar
A progress bar that changes colour when below 50%.

Parent | Creatable | Res File
------ |:---------:| --------
[ProgressBar](/reference/PanelList.md#ProgressBar) | 🟩 |

Default scheme values
Font | Color | Border
---- | ----  | ------
   | BuildingHealthBar.BgColor | 
   | BuildingHealthBar.Health | 
   | BuildingHealthBar.LowHealth | 


## CircularProgressBar

Parent | Creatable | Res File
------ |:---------:| --------
[ProgressBar](/reference/PanelList.md#ProgressBar) | 🟩 |

Parameter | Data Type | Info
--------- | --------- | ----
fg_image | material | Image to use as the progress bar
bg_image | material | Image to use as the background



## RotatingProgressBar

Parent | Creatable | Res File
------ |:---------:| --------
[ProgressBar](/reference/PanelList.md#ProgressBar) | 🟩 |

Parameter | Data Type | Info
--------- | --------- | ----
image | material | Image that rotates
rotating_x | float | X position of the image
rotating_y | float | Y position of the image
rotating_wide | float | Wide of the image
rotating_tall | float | Tall of the image
start_degrees | float | Rotation of the image when variable == 0
end_degrees | float | Rotation of the image when variable == 100
rot_origin_x_percent | float | X position of what point the image rotates around, float value 0.0 - 1.0
rot_origin_Y_percent | float | Y position of what point the image rotates around, float value 0.0 - 1.0
approach_speed | float | The speed of rotation


## CAccountPanel

Parent | Creatable | Res File
------ |:---------:| --------
[EditablePanel](/reference/PanelList.md#EditablePanel) | 🟥 |

Parameter | Data Type | Info
--------- | --------- | ----
delta_item_start_y | int
delta_item_end_y | int
delta_item_x | int
delta_item_end_x | int
bg_texture | material
bg_image_x | int
bg_image_y | int
bg_image_wide | int
bg_image_tall | int
PositiveColor | color
NegativeColor | color
EventColor | color
RedRobotScoreColor | color
BlueRobotScoreColor | color
delta_lifetime | float
delta_item_font | font
delta_item_font_big | font
negative_flip_dir | bool


## CModelPanel
A panel that shows a 3D model.

Parent | Creatable | Res File
------ |:---------:| --------
[EditablePanel](/reference/PanelList.md#EditablePanel) | 🟩 |

Parameter | Data Type | Info
--------- | --------- | ----
fov | int | FOV of the model
start_framed | bool
allow_offscreen | bool
model{}

The following parameters need to be in model{}
Parameter | Data Type | Info
--------- | --------- | ----
modelname | string | What model to use
modelname_hwm | string
skin | int | Which skin to use
angles_x | float | Rotation around X axis
angles_y | float | Rotation around Y axis
angles_z | float | Rotation around Z axis
origin_x | float | Position in the X axis
origin_y | float | Position in the Y axis
origin_z | float | Position in the Z axis
frame_origin_x | float
frame_origin_y | float
frame_origin_z | float
vcd | string
spotlight | bool
animation{} | | Animations of the model
attached_model{} | | Attach another model eg. a gun

The following parameters need to be in animation{}
Parameter | Data Type | Info
--------- | --------- | ----
name | string
sequence | string
activity | string
default | bool
pose_parameters{}

The following parameters need to be in attached_model{}
Parameter | Data Type | Info
--------- | --------- | ----
modelname | string
skin | int


## CPotteryWheelPanel

Parent | Creatable | Res File
------ |:---------:| --------
[EditablePanel](/reference/PanelList.md#EditablePanel) | 🟥 |

Parameter | Data Type | Info
--------- | --------- | ----
useparentbg | bool
lights{}

The following parameters need to be in lights{}
Parameter | Data Type | Info
--------- | --------- | ----
name | string | Accepts "directional", "point" or "spot"
color | color
direction | vector | directional & spot
attenuation | vector | point & spot
origin | vector | point & spot
maxDistance | float | point & spot
inner_cone_angle | float | spot
outer_cone_angle | float | spot
exponent | float | spot

```
"lights"
{
	"1"
	{
		"name"	"directional"
		"color"	"10 10 10"
		"direction" "0 0 0"
	}
}
```


## CMDLPanel

Parent | Creatable | Res File
------ |:---------:| --------
[CPotteryWheelPanel](/reference/PanelList.md#CPotteryWheelPanel) | 🟥 |


## CBaseModelPanel

Parent | Creatable | Res File
------ |:---------:| --------
[CMDLPanel](/reference/PanelList.md#CMDLPanel) | 🟩 |

Parameter | Data Type | Info
--------- | --------- | ----
render_texture | bool
use_particle | bool
start_framed | bool
disable_manipulation | bool
fov | int
allow_rot | bool
allow_pitch | bool
allow_manip | bool
max_pitch | float
model{}

The following parameters need to be in model{}
Parameter | Data Type | Info
--------- | --------- | ----
force_pos | bool
modelname | string | What model to use
modelname_hwm | string
skin | int | Which skin to use
angles_x | float | Rotation around X axis
angles_y | float | Rotation around Y axis
angles_z | float | Rotation around Z axis
origin_x | float | Position in the X axis
origin_y | float | Position in the Y axis
origin_z | float | Position in the Z axis
frame_origin_x | float
frame_origin_y | float
frame_origin_z | float
vcd | string
spotlight | bool
animation{} | Animations of the model
attached_model{} | Attach another model eg. a gun

The following parameters need to be in animation{}
Parameter | Data Type | Info
--------- | --------- | ----
name | string
sequence | string
activity | string
default | bool
pose_parameters{}

The following parameters need to be in attached_model{}
Parameter | Data Type | Info
--------- | --------- | ----
modelname | string
skin | int


## CTFPlayerModelPanel

Parent | Creatable | Res File
------ |:---------:| --------
[CBaseModelPanel](/reference/PanelList.md#CBaseModelPanel) | 🟩 |

Parameter | Data Type | Info
--------- | --------- | ----
disable_speak_event | | bool
customclassdata{} | Allows you to set fov, origin and angles for each class individually


## CItemModelPanel
A panel that shows an item.

Parent | Creatable | Res File
------ |:---------:| --------
[EditablePanel](/reference/PanelList.md#EditablePanel) | 🟩 |

Parameter | Data Type | Info
--------- | --------- | ----
special_attributes_only | bool
model_xpos | int | Position of the model in the X axis
model_ypos | int |  Position of the model in the Y axis
model_wide | int |  Wide of the model
model_tall | int |  Tall of the model
model_center_x | bool | Center the model in the X axis
model_center_y | bool | Center the model in the Y axis
tf2_icon_offset_x | int
tf2_icon_offset_y | int
noitem_use_fullpanel | bool
text_center | bool | Center the text in the Y axis
text_center_x | bool | Center the text in the X axis
use_item_sounds | bool
name_only | bool | Don't show the stats of the item
attrib_only | bool | Don't show the name of the item
model_only | bool | Don't show the name or the stats of the item
model_hide | bool | Don't show the model
paint_icon_hide | bool
resize_to_text  | bool
name_label_alignment | int
text_xpos | int | Position of the text in the X axis
text_ypos | int | Position of the text in the Y axis
text_wide | int | Wide of the text
text_yoffset | int
padding_height | int
max_text_height | int
text_forcesize | int
inset_eq_x | int| Equipped label X position
inset_eq_y | int | Equipped label Y position
standard_text_color | bool
is_mouseover | bool
wide | int
tall | int
collection_list_xpos | int
text_xpos_collection | int
hide_collection_panel | bool
hide_modifier_icons | bool
itemmodelpanel{}

Default scheme values
Font | Color | Border
---- | ----  | ------
ItemFontNameSmallest |  | 
ItemFontNameSmall |  | 
ItemFontNameLarge |  | 
ItemFontNameLarger |  | 
ItemFontAttribSmallest |  | 
ItemFontAttribSmallv2 |  | 
ItemFontAttribLarge |  | 
ItemFontAttribLarger |  | 


### CEmbeddedItemModelPanel
Model panel inside CItemModelPanel.

Parent | Creatable | Res File
------ |:---------:| --------
[CBaseModelPanel](/reference/PanelList.md#CBaseModelPanel) | 🟩 |

Parameter | Data Type | Info
--------- | --------- | ----
force_use_model | bool
use_item_rendertarget | bool
inventory_image_type | int
force_square_image | bool
model_rotate_yaw_speed | int
use_pedestal | bool


## CTFParticlePanel
A panel that displays a particle effect.

Parent | Creatable | Res File
------ |:---------:| --------
[EditablePanel](/reference/PanelList.md#EditablePanel) | 🟩 |

Parameter | Data Type | Info
--------- | --------- | ----
ParticleEffects{}

The following parameters need to be in ParticleEffects{}
Parameter | Data Type | Info
--------- | --------- | ----
particle_xpos | string | X position of the particle
particle_ypos | string | Y position of the particle
particle_scale | float | Scale of the prticle
loop | bool | Loop the particle animation
start_activated | bool | Activate the particle animation immediately
particleName | string | Name of the particle
angles | vector | Rotation of the particle, takes 3 values
control_point* | vector | Particle control point setting, takes 3 values. Replace * with the number of the control point

```
"ParticleEffects"
{
	"1"
	{
		"particle_xpos"	"r20"
		"particle_ypos"	"c0"
		"particle_scale"	"1.0"
		"loop"			"1"
		"start_activated"	"1"
		"particleName"	""
		"angles"		"0 0 0"
		"control_point0"	"4 2 0"
		"control_point1"	"6 9 6"
	}
}
```


## CDrawingPanel
A panel you can draw in.

Parent | Creatable | Res File
------ |:---------:| --------
[Panel](/reference/PanelList.md#Panel) | 🟩 |

Parameter | Data Type | Info
--------- | --------- | ----
linecolor | color |  What colour the line should be
team_colors | bool | Use team colours for the line


## CNavigationPanel
A panel that has a list of buttons. The command the buttons use is select_0, select_1, select_2 etc. The commands can be aliased to something else.

Parent | Creatable | Res File
------ |:---------:| --------
[EditablePanel](/reference/PanelList.md#EditablePanel) | 🟩 |

Parameter | Data Type | Info
--------- | --------- | ----
auto_layout | bool
auto_scale | bool
display_vertically | bool
auto_layout_horizontal_buffer | int
auto_layout_vertical_buffer | int
selected_button_default | int
ButtonSettings{} | Settings for the buttons to use
Buttons{} | List of buttons

## VideoPanel

Parent | Creatable | Res File
------ |:---------:| --------
[EditablePanel](/reference/PanelList.md#EditablePanel) | 🟥 |

## CTFVideoPanel

Parent | Creatable | Res File
------ |:---------:| --------
[VideoPanel](/reference/PanelList.md#VideoPanel) | 🟩 |

Parameter | Data Type | Info
--------- | --------- | ----
command | string
start_delay | float
end_delay | float
loop | bool


## CTFArrowPanel

Parent | Creatable | Res File
------ |:---------:| --------
[Panel](/reference/PanelList.md#Panel) | 🟩 |


## CTFPlayerPanel

Parent | Creatable | Res File
------ |:---------:| --------
[EditablePanel](/reference/PanelList.md#EditablePanel) | 🟥 |

Parameter | Data Type | Info
--------- | --------- | ----
HealthIcon{} | ControlName: CTFPlayerPanelGUIHealth
ReadyBG{} | ControlName: ScalableImagePanel
ReadyImage{} | ControlName: ImagePanel



## CTFTeamStatus

Parent | Creatable | Res File
------ |:---------:| --------
[EditablePanel](/reference/PanelList.md#EditablePanel) | 🟥 |

Parameter | Data Type | Info
--------- | --------- | ----
team1_grow_dir | string | "west" or "east"
team2_grow_dir | string
max_size | int
6v6_gap | int
12v12_gap | int
team1_base_x | int
team1_max_expand | int
team2_base_x | int
team2_max_expand | int
playerpanels_kv{}


## CTFTeamStatusPlayerPanel

Parent | Creatable | Res File
------ |:---------:| --------
[CTFPlayerPanel](/reference/PanelList.md#CTFPlayerPanel) | 🟥 |

Parameter | Data Type | Info
--------- | --------- | ----
color_portrait_bg_red_local_player | color
color_portrait_bg_blue_local_player | color
color_portrait_bg_red | color
color_portrait_bg_blue | color
color_portrait_bg_red_dead | color
color_portrait_bg_blue_dead | color
color_bar_health_high | color
percentage_health_med | float
color_bar_health_med | color
percentage_health_low | float
color_bar_health_low | color
color_portrait_blend_dead_red | color
color_portrait_blend_dead_blue | color
healthbar{} | ControlName: ContinuousProgressBar
overhealbar{} | ControlName: ContinuousProgressBar
classimagebg{} | ControlName: Panel
DeathPanel{} | ControlName: ImagePanel


## CTFHudPlayerHealth

Parent | Creatable | Res File
------ |:---------:| --------
[EditablePanel](/reference/PanelList.md#EditablePanel) | 🟥 | resource/UI/HudPlayerHealth.res

Parameter | Data Type | Info
--------- | --------- | ----
HealthBonusPosAdj | int
HealthDeathWarning | float
HealthDeathWarningColor | color



## CTFSpectatorGUIHealth

Parent | Creatable | Res File
------ |:---------:| --------
[CTFHudPlayerHealth](/reference/PanelList.md#CTFHudPlayerHealth) | 🟥 | resource/UI/SpectatorGUIHealth.res



## CTFPlayerPanelGUIHealth

Parent | Creatable | Res File
------ |:---------:| --------
[CTFSpectatorGUIHealth](/reference/PanelList.md#CTFSpectatorGUIHealth) | 🟥 | SpectatorTournamentGUIHealth.res



## CHudBaseDeathNotice

Parent | Creatable | Res File
------ |:---------:| --------
[Panel](/reference/PanelList.md#Panel) | 🟥 |

Parameter | Data Type | Info
--------- | --------- | ----
LineHeight | float
LineSpacing | float
CornerRadius | float
MaxDeathNotices | float
RightJustify | bool
TextFont | font
IconColor | color
BaseBackgroundColor | color
LocalBackgroundColor | color
KillStreakBackgroundColor | color


## CTFHudDeathNotice

Parent | Creatable | Res File
------ |:---------:| --------
[CHudBaseDeathNotice](/reference/PanelList.md#CHudBaseDeathNotice) | 🟥 |

Parameter | Data Type | Info
--------- | --------- | ----
TeamBlue | color
TeamRed | color
PurpleText | color
GreenText | color
LocalPlayerColor | color


## CPvPRankPanel

Parent | Creatable | Res File
------ |:---------:| --------
[EditablePanel](/reference/PanelList.md#EditablePanel) | 🟩 |

Parameter | Data Type | Info
--------- | --------- | ----
matchgroup | string | MatchGroup_Ladder_6v6 or MatchGroup_Casual_12v12
show_type | bool
show_name | bool
show_model | bool
show_progress | bool
instantly_update | bool
show_sources_when_hidden | bool
xp_source_notification_center_x | int


## CMiniPvPRankPanel

Parent | Creatable | Res File
------ |:---------:| --------
[CPvPRankPanel](/reference/PanelList.md#CPvPRankPanel) | 🟩 |


## CTFMatchmakingDashboard

Parent | Creatable | Res File
------ |:---------:| --------
[ExpandablePanel](/reference/PanelList.md#ExpandablePanel) | 🟥 |

Commands | Info
-------- | ----
PlayCompetitive
PlayCasual
PlayMvM
PlayMvM_MannUp
PlayMvM_BootCamp
PlayTraining
PlayCommunity
CreateServer
PlayEvent
ShowCompAccess
ViewMatchSettings
CloseSideStack
NavigateSideStack
Context_LeaveParty
Context_OpenSettings
NotificationCreated
NotificationCleared


## CDashboardPartyMember

Parent | Creatable | Res File
------ |:---------:| --------
[EditablePanel](/reference/PanelList.md#EditablePanel) | 🟩 | resource/UI/DashboardPartyMember.res

Parameter | Data Type | Info
--------- | --------- | ----
party_slot | int


## CSteamFriendsListPanel

Parent | Creatable | Res File
------ |:---------:| --------
[CExScrollingEditablePanel](/reference/PanelList.md#CExScrollingEditablePanel) | 🟩 | 

Parameter | Data Type | Info
--------- | --------- | ----
columns_count | int
inset_x | int
inset_y | int
row_gap | int
column_gap | int
friendpanel_kv{} | 


### CSteamFriendPanel

Parent | Creatable | Res File
------ |:---------:| --------
[EditablePanel](/reference/PanelList.md#EditablePanel) | 🟥 | resource/UI/SteamFriendPanel.res

Commands | Info
-------- | ----
open_menu
Context_InviteParty
Context_JoinParty
Context_JoinServer
Context_SendMessage


## CPlaylistEntry

Parent | Creatable | Res File
------ |:---------:| --------
[EditablePanel](/reference/PanelList.md#EditablePanel) | 🟩 | resource/ui/MainMenuPlayListEntry.res

Parameter | Data Type | Info
--------- | --------- | ----
image_name | string
button_token | string
button_command | string
desc_token | string
matchgroup | int


## CMVMCriteriaPanel

Parent | Creatable | Res File
------ |:---------:| --------
[EditablePanel](/reference/PanelList.md#EditablePanel) | 🟥 | Resource/UI/MvMCriteria.res

Parameter | Data Type | Info
--------- | --------- | ----
challenge_spacer | int
challenge_name_width | int
challenge_skill_width | int
challenge_completed_size | int
challenge_map_width | int
challenge_map_height | int
has_ticket_width | int
squad_surplus_width | int
squad_surplus_width | int
badge_level_width | int
tour_name_width | int
tour_skill_width | int
tour_progress_width | int
tour_number_width | int


## CExplanationPopup
A speech bubble panel. Accepts button commands "close", "nextexplanation" & "prevexplanation".

Parent | Creatable | Res File
------ |:---------:| --------
[EditablePanel](/reference/PanelList.md#EditablePanel) | 🟩 | resource/ui/ExplanationPopup.res

Parameter | Data Type | Info
--------- | --------- | ----
next_explanation | string | Next speech bubble to draw
res_file_controls | bool |
force_close | bool | Disable the rest of the screen until this popup is closed
callout_inparents_x | int | X position of the speech bubble's tail
callout_inparents_y | int | Y position of the speech bubble's tail
start_x | int | X position before the expanding animation
start_y | int | y position before the expanding animation
start_wide | int | Wide before the expanding animation
start_tall | int | Tall before the expanding animation
end_x | int | X position after the expanding animation
end_y | int | y position after the expanding animation
end_wide | int | Wide after the expanding animation
end_tall | int | Tall after the expanding animation
explanation_title | string
explanation_body | string


## CRepeatingContainer
A panel that automatically positions its contents.

Parent | Creatable | Res File
------ |:---------:| --------
[EditablePanel](/reference/PanelList.md#EditablePanel) | 🟩 |

Parameter | Data Type | Info
--------- | --------- | ----
spacing_method | string | How to space the panels. METHOD_STEP spaces them by a certain value, METHOD_EVEN spaces them evenly
x_step | int | Value to space the panels when using METHOD_STEP
IndividualSettings{} | Where you place the panels to be sorted
CommonSettings{} | What settings the panels should have by default

```
"Example"
{
  "ControlName"  "CRepeatingContainer"

  "IndividualSettings"
  {
    "Item1"
    {
      "ControlName"  "Label"
    }
    "Item2"
    {
      "ControlName"  "Label"
    }
    "Item3"
    {
      "ControlName"  "Label"
    }
  }

  "CommonSettings"
  {
    "fgcolor_override"  "69 69 69 255"
    "font"              "Default"
  }
}
```

## CLoadoutPresetPanel

Parent | Creatable | Res File
------ |:---------:| --------
[EditablePanel](/reference/PanelList.md#EditablePanel) | 🟥 | Resource/UI/LoadoutPresetPanel.res

Parameter | Data Type | Info
--------- | --------- | ----
presetbutton_kv{}


## CCyclingAdContainerPanel

Parent | Creatable | Res File
------ |:---------:| --------
[EditablePanel](/reference/PanelList.md#EditablePanel) | 🟩 | Resource/UI/econ/CyclingAdContainer.res

Parameter | Data Type | Info
--------- | --------- | ----
items{}


## CBaseAdPanel

Parent | Creatable | Res File
------ |:---------:| --------
[EditablePanel](/reference/PanelList.md#EditablePanel) | 🟥 |

Parameter | Data Type | Info
--------- | --------- | ----
present_time | float


## CItemAdPanel

Parent | Creatable | Res File
------ |:---------:| --------
[CBaseAdPanel](/reference/PanelList.md#CBaseAdPanel) | 🟥 |

Parameter | Data Type | Info
--------- | --------- | ----
item | string
show_market | bool
show_name | bool
show_ad_text | bool
show_background | bool


## CBuildingStatusAlertTray

Parent | Creatable | Res File
------ |:---------:| --------
[Panel](/reference/PanelList.md#Panel) | 🟩 |

Parameter | Data Type | Info
--------- | --------- | ----
icon | string
deployed | float


## CDimmerButton

Parent | Creatable | Res File
------ |:---------:| --------
[Button](/reference/PanelList.md#Button) | 🟥 |


## CDraggableScrollingPanel
A panel that changes size when you mouse wheel over it.

Parent | Creatable | Res File
------ |:---------:| --------
[EditablePanel](/reference/PanelList.md#EditablePanel) | 🟩 |

Parameter | Default Value | Data Type | Info
--------- | ------------- | --------- | ----
min_zoom | "1.0" | float
max_zoom | "2.0" | float
zoom | "1.0" | float
mouse_wheel_zoom_rate | "0.05" | float
pending_children{} | |

The following parameters need to be in pending_children{}
Parameter | Default Value | Data Type | Info
--------- | ------------- | --------- | ----
child_name | | string | The fieldname of a child panel
pin | "4" | int | Doesn't seem to have an effect for some reason
scale | "1" | bool
move | "1" | bool

```
"pending_children"
{
	"1"
	{
		"child_name"	"test_panel_1"
		"pin"		"0"
		"scale"		"1"
		"move"		"1"
	}
	"2"
	{
		"child_name"	"test_panel_2"
		"pin"		"0"
		"scale"		"1"
		"move"		"1"
	}
}
```

## CWarLandingPanel
Parent | Creatable | Res File
------ |:---------:| --------
[EditablePanel](/reference/PanelList.md#EditablePanel) | 🟩 | Resource/UI/Econ/WarJoinPanel.res

Parameter | Default Value | Data Type | Info
--------- | ------------- | --------- | ----
scene_anim_name | NULL | string | Name of animation that runs in SceneContainer

Commands | Info
-------- | ----
close |
join_war* |
confirm_team |
dismiss_joining_result |
view_update_comic |


## CWarStandingPanel
Parent | Creatable | Res File
------ |:---------:| --------
[EditablePanel](/reference/PanelList.md#EditablePanel) | 🟩 | Resource/UI/Econ/WarStandingPanel.res


Parameter | Default Value | Data Type | Info
--------- | ------------- | --------- | ----
war_name | NULL | string | Name of war to use, crashes game if not valid

## CTFItemCardPanel
A leftover unused panel.

Parent | Creatable | Res File
------ |:---------:| --------
[EditablePanel](/reference/PanelList.md#EditablePanel) | 🟩 | Resource/UI/Econ/ItemCardPanel_Series1.res

Parameter | Data Type | Info
--------- | --------- | ----
shadowoffset | int
