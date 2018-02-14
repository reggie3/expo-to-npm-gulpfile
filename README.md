# Expo to NPM Gulpfile
## A gulpfile that performs the steps needed to publish portions of an Expo project as an NPM package
### Why use this?
You need to download files to a mobile device, and you need to be able to download files again when their versions change.

### Why not use this?
You're not downloading files to a mobile device

[![npm](https://img.shields.io/npm/v/versioned-file-downloader.svg)](https://www.npmjs.com/package/versioned-file-downloader)
[![npm](https://img.shields.io/npm/dm/versioned-file-downloader.svg)](https://www.npmjs.com/package/versioned-file-downloader)
[![npm](https://img.shields.io/npm/dt/versioned-file-downloader.svg)](https://www.npmjs.com/package/versioned-file-downloader)
[![npm](https://img.shields.io/npm/l/versioned-file-downloader.svg)](https://github.com/react-native-component/versioned-file-downloader/blob/master/LICENSE)


## Usage
~~~
npm install --save versioned-file-downloader
~~~
or
~~~
yarn add versioned-file-downloader
~~~

And import like this
~~~
import versionedFileDownloader from 'versioned-file-downloader';
~~~

Call the asynchronous versionedFileDownloader and pass it the parameters shown below to save the files to a directory of the form [device document root return by Expo FileSystem API]/[package name]/[version]/
~~~
let downloadStatus = await versionedFileDownloader(
    this.webViewDownloadStatusCallBack,
    {
        name: config.PACKAGE_NAME,          // the name of the package, this will be the root directory for the files
        version: config.PACKAGE_VERSION,    // the version number, this will be a subfolder of the root that the file will be saved to
        files: FILES_TO_DOWNLOAD,           // the files to be saved 
    }
);
~~~

