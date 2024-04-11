# This log is to show potential errors that may occur when using advanced formatting within ArcGIS Dashboards, and how to avoid/fix them.

> [!TIP]
> More information on advanced formatting for Dashboards can be found [here](https://doc.arcgis.com/en/dashboards/latest/create-and-share/advanced-formatting.htm).

> [!NOTE]
> Examples used in the photos were take from a [tutorial](https://learn.arcgis.com/en/projects/get-started-with-advanced-formatting-in-arcgis-dashboards/)

> [!IMPORTANT]
> Please note that the advanced formatting in Dashboards uses the Arcade scripting language.

### To begin, ensure you have a dashboard open with either a list, indicator, or table element (these are the elements that support advanced formatting). The screenshots seen below were taken from both table and indicator elements.
### To open advanced formatting (in this case, for a list):
1. Go to the 3 horizontal dots in the top left corner of the list, and click the configure/settings icon.
2. In the settings, select the "list" option from the tabs on the left:

    ![image](https://github.com/jsteinma/TechnicalLogs/assets/146376062/e78c2122-7e73-4e5a-bcaa-0468edecd41a)

4. To enable advanced formatting, select the enable button beside "Advanced Formatting":

    ![image](https://github.com/jsteinma/TechnicalLogs/assets/146376062/c62f9d89-7111-4546-8ed9-99f623fa5883)

7. Click on the pop-out editor option in the advanced formatting tab:

    ![image](https://github.com/jsteinma/TechnicalLogs/assets/146376062/b47b5cc9-3cb8-4f3b-8ae2-9febee5e4370)

9. Once you are here, you can either type in your own code, or get help from the profile variables and functions tabs:

    ![image](https://github.com/jsteinma/TechnicalLogs/assets/146376062/65d9535a-534e-4e6e-ada5-303be77a94d1)


## 1. Possible Profile Variable Error
If you are using a profile variable from the list given, ensure you click on the **arrow** on the right hand side beside the "$datapoint": 

  ![image](https://github.com/jsteinma/TechnicalLogs/assets/146376062/9b979612-082b-4390-9920-a9c8683d1df7)

- If just the "$datapoint" bar is clicked, it will add the word "$datapoint" to the codeblock, and will not show the list of fields/variables from the data.
- In addition to this, if you click on a variable from the list after clicking on just the regular "$datapoint" bar, it will add an additional "$datapoint" to the code block, creating an incorrect line of code:
```
$datapoint$datapoint.OBJECTID
```

## 2. Correct Variable Terminology

If your code requires you to use and set multiple variables, each one requires a starting of "var" to the variable assigning line. If var is not added, the code line will be incorrect and unusable, since the variable is not correctly defined.
- In a code where we want to set a variable equal to a certain colour depending on if a condition is true or false, the code without the "var" may look like this:
```
severityColor = IIF(reliabilityIndex > 1, '#C22E00', '#363636');
```
- The corrected code should look like this (notice the "var"):
```
var severityColor = IIF(reliabilityIndex > 1, '#C22E00', '#363636');
```

## 3. Issues when using HTML to format the List

HTML can be used to format the look of lists depending on what you want it to look like.

This can be done below the advanced formatting tab, under "Line item template", under the "Source" option. When blank, it will show no data in the list on the right:

  ![image](https://github.com/jsteinma/TechnicalLogs/assets/146376062/f5cc15a9-5a10-4cc9-ba8b-a11235997459)

- When using HTML to format the list points, ensure that "Source" is clicked, otherwise you will be entering code into the regular line item template section, and the list will show the HTML code you put in as the display of the list:

  ![image](https://github.com/jsteinma/TechnicalLogs/assets/146376062/ec25ea6a-e361-4906-adb2-0f477cbd8505)

- You can ensure source is clicked when it shows slightly blue in colour:

  ![image](https://github.com/jsteinma/TechnicalLogs/assets/146376062/975467a8-92d1-4508-80ce-86c8f57bc49a)

- After entering your code into the "Source" section of the formatting, you can click on source again to show a preview how the formatted output will look without data:

  ![image](https://github.com/jsteinma/TechnicalLogs/assets/146376062/5350470d-60bc-457a-8d1e-7c3b92b19417)

  and with data (displaying on the right):

  ![image](https://github.com/jsteinma/TechnicalLogs/assets/146376062/985c2c6e-40e2-44e1-8f8a-0f015b6dd62c)

## 4. Missing Fields in List Display

Once entering fields and possibly a format for the list, there may be some missing data in the preview (as seen in the image below, even though there is 
{UtilityCompany} - {County} on the middle line in the format text, the only thing that shows is the "-" on the middle line in the actual data preview):

  ![image](https://github.com/jsteinma/TechnicalLogs/assets/146376062/c2807f93-72d9-46d2-9657-9cb54e282869)

One thing to remember is when inserting fields or expressions into the line item template, we need to indicate what time of data they are with the 
‘type/’ before the name - where type can be either 'field' or 'expression'. To make the example in the previous photo work properly, add ‘field/’ 
within the curly brackets, in front of the field names. The corrected input and display would look like this: 

  ![image](https://github.com/jsteinma/TechnicalLogs/assets/146376062/a8bad242-251e-4c94-a278-a99e683b3328)

## 5. Semicolons

Semi-colons in arcade language aren’t always necessary and needed, and are typically used in part for structure, readability and within multi-line 
expressions. More on Arcade statements can be read [here](https://developers.arcgis.com/arcade/guide/statements/).

In the following two images, differences in structure due to the presence/absence of semicolons at the ends of statements can be seen. Although the 
structures differ, both scripts will execute the same way and display the exact same output.

- In the first image, semi-colons were removed from the ends of lines and statements:

  ![image](https://github.com/jsteinma/TechnicalLogs/assets/146376062/d20012be-8334-4f49-bdf7-c605c96f7757)

- In the second image, semi-colons were added to the ends of statements and highlighted to see easier:

  ![image](https://github.com/jsteinma/TechnicalLogs/assets/146376062/ca97f34d-102f-46a8-b952-83e90579f041)
