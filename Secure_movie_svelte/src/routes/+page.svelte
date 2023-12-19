<script lang="ts">
    import { onMount } from "svelte";

    import MovieGrid from "../lib/components/MovieGrid.svelte"
    import type { Movie } from "../model/Movie";

    let movies: Movie[] = [];

    onMount(async () => {
        fetch("http://localhost:8000/api/v1/movies")
            .then(response => response.json())
            .then(data => {
                console.log(data);
                movies = data;
            }).catch(error => {
                console.log(error);
                return [];
            })
    });
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
