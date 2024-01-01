<script>
    import Title from './Title.svelte';

    const getEdu = async () => {
            let res = await fetch("./education.json");
            let edu = await res.json();
            return edu;
        }
    const eduPromise = getEdu();
</script>

<div class="education">
    <Title name="Education"/>
    {#await eduPromise}
        <p>Loading education...</p>
    {:then edu} 
    <h3 class="primary-heading">{edu.degree}</h3>
    <div class="icon-row">
        <h4 class="secondary-heading">{edu.school}</h4>
        <span>{edu.duration}</span>
    </div>
    {/await}
</div>

<style>
    .icon-row {
        display: flex;
        justify-content: space-between;
        align-items: center;
    }

    .secondary-heading {
        margin-right: 10px;
    }
</style>
