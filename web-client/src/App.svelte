<script>
    import {onMount} from "svelte";

    let songs = [];

    onMount(() => {
        fetch("/api/songs")
            .then(response => response.json())
            .then(data => songs = data)
    });
</script>

<p>Hola desde svelte!</p>

{#each songs as {title, author}}
    <div>{title} by {author}</div>
{/each}