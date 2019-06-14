---

title: 1. Objective of This Guidance Note
weight: 2

---


The objective of this guidance note is to establish key principles for end use of unmanned aerial vehicles (UAVs) in a Pacific Island Country (PIC) context. The document addresses how, when, and for what applications UAVs should be used. For pilots who are new to UAV mapping, it also provides instructions and recommendations to ensure that imagery of high quality is generated for accurate integration with other geospatial layers. 

The ultimate goal is to establish UAVs as the principal data collection and survey mapping instrument for Small Island Developing States in the Pacific region and beyond. As the principles and best practices described in this document are applicable globally, the plan is for this document to continue to evolve and for its online version to reflect the latest in UAV technology.  

To take stock of the current operating conditions in the Pacific region, field tests were conducted in Tonga and Fiji in October 2017. Five survey mapping challenges were carried out to generate five types of typical geospatial data products that are high in demand (shown in table 1).[^1] Lessons learned and best practices derived from these exercises are offered throughout this note to help the reader better understand how most effectively to use UAVs for survey mapping. Other applications of UAVs, such as for cargo delivery, are beyond the scope of this note.

Flight itself constitutes only a small portion of the entire UAV operation (as explained in chapter 7). Post-flight data processing and data sharing with end users represent a much larger share of the operation, and they present huge challenges given the sheer volume of data that needs to be processed;[^2] challenges are even greater if time is limited. Important lessons on data sharing, learned from the Pacific Drone Imagery Dashboard (PacDID) project,[^3] have been integrated in this guidance note. Efficient access to imagery can lead to improved mapping work flows for disaster risk management and other applications. 

Table 7. Five Data Types Generated During UAV Field Testing in Tonga and Fiji 


<table>
  <tr>
   <td><strong>Survey type/UAV platform</strong>
   </td>
   <td><strong>Area</strong>
   </td>
   <td><strong>Output/file type</strong>
   </td>
   <td><strong>Output example</strong>
   </td>
   <td><strong>Output use/application</strong>
   </td>
  </tr>
  <tr>
   <td>Small area (Challenge 1)
<p>
Fixed-wing 
   </td>
   <td>10 km<sup>2</sup>
   </td>
   <td>2D orthorectified mosaic 
<p>
RGB and RGB+ NIR 
<p>
(GeoTIFF)
   </td>
   <td>

<img src="/images/Technical-Guidelines0.png" width="" alt="alt_text">

   </td>
   <td>General mapping, including delineating building footprints and road networks; location and geometric features of bridges and other key infrastructure, such as electricity/telephone poles, power lines; river embankments, bridges and land use and land cover. If an NIR channel is available, classification of vegetated areas, identification of permanent and temporary water bodies, etc. are possible.
   </td>
  </tr>
  <tr>
   <td>Medium area (Challenge 2)
<p>
Fixed-wing with RGB camera
   </td>
   <td>50 km<sup>2</sup>
   </td>
   <td>2D orthorectified mosaic 
<p>
RGB 
<p>
(GeoTIFF)
   </td>
   <td>

<img src="/images/Technical-Guidelines1.png" width="" alt="alt_text">

   </td>
   <td>Same as Challenge 1. 
   </td>
  </tr>
  <tr>
   <td>Elevation
<p>
(Challenge 3)
<p>
Multirotor with LiDAR sensor 
   </td>
   <td>0.5 km<sup>2</sup>
   </td>
   <td>Surface model 
<p>
Point cloud
<p>
(GeoTIFF)
   </td>
   <td>

<img src="/images/Technical-Guidelines2.png" width="" alt="alt_text">

   </td>
   <td>Inputs for flood modeling, drainage design, transportation design, coastal engineering, landslide modeling (susceptibility), and erosion monitoring for slope stability studies.
   </td>
  </tr>
  <tr>
   <td>Real-time, beyond line of sight (Challenge 4)
<p>
Delta wing fixed-wing 
   </td>
   <td>0.5 km<sup>2</sup> (10 km from take off location)
   </td>
   <td>Video, photos, orthomosaic 
<p>
(MP4, JPEG GeoTIFF)
   </td>
   <td>

<img src="/images/Technical-Guidelines3.jpg" width="" alt="alt_text">

   </td>
   <td>Near-real-time information collected by flying the UAV beyond line of sight for post-disaster reconnaissance, situational awareness, damage assessment, post-disaster mapping, etc. 
   </td>
  </tr>
  <tr>
   <td>Bathymetry (Challenge 5)  
<p>
Multirotor
   </td>
   <td>0.5 km<sup>2</sup>
   </td>
   <td>Point cloud and DEM 
<p>
(GeoTIFF)
   </td>
   <td>

<img src="/images/Technical-Guidelines4.png" width="" alt="alt_text">

   </td>
   <td>Tsunami and storm surge modeling, coastal inundation/erosion modeling, reef monitoring, etc.  
   </td>
  </tr>
</table>


_Source: _ _UAV4Resilience 2017_

_Note:_ RGB = red-green-blue; NIR = near infrared; DEM = digital elevation model. The field tests used various types of UAVs. All orthomosaic outputs are available from OpenAerialMap.org.


[^1]: 
     Details on the field tests carried out to generate the five types of data products are in Table1.

[^2]: 
     The data size often runs into hundreds of gigabytes.

[^3]: 
     PacDID is a platform that leverages the OpenAerialMap (OAM) concept, making open imagery collected by satellites and UAVs easily available and accessible, particularly for the target audience in Pacific Island Countries. More information is available at Pacific Humanitarian Challenge (n.d.).
