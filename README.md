# Covid-19 Live Data Json
The json contains the number of Coronavirus confirmed cases, deaths, and recovered cases of world, also contains more details for every country, all information is updated every 15 minutes.

```
{
   "coronavirus_cases":"740,235",
   "deaths":"35,035",
   "recovered":"156,588",
   "last_update":"30/03/2020 14:07:45",
   "territories":[
      {
         "country":"USA",
         "total_cases":"142,793",
         "new_cases":"+333",
         "total_deaths":"2,490",
         "new_deaths":"+6",
         "total_recovered":"4,562",
         "active_cases":"135,741",
         "critical_cases":"2,970",
         "first_case":"Jan 20"
      } ....
```

You can to use if you want it from a web site, for example:
```js
fetch('https://raw.githubusercontent.com/NoiseControllers/Covid-19-Data-Live/master/covid19.json')
    .then(response => response.json())
    .then(data => {
        data["territories"].forEach(({
                country,
                total_cases,
                new_cases,
                total_deaths,
                new_deaths,
                total_recovered,
                active_cases,
                critical_cases,
                first_case
            }) =>
            console.log(`${country} - ${total_cases} - ${new_cases} - ${total_deaths} - ${new_deaths} - ${total_recovered} - ${active_cases} - ${critical_cases} - ${first_case}`)
        );
    })
    .catch(function(err) {
        console.error(err);
    });
```
