<script lang="ts">
    import { onMount } from "svelte";
    import { page } from "$app/stores";

    import type { Movie } from "../../../model/Movie";

    const index: number = $page.url.toString().indexOf("movieDetails/") + 13;
    const movieID: number = parseInt($page.url.toString().substring(index).split("/")[0]);

    let movie: Movie = {
        id:-1,
        title:"",
        category:"",
        year:-1,
        director:"",
        description:"",
        image_url:""
    };

    onMount(async () => {
        fetch("http://localhost:8000/api/v1/movies/"+movieID)
            .then(response => response.json())
            .then(data => {
                console.log(data);
                movie = data;
            }).catch(error => {
                console.log(error);
            })
    });
</script>

<div class="container">
    <img src={movie.image_url} alt="not available">
    <div class="details">
        <div class="title">
            {movie.title || "-"}
        </div>
        <div class="major-data">
            <b><em>Year :</em></b> {movie.year || "-"}
        </div>
        <div class="major-data">
            <b><em>Category :</em></b> {movie.category || "-"}
        </div>
        <div class="major-data">
            <b><em>Director :</em></b> {movie.director || "-"}
        </div>
        <div class="minor-data">
            Description:<br>
            {movie.description || "-"}
        </div>
    </div>
</div>

<style>
    * {
        text-align: center;
        color: #fff;
    }

    .container {
        display: flex;
        justify-content: space-evenly;
    }

    .details {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        margin: 40px;
        padding: 30px;
        border-radius: 20px;
        max-width: 800px;
    }

    .container img {
        object-fit: cover;
        width: 100%;
        max-width: 400px;
        border-radius: 10px;
        margin: 10px;
    }

    .title {
        font-size: 4.5em;
        margin: 10px;
    }

    .major-data {
        font-size: 2em;
        margin: 10px;
    }

    .minor-data {
        font-size: 1.5em;
        margin: 10px;
    }
</style>