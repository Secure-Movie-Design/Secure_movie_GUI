<script lang="ts">
    import MovieCard from "./MovieCard.svelte";
    import type { Movie } from "../../model/Movie";

    export let movies:Movie[];
</script>

<div class="container">
    {#each movies as movie}
        <MovieCard
            title={movie.title}
            director={movie.director}
            img={movie.image_url}
            category={movie.category}
        ></MovieCard>
    {/each}
</div>

<!--
<table>
    {#each {length: (movies.length/cols)} as _}
        <tr>
            {#each {length: cols} as _}
                {#if getIndex() < movies.length}
                    <th class="col-2">
                        <MovieCard
                            title={chooseMovie().title}
                            director={chooseMovie().director}
                            img={chooseMovie().image_url}
                            description={chooseMovieWithIncrement().description}
                        ></MovieCard>
                    </th>
                {/if}
            {/each}
        </tr>
    {/each}
</table>
-->

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

    /*
    .cards-grid {
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(13rem, 1fr));
        gap: 1rem;
    }
    */
</style>