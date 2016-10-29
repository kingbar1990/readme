# Package Control
    import urllib.request,os,hashlib; h = 'df21e130d211cfc94d9b0905775a7c0f' + '1e3d39e33b79698005270310898eea76'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)

# Sublime Settings
    {
        "auto_complete": true,
        "caret_style": "solid",
        "color_scheme": "Packages/Theme - Brogrammer/brogrammer.tmTheme",
        "ensure_newline_at_eof_on_save": true,
        "file_exclude_patterns":
        [
            ".DS_Store",
            "*.pid",
            "*.pyc"
        ],
        "find_selected_text": true,
        "fold_buttons": false,
        "folder_exclude_patterns":
        [
            ".git",
            "__pycache__",
            "env",
            "env3"
        ],
        "font_face": "Inconsolata",
        "font_options":
        [
            "subpixel_antialias",
            "no_bold"
        ],
        "font_size": 13.0,
        "highlight_line": true,
        "highlight_modified_tabs": true,
        "ignored_packages":
        [
            "Vintage"
        ],
        "line_padding_bottom": 0,
        "line_padding_top": 0,
        "rulers":
        [
            79
        ],
        "scroll_past_end": false,
        "show_full_path": true,
        "show_minimap": false,
        "tab_size": 4,
        "theme": "Boxy Tomorrow.sublime-theme",
        "translate_tabs_to_spaces": true,
        "trim_trailing_white_space_on_save": true,
        "wide_caret": true,
        "word_wrap": true
    }
## Plugins
AdvancedNewFile, AutoFileName, Boxy Theme, BracketHighlighter, Color Highlighter, Djaneiro, Emmet, HTML5, Inc-Dec-Value, JavaScript Snippets, Material Theme, Predawn, SideBarEnhancements, SublimeOnSaveBuild, Tomorrow Color Schemes, Anaconda, ColorPicker, Emmet Css Snippets, HTML-CSS-JS Prettify, Minify, Random Everything, Terminal, Theme - Brogrammer

## Minify
    npm install -g clean-css uglifycss js-beautify html-minifier uglify-js minjson svgo stylus jade
