Added native messaging to `openWith` extension.

A way to send a url from `vimium-c` to `openWith` and open it with a native os application.

Import the `openWith.xpi` file via the `Install Addon From File...` in `about:addons`, make sure you have the `xpinstall.signatures.required` flag set to `false` in `about:config`.

To receive messages from your browser, run the Python scripts (runtimes) from the native folder according to your OS.

After creating a browser (native app executable) in the extension, you can get the `browser_id` by requesting the `browsers` variable in the `openWith` DevTool console:

<img width="1920" height="163" alt="image" src="https://github.com/user-attachments/assets/5ae3ea78-4855-40fd-a979-fb1866f14fd4" />

From `vimium-c`:

Add a custom key mapping:

```
map <v-openWith> sendToExtension id="openwith@darktrojan.net" raw
map vvv LinkHints.activateOpenUrl keyword="_openWith"
```
Add a custom search engine:
```
_openWith: vimium://run1/openWith#data={"type":"openUrl","browser_id":"1","url":"$s"}
```
Add as many variations you want.

