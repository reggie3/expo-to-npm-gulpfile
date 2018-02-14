# Expo to NPM Gulpfile
## A gulpfile that performs the steps needed to publish portions of an Expo project as an NPM package
### Why use this?
You've created an Expo project similar to what is described in my article here [Using Expo, Gulp, and Webpack to Create and Publish React Components](link), and you want to publish an NPM package from it.


## Usage
1. Copy gulpfile.js to your project
2. Install dependencies:
~~~
npm install --dev gulp-concat gulp-json-editor gulp-bump webpack-stream gulp-run
~~~
3. Create the files webpack.config.dev and webpack.config.prod containing development and production build configurations
4. Edit anything to suit your needs
5. Run the script with either 
~~~
gulp dev
~~~
or
~~~
gulp prod
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

