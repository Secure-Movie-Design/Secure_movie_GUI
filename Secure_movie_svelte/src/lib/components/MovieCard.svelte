<script lang="ts">
    import { Card, CardHeader, CardTitle, CardBody, CardSubtitle, CardText, CardImg } from "sveltestrap"

    export let id: number;
    export let title: string;
    export let director: string;
    export let img:string;
    export let category: string;

</script>

<div class="card">
    <Card>
        <CardHeader>
            <a href="/movieDetails/{id}"><img src={img} alt="not available" width="100%"></a>
            <div class="title">
                <h2>
                    <a href="/movieDetails/{id}">{title}</a>
                </h2>
            </div>
        </CardHeader>
        <CardBody>
          <h4 class="body">{director}</h4>
          <h4 class="body">{category}</h4>
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
        border: 1px solid #000;
        border-radius: 10px;
        background-color: rgb(33,36,40);
        transition: .3s;
    }

    .card:hover {
        border: 1px solid #fff;
    }

    .title {
        background-color: rgb(67, 72, 80);
        border-radius: 5px;
        text-align: center;
    }

    .title a {
        color: #000;
        text-decoration: none;
        transition: .3s;
    }

    .title a:hover {
        color: #fff;
        font-weight: 1000;
    }

    .body {
        color: #afafaf;
        font-weight: 500;
        text-align: center;
    }
</style>
