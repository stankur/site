<script lang="ts">
    export let label: string;
    export let url: string;
</script>

<a href={url} class="flex grow text-ellipsis justify-left items-center pl-4 pr-4 hover:bg-neutral-200 rounded-lg">
    {label}
</a>
