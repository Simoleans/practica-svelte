<script>
    let skills = [
        {
            id: 1,
            name: 'HTML'
        },
        {
            id : 2,
            name : 'JavaScript'
        },
        {
            id : 3,
            name : 'PHP'
        }
    ]
</script>

<style>
    .Skills {
        display: flex;
        justify-content: center;
        align-items: center;
    }

    ul {
        margin: 0;
        padding: 0;
        list-style: none;
    }

    li {
        display: inline;
        margin: 0 0 0 0.4em;
    }
</style>

<div class="Skills">
    <h3>Habilidades</h3>
    <ul>
        {#each  skills as {name}, i }
            <li>{name}</li>
        {/each}
    </ul>
</div>