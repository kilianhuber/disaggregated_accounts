# Disaggregated Accounts

This repo houses the scripts, assets and source files for [Disaggregated Accounts](https://www.disaggregatedaccounts.com/).

<!-- ![](src/assets/img/main_plot_white_highres.jpg) -->

## Usage

### 1. Download

- Clone the repo: `git clone https://github.com/jasonjiajs/disaggregated_accounts.git`.

### 2. Updating the data files (`process_data_for_tableau`)

- Put the updated data in the corresponding subfolder in `process_data_for_tableau/data/[subfolder]`. The file name should be the same. `process_data_for_tableau/data/overview/Flows in DK_v2_overview.xlsx` provides more information.
- Run `process_data_for_tableau/code/process_data_for_tableau.ipynb` to get the processed csv files that will be inputs to Tableau workbooks for public viewing.
  - The csv files are saved in `process_data_for_tableau/output_csv`.
- Run `process_data_for_tableau/code/process_data_for_public_download.ipynb` to get the processed csv and dta files that will be published on the website and are available for public download.
  - The csv files are saved in `src/assets/data/csv`.
  - The dta files are saved in `src/assets/data/dta`.
- Update the Tableau notebooks in `process_data_for_tableau/output_tableau` using the new csv files from `process_data_for_tableau/output_csv`.
  - If a data extract used to exist but is no longer found ('Extract Not Found'), click 'Remove the extract'. The notebook will then automatically load the updated csv file, as the csv file name is unchanged.
- Extract the data and use the data extract: Data → [Name of dataset, last option] → Extract Data → Extract → Save (default location is fine) -> Yes (replace it if it already exists).  
- Publish the updated Tableau notebooks to [Tableau Public](https://public.tableau.com/app/profile/jason.jia1132): Server → Publish Workbook → Connect → Sign in → Save → Yes (overwrite existing data).

### 3. Updating the website assets (`src`, `dist`, `scripts`)

- Download and install [Node.js](https://nodejs.org/en/), which will also install npm.
- Check that you have Node.js and npm installed: `node -v`, `npm -v`.
- `cd` into the repo's root directory (which contains `package.json` and `package-lock.json`).
- Run `npm install`. This should install modules in a new folder `/node_modules`.
- Run `npm start`. This should open up a preview of the website in your default browser. It will also automatically watch for changes to core files, and live reload the browser when changes are saved.
- Place the relevant images in `src/assets/img` and the latest version of the paper in `src/assets/paper`. The processed data files should already be in `src/assets/data`.
- Edit the PUG files in `src/pug` and the SCSS files in `src/scss`. The JS files in `src/js` and `scripts` can be ignored.
- These edits will change the final outputs: the assets, HTML files and CSS files in `dist`.
- View changes in your browser and iterate accordingly. Note that you can preview changes by opening the corresponding HTML files.
- Once you have finished making changes, push your changes to the repo. [Netlify](https://app.netlify.com/sites/disaggregatedaccounts/overview) will recognize a new commit and automatically rebuild the website in a few minutes.

#### Note: npm scripts

You can view the `package.json` file to see which scripts are included.

- `npm run build` builds the project - this builds assets, HTML, JS, and CSS into `dist`
- `npm run build:assets` copies the files in the `src/assets/` directory into `dist`
- `npm run build:pug` compiles the Pug located in the `src/pug/` directory into `dist`
- `npm run build:scripts` brings the `src/js/scripts.js` file into `dist`
- `npm run build:scss` compiles the SCSS files located in the `src/scss/` directory into `dist`
- `npm run clean` deletes the `dist` directory to prepare for rebuilding the project
- `npm run start:debug` runs the project in debug mode
- `npm start` or `npm run start` runs the project, launches a live preview in your default browser, and watches for changes made to files in `src`

## Notes

### Only updating the research paper

If you only want to update the research paper, you can do the following:

- Go to [`src/assets/paper`](https://github.com/jasonjiajs/disaggregated_accounts/tree/master/src/assets/paper).
- Click 'Add file' -> 'Upload files'
- Upload a new copy of `DEA.pdf` (the name needs to be the same; otherwise, the HTML code also needs to change to reflect the new file name).
- Click 'Commit changes'. The new file will override the old file.
- Wait for a few minutes. The website should be updated with the new file.

## Acknowledgements

This website is adapted from [Start Bootstrap - Creative](https://github.com/startbootstrap/startbootstrap-creative).

## Copyright and License

Copyright © 2023 - Disaggregated Accounts. All rights reserved.

Code released under the [MIT](LICENSE) license.
