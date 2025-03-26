### manifest.json
- `manifest.json`. This JSON file describes the extension's capabilities and configuration. 
- most manifest files contain an `"action"` key which declares the image Chrome should use as the extension's action icon and the HTML page to show in a popup when the extension's action icon is clicked.


### When to reload the extension

The following table shows which components need to be reloaded to see changes:

|Extension component|Requires extension reload|
|---|---|
|The manifest|Yes|
|Service worker|Yes|
|Content scripts|Yes (plus the host page)|
|The popup|No|
|Options page|No|
|Other extension HTML pages|No|

