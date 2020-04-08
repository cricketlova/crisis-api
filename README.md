# EcoMediations API
An impractical API for our current Anthropocene.


## Introduction:
Most API integrations help developers and designers build applications. Few approaches to APIs have investigated the potentials for incorporating and aggregating environmental crisis as a resource for programmatic incorporation into our digital and virtual experiences. The commoditization of programs, software, computing provide a new potential for delivering instantaneous climate feedback to the consumer, if we so choose to.

We at the VRC propose that developers, makers,  and more should begin moving towards an ecological  hybridity of our degrading environment to our lived, digital, and virtual realities. There is no promise of a better environment tomorrow, but we can at least do our part in raising a new relationship and awareness with it.

The EcoMediations API is speculated around REST protocols. This API is for use in our crisis driven future and can be built around resource-oriented URLs, JSON-responses, HTTP response codes, etc... (or something else entirely).



## Reference:

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

[![Alt text](https://damien.pobel.fr/images/200x/syrphe-phacelie.jpg)](https://www.youtube.com/embed/enMumwvLAug)









-------
Technical topics:
- authentication
- format
- How (RestFUL)
- Endpoints & Responses (examples) =
