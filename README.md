# International Space Station APIs

APIs packed with information regarding all ongoing spaceflights and spacecraft operations at the International Space Station.

The inspiration for this project came from various space-related APIs, including [Open Notify](http://open-notify.org/) by Nathan Bergey and the excellent [Where The ISS At](https://wheretheiss.at/w/developer) resource, which I called upon when creating my own [ISS Tracker app](https://corquaid.github.io/react-iss-tracker/).

It's my goal to keep these APIs up to date depending on rocket launch schedules and spacecraft docking and departures from the ISS.

I hope the level of detail in these APIs is useful for your own projects.

Ad Astra!

## APIs

### People In Space :woman_astronaut:

[People In Space](https://corquaid.github.io/international-space-station-APIs/JSON/people-in-space.json) (JSON)

`https://corquaid.github.io/international-space-station-APIs/JSON/people-in-space.json`

Calling this API will return lots of information about the only humans not currently on Earth.

Here's an example of the returned JSON:

> ```
> {
>  number: 11,
>  iss_expedition: 67,
>  expedition_patch: "https://upload.wikimedia.org/wikipedia/commons/d/d3/ISS_Expedition_67_Patch.png",
>  expedition_url: "https://en.wikipedia.org/wiki/Expedition_67",
>  expedition_image: "https://upload.wikimedia.org/wikipedia/commons/5/5e/Expedition_67_crew_portrait.jpg",
>  people: [
>     {
>  id: 1,
>  name: "Raja Chari",
>  country: "United States",
>  flag_code: "us",
>  agency: "NASA",
>  position: "Flight Engineer",
>  spacecraft: "Crew-3 Dragon",
>  launched: 1636592611,
>  iss: true,
>  days_in_space: 0,
>  url: "https://en.wikipedia.org/wiki/Raja_Chari",
>  image: "https://upload.wikimedia.org/wikipedia/commons/thumb/c/c1/SpaceX_Crew-3_Commander_Raja_Chari_%28cropped%29.jpg/> 1558px-SpaceX_Crew-3_Commander_Raja_Chari_%28cropped%29.jpg"
>     },
>  ]
> }
> ```

`"flag_code"` can be used with resources like [countryflags.io](www.countryflags.io) to add national flags to your app.

`"days_in_space"` is the person's total spaceflight experience **_before_** their current mission.

`"launched"` is the start time for their current mission, measured in seconds, since the [UNIX epoch](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date).

Using `"launched"` and `"days_in_space"` together, you can calculate the up-to-date total time a person has spent above the [Karman line](https://en.wikipedia.org/wiki/K%C3%A1rm%C3%A1n_line)!

### Spacecraft at the ISS :rocket:

[ISS Docked Spacecraft](https://corquaid.github.io/international-space-station-APIs/JSON/iss-docked-spacecraft.json) (JSON)

`https://corquaid.github.io/international-space-station-APIs/JSON/iss-docked-spacecraft.json`

If you want to know all about the spacecraft currently docked at the International Space Station, this API will get you up to speed.

Here's an example of the returned JSON:

> ```
> {
>   "name": "Crew-4 Dragon",
>   "country": "United States",
>   "operator": "SpaceX",
>   "manufacturer": "SpaceX",
>   "launched": 1651038775,
>   "launch_site": "KSC, LC-39A",
>   "docked": 1651095420,
>   "docking_port": "Harmony zenith",
>   "launch_mass": 12519,
>   "payload_mass": null,
>   "launch_vehicle": "Falcon 9",
>   "mission_type": "Crew",
>   "crew": [
>      "Kjell Lindgren",
>      "Bob Hines",
>      "Samantha Cristoforetti",
>      "Jessica Watkins"
>    ]
> }
> ```

The same calculation can be performed here where you use the `"docked"` UNIX timestamp and your current `Date()` timestamp to return the total time each spacecraft has been docked at the ISS.

This NASA resource is also useful with a nice visualisation of the docked spacecraft:

[ISS Visiting Vehicles (NASA site)](https://www.nasa.gov/feature/visiting-vehicle-launches-arrivals-and-departures)

# References

[Open Notify](http://open-notify.org/) by [Nathan Bergey](http://t.co/jIv30xdyTZ?amp=1).

[Where The ISS At?](https://wheretheiss.at/) by Bill Shupp.

>
