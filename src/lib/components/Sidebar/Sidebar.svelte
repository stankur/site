<script lang="ts">   
    import type { Node } from './SidebarTypes';
    import SidebarNode from './SidebarNode.svelte';

    export let nodes: Node[];
</script>

<div class="sidebar">
    {#each nodes as node (node.url)}
        <SidebarNode node={node} />
    {/each}
</div>

<style>
    .sidebar {
        min-width: 20%;
    }
</style>


