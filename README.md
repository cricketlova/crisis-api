> :warning: **This API is not stable or real yet!**: This document is a speculative API that details deep integration of environmental crisis data into our digital and virtual devices. Please note that until we can get further support and development, this API is not considered stable or real yet, and any of these proposals may change with time. We’re incredibly interested in your feedback. If you spot an instance where this EcoMediations API can be improved, please do email for discussion. For any other questions, including support on how to use the API and as a place for open discussions on the design and principles, email us too.

# EcoMediations API
An impractical API for the current Anthropocene.


## Introduction
Most API integrations help developers and designers build applications. Few approaches to APIs have investigated the potentials for incorporating and aggregating environmental crisis as a resource for programmatic incorporation into our digital and virtual experiences. The commoditization of programs, software, computing provide a new potential for delivering instantaneous climate feedback to the consumer, if we so choose to.

We at the VRC propose that developers, makers,  and more should begin moving towards an ecological  hybridity of our degrading environment to our lived, digital, and virtual realities. There is no promise of a better environment tomorrow, but we can at least do our part in raising a new relationship and awareness with it.

The EcoMediations API is speculated around REST protocols. This API is for use in our crisis driven future and can be built around resource-oriented URLs, JSON-responses, HTTP response codes, etc... (or something else entirely).

### Data Input & Storing
The consortium's EcoMediations API is organized around public, private, and open source data sources. The VRC will have a crisis database in which stores all of the data sources from satellite to UAV surveying.

![eco-api-architecture](https://raw.githubusercontent.com/cricketlova/crisis-api/master/eco-api-architecture.png)

### Data Vetting
Future data will be vetted through the VRC Data Ethics governing body where the source data is parsed for accuracy and filtered of redundancies. This governing body will help maintain consistency through an internal ETL/data cleaning process, especially as data is contributed from all fronts from the most micro DIY sensors to more complex uploads from institutions.


### Event & Data Thresholds
Through a few speculative near-future partnerships with environmental agencies such as the EPA, NASA, WWF, USDA, US Forest Service, and more... the VRC will be able to facilitate local and global agreements on thresholds in which environmental data cross and automates a new climactic event. Additionally, organizations using the EcoMediations API may follow the threshold examples below for their own implementation purposes.



## Reference

### Crisis Event
This is an object that represents the type of Crisis Event in which you can call. You can retrieve it to see the highest level of the crisis itself.

```Javascript
GET /v1/crisis-events
```

#### The Crisis Event Object

##### Attributes:
- <b>Type</b> - Type of crisis
- <b>id</b> - UUID
- <b>name</b> -  Name of the crisis
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

Example Implementation:

[![test](http://img.youtube.com/vi/enMumwvLAug/0.jpg)](http://www.youtube.com/watch?v=enMumwvLAug "test")









-------
Technical topics:
- authentication
- format
- How (RestFUL)
- Endpoints & Responses (examples) =
