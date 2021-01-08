# International Space Station APIs

APIs packed with information regarding all ongoing spaceflights and spacecraft operations at the International Space Station.

The idea for this project came from various space-related APIs, including [Open Notify](http://open-notify.org/) by Nathan Bergey and the excellent [Where The ISS At](https://wheretheiss.at/w/developer) resource, which I called upon when creating my own  [ISS Tracker app](https://corquaid.github.io/api-iss-tracker).

I hope the level of detail in these APIs is useful for your own projects. 

Ad Astra!

## APIs

### People In Space

[People In Space](https://corquaid.github.io/international-space-station-APIs/JSON/people-in-space.json) (JSON)

Calling this API will return lots of information about the only humans not currently on Earth.

Here is a snippet:

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

To calculate an updated total time in space for this person, you could do something like this:

>```
>const date = new Date().getTime() / 1000; // divide by 1000 because the Javascript Date() function returns milliseconds
>const totalTime = parseInt(date - launched); // having deconstructed the launched variable from the returned JSON object
>```



