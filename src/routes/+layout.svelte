<script lang="ts">
	import Sidebar from "$lib/components/Sidebar.svelte";
	import type { Node } from "$lib/components/SidebarTypes";

	const contents: Node[] = [
		{
			title: "Home",
			url: "/",
			children: [
				{
					title: "About",
					url: "/about",
					children: [
						{
							title: "Home",
							url: "/",
							children: [
								{
									title: "About",
									url: "/about",
									children: [],
								},
								{
									title: "Blog",
									url: "/blog",
									children: [],
								},
							],
						},
					],
				},
				{
					title: "Blog",
					url: "/blog",
					children: [],
				},
			],
		},
		{
			title: "Projects",
			url: "/projects",
			children: [],
		},
	];
</script>

<svelte:head>
	<style>
		@import url("https://fonts.googleapis.com/css2?family=Inter:wght@100..900&display=swap");

		* {
			font-family: Inter, sans-serif;
			line-height: 1.5;
			box-sizing: border-box;
		}
	</style>
</svelte:head>

<div class="container">
	<Sidebar nodes={contents} />
    <div class="content-container">
        <div class="content">
            <slot />
        </div>
    </div>
</div>

<style>
    .container {
        display: flex;
    }

    .content {
        width: 50vw;
    }

    .content-container {
        flex-grow: 1;
        display: flex;
        justify-content: center;
    }
</style>
