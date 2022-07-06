<script>


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
    const { country } = location;
    const { condition } = current;
    return {
      condition,
      country
    }
  })

</script>

{#await weatherPromise then weather}
 <h1>{ weather.country }</h1>
{/await}
<style>
 
</style>
