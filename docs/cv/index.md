# Eric Swanson - JSON Resume

## Overview

The following schema and formatting have been applied to convert LinkedIn Profile contents into a résumé / curriculum vitae (CV).

1. [LinkedIn to JSON Résumé](https://github.com/swanson8r/linkedin-to-json-resume)
   - Starts with a source of zip archived csv files from [LinkedIn > Settings & Privacy > Data privacy > Get a copy of your data](https://www.linkedin.com/mypreferences/d/download-my-data)
   - Spins up a local node.js webserver to convert the export into a json file matching the [JSON Resume](http://jsonresume.org) [Schema](https://jsonresume.org/schema)
         ```bash
         npm install
         npm run build
         ```
     - See original web version at [jmperezperez.com/linkedin-to-json-resume](https://jmperezperez.com/linkedin-to-json-resume/)
   - Manual editing of the JSON file is currently required post-conversion to populate a number of attributes.
     - `Skills` need to be categorized and moved into keywords
     - `Experience` Summary often needs to be moved into separate Highlights
     - `countryCode` needs to be changed from empty or "United States" to "US"
2. [jsonresume-theme-dev-ats](https://github.com/swanson8r/jsonresume-theme-dev-ats)
   - Spins up a local node.js webserver to convert the json resume file into an html printable resume
         ```bash
         npm install
         cp <~/Downloads/your-resume>.json resume.json
         npm start
         ```
     - Uses a custom json resume template designed to follow guidance from [r/EngineeringResumes > Wiki](https://www.reddit.com/r/EngineeringResumes/wiki/index/)
     - Until the source code is updated, manual edits to the generated HTML are required for proper format.
       - `Education` section should only list the End Date if completed.
       - Multiple Social Media `Profiles` are not currently populated into the template.
     - HTML file can then be printed to PDF.
       - Make sure to uncheck Headers and Footers to omit page numbers, filename, and timestamp.
3. Upload to [Github Pages](https://swanson8r.github.io/cv)
   - This is currently a manual process, but could be performed as a Github Actions workflow if the manual steps are addressed.
     - Files are stored under [/docs/cv](./) with this page ([index.md](./index.md))
