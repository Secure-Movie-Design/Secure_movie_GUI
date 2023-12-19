<script lang="ts">
    import MovieCard from "./MovieCard.svelte";
    import type { Movie } from "../../model/Movie";

    export let movies:Movie[];
</script>

<div class="container">
    {#each movies as movie}
        <MovieCard
            id={movie.id}
            title={movie.title}
            director={movie.director}
            img={movie.image_url}
            category={movie.category}
        ></MovieCard>
    {/each}
</div>

<style>
    .container {
        display: grid;
		grid-template-columns: 1fr 1fr 1fr 1fr;
		grid-template-rows: 10fr;
		grid-gap: 5px;
    }

    @media only screen and (max-width: 1100px) {
		.container {
            display: grid;
			grid-template-columns: 1fr 1fr;
            grid-template-rows: 10fr;
            grid-gap: 5px;
		}
	}

    @media only screen and (max-width: 600px) {
        .container {
            display: grid;
			grid-template-columns: 1fr;
            grid-template-rows: 10fr;
            grid-gap: 5px;
		}
    }
</style>