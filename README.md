Added native messaging to `openWith` extension.

A way to send a url from `vimium-c` to `openWith` and open it with a native os application.

Import the `openWith.xpi` file via the `Install Addon From File...` in `about:addons`, make sure you have the `xpinstall.signatures.required` flag set to `false` in `about:config`.

To receive messages from your browser, run the scripts(runtimes) from the native folder according to your os.

After creating a browser(app runner) in the extension, you can find the `browser_id` key by opening the `openWith` extension debug console in `about:debugging#/runtime/this-firefox` then typing `browsers`.

<img width="1920" height="175" alt="image" src="https://github.com/user-attachments/assets/548f76d5-9ec8-42d9-baba-ecee27fed440" />

Add a Custom key mapping:

```
map <v-openWith> sendToExtension id="openwith@darktrojan.net" raw
map vvv LinkHints.activateOpenUrl keyword="_openWith"
```
Add a custom search engine:
```
_openWith: vimium://run1/openWith#data={"type":"openUrl","browser_id":"5","url":"$s"}
```
Add as many variations you can.

