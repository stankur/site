<script lang="ts">
    import type { Node } from './SidebarTypes';

    import SidebarNode from './SidebarNode.svelte';

    export let node: Node;

    let expanded = false;
</script>

<div>
    <div class="title-group">
        <a class="title" href={node.url}>
            <span>{node.title}</span>
        </a>

        {#if node.children.length}
            <span class="toggle" on:click={() => expanded = !expanded} role="none">{expanded ? '-' : '+'}</span>
        {/if}
    </div>


    {#if expanded && node.children.length}
        <div class="sidebar-node-children-container">
            {#each node.children as child (child.url)}
                <SidebarNode node={child} />
            {/each}
        </div>
    {/if}
</div>

<style>
    .sidebar-node-children-container {
        border-left: 1px solid rgb(185, 185, 185);
        margin-left: 8px;
    }

    .toggle {
        cursor: pointer;
        display: inline-block;
        display: flex;
        align-items: center;
        justify-content: center;

        width: 24px;
        height: 24px;
    }

    .title-group {
        display: flex;
        align-items: center;
    }

    .toggle:hover {
        background-color: rgb(218, 218, 218);
    }

    .title {
        color: black;
        padding: 8px;
        display: inline-block;
    }
</style>

