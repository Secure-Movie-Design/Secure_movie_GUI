<script lang="ts">
    import { Card, CardHeader, CardTitle, CardBody, CardSubtitle, CardText, CardImg } from "sveltestrap"

    export let title: string;
    export let director: string;
    export let img:string;
    export let description: string;

</script>

<div class="card">
    <Card>
        <CardHeader>
            <div class="title">
                <h2>
                    <a href="/movieDetails">{title}</a>
                </h2>
            </div>
        </CardHeader>
        <CardBody>
          <h4>{director}</h4>
          <img src="{img}" alt="not available" width="100px">
          <CardText>{description}</CardText>
        </CardBody>
    </Card>
</div>

<style>
    @import url(https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap);

    * {
        font-family: "Poppins";
    }

    .card {
        padding: 20px;
        margin: 5px;
        width: 200px;
        height: fit-content;
        border: 1px solid black;
        border-radius: 10px;
        background-color: rgb(230, 156, 59);
    }

    .title {
        background-color: rgb(165, 109, 35);
    }

    .title a {
        color: black;
        text-decoration: none;
        transition: .3s;
    }

    .title a:hover {
        color: #fff;
    }
</style>
