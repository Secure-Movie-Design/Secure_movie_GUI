<script lang="ts">
    import { onMount } from "svelte";

    import type { Movie } from "../../model/Movie";

    let movie: Movie;

    onMount(async () => {
        fetch(" http://localhost:8000/api/v1/movies/{movie_id}")
            .then(response => response.json())
            .then(data => {
                console.log(data);
                movie = data;
            }).catch(error => {
                console.log(error);
                return [];
            })
    });
</script>

<h1>Movie Datail Page ?</h1>