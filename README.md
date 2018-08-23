![A board with passing tests](https://github.com/alffox/growser/blob/master/app/images/icon-96.png)

# Growser

A browser plugin that injects and runs Jasmine tests into a Liferay DXP web site

##  What does it do ?

Once installed, the plugin will load a suite of front-end tests written in [Jasmine](https://jasmine.github.io/) / [Jasmine-jquery](https://github.com/velesin/jasmine-jquery) that will be applied to a certain URL (in this case, a Liferay DXP website).

After the page will be loaded, the test results will be appearing at the very bottom of the page:

![Jasmine tests running on a Liferay DXP page](https://github.com/alffox/grow-theme-user-profile-theme-automated-tests/blob/master/images/preview.png)

## How to install it ?

### For Chrome:

1) Get the standalone plugin with `.chrome` string appended to the filename (e.g.: `growser.v1.0.0.chrome.zip`), this is at: https://github.com/alffox/growser/tree/master/extensions
2) Type `chrome://extensions/` in your address bar and hit enter
3) Enable Developer Mode: https://developers.chrome.com/extensions/faq#faq-dev-01
4) Drag and drop the file into the Chrome Extensions window
4) The plugin will be installed and will appear in the extensions list. Navigate to the pages you wish to test in order to output the related Jasmine test results at the bottom of the page.

Chrome FAQ's on extensions: https://developers.chrome.com/extensions/faq

### For Firefox:

1) Get the standalone plugin with `.firefox` string appended to the filename (e.g.: `growser.v1.0.0.firefox.zip`), this is at: https://github.com/alffox/growser/tree/master/extensions
2) Type `about:debugging#addons` in your address bar and hit enter
3) Click on `Load Temporary Add-on...` on the top-right side of the column
4) Select your Firefox plugin. The plugin will be temporarily installed and will appear at the top of the temporary extensions list. Navigate to the pages you wish to test in order to output the related Jasmine test results at the bottom of the page.
5) The plugin will be removed automatically upon restarting Firefox

Learn more at: https://developer.mozilla.org/en-US/docs/Tools/about:debugging#Enabling_add-on_debugging

## How to add more test ?

1) Write your Jasmine tests suite and save it in a .js file at: https://github.com/alffox/growser/tree/master/app/tests
2) Add your URL pattern and tests suite file at https://github.com/alffox/growser/blob/master/app/manifest.json within the `"content_scripts"` element, for example:

```
    {
      "matches": ["https://my-dummy-url.com/"],
      "js" : ["tests/my-dummy-tests.js"],
      "run_at": "document_end",
      "all_frames": false
    }
```
3) Rebuild the app with the [automated](https://github.com/alffox/growser#how-to-build-and-develop-it-automatically-) or the [manual](https://github.com/alffox/growser#how-to-build-it-manually-) method

## How to build and develop it automatically ?

Please check these resources:

https://github.com/webextension-toolbox/webextension-toolbox
https://github.com/webextension-toolbox/generator-web-extension

## How to build it manually ?

At times, there may be need to run the plugins locally, temporarily, in developer mode. Follow these methods in order to rebuild the plugin:

### Chrome
1) Navigate to the app folder and zip all the files and folders contained in it under a conventional name, e.g. `growser.v1.0.0.chrome.zip`
2) Follow the relevant "How to Install it?" section: https://github.com/alffox/growser#for-chrome

### Firefox
1) Install web-ext as per these instructions: https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/Getting_started_with_web-ext
2) Run the command `web-ext build` from the app folder and get the plugin in the generated `web-ext-artifacts` directory
3) Follow the relevant "How to Install it?" section: https://github.com/alffox/growser#for-firefox

## External libraries used

- [jQuery](https://jquery.com/) - v. 1.7.2
- [Jasmine](https://jasmine.github.io/) - v. 3.1.0
- [Jasmine-Jquery](https://github.com/velesin/jasmine-jquery) - v. 2.1.1