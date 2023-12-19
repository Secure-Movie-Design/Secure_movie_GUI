<script>
</script>

<div class="container">
    <nav class="navbar">
        <p>Secure Movie Design</p>
        <a href="/">home</a>
    </nav>
    
    <slot></slot>

    <footer>
        <p>Secure Movie Design</p>
        <p>@GitHub: https://github.com/Secure-Movie-Design</p>
    </footer>
</div>

<style>
    .container {
        background-color: rgb(21,21,21);
    }

    .navbar {
        display: flex;
        align-items: center;
        justify-content: space-between;
        background-color: rgb(82,50,163);
        color: #fff;
        font-size: 1.4em;
        height: 70px;
        padding: 0 40px;
        z-index: 99;
        margin-bottom: 30px;
    }

    .navbar p {
        font-size: larger;
        font-weight: 500;
    }

    .navbar a {
        margin-left: 5px;
        position: relative;
        font-size: 100%;
        color: #fff;
        text-decoration: none;
        font-weight: 500;
    }

    .navbar a::after {
        content: '';
        position: absolute;
        left: 0;
        bottom: -6px;
        width: 100%;
        height: 3px;
        background: #fff;
        border-radius: 5px;
        transform-origin: right;
        transform: scaleX(0);
        transition: transform .3s;
    }

    .navbar a:hover::after {
        transform-origin: left;
        transform: scaleX(1);
    }

    footer {
        display: flex;
        align-items: center;
        justify-content: space-between;
        background-color: rgb(82,50,163);
        color: #fff;
        font-size: 1.4em;
        height: 50px;
        padding: 0 40px;
        z-index: 99;
        margin-top: 30px;
    }

    .navbar p {
        font-size: larger;
        font-weight: 500;
    }
</style>
