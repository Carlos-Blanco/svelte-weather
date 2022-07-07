<script>
export let location;
const options = {
	method: 'GET',
	headers: {
		'X-RapidAPI-Key': 'f8d9521e48msh7f5069aa2cea2a8p10d432jsnd92a13465de7',
		'X-RapidAPI-Host': 'weatherapi-com.p.rapidapi.com'
	}
};

const weatherPromise = fetch('https://weatherapi-com.p.rapidapi.com/current.json?q=Madrid', options)
	.then(response => response.json())
	.then(response => {
    console.log(response);
    const { location, current } = response;
    const { name, country, } = location;
    const { condition, temp_c, pressure_mb, humidity, precip_mm } = current;
    return {
      name,
      country,
      condition,
      temperature: temp_c,
      pressure: pressure_mb,
      humidity,
      precipitation: precip_mm
    }
  })

</script>
{location}
{#await weatherPromise}
  <p>Waiting ...</p>
{:then weather} 
  <h1>{ weather.name }</h1>
  <img src={weather.condition.icon} alt="weather.condition.text">
  <p>{ weather.condition.text }</p>
  <p>{ weather.temperature }°</p>
  <p>Pressure: { weather.pressure } mb</p>
  <p>Humidity: { weather.humidity } %</p>
  <p>Precipitation: { weather.precipitation } mm</p>
{/await}
<style>
 
</style>
