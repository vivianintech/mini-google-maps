# Simple Google Map
This mini TypeScript project displays Google Map horizontally. There are 2 markers shown on the screen:
- One for a random user
- One for a random company
When you click on the markers, information of the random user and company will be shown. Each time you refresh the page, new user and new company information will be displayed, again randomly

## How to run the project
- To run it locally, you can clone this project and use this command for terminal`npx parcel index.html`

## Notes
1. Install parcel
- `yarn global add parcel-bundler`

2. Create project folder
- `mkdir [project_name]`

3. Initialize package.json
- `npm init -y` or `yarn init -y`

4. Install package.json
- `npm i`

5. Install faker to access random fake data
- `npm i faker`

6. Add definition files for an npm package
- Some npm package will auto include definition files, but some will not
- Go to npmjs.com
- Search for @types/[package-name]
- Use the command found from that search
- In this example, search for @types/faker
- The command for this example is `npm i @types/faker`

7. Add Google Map support
- Go to https://console.cloud.google.com/ & create new project
- Then click on API & services & search for Maps Javascript API & enable
- Generate an API key: click on credentials > Create credentials
- Place this API key inside `index.html`

8. Google Map integratioin
- `npm install @types/google.maps`
- As the very first line in the index.ts file, you will need to add a triple slash directive:
/// <reference types="@types/google.maps" />

You can read about this in the official docs here:
https://developers.google.com/maps/documentation/javascript/using-typescript#Module_Import

9. Hiding functionality
- In index.ts, to avoid other developers coming to our file and call methods that might break our application, you should have comment to state that the only thing you can do inside this file is:
  - Create new company, reference its properties
  - Create new user, reference its properties
  - Create a new class called "map", and this custom class "map" is used to create a new instance of the google map. Also, you can add a method called "addMarker"