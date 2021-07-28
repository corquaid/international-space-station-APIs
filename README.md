# International Space Station APIs

APIs packed with information regarding all ongoing spaceflights and spacecraft operations at the International Space Station.

The idea for this project came from various space-related APIs, including [Open Notify](http://open-notify.org/) by Nathan Bergey and the excellent [Where The ISS At](https://wheretheiss.at/w/developer) resource, which I called upon when creating my own  [ISS Tracker app](https://corquaid.github.io/api-iss-tracker).

It's my goal to keep these APIs up to date depending on rocket launch schedules and spacecraft docking and departures from the ISS.

*Update:* I am now using these APIs in my [React ISS Tracker app](https://corquaid.github.io/react-iss-tracker).

I hope the level of detail in these APIs is useful for your own projects.

Ad Astra!

## APIs

### People In Space :woman_astronaut:

[People In Space](https://corquaid.github.io/international-space-station-APIs/JSON/people-in-space.json) (JSON)

`https://corquaid.github.io/international-space-station-APIs/JSON/people-in-space.json`

Calling this API will return lots of information about the only humans not currently on Earth.

Here's an example of the returned JSON:

>```
>{ 
>  "number": 7,
>  "iss_expedition": 64,
>  "expedition_patch": "https://upload.wikimedia.org/wikipedia/commons/thumb/c/cd/ISS_Expedition_64_Patch.png/1024px-ISS_Expedition_64_Patch.png",
>  "people": [
>     {
>         "id": 1,
>         "name": "Sergey Ryzhikov",
>         "country": "Russia",
>         "flag_code": "ru",
>         "agency": "Roscosmos",
>         "position": "Commander",
>         "spacecraft": "Soyuz MS-17",
>         "launched": "2020-10-14",
  >       "days_in_space": 173
>    }
>  ]  
>}
>```

`"flag_code"` can be used with resources like [countryflags.io](www.countryflags.io) to add national flags to your app.

`"days_in_space"` is the person's total spaceflight experience ***before*** their current mission.

`"launched"` is the start time for their current mission, measured in seconds, since the [UNIX epoch](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date).

Using `"launched"` and `"days_in_space"` together, you can calculate the up-to-date total time a person has spent above the [Karman line](https://en.wikipedia.org/wiki/K%C3%A1rm%C3%A1n_line)!


### Spacecraft at the ISS :rocket:

[ISS Docked Spacecraft](https://corquaid.github.io/international-space-station-APIs/JSON/iss-docked-spacecraft.json) (JSON)

`https://corquaid.github.io/international-space-station-APIs/JSON/iss-docked-spacecraft.json`

If you want to know all about the spacecraft currently docked at the International Space Station, this API will get you up to speed.

Here's an example of the returned JSON:

>```
>{
>   "name": "Crew-1 Dragon",
>   "country": "United States",
>   "operator": "SpaceX",
>   "manufacturer": "SpaceX",
>   "launched": 1605482837,
>   "launch_site": "KSC, LC-39A",
>   "docked": 1605582060,
>   "docking_port": "Harmony forward",
>   "launch_mass": 12055,
>   "payload_mass": null,
>   "launch_vehicle": "Falcon 9",
>   "mission_type": "Crew",
>   "crew": [
>     "Mike Hopkins", "Victor Glover", "Shannon Walker", "Soichi Noguchi"
>    ]
>}
>```

The same calculation can be performed here where you use the `"docked"` UNIX timestamp and your current `Date()` timestamp to return the total time each spacecraft has been docked at the ISS.

This NASA resource is also useful with a nice visualisation of the docked spacecraft:

[ISS Visiting Vehicles (NASA site)](https://www.nasa.gov/feature/visiting-vehicle-launches-arrivals-and-departures)

# References

[Open Notify](http://open-notify.org/) by [Nathan Bergey](http://t.co/jIv30xdyTZ?amp=1).

[Where The ISS At?](https://wheretheiss.at/) by Bill Shupp.




