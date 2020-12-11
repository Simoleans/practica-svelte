<script>
    import { onMount } from 'svelte';

    let photos = [];

    onMount(async () => {
        console.log("onmount")
        const response = await fetch('https://jsonplaceholder.typicode.com/photos?_limit=10');

        photos = await response.json();
    })
</script>

<style>
    .Photos {
        width: 100%;
        display: grid;
        grid-template-columns: repeat(5,1fr);
        grid-gap: 8px;
    }

    @media (min-width: 640px) {
		.Photos {
            display: grid;
            grid-template-columns: repeat(3,1fr);
            grid-gap: 3px;
		}
	}
</style>

<div class="Photos">
    {#each photos as photo }
        <figure>
            <img src={photo.thumbnailUrl} alt={photo.title}>
            <figcaption>{photo.title}</figcaption>
        </figure>
        {:else}
        <p>Cargando...</p>
    {/each}
</div>
