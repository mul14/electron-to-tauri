# Electron to Tauri

## Path

```js
// Electron

const { app } = require('electron');

app.getPath('home');         // ~/

app.getPath('appData');      // ~/Library/Application\ Support
                             // ~/.config

app.getPath('userData');     // ~/Library/Application\ Support/app-name
                             // ~/.config/app-name

app.getPath('cache');        // ~/Caches
app.getPath('temp');         //
app.getPath('exe');          //
app.getPath('module');       //
app.getPath('desktop');      // ~/Desktop
app.getPath('documents');    // ~/Documents
app.getPath('downloads');    // ~/Downloads
app.getPath('music');        // ~/Music
app.getPath('pictures');     // ~/Pictures
app.getPath('videos');       // ~/Videos
app.getPath('recent');       //
app.getPath('logs');         //
app.getPath('crashDump');    //
```

```rs
// Tauri

use tauri::api::path;

path::home_dir();        // /Users/mul14
path::desktop_dir();     // /Users/mul14/Desktop
path::document_dir();    // /Users/mul14/Documents
path::download_dir();    // /Users/mul14/Downloads
path::audio_dir();       // /Users/mul14/Music
path::video_dir();       // /Users/mul14/Movies
path::picture_dir();     // /Users/mul14/Pictures
path::public_dir();      // /Users/mul14/Public

path::data_dir();        // /Users/mul14/Library/Application\ Support
path::local_data_dir();  // /Users/mul14/Library/Application\ Support
path::config_dir();      // /Users/mul14/Library/Application\ Support

path::cache_dir();       // /Users/mul14/Library/Caches
path::font_dir();        // /Users/mul14/Library/Fonts
```




