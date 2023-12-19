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
    <div class="card">
        <div class="title">
            {movie.title || "-"}
        </div>
        <img src={movie.image_url} alt="not available">
        <div class="major-data">
            Director: {movie.director || "-"}
        </div>
        <div class="major-data">
            Category: {movie.category || "-"}
        </div>
        <div class="minor-data">
            Year: {movie.year || "-"}
        </div>
        <div class="minor-data">
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
        justify-content: center;
    }

    .card {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        background-color: rgb(33,36,40);
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
        margin: 20px;
    }

    .title {
        font-size: 4.5em;
        margin: 20px;
    }

    .major-data {
        font-size: 2em;
        margin: 20px;
    }

    .minor-data {
        font-size: 1.5em;
        margin: 20px;
    }
</style>