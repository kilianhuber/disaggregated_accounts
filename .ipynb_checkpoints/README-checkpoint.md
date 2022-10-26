# Disaggregated Accounts

This repo houses the scripts, assets and source files for [Disaggregated Accounts](https://www.disaggregatedaccounts.com/).

![image](src/assets/img/main_plot_white_highres.PNG)

## Usage

### 1. Download

- Clone the repo: `git clone https://github.com/jasonjiajs/disaggregated_accounts.git`.

### 2. Making changes

- Download and install [Node.js](https://nodejs.org/en/), which will also install npm.
- Check that you have Node.js and npm installed: `node -v`, `npm -v`.
- `cd` into the repo's root directory (which contains `package.json` and `package-lock.json`).
- Run `npm install`. This should install modules in a new folder `/node_modules`.
- Run `npm start`. This should open up a preview of the website in your default browser. It will also automatically watch for changes to core files, and live reload the browser when changes are saved.
- Place the relevant images and data in `src/assets`.
- Edit the PUG files in `src/pug` and the SCSS files in `src/scss`. The JS files in `src/js` and `scripts` can be ignored.
- These edits will change the final outputs: the assets, HTML files and CSS files in `/dist`.
- View changes in your browser and iterate accordingly. Note that you can preview changes by opening the corresponding HTML files.

#### npm scripts

You can view the `package.json` file to see which scripts are included.

- `npm run build` builds the project - this builds assets, HTML, JS, and CSS into `dist`
- `npm run build:assets` copies the files in the `src/assets/` directory into `dist`
- `npm run build:pug` compiles the Pug located in the `src/pug/` directory into `dist`
- `npm run build:scripts` brings the `src/js/scripts.js` file into `dist`
- `npm run build:scss` compiles the SCSS files located in the `src/scss/` directory into `dist`
- `npm run clean` deletes the `dist` directory to prepare for rebuilding the project
- `npm run start:debug` runs the project in debug mode
- `npm start` or `npm run start` runs the project, launches a live preview in your default browser, and watches for changes made to files in `src`

## Acknowledgements

This website is adapted from [Start Bootstrap - Creative](https://github.com/startbootstrap/startbootstrap-creative).

## Copyright and License

Copyright © 2022 - Disaggregated Accounts. All rights reserved.

Code released under the [MIT](https://github.com/StartBootstrap/startbootstrap-creative/blob/master/LICENSE) license.
