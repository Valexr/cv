<script lang="ts">
    let { skill }: { skill: { head: string[]; list: string[] } } = $props();
</script>

<article>
    <ul class="inline">
        {#each skill.head as head}
            <li>{@html head}</li>
        {/each}
    </ul>
    <ul>
        {#each skill.list as list}
            <li>{@html list}</li>
        {/each}
    </ul>
</article>

<style>
    article {
        margin-bottom: 2em;
    }
</style>
