# ArcGIS Field Maps Tips
## Setting Up a New Map
> [!NOTE]
> The full tutorial for map creation and configuration can be found [here](https://doc.arcgis.com/en/field-maps/latest/prepare-maps/create-a-map.htm#ESRI_SECTION2_87583C7770704063AA62479A1CBA9506).

### Creating a New Map
> [!NOTE]
> The full tutorial to create a new map can be found [here](https://doc.arcgis.com/en/field-maps/latest/prepare-maps/create-a-map.htm#ESRI_SECTION2_87583C7770704063AA62479A1CBA9506).

After selecting and naming the layers you want to be added, move onto layer settings.
> [!CAUTION]
> Layer settings cannot be changed after map creation so ensure you have what you need checked

Settings:
- High accuracy GPS receivers will provide centimeter to submeter accuracy/precision. Without this checked, accuracy may be around 3 metres.
- Z-values will provide elevation data or non-position information like density or quantity.
- M-values will provide measurements to line features (used in linear referencing).

### Creating a New Empty Map
> [!NOTE]
> The full tutorial to create an empty map can be found [here](https://doc.arcgis.com/en/field-maps/latest/prepare-maps/create-a-map.htm#GUID-69D4F061-19E6-46AE-BAC6-A6FB2F2F865C).

- An empty map will only give the options of map Name and Save the map

### Configuring the Form
- When setting the date, set to required and no null values to ensure data is captured.
- When creating a **list**, the field type cannot be changed after creation.
- When editing the App settings, can set the required accuracy to metres or centimeters and a specific number.
- If streaming is turned on, if will collect a point automatically (may not be needed).
- Can also set the manual location settings (select warning when manual location is used).
- Can set size of uploading photo to smaller to help with sync efficiency.
- Can set the detail level of the offline map shown to mobile users.

## Collecting on Android Device
- Ensure when opening the map, turn location on and allow it for 'While using the app'
- If issues occur when taking a photo in the form, follow on of the two options:
  1. Remove the photo and add it last prior to submitting the form.
  2. Remove the photo, take it on your normal camera app and then attach as a file to the form.
