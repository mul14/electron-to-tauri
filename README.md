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

path::home_dir();        // ~/
path::desktop_dir();     // ~/Desktop
path::document_dir();    // ~/Documents
path::download_dir();    // ~/Downloads
path::audio_dir();       // ~/Music
path::video_dir();       // ~/Movies
path::picture_dir();     // ~/Pictures
path::public_dir();      // ~/Public

path::data_dir();        // ~/Library/Application\ Support
path::local_data_dir();  // ~/Library/Application\ Support
path::config_dir();      // ~/Library/Application\ Support

path::cache_dir();       // ~/Library/Caches
path::font_dir();        // ~/Library/Fonts
```
