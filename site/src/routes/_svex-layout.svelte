<script>
    export let slug
    export let title
</script>

<style>
    div {        
        display: block;
        padding: 0 2rem .75rem 1rem;
        position: relative;
        width: 100%;
    }

    div > :global(* + *) {
        margin-top: 1rem;
    }

    div :global(ul) {
        list-style-type: square;
        padding-left: 1.5rem;
    }

    div :global(pre) {
        background-color: var(--grey-light);
        border: 0;
        border-left: 2px solid var(--orange);
        display: block;
        overflow-x: auto;
        padding-top: .5rem;
        max-width: 100%;
        width: 100%;
    }
</style>

<svelte:head>
	<meta name="og:description" content="{title}">
	<meta name="og:url" content="https://www.renderless-svelte.dev/{slug ? slug : ''}">
	<meta name="twitter:description" content="{title}">
	<meta name="twitter:url" content="https://www.renderless-svelte.dev/{slug ? slug : ''}">
</svelte:head>

<div>
    <slot></slot>
</div>