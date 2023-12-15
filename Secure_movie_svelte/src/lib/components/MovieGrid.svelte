<script lang="ts">
    import MovieCard from "./MovieCard.svelte";
    import type { Movie } from "../../model/Movie";

    export let movies:Movie[];
    let cols: number = 4;
    let index: number = 0;

    function getIndex(): number {
        return index;
    }

    function chooseMovie(): Movie {
        return movies[index];
    }

    function chooseMovieWithIncrement(): Movie {
        let target = movies[index];
        index++;
        return target;
    }
</script>

<table>
    {#each {length: (movies.length/cols)} as _}
        <tr>
            {#each {length: cols} as _}
                {#if getIndex() < movies.length}
                    <th class="col-2">
                        <MovieCard
                            title={chooseMovie().title}
                            director={chooseMovie().director}
                            img={chooseMovie().img}
                            description={chooseMovieWithIncrement().description}
                        ></MovieCard>
                    </th>
                {/if}
            {/each}
        </tr>
    {/each}
</table>