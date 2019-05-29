6. Choosing the Sensor

Many survey mapping UAV platforms come with built-in or recommended cameras, which are already configured for optimal mapping outcomes. However, built-in cameras may also limit the user’s ability to customize optimal sensor configurations. 


## Preferred camera specifications

The UAV’s flight altitude and sensor determine the spatial resolution of the imagery. To put this another way, the focal length, sensor size (size of the chip that detects light), and density of detectors on that chip all influence the altitude required to collect data of a given spatial resolution (i.e., minimum resolvable object size). Most survey mapping UAVs use digital RGB cameras that capture imagery in the visible range of the light spectrum. When the camera can be selected separately, the following characteristics may be desirable:



*   _Large detector size. _A larger detector size means that the imagery collected will be of higher quality or fidelity. This is in part because larger detectors are typically found in larger, higher-quality cameras, but also because larger detectors can collect more energy from a given pixel and therefore typically have a much higher signal-to-noise ratio.
*   _Uncompressed image formats._ Many cameras record only compressed formats (JPG), which reduces the radiometric quality of the imagery. Sensors that are capable of recording in RAW, TIFF, or other uncompressed formats produce higher-quality images.
*   _Trigger control._ Ideally, the camera shutter is triggered by an external system that records the location and time of each shot. This is typically the flight control system (autopilot) or a separate GPS sensor. Many professional-grade cameras have software that enables remote control, but consumer cameras often lack remote trigger ability unless custom modifications are made. For these consumer cameras, the shutter must be triggered continuously by time interval (though not all cameras have even this capability). If triggering by time interval is the only option, the sensor must have a buffer sufficient to enable continuous acquisition at the rate required to collect the forward overlap selected.
*   _High-quality prime lenses._ When possible, high-quality prime lenses (i.e., lenses of fixed focal length) should be used. Many smaller sensors do not allow for the use of prime lenses. Where they are absent, the camera should be operated only at the extremes (minimum or maximum of the focal range) for digitally controlled “zoom”; or in the case of variable focal length lenses controlled manually, tape can be physically applied to the focus wheel to ensure that the focal length remains consistent throughout and between flights, which is critical for processing. Wide-angle lenses (~ < 24 mm in 35 mm equivalent) increase view angle distortions and can severely affect the geometric and radiometric quality of the resulting orthomosaic.
*   _Calibrated camera model._ Images collected with digital cameras are subject to a certain degree of geometric distortion. A fundamental prerequisite of automatic triangulation (AT) and mosaicking is the accurate calibration of the sensor to undistort captured images correctly. The set of parameters describing sensor and lens geometric properties is called a camera model. For optimal photogrammetric results, each sensor should be calibrated by a specialized laboratory for each lens combination. Several UAV photogrammetric software programs automatically calculate camera models as part of the AT processing routine.
*   _Global shutter_. Most consumer cameras employ a “rolling shutter,” which can greatly affect image quality when placed on fast-moving UAVs. In recent years, manufacturers have developed “global shutter” sensors that greatly reduce distortion and image geometry issues.

Increasingly, mapping-UAV manufacturers provide cameras that are already optimized for mapping, minimizing the effort that end users must make to ensure appropriate cameras and calibrations. 

Ultimately, the payload capacity of available platforms will determine which cameras can be carried. Some systems have embedded cameras that cannot be swapped, while others allow for different sensor configurations. Digital single-lens reflex (DSLR) cameras with full-frame sensors can be carried only by larger multirotor UAVs. Most portable small UAVs have either embedded sensors or compact cameras that typically weigh less than 500 g. Table 4 compares three common RGB cameras used on mapping UAVs.

Table 10. Comparison of RGB Cameras Used on Mapping UAVs


<table>
  <tr>
   <td><strong>Camera</strong>
   </td>
   <td><strong>Sensor size</strong>
   </td>
   <td><strong>Resolution (MP)</strong>
   </td>
   <td><strong>Weight (g)</strong>
   </td>
   <td><strong>Price (US$)</strong>
   </td>
  </tr>
  <tr>
   <td><a href="https://www.mapir.camera/collections/survey3">Mapir Survey3W</a>
   </td>
   <td>6.17 x 4.55 mm (1/2.3 in.)
   </td>
   <td>12 
   </td>
   <td>76 
   </td>
   <td>400
   </td>
  </tr>
  <tr>
   <td><a href="https://www.sony.com/electronics/interchangeable-lens-cameras/ilce-6000-body-kit">Sony A6000</a>
   </td>
   <td>25.1×16.7 mm (APS-C)
   </td>
   <td>24 
   </td>
   <td>468 
   </td>
   <td>800
   </td>
  </tr>
  <tr>
   <td><a href="https://www.usa.canon.com/internet/portal/us/home/products/details/cameras/dslr/eos-5d-mark-iv">Canon EOS 5D Mark IV</a>
   </td>
   <td>36 x 24 mm (full frame)
   </td>
   <td>30 
   </td>
   <td>890 
   </td>
   <td>3,000
   </td>
  </tr>
</table>


_Source: Information on cameras compiled from manufacturers' materials_


## Tagging images using GPS 

**GPS tags matter!** For post-processing, each frame taken by the camera needs to be tagged with its GPS location. This is an important process to ensure positional accuracy of the output. If the camera is linked to an onboard GPS, the tagging can be achieved automatically by triggering the sensor through the computer managing the flight (e.g., as waypoints or by time) on the ground. This approach insures that the trigger is included as part of the flight record along with the location and orientation information, permitting extraction of location information for each frame from the flight log. 

When operating a sensor system that is not linked to a GPS by design, the only option is post-flight syncing of GPS data with the camera time exchangeable image file format (EXIF) tags. Even when done correctly, this introduces significant error into the location estimates for each frame and is not recommended. Most cameras record frames at only 1 hz (once per second) frequency, which means that syncing to a 1–5 hz GPS record can introduce up to two seconds of error in the syncing process. When compounded with GPS error, this can result in location errors of tens of meters, depending on the flight speed. To achieve the best mapping results,** the sensors and systems used should be linked to a GPS and able to tag image frames automatically**.


## Other important considerations

There are other important considerations for choosing a UAV sensor in addition to the camera specifications and ability to tag images:

 



*   _Obstacle avoidance_. Even UAVs that are small and relatively inexpensive (less than US$1,000) now are equipped with basic “sense and avoid” systems that allow the aircraft to detect any obstacle in its path and automatically change course to avoid it.
*   _RTK/PPK GPS correction technology_. For accurate data capture, an alternative to using ground control points (described in chapter 7) is to use UAVs equipped with high-precision GPS, which is able to record the position of the aircraft much more precisely than standard GPS receivers. Real-Time Kinematic (RTK) allows high-precision measurements of locations by using a base station with known coordinates that are accurately measured and a radio link or other means to send and receive the correction data from the base station, thus performing “live” triangulation corrections while the UAV is flying. Post-Processed Kinematic (PPK) is similar to RTK, except that the corrections to the GPS positions are calculated not during but after the flight. Both PPK and RTK systems can be purchased as additional features on many professional mapping UAVs. 