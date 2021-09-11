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

fn main() {

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

}
```


## Desktop Notification

```js
// Electron

const { Notification } = require('electron');

new Notification({ 
  title: 'Greetings', 
  body: 'Hello World',
}).show();
```

```rs
// Tauri

use tauri::api::notification;

fn main() {

    let result = notification::Notification::new("id")
        .title("Greetings")
        .body("Hello world")
        .show();

    match result {
        Ok(v) => println!("Success: {:?}", v),
        Err(e) => println!("Error: {:?}", e),
    }

}
```


## Open a folder/file with default application

```js
const { shell } = require('electron')

await shell.showItemInFolder('/');
await shell.openPath('/Users/mul14/sample.txt');
```

```rs
fn main() {
    // Open folder with default application
    let _ = shell::open("/".into(), None);

    // Open text file with default application
    let result = shell::open("/Users/mul14/sample.txt".into(), None);

    match result {
        Ok(v) => println!("Success: {:?}", v),
        Err(e) => println!("Error: {:?}", e),
    }
}
```
