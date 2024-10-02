<script>
    const getInfo = async () => {
        let res = await fetch("./header.json");
        let info = await res.json();
        return info;
    }
    const infoPromise = getInfo();
</script>
{#await infoPromise}
    <p>Loading info...</p>
{:then info} 
<h1>{info.name}</h1>
<div class="links">
    <span>
        <a href="mailto:{info.email}" target="_blank">{info.email}</a>
    </span>
    <span>
        {info.phone}
    </span>
    <!-- <span> -->
    <!--     <a href="https://{info.website}" target="_blank">{"Website"}</a> -->
    <!-- </span> -->
    <!-- <span> -->
    <!--     <a href="https://github.com/{info.github}" target="_blank">{"GitHub"}</a> -->
    <!-- </span> -->
    <!-- <span> -->
    <!--     <a href="https://linkedin.com/in/{info.linkedin}" target="_blank">{"LinkedIn"}</a> -->
    <!-- </span> -->
</div>    
{/await}


<style>
    h1{
        font-size: 2.5rem;
        font-weight: 500;
        text-transform: uppercase;
        margin-bottom: 15px;
    }

    .links {
        display: flex;
        justify-content: left;
        padding-bottom: 15px;
    }
    .links > span {
        font-size: 12px;
        font-weight: 600;
        padding-right: 15px;
    }

</style>
