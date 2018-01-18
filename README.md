# San Francisco Films

This is the frontend part of this MEAN stack project for enabling user to locale all of the places in San Francisco, where movies have been filmed since 1928. User can search by name of the movie or name of the place. All the places will be shown on google map using Google map APIs.

# Technologies used
1. Angular 4 Framework
2. Google Map Apis
3. Bootstrap 4

# Approach

Data preprocessing:

We use sfgov API to get the data of the location and movies filmed on that location. These location are however just text and not the longitute and latitudes which we require to pin point the place on map. To solve this issue we do following:
1.Import all the data to our mongoDB database using MongoChef client.
2.For each location get longitute and latitudes from using the Google map API
3.Write longitute and latitudes in each location record/document.

Workflows:

Everytime user performs search in the input of frontend, we query database via express backend and show these results as typeahead below the input. User can select fields which they want to perform search against: Location or movie name. After performing searching, if user clicks on any typeahead, we again query DB to get all details of the that record including longitute and latitudes

After getting longitute and latitudes we show mark these places using Google map markers.
User can click on these markers to get additional details about the movie and place.


## Development server
Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory. Use the `-prod` flag for a production build.

## Author

Sandeep Gupta

