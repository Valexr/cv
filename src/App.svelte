<script lang="ts" context="module">
    import data from "./data";
    import Skill from "$lib/components/Skill.svelte";
</script>

<script lang="ts">
    export let name: string;
</script>

<svelte:head>
    <title>{name}</title>
</svelte:head>

<header>
    {#each data.bio as bio}
        <p>{@html bio}</p>
    {/each}
</header>

<main>
    <!-- <p>{data.job}</p> -->
    <section>
        <h2>Опыт работы</h2>
        {#each data.skills as skill}
            <Skill {skill} />
        {/each}
    </section>
    <section>
        <h2>Образование и сертификаты</h2>
        <ul class="inline">
            {#each data.docs as doc}
                <li>{doc}</li>
            {/each}
        </ul>
    </section>
    <section>
        <h2>Языки и технологии</h2>
        <ul>
            {#each data.tech as tech}
                <li>{tech}</li>
            {/each}
        </ul>
    </section>
</main>

<footer>
    <p>© {new Date().getFullYear()}</p>
</footer>

<style>
    @import "app.css";
</style>
