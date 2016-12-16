# Giella CKEditor Plugin

This plugin is based on the SCAYT plugin for CKEditor (by webspellchecker.net), but uses a custom server and hfst-ospell for spell checking.

## Install

This bascially follows the [instructions](http://docs.ckeditor.com/#!/guide/dev_plugins) to manually install a CKEditor plugin (automatic installation only works for plugins that are in the CKEditor Add-ons Repository).

1. Copy the directory that contains this Readme file to your CKEditor plugin directory (and rename it to 'giella' if necessary). The plugin contents should the be in `ckeditor/plugins/giella/`.
2. Enable the plugin by adding it to `CKEDITOR.config.extraPlugins` and adjust its settings (see below).

## Plugin Settings

Assuming `CKEDITOR` is the instance of CKEditor you want to enable the giella plugin for.

```js
	// Activate customized 'giella' plugin. If you have other (extra) plugins, you can separate them with a comma (e.g, `'giella,other_plugin,third_plugin'`).
	config.extraPlugins = 'contextmenu,giella';
	config.giella_multiLanguageMode = true;
	config.giella_autoStartup = false;
	config.giella_sLang = 'se';

	// Set the URLs for the server giella should use. Below is the setting for using the Divvun server:
	config.giella_servicePath = "http://divvun.no:3000/spellcheck31/script/ssrv.cgi";
	config.giella_srcUrl = "http://divvun.no:3000/spellcheck/lf/giella3/ckgiella/ckgiella.js";
```

Setting ``config.giella_autoStartup`` to ``true`` will cause the spelling checker to automatically start when running the editor.
