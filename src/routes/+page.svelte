<div class="diapositive" id="pageA">
    <h1>Page A</h1>
</div>
<div class="diapositive" id="pageB">
    <h1>Page B</h1>
</div>
<div class="diapositive" id="pageC">
    <h1>Page C</h1>
</div>

<style>
    :global(html, body) {
        margin: 0;
        padding: 0;
        width: 100%;
        height: 100%;
        font-family: Arial, sans-serif;
        scroll-behavior: smooth;
        scroll-snap-type: y mandatory;
    }

    .diapositive {
        width: 100vw;
        height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        scroll-snap-align: start;
        padding: 20px;
        box-sizing: border-box;
    }

    .diapositive h1 {
        font-size: 3rem;
        text-align: center;
    }

    #pageA {
        background-color: lightcoral;
    }

    #pageB {
        background-color: lightseagreen;
    }

    #pageC {
        background-color: lightgoldenrodyellow;
    }
</style>