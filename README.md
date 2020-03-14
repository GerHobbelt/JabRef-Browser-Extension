# JabRef Browser Extension
> [Firefox](https://addons.mozilla.org/en-US/firefox/addon/jabfox?src=external-github) -  [Chrome](https://chrome.google.com/webstore/detail/jabref-browser-extension/bifehkofibaamoeaopjglfkddgkijdlh) - [Vivaldi](https://chrome.google.com/webstore/detail/jabref-browser-extension/bifehkofibaamoeaopjglfkddgkijdlh)

Browser extension for users of the bibliographic reference manager [JabRef](https://www.jabref.org/).
It automatically identifies and extracts bibliographic information on websites and sends them to JabRef with one click.

When you find an interesting article through Google Scholar, the arXiv or journal websites, this browser extension allows you to add those references to JabRef.
Even links to accompanying PDFs are sent to JabRef, where those documents can easily be downloaded, renamed and placed in the correct folder. 
[A wide range of publisher sites, library catalogs and databases are supported](https://www.zotero.org/support/translators).

_Please post any issues or suggestions [here on GitHub](https://github.com/JabRef/JabRef-Browser-Extension/issues)._

## Installation and Configuration
Normally, you simply install the extension from the browser store and are ready to go.
> [Firefox](https://addons.mozilla.org/en-US/firefox/addon/jabfox?src=external-github) -  [Chrome](https://chrome.google.com/webstore/detail/jabref-browser-extension/bifehkofibaamoeaopjglfkddgkijdlh) - [Vivaldi](https://chrome.google.com/webstore/detail/jabref-browser-extension/bifehkofibaamoeaopjglfkddgkijdlh)

Sometimes, a manual installation is necessary (e.g. if you use the portable version of JabRef). In this case, please follow the steps described [in the user manual](https://docs.jabref.org/import-export/import/jabref-browser-extension)

## Usage
After the installation, you should be able to import bibliographic references into JabRef directly from your browser.
Just visit a publisher site or some other website containing bibliographic information (for example, [the arXiv](http://arxiv.org/list/gr-qc/pastweek?skip=0&show=5)) and click the JabRef symbol in the Firefox search bar (or press <kbd>Alt</kbd>+<kbd>Shift</kbd>+<kbd>J</kbd>).
Once the JabRef browser extension has extracted the references and downloaded the associated PDF's, the import window of JabRef opens.

You might want to configure JabRef so that new entries are always imported in an already opened instance of JabRef.
For this, activate "Remote operation" under the Advanced tab in the JabRef Preferences.


## About this Add-On

Internally, this browser extension uses the magic of Zotero's site translators.
Thus most of the credit has to go to the Zotero development team and to the many authors of the [site translators collection](https://github.com/zotero/translators).
Note that this browser extension does not make any changes to the Zotero database and thus both plug-ins coexist happily with each other.

## Contributing to the Development

JabRef browser extension uses the [WebExtensions API](https://developer.mozilla.org/en-US/Add-ons/WebExtensions).

Preparation:
1. Install [Node.js](https://nodejs.org) (e.g., `choco install nodejs`)
2. Install [gulp](https://gulpjs.com/) and [web-ext](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/Getting_started_with_web-ext): `npm install --global gulp-cli web-ext`
3. [Fork the repository](https://help.github.com/articles/fork-a-repo/).
4. Start browser with the add-on activated: 
   Firefox: `npm run dev:firefox`
   Chrome: `npm run dev:opera`

Now just follow the typical steps to [contribute code](https://guides.github.com/activities/contributing-to-open-source/#contributing):
1. Create your feature branch: `git checkout -b my-new-feature`
3. Build and run the add-on as described above.
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request.

To update dependencies:

 - `npm outdated` gives an overview of outdated packages ([doc](https://docs.npmjs.com/cli/outdated))
 - `npm-upgrade` updates all packages 
 - `npm install` install updated packages
 - 
   ```
    git subtree pull --prefix zotero-connectors https://github.com/zotero/zotero-connectors.git master --squash
    git subtree pull --prefix zotero-connectors/src/zotero https://github.com/zotero/zotero.git master --squash
   ```
   updates `zotero-connectors` submodule

 - `gulp update-zotero-scripts` copies and post-processes Zotero scripts from `zotero-connectors` to `Zotero` folder
