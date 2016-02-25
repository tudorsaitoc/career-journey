Settings check order:
1 Packages/Default/Prefreences.sublime-settings
2 Packages/Default/(platform).sublime-settings
3 Packages/User/Prefreences.sublime-settings
4 <project>
5 pack/<language(HTML, CSS, etc)>/lang.ssublimeserttings
6 pack / user/lang.sublimesettings
7 <buffer settings>

***  8 You can also save setttings under distraction mode settings *** 

Changing Settings with a Key Binding

The toggle_setting command can be used to toggle a setting. For example, to make a key binding that toggles the word_wrap setting on the current file, you can use (in Preferences/Key Bindings - User):

{
    "keys": ["alt+w"],
    "command": "toggle_setting",
    "args":
    {
        "setting": "word_wrap"
    }
}
The set_setting command can be used to set a setting to a specific value. For example, this key binding makes the current file use the Cobalt color scheme:

{
    "keys": ["ctrl+k", "ctrl+c"],
    "command": "set_setting",
    "args":
    {
        "setting": "color_scheme",
        "value": "Packages/Color Scheme - Default/Cobalt.tmTheme"
    }
}
The settings modified here are buffer specific settings: they override any settings placed in a settings file, but apply to the current file only.



{
    "folders":
    [
        {
            "path": "src",
            "folder_exclude_patterns": ["backup"]
        },
        {
            "path": "docs",
            "name": "Documentation",
            "file_exclude_patterns": ["*.css"]
        }
    ],
    "settings":
    {
        "tab_size": 8
    },
    "build_systems":
    [
        {
            "name": "List",
            "cmd": ["ls"]
        }
    ]
}


