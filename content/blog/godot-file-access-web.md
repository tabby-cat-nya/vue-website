---

title: 'Managing files in Godot HTML5 Builds'
description: "In Web builds the standard FileAccess class dosen't work so you'll need to get a bit more creative"
date: '30-07-2024'
id: 3
tags: 'Programming, Godot'

---

Recently I worked on a project that required a file to be loaded, converted into a different file type and then saved to the users device.

Under most circumstances this task would be relatively simple, the inbuilt [FileAccess](https://docs.godotengine.org/en/stable/classes/class_fileaccess.html) class contains everything you need to load and save file, but, theres a catch. Due to web browser and Godot limitations this class *does not* work on HTML builds. here's what i ended up using to get around this:

## JavaScriptBridge
While FileAccess may not work, we do fortunately have another class which we can use to our advantage, that is [`JavaScriptBridge`](https://docs.godotengine.org/en/stable/classes/class_javascriptbridge.html).
This singleton only works in web exports since it allows us to connect the engine to the browsers JavaScript context meaning we can do all sorts of things through JavaScript

- Pros: If you can do it in JS, you can almost certainly do it here
- Cons: Godots inbuilt editor has basically no support for it so you'll be editing JS code without any error checking/IntelliSense unless you make it in another IDE 

![A text string containing JavaScript Code](https://github.com/Clevertop/vue-website/blob/master/public/img/blogImages/JsCodeInString.png?raw=true)

## Loading/Uploading Files
Uploading files is by far more complicated and while I'm sure you could implement it from scratch with the bridge I opted to use the [FileAccessWeb addon by scrawach](https://godotengine.org/asset-library/asset/2118) as it is exactly what I needed for my project

With it enabled its works much like the FIleAccess class + a FileDialog too

1. Create a variable to access it: `var file_access_web: FileAccessWeb = FileAccessWeb.new()`
2. Connect to its signals in your ready function: `file_access_web.loaded.connect(_on_file_loaded)` (there are more for tracking errors and upload progress, but this is all i needed)
3. Then when you want to bring up the file picker and start an upload, just call the `open()` function: `file_access_web.open()`

Note that your file will be uploaded in base64 format so you will need to convert it back to text (or the format its meant to be): 

```
func _on_file_loaded(file_name: String, type: String, base64_data: String):
	var file_contents = Marshalls.base64_to_utf8(base64_data)
```


## Saving/Downloading Files
Saving files is far easier since all we need to do is mess with the JavaScript download buffer:

`JavaScriptBridge.download_buffer(text.to_utf8_buffer(), "outputFilename.txt", "text/plain")`

---

And that's all there is too it, Hopefully support for this gets added to Godot as a whole in the future as this approach does have some limitations due to the types of files that can be encoded for the download buffer and converted back out of the base64 format but other than that, it since to see that the open source community is able to find solutions to these flaws and hopefully this can help you too :)