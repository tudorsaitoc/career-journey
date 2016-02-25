alt+. - Jump to the definition of the thing that the cursor is pointing at. If there is no known code location, goes to URL (if avail)
alt+, - Jump back to where you were when executing the previous alt+. command.

alt+space - When on a variable, select all references to that variable in the current file.

alt+o - Show quick documentation for the thing that the cursor is pointing at. Documentation includes the type, a description (if available), and documentation url (if available).

Troubleshooting
---------
As settings can be specified in several different places, sometimes in can be helpful to view the applied setting that's actually being used by the current file. You can do this by using the console:

view.settings().get('font_face')

Settings check order:
----------  
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


cd /path/to/sublime-text-N/Packages
git clone git://github.com/ternjs/tern_for_sublime.git
Next, make sure node.js and npm are installed (Tern is a JavaScript program), and install the depedencies of the package.

cd tern_for_sublime
npm install
On OS X, you might also need to install the Fix Mac Path Sublime plugin to help ST actually find your node binary.

You should be all set now.





JSON EXAMPLE:
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


