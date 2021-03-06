# Asp Net Core Angular Spa Template updated to Angular 5 components
Asp Net Core Angular 4 template updated to Angular 5

package.json
```json
{
  "name": "AspNetCoreAngular4To5",
  "private": true,
  "version": "0.0.0",
  "scripts": {
    "test": "karma start ClientApp/test/karma.conf.js"
  },
  "dependencies": {
    "@angular/animations": "^5.0.2",
    "@angular/common": "^5.0.2",
    "@angular/compiler": "^5.0.2",
    "@angular/compiler-cli": "^5.0.2",
    "@angular/core": "^5.0.2",
    "@angular/forms": "^5.0.2",
    "@angular/http": "^5.0.2",
    "@angular/platform-browser": "^5.0.2",
    "@angular/platform-browser-dynamic": "^5.0.2",
    "@angular/platform-server": "^5.0.2",
    "@angular/router": "^5.0.2",
    "@ngtools/webpack": "^1.8.2",
    "@types/webpack-env": "1.13.2",
    "angular2-template-loader": "^0.6.2",
    "aspnet-prerendering": "^3.0.1",
    "aspnet-webpack": "^2.0.1",
    "awesome-typescript-loader": "3.2.1",
    "bootstrap": "3.3.7",
    "css": "2.2.1",
    "css-loader": "0.28.7",
    "es6-shim": "0.35.3",
    "event-source-polyfill": "0.0.11",
    "expose-loader": "0.7.3",
    "extract-text-webpack-plugin": "2.1.2",
    "file-loader": "0.11.2",
    "html-loader": "0.4.5",
    "isomorphic-fetch": "2.2.1",
    "jquery": "3.2.1",
    "json-loader": "0.5.7",
    "preboot": "4.5.2",
    "raw-loader": "0.5.1",
    "reflect-metadata": "0.1.10",
    "rxjs": "^5.5.2",
    "style-loader": "^0.19.0",
    "to-string-loader": "^1.1.5",
    "tslint": "^5.7.0",
    "typescript": "~2.4.2",
    "url-loader": "^0.5.9",
    "webpack": "^2.7.0",
    "webpack-hot-middleware": "^2.20.0",
    "webpack-merge": "^4.1.1",
    "zone.js": "^0.8.18"
  },
  "devDependencies": {
    "@types/chai": "4.0.5",
    "@types/jasmine": "2.5.53",
    "chai": "4.0.2",
    "jasmine-core": "2.8.0",
    "karma": "1.7.1",
    "karma-chai": "0.1.0",
    "karma-chrome-launcher": "2.2.0",
    "karma-cli": "1.0.1",
    "karma-jasmine": "1.1.0",
    "karma-webpack": "2.0.6"
  }
}
```
webpac.config.js
webpack.config.vendor.js 
```javascript
//add this line to plugins array
new webpack.ContextReplacementPlugin(/@angular(\\|\/)core(\|\/)esm5/, path.join(__dirname, './ClientApp')),
```

Update dependecies to latest version: 
```
npm install @angular/common@latest @angular/compiler@latest @angular/compiler-cli@latest @angular/core@latest @angular/forms@latest @angular/http@latest @angular/platform-browser@latest @angular/platform-browser-dynamic@latest @angular/platform-server@latest @angular/router@latest @angular/animations@latest typescript@latest 
```
```
npm install --save-dev @ngtools/webpack@latest
```
Recompile 
```
webpack --config webpack.config.vendor.js 
```
(must have webpack installed globally: npm install -g webpack@latest)

Replaced files manully in app.module:
```
import { HttpModule } from '@angular/http';
```
to 
```
import { HttpClientModule } from '@angular/common/http';
```
in services files instead of Http I've used HttpClient:
```
import { HttpClient } from '@angular/common/http'; 
```
