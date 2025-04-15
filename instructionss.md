4b.terrian data

1. Go to layers_add layers_add raster data, open files_dataset_practical4b_B_open mea file_add file
2. Zoom to himalayas
3. Go to raster_extraction_click raster by extent
4. Input layer consist the himalaya mea file_clipping extent-use canvas extent _clipped(save the file)_then run
           (you’ll see 2 files first is clipped and other the previous file(mea), so untick the previous file)
5.  Go to raster_extraction_contour
6. Contour interval(change to 100)_then save file in advance parameter option_then run
                             (result- contour lines will appear )
7. Uncheck the clipped file_Open attribute table of contour layer_click the first row_click on zoom(the magnifier with file icon)
8.go to properties of the layer_labels_change no labels to single labes_change ID to elev_apply
9.go to raster_analysis_hill shade_input layer as clipped_then save the file in advanced parameters_run
         (result as youll see the shades of hill after you zoom out)




5a.Working with Projections and WMS Data

1.open vector layer_practical 5a_go down and select ne.10m.admin.0countries.zip and open all zip files,
2.click zip layer_go to layers_save as_format - esri shapefile_file name(my_worldmap and save it)_CRS(press on the rightmost icon)_on filter search for 102008_click north america_then ok_again ok
3.uncheck neadmin.zip layer_ add raster layer_add miniscale.tif file
4.go to project_properties_CRS_filter-27700_click british_apply_then ok



6a.Georeferencing Topo Sheets and Scanned Maps

1. Open vector layer_practical6a_open india.admin0.shp_zoom to mumbai_plugins-tick georeference gdal
2. Go to raster_georeferencer(if not then fid it in layers)_file_open raster_open bombay.jpg_click the sunlike icon(next to x icon)_hit a point on bombay map_open canvas_click on the exact point of mumbai(previous window)_do 3 more points to capture mumbai_
3. (after completing)click on settings_transformation settings_tran type-thin spline_resampling-nearest neighbour_target srs-rightmost icon-4044_then ok
4. Save the file as (…modified2)_check the load in qgis_then ok_then run(below edit button)
5. Go to properties of the layer_transperancy_low it_then ok(to see the map bombay map on vector data)



6b.Aerial Imagery

1.open plugin_install open layer plugin, Osm place search_then ok_go to web-open layer-openstreetmap-open street map_in the left corner(search gateway of india)_then ok_plugins-install or tick georefencer_go to raster-georefencer
 
2. Click file-open raster_gatewayofindia.arielimage_then click on (sunlike icon next x icon )_point out the borders of gateway_open wit canvas_click on the same point on street map_then ok_complete the borders with 4 points)_(after completing)

3.click settings-transformation settings_tran type-thinplate spline,method-nearest neighbour,SRS(click on rightmost icon)-3857_select pseudo med.._then ok_output raster(save it wit any name)_then ok_tick the load in qgis_then ok_then run(below edit button on top)_save the gcp
4.right click on the existing layer_properties_transperency_low it_then ok



6c.Digitizing Map Data

1.add raster layer_practical6c_christchurchtop50.tif_add it_go to its properties-pyramids_select all the resolutions_build pyramids_settings_options_degitizing_defaultsnapmode-vertex and segment_then ook_
 
2.layer-create layer-new spatialite layer_database-(save it as digitroad2)_layername-roads_geometrytype-line_(below icon like srs)_filter-4167_ok_name-roadsName,roadDesc_add to field list_ok
 
3.click on toggle button(pencil like icon)_addlinefeature icon(next to toggle button)_create a road on the map(left click to create,right click to save)_save it as road1(name,desc)_then ok_go to properties of road layer_color-black_width-1.26000_then ok(to see the road in black color)_create another road_color it_then ok

4.layer_create layer_new spatilelayer_database-(save it)_layername_garden_geometry-polygon_SRS-4167_select nzgd_then ok_name-GardenName_then ok
 
5_toggle_add polygon feature_create garden on map(left click to create,right click to save)_save it as garden1(name)_then ok_go to properties of garden_layer_color-green_apply_then ok(to see the garden in green color)_create another garden_color it_then ok
 
6.do same for shops_geometry-point_srs-4167_name-shopname_then ok_toggle_point icon_point it on map(left click to create,right click to save)_save it as shop1(shopname)_then ok_go to properties of shop_layer_color-blue_apply_then ok(to see the shop in blue color)_create another shop_color it_then ok




7a.Managing Data Tables and Saptial data Sets_ Table joins,

1.go to layers_add layers_add new vector layer
2.select- tl_2013_06_tract.zip
3.open notepad_(write- “String”,”String”,”String”,”String”,”String”,”Integer”)_save the file as “ca_tract_pop.csvt” in 7a_then ok
4.Layer_Add layer_Add delimited text layer_open file ca_tract_pop_ tick custom delimiter-semicolon,comma_no geometry_CRS-wgs84(at ending)_add_close
5.go to tl_2013 ka properties_ joints_press(+)_joint layer-ca.tact.pop_jointfield-geo.id2_targetfeild-GEOID_then ok_apply
6.go to attribute table of tl_2013_(if you see data then this means joint is performed)_close
7.go to properties of tl_2013_symbology_(single symbol change it to graduate)_value-ca.tact.pop001_mode-equal interval_class-5_apply_ok
done


7b. spatial joinsVersion 3.10
 
1.layer_add layer_add vector layer_open-nybb.shp_then add
2.layer_add layer_add vector layer_open-oem.nursinghomes001.shp_then add
3.vector_data management tool_join attributes by location
4.input layer-nybb_join layer-oem nursinghomes_feilds to add-(3dot) select all fields then ok_join type_take attribute of first feature only_then Run
5.open attribute table of joined laye(if u see data this means the table has joined)_then close
6.press identify feature(icon looks like i)_then press any area on map_ull get the data
done



7c.counting points in polygon

1.add vector layer_open-ne.10m.admin.0.zip_select all then ok
2.layer_add layer_add delimited text layer_file-open earthquakedatabase.txt(7c)_custom delimeters-tab,colon_point coordinates-xfeild-longitude-y field-latitude_CRS-wgs84_then Add
3.vector_analysis_count points in polygon
4.polygons_ne.10m__points-earthquakedatabse_weightfeild-locationname_classfeild-country_
then run
5.press feature selection icon( looks like i)_select any country to see data
 done


7d.points in polygon analysis, performing spatial queries

1.layer_add layer_add vector layer_open-populatedplaces.zip_add only shp file
2..layer_addlayer_add vector layer_opem-riverlake.zip_add only shp file
3.project_properties_filter-54032_select worldazit.._apply
4.vector_geoprocessing_buffer_input-river_distance-0.02_then run
5.vector_reserch tool_select by location_input-buffered_comparing-populated places_then run
 Done


8a.Nearest Neighbor Analysis

1.layer_add layer_add vector layer_open-populatedplacessimple.shp_then ok
 
2.layer_add layer_add delimited text layer_file-earthquake database_custom delimeters-tab,space_xfeild-loggitude_y field-latitude_then ok_close_then ok
 
3.vector_analysis_distance matrix_input point-earthquake database_input unique-locartion name_targetpoint-populated places simple_targetunigue_name_output matrix-standard-browse-save it as output_then ok_then ok





 8b.point sampling | Version 3.10
 
1.layer_add layer_add raster layer_ search for *.tif file_select and open
2.layer_add layer_add delimited text layer
3.filename-search for *.txt file_select and open_custom-tab,color_point coordinates_x-intplon_y-intplat_CRS-wgs84_Add_close
4.click the( i )icon(below processing)_select any country to check the temperature
 
Now for point sampling
 
5.plugins_search-pointsampling tool(install it and tick it)_settings-show also experimental plugins(tick it)_close
6. Plugin_analysis_point sampling tool_
7.in general_Layer-2013.gaz_in layer with fields-press control and select GEOID,NAME and BAND 1(LAST ROW)_browse-save it as “maxtemp2”_then ok
 
8. Press the i icon_ select the any country to see the max temp of the area
 done




8c.interpolating point data

