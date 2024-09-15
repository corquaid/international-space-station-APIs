# International Space Station APIs

APIs packed with information regarding all ongoing spaceflights and spacecraft operations at the International Space Station and the Chinese Space Station (Tiangong).

The inspiration for this project came from various space-related APIs, including [Open Notify](http://open-notify.org/) by Nathan Bergey and the excellent [Where The ISS At](https://wheretheiss.at/w/developer) resource.

It's my goal to keep these APIs up to date depending on rocket launch schedules and spacecraft docking and departures from the ISS and CSS.

I hope the level of detail in these APIs is useful for your own projects.

Please let me know if there is any information that you would like to have added to either API, just open an issue, or go ahead and create a PR!

Ad Astra!

(Please note that I won't be updating for sub-orbital spaceflights (New Shepard, Virgin Galactic and the like), only orbital flights.)

## APIs

### People In Space :woman_astronaut:

[People In Space](https://corquaid.github.io/international-space-station-APIs/JSON/people-in-space.json) (JSON)

`https://corquaid.github.io/international-space-station-APIs/JSON/people-in-space.json`

Calling this API will return lots of information about the only humans not currently on Earth.

Here's an example of the returned JSON:

```json
{
  "number": 15,
  "iss_expedition": 71,
  "expedition_patch": "https://upload.wikimedia.org/wikipedia/commons/b/b4/ISS_Expedition_71_Patch.png",
  "expedition_url": "https://en.wikipedia.org/wiki/Expedition_71",
  "expedition_image": "https://upload.wikimedia.org/wikipedia/commons/8/81/The_official_Expedition_71_crew_portrait.jpg",
  "expedition_start_date": 1712354400,
  "expedition_end_date": 1727128800,
  "people": [
    ...
    {
      "id": 15,
      "name": "Don Pettit",
      "country": "United States",
      "flag_code": "us",
      "agency": "NASA",
      "position": "Flight Engineer",
      "spacecraft": "Soyuz MS-26",
      "launched": 1726150992,
      "iss": true,
      "days_in_space": 369,
      "url": "https://en.wikipedia.org/wiki/Donald_Pettit",
      "image": "https://i.ibb.co/cgvcwqN/NASA-astronaut-Don-Pettit-pillars.jpg",
      "instagram": "https://www.instagram.com/astro_pettit/",
      "twitter": "https://x.com/astro_Pettit",
      "facebook": ""
    },
    ...
  ]
}
```

`"flag_code"` can be used with resources like [countryflags.io](www.countryflags.io) to add national flags to your app.

`"days_in_space"` is the person's total spaceflight experience **_before_** their current mission.

`"launched"` is the start time for their current mission, measured in seconds, since the [UNIX epoch](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date).

Using `"launched"` and `"days_in_space"` together, you can calculate the up-to-date total time a person has spent above the [Karman line](https://en.wikipedia.org/wiki/K%C3%A1rm%C3%A1n_line)!

### Spacecraft at the ISS :rocket:

[ISS Docked Spacecraft](https://corquaid.github.io/international-space-station-APIs/JSON/iss-docked-spacecraft.json) (JSON)

`https://corquaid.github.io/international-space-station-APIs/JSON/iss-docked-spacecraft.json`

If you want to know all about the spacecraft currently docked at the International Space Station, this API will get you up to speed.

Here's an example of the returned JSON:

```json
{
  "number": 6,
  "spacecraft": [
    {
      "id": 1,
      "name": "Crew-8 Dragon",
      "country": "United States",
      "flag_code": "us",
      "operator": "SpaceX",
      "manufacturer": "SpaceX",
      "spacecraft_name": "Endeavour",
      "launched": 1709520840,
      "launch_site": "KSC, LC-39A",
      "iss": true,
      "docked": 1709620080,
      "docking_port": "Harmony forward",
      "launch_mass": 12519,
      "payload_mass": null,
      "launch_vehicle": "Falcon 9",
      "launch_vehicle_name": "B1083.1",
      "mission_type": "Crew",
      "crew": [
        "Matthew Dominick",
        "Michael Barratt",
        "Jeanette Epps",
        "Alexander Grebenkin"
      ],
      "mission_patch": "https://upload.wikimedia.org/wikipedia/commons/a/a0/SpaceX_Crew-8_logo.png",
      "url": "https://en.wikipedia.org/wiki/SpaceX_Crew-8",
      "image": "https://upload.wikimedia.org/wikipedia/commons/f/fd/Jsc2023e070781.jpg"
    },
    ...
  ]
}

```

The same calculation can be performed here where you use the `"docked"` UNIX timestamp and your current `Date()` timestamp to return the total time each spacecraft has been docked at the ISS.

This NASA resource is also useful with a nice visualisation of the docked spacecraft:

[ISS Visiting Vehicles (NASA site)](https://www.nasa.gov/international-space-station/space-station-visiting-vehicles/)

# References

[Open Notify](http://open-notify.org/) by [Nathan Bergey](http://t.co/jIv30xdyTZ?amp=1).

[Where The ISS At?](https://wheretheiss.at/) by [Bill Shupp](https://about.me/shupp).

>
