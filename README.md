# PreSS
Preprocessed Style Sheet (PreSS) [Pronounced either Pre-S-S or Press]

PreSS is a preprocessed stylesheet syntax similar to the CSS syntax which
allows one to use JSON, to to set and use values which can be reused in
the PreSS file.

##How Is It Useful
PreSS is useful for when you want to be able to reuse CSS properties, and
handle many elements at once. For example, if you were to use one color theme
today, you may use "#212121" everywhere in your CSS. When it comes time to change
the color theme, you will have to revise every line of CSS. Instead these colors
can be predifined, and applied everywhere in your CSS.

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

