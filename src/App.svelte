<script>
    import {beforeUpdate, onMount} from "svelte";

    let ip_address = ""

    const getIPFromAmazon = () => {
        fetch("https://checkip.amazonaws.com/").then(res => res.text()).then(data => {
            ip_address = data
        })
    }
    onMount(() => {
        getIPFromAmazon()
    })

</script>

<main>
    <div id="center">
        <h1 class="title nanum-gothic-bold">
            Your IP IS
        </h1>
        <h3 class="subtitle nanum-gothic-bold">{ip_address}</h3>
    </div>
</main>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Nanum+Gothic:wght@400;700;800&display=swap');

    .nanum-gothic-bold {
        font-family: "Nanum Gothic", system-ui;
        font-weight: 700;
        font-style: normal;
    }

    #center {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
    }

    .title {
        font-size: 40px;
        font-weight: bold;
    }

    .subtitle {
        font-size: 60px;
        font-weight: bold;
        margin-top: 10px
    }
</style>