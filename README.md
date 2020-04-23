> :warning: **This API is not stable or real yet!**: This document is a speculative API that details the deep integration of environmental crisis data into our digital and virtual devices. Please note that until we can get further support and development, this API is not considered stable or real yet, and any of these proposals may change with time. We’re incredibly interested in your feedback. If you spot an instance where this EcoMediations API can be improved, please do email for discussion. For any other questions, including support on how to use the API and as a place for open discussions on the design and principles, email us too.

# EcoMediations API
An ecomediated API for the current Anthropocene and deep integrations with the [Hyper Green Initiative](https://raw.githubusercontent.com/cricketlova/crisis-api/master/Assets/eco-api-architecture.png).


## Introduction
Most API integrations help developers and designers build applications. Few approaches to APIs have investigated the potentials for incorporating and aggregating environmental crisis as a resource for programmatic incorporation into our digital and virtual experiences. The commoditization of programs, software, computing provide a new potential for delivering instantaneous climate feedback to the consumer, if we so choose to.

We at the [Virtually Real Consortium](https://www.virtuallyrealconsortium.org/) propose that developers, makers, and more should begin moving towards an ecological hybridity of our degrading environment to our lived, digital, and virtual realities. There is no promise of a better environment tomorrow, but we can at least do our part in raising a new relationship and awareness with it.

This API is for use in our crisis driven future and follows RESTful standards and uses JSON.

### Data Input & Storing
#### Inputs
The consortium's EcoMediations API is organized around public, private, and open source data sources. The Virtually Real Consortium (VRC) will have a crisis database in which stores all of the data sources from satellite to UAV surveying.

![eco-api-architecture](https://raw.githubusercontent.com/cricketlova/crisis-api/master/Assets/eco-api-architecture.png)

#### Data Vetting
Future data will be vetted through the VRC Data Ethics governing body where the source data is parsed for accuracy and filtered of redundancies. This governing body will help maintain consistency through an internal ETL/data cleaning process, especially as data is contributed from all fronts from the most micro DIY sensors to more complex uploads from institutions.

#### The Human
With the data and measurements of our environments, there is the idea of distinction between what is human influenced versus naturally occurring.

### Event & Data Thresholds
Through a few speculative near-future partnerships with environmental agencies such as the EPA, NASA, WWF, USDA, US Forest Service, and more... the VRC will be able to facilitate local and global agreements on thresholds in which environmental data cross and automates a new climactic event. Additionally, organizations using the EcoMediations API may follow the threshold examples below for their own implementation purposes.

### Outputs
The outputs of this crisis focused database is an embedding of crisis moments as an integrated moment in between our digital and virtual experiences. The goal is to partner with technology to showcase environmental crisis not as a static visualization, report, or mapping dashboard, but rather a truly dynamic imaginary implicitly part of products and software we consume on a day to day. A consumer grade level integration across all of our media.

![hypergreen-environment-model](https://raw.githubusercontent.com/cricketlova/crisis-api/master/Assets/Current%20Environmental%20Model.png)


## Reference

### General Structure
All of the following events and objects will follow a format of containing attributes type & id. This will be followed by the attributes you may call.

### Crisis Event
This is an object that represents the type of Crisis Event in which you can call. You can retrieve it to see the highest level of the crisis itself.

```
GET /v1/crisis-events
```

#### Crisis Event Object

##### Attributes:
- <b>Type</b> - Type of crisis event for the object.
- <b>id</b> - Unique identifier for the event.
- <b>name</b> - Specific name of the crisis event for the object.
- <b>start_at</b> - The beginning in which the crisis started based on the beginning of time.
- <b>end_at</b> - The end in which the crisis has ended. Potentially `null` if it is ongoing.

Example Code:

```JSON
{
  "data": [
  {
  "type": "crisis-event",
  "id": "1",
  "attributes": {
  "name": "Global Brush Fire",
  "start_at": "2020-03-01 00:00:00 -007",
  "end_at": "2020-03-01 00:00:00 -007",
      }
    }
  ]
}
```

### Crisis Scenario
Scenarios mainly hold two types of records that can be retrieved from any crisis event, population (e.g. biodiversity, species identification, etc...) and/or environmental (seismologic data, atmospheric data, etc...). Within these two categories of records, there are many records in which can be pulled.

```
GET /v1/crisis-event/1/scenarios
```

#### Crisis Scenario Object

##### Attributes:
- <b>id</b> - Unique identifier for the scenario.
- <b>name</b> -  Specific name of the crisis event for the object.
- <b>start_at</b> - The beginning in which the crisis started based on the beginning of time.
- <b>end_at</b> - The end in which the crisis has ended. Potentially `null` if it is ongoing.

Example Code:
```JSON
{
  "data": [
  {
  "type": "crisis-scenario",
  "id": "1",
  "attributes": {
  "scenario_type": "environmental",
  "crisis_event_id": "1"
   }
  }
 ]
}
```

### Records
Records contain all data that contribute to a specific crisis scenario within both the environment and population groups. Each of these records return an assortment of attributes that range from temporal to amount measurements based on the type of crisis.

Note: Not all records contain the same data.

---

#### Atmosphere Record

```
GET /v1/scenarios/:scenario_id/records?record_type=atmosphere
```

##### Attributes:
- <b>id</b> - Unique identifier for the record
- <b>measured_at</b> - Time in which record was measured
- <b>temperature</b> - Log of temperature
- <b>measured_lat</b> - Latitude of measurement devices
- <b>measured_long</b> - Longitude of measurement devices
- <b>co2_level</b> - Carbon levels in the air
- <b>co2_unit_descriptor</b> - Carbon level descriptor (PPM)
- <b>ch4_level</b> - Methane levels in the air
- <b>ch4_unit_descriptor</b> - Methane level descriptor
- <b>no_level</b> - Nitrogen Monoxide levels in the air
- <b>no_unit_descriptor</b> - Nitrogen Monoxide level descriptor
- <b>no2_level</b> - Nitrogen Dioxide levels in the air
- <b>no2_unit_descriptor</b> - Nitrogen Dioxide level descriptor
- <b>pm2.5_level</b> - Fine Particulate Matter levels
- <b>pm2.5_unit_descriptor</b> - Fine Particulate Matter descriptor (μg/m3)
- <b>pm10_level</b> - Fine Particulate Matter levels
- <b>pm10_unit_descriptor</b> - Large Particulate Matter descriptor (μg/m3)


##### Example Implementation:
An example of how CCTV has implemented with `pm2.5` and `pm10` are new markers on all of their footage across their natural surveying cameras. You can their incorporations of the location of area as well.
<br>

![CCTV Atmosphere GIF](https://github.com/cricketlova/crisis-api/blob/master/Assets/CCTV-visualizer.gif?raw=true)

---

#### Seismologic Record

```
GET /v1/scenarios/:scenario_id/records?record_type=seismologic
```

##### Attributes:
- <b>id</b> - Unique identifier for the record
- <b>started_at</b> - Time in which record was measured
- <b>duration</b> - How long the seismic event lasted (minutes:seconds)
- <b>epicenter_lat</b> - Latitude of epicenter in which the earthquake started
- <b>epicenter_long</b> - Longitude of epicenter in which the earthquake started
- <b>magnitude</b> - Logged magnitude of earthquake from epicenter
- <b>aftershock</b> - Whether or not there was an aftershock
- <b>ground_shift_mm</b> - How much the ground shifted after the seismic event

<br>

Example Code:
```JSON
{
  "data": [
  {
  "type": "crisis-scenario",
  "id": "1",
  "attributes": {
  "scenario_type": "Environmental"
  [
  {
  "id": "SeismologicRecord",
  "scenario_id": "1",
  "report_id": "1",
  "report_type": "SeismologicRecord",
  }
  ]
  }
  }
  ]
}
```

---

#### Canopy Cover Record

```
GET /v1/scenarios/:scenario_id/records?record_type=canopyCover
```

##### Attributes:
- <b>id</b> - Unique identifier for the record
- <b>measured_at</b> - Time in which record was measured first
- <b>total_area</b> - the whole area in which the measurement is taking place
- <b>tree_gain</b> - how much canopy gain has happened in the area relative to a base measurement
- <b>tree_loss</b> - how much canopy loss has happened in the area relative to a base measurement
- <b>total_loss_by_human</b> - how much canopy loss to deforestation or other human activity
- <b>total_loss_by_natural</b> - how much canopy loss to natural occurrences
- <b>density</b> - volume density of the canopy growth within the Forest
- <b>change_over_time</b> an attribute based on two time parameters and change in either loss or gain from it


##### Example Implementation #1:
A few examples of Spotify's revamp on their music filter. Where songs are now modified based on `total_loss_by_natural` to adjust pitch and tone. Just as well, additional elements of modification are drawn from the Species Record as an inclusion of Bark Beetle data in the Northern California forestry areas.
<br>
<br>
Sample Spotify EcoAudio Files:
<br>
[Simon & Garfunkel - The Sound of Silence](/Assets/SimonGarfunkel_SoundofSilence.mp3)
<br>
[The Temptations - Ain't too Proud](/Assets/TheTemptations_AintTooProudToBeg.mp3)

<b>

##### Example Implementation #2:
An example of how Unity developers are now including levels of growth and decay in in their VR development. Objects in Unity can link to our SDK for `tree_gain` in which include an assortment of crisis centric realism that can be added to your plant life based on growth over time as well as cross-referencing moisture levels in the Atmospheric record.
<br>

![Rain-plant-growth-example](https://github.com/cricketlova/crisis-api/blob/master/Assets/plant-growth.gif?raw=true)

---

#### Arctic Ice Mass Record

```
GET /v1/scenarios/:scenario_id/records?record_type=arcticIceMass
```

##### Attributes:
- <b>id</b> - Unique identifier for the record
- <b>measured_at</b> - Time in which record was measured first
- <b>total_area</b> - the whole area in which the measurement is taking place
- <b>ice_gain</b> - how much arctic ice gain has happened in the area relative to a base measurement
- <b>ice_loss</b> - how much arctic ice loss has happened in the area relative to a base measurement
- <b>methane_release</b> - amount of methane released into the air based on ice_loss

##### Example Implementation:
An example of a remix and redux of Super Mario by Nintendo. With their re-release of the game, they hooked their web emulator to include `ice_loss` in their most classic and beloved Super Mario Bros. Now Mario faces more than just Koopa Troopas but also a variety of ice and arctic based level obstacles integrated into gameplay.
<br>

[![super-mario-example](https://raw.githubusercontent.com/cricketlova/crisis-api/master/Assets/superMario-Frame.png)](https://youtu.be/fB14xb4M7Yo?t=5)


---

#### Sea Level Record

```
GET /v1/scenarios/:scenario_id/records?record_type=seaLevel
```

##### Attributes:
- <b>id</b> - Unique identifier for the record
- <b>measured_at</b> - Time in which record was measured first
- <b>temperature</b> - temperature of the sea
- <b>total_height</b> - based on measurements from the designated sea gauge
- <b>sea_height_variation</b> - how much sea levels have risen compared and relative to a base measurement
- <b>sea_level_change</b> - change over time of sea level from base measurement

Example Code:
```JSON
{
  "data": [
  {
  "type": "crisis-scenario",
  "id": "1",
  "attributes": {
  "scenario_type": "Environmental"
  [
  {
  "id": "seaLevelRecord",
  "scenario_id": "1",
  "report_id": "1",
  "report_type": "seaLevelRecord",
  }
  ]
  }
  }
  ]
}
```
