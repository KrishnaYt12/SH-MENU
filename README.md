# SH-Menu Customly Redesigned Full HTML JS, CSS By Shadows HUB 
Menu System for the qbcore Framework with better interface and this menu comes with a custom search option which is also editable through the css file inside the HTML folder.

# Steps Of How to Use Search Option :
* Open Your Menu
* Tap In The Search Bar With Your Cursor
* Type Anything What You Want
* Press Enter On Your Keyboard For The Results

# How To Go Back :
* Tap In The Search Bar With Your Cursor
* Delete Everything You Have Written There
* Press Enter On Your Keyboard For The Results

# Previews :
![Redesigned Menu With Search Option](https://cdn.discordapp.com/attachments/1182416054941667388/1208163641442959420/Screenshot_2024-02-17_025223.png?ex=65e24912&is=65cfd412&hm=b52c58a4ec25527dc8996d03d61466801b03656d56334775f82eba46024a49be&)

This is a modified version of **[NH Context](https://forum.cfx.re/t/no-longer-supported-standalone-nerohiro-s-context-menu-dynamic-event-firing-menu/2564083)** by **[NeroHiro](https://github.com/nerohiro)**

--[[
EXAMPLE MENU
--]]

```
RegisterCommand("shmenutest", function(source, args, raw)
    openMenu({
        {
            header = "Main Title",
            isMenuHeader = true, -- Set to true to make a nonclickable title
        },
        {
            header = "Sub Menu Button",
            txt = "This goes to a sub menu",
            params = {
                event = "qb-menu:client:testMenu2",
                args = {
                    number = 1,
                }
            }
        },
        {
            header = "Sub Menu Button",
            txt = "This goes to a sub menu",
            disabled = true,
            -- hidden = true, -- doesnt create this at all if set to true
            params = {
                event = "qb-menu:client:testMenu2",
                args = {
                    number = 1,
                }
            }
        },
    })
end)
```
```
RegisterNetEvent('qb-menu:client:testMenu2', function(data)
    local number = data.number
    openMenu({
        {
            header = "< Go Back",
        },
        {
            header = "Number: "..number,
            txt = "Other",
            params = {
                event = "qb-menu:client:testButton",
                args = {
                    message = "This was called by clicking this button"
                }
            }
        },
    })
end)
```
```
RegisterNetEvent('qb-menu:client:testButton', function(data)
    TriggerEvent('qbcore:Notify', data.message)
end)
```

# License

    qbcore Framework
    Copyright (C) 2021 Joshua Eger

    This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program.  If not, see <https://www.gnu.org/licenses/>
