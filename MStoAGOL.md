# Viewing/Adding a Published Map Service to ArcGIS Online
> [!CAUTION]
> The server must be running prior to accessing the REST Services Directory as well as any maps referencing its data. If maps or
> layers containing the data are opened prior to starting the server (and configuring IP of variable IP servers), the files can
> get corrupted.

> [!NOTE]
> These steps can be completed following a Map Service being published to the server.
>
> Steps on how to publish from ArcGIS Pro can be found [here](https://www.youtube.com/watch?v=nIRlZN9ECwY&t=5s).

After publishing map service, you should recieve a link to the ArcGIS REST Services.

The link will be similar to **'https://{{IPAddress}{gisserver.domain}}/arcgis/rest/services'**, where {IPAddress} is the IP address 
used for your server/virtual machine (External IP if using Google Cloud Platform to host the Virtual Machine), 
and {gisserver.domain} is the server name and domain if not using an IP address.

The AG REST Services Directory will look similar to this:

<kbd>![image](https://github.com/jsteinma/TechnicalLogs/assets/146376062/1b6020fc-9282-4cad-a0a8-d84a3de430c0)</kbd>

> [!NOTE]
> This is not the link to use when adding this data to ArcGIS Online.

Because a Map Service was published to the server, prior to adding the data to AG Online we need to click on the 
specific MapServer subfolder link under Services. In the photo above, this is called "SampleWorldCities".

Once here, you will see a page similar to this: 

<kbd>![image](https://github.com/jsteinma/TechnicalLogs/assets/146376062/049280a6-22d6-4af1-b79c-0e08f2488c39)</kbd>

An example URL: https://{X}/arcgis/rest/services/{MapServerName}/MapServer

In this example, the [MapServerName] would be SampleWorldCities, as this is our published MapServer.

# Viewing The Map

> [!WARNING]
> If using a variable IP address that changes every time the server/VM starts/stops, it is recommended to
> add the MapService or Layers as a 'New item' into ArcGIS Online 'Contents' prior to Saving into a Web Map.
>
> If adding the MapServer as a whole, it will save as a 'Map Image Layer', and the symbology for this will **not** be editable.
>
> If adding each layer individually as items, they will save as a 'Feature Layer', and the symbology for each will be editable.

## A Quick Look at the Data

To view a map briefly to see the data, select 'ArcGIS Onilne Map Viewer' found under the MapServer title:
<kbd>![image](https://github.com/jsteinma/TechnicalLogs/assets/146376062/186891b5-01ad-472f-b52f-061e6f4a54b9)</kbd>
> [!NOTE]
> This method does not let you save the map.

## Creating a Web Map using Base MapServer Link

1. In ArcGIS Online, click 'Map'. This will open a new map.
2. Once inside, under 'Layers', use the dropdown arrow beside 'Add' and click on 'Add layer from URL':

<kbd>![image](https://github.com/jsteinma/TechnicalLogs/assets/146376062/17ba31cf-04b6-404d-9f10-e29759f6aac5)</kbd>

3. Once here, enter the link to the MapServer from the ArcGIS REST Services Directory site. It should look similar
   to this: **https://{X}/arcgis/rest/services/{X}/MapServer**
4. The layer type should automatically be selected as 'ArcGIS Server web service'.
5. Click 'Add to map'.
6. Once the data is added, you can save it as a 'Web Map'.

## Creating a Web Map using the REST JSON Link

1. In your MapServer REST Service Directory site, click the option 'JSON' under the page pathway:
<kbd>![image](https://github.com/jsteinma/TechnicalLogs/assets/146376062/5ab4e7be-2f35-4bc2-8dca-63a868e1d47b)</kbd>
2. In ArcGIS Online, click 'Map'. This will open a new map.
3. Once inside, under 'Layers', use the dropdown arrow beside 'Add' and click on 'Add layer from URL':

<kbd>![image](https://github.com/jsteinma/TechnicalLogs/assets/146376062/17ba31cf-04b6-404d-9f10-e29759f6aac5)</kbd>

4. Once here, enter the link to the MapServer from the ArcGIS REST Services Directory site. It should look similar
   to this: **https://{X}/arcgis/rest/services/{X}/MapServer?f=pjson**
   - If this link does not work, remove the 'p' in 'f=pjson' at the end of the link and re-add it.
5. The layer type should automatically be selected as 'ArcGIS Server web service'.
6. Click 'Add to map'.
7. Once the data is added, you can save it as a 'Web Map'.

Note: any REST Directory links using a variable IP address will need to be changed prior to opening.

## Creating a Web Map using the REST WMS (Web Map Service) Link
> When zooming, data might take a while to load and may not load properly when scale changes

1. In your MapServer REST Service Directory site, click the option 'WMS' under the page pathway:
<kbd>![image](https://github.com/jsteinma/TechnicalLogs/assets/146376062/d0b68cc2-0c60-4854-9208-3e04c468128e)</kbd>

  - The link to this page should look similar to this: **https://{X}/arcgis/services/{X}/MapServer/WMSServer?request=GetCapabilities&service=WMS**

2. In ArcGIS Online, click 'Map'. This will open a new map.
3. Once inside, under 'Layers', use the dropdown arrow beside 'Add' and click on 'Add layer from URL':

<kbd>![image](https://github.com/jsteinma/TechnicalLogs/assets/146376062/17ba31cf-04b6-404d-9f10-e29759f6aac5)</kbd>

4. Once here, enter the link to the WMS version of the MapServer from the ArcGIS REST Services Directory site. 
5. The layer type should automatically be selected as 'WMS(OGC)'.
6. You will be able to add specific layers prior to adding to map.
7. Click 'Add to map'.
8. Once the data is added, you can save it as a 'Web Map'.


## Saving the Layers Individually onto a Map
> This option loads the data onto the map quickly.

1. In your MapServer REST Service Directory site, click one one of the available layers found under 'Layers':

<kbd>![image](https://github.com/jsteinma/TechnicalLogs/assets/146376062/381f4f3b-f1bf-4858-84cc-8ec8286ab2ef)</kbd>

  - The link to this page should look similar to this: **https://{X}/arcgis/rest/services/{X}/MapServer/0** . Notice the /0 on the end.
2. In ArcGIS Online, click 'Map'. This will open a new map.
3. Once inside, under 'Layers', use the dropdown arrow beside 'Add' and click on 'Add layer from URL':

<kbd>![image](https://github.com/jsteinma/TechnicalLogs/assets/146376062/17ba31cf-04b6-404d-9f10-e29759f6aac5)</kbd>

3. Once here, enter the link to the WMS version of the MapServer from the ArcGIS REST Services Directory site. 
4. The layer type should automatically be selected as 'ArcGIS Server web service'.
5. Click 'Add to map'.

> [!NOTE]
> This will only add the one layer specified in the link.

