To set up use npm install


to run tests use npx playwright test --headed this runs in headed moded removing --headed runs inn headless mode

All test files have to end with .spec.js

page objects have been set up for login and sidebar for examples.

for api add  const {test,request, expect,chromium} = require('@playwright/test');

under data I have added the body for personal cadence which is imported into the sample test. This can be used directly through personalCadence
ex const personalCadence = require('../data/PersonalCadence.json');

for assertions playwrite uses inbuilt assertion example expect(page)toHaveURL('https://app.qasalesloft.com/app/dashboard');

if you are working on a set of tests and only want to run one in that set you can do test.only
simiraly if you are working with several blocks of tests and want one block to run use describe.only

React componets ie Table 
to work with react components download react developer tools extension

go to your react page and inspect the object as usual and in the dev tools window expand the profiler and select components 
this will take you into the react dev tools and bring you to the elempent where you can see the component type such as R for the table
it will also on the right side show all the attributes of the component. for the Cadence table a single row the component is R now using playwrite the selector would look like _react=R[name='CadenceName']. to test this you can open 
npx playwright codegen https://app.qasalesloft.com navigate to the area you are working on open dev tools and go to console than type playwright.$(yourselector)

Additional Command line calls
npx playwright test tests/todo-page.spec.ts runs a specific spec or test file

npx playwright test -g "test title" runs a test that has a specific title

npx playwright test --debug goes to debug mode
