# PreSS
Preprocessed Style Sheet (PreSS) [Pronounced either Pre-S-S or Press]

PreSS is a preprocessed stylesheet syntax similar to the CSS syntax which
allows one to use JSON, to to set and use values which can be reused in
the PreSS file.

##Use

config.json

    {
        "theme": {
            "background": "#F44336",
            "font_color": "white",
        },

        "inverted_theme": {
            "background": "rgb(200, 200, 200)",
            "font_color": "#F44336"
        }
    }
    
myFile.pss

    div.navigation_menu {
        background: </[theme][background]/>;
        color: </[theme][font_color]/>;
    }

terminal
    
    user@localhost ~/path/to/pss/file $ pss myFile

terminal (if you want to use another config file other than `config.json`)

    user@localhost ~/path/to/pss/file $ pss myFile theme.json

    (pss <file without .pss> <configuration file>)

