<script lang="ts">
    import MovieGrid from "../lib/components/MovieGrid.svelte"
    import type { Movie } from "../model/Movie";

    let movies: Movie[] = [];
    //TODO: make an API request to retrieve real datas from backend
    for (let i = 0; i<10; i++) {
        let movie:Movie = {
            id:i,
            title:"title"+i,
            director:"director"+i,
            img:"https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.nationalgeographic.com%2Fanimals%2Fmammals%2Ffacts%2Fdomestic-cat&psig=AOvVaw2NAbROHLMvJ1ca2VYFsKLq&ust=1702751962620000&source=images&cd=vfe&opi=89978449&ved=0CBEQjRxqFwoTCIi_6sSLkoMDFQAAAAAdAAAAABAD",
            description:"description"+i
        }
        movies.push(movie)
    }
</script>

<div class="container">
    <MovieGrid movies={movies}></MovieGrid>
</div>

<style>
    .container {
        display: flex;
        justify-content: center;
        align-items: center;
    }
</style>
