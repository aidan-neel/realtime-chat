<script lang="ts">
    import { flyAndScale } from "$lib/anims";
	import { fade } from "svelte/transition";

    let isOpen = $state(true)
    let username = $state("")
</script>

{#if isOpen}
    <div transition:fade={{ duration: 100 }} class="h-screen w-screen flex items-center justify-center absolute top-0 left-0 bg-gray-950/50 backdrop-blur-sm">
        <div transition:flyAndScale class=" w-[30rem] bg-gray-900 flex flex-col gap-3 p-5 rounded-lg">
            <header class="">
                <h1 class="font-semibold text-lg">
                    Choose your username
                </h1>
                <p class="text-sm text-gray-500 font-medium">
                    You can change this later
                </p>
            </header>
            <input type="text" placeholder="Username" class='rounded-lg text-sm bg-gray-800/70 h-10 border-none font-normal placeholder:font-normal focus:outline-white focus:ring-0 text-white placeholder:text-white/50'>
            <div class="flex flex-row items-center justify-end">
                <button onclick={() => {
                    if(username !== "") {
                        isOpen = false;
                        localStorage.setItem("username", username)
                    }
                }} class="p-2 bg-indigo-700 px-6 rounded-lg text-sm duration-150 hover:cursor-pointer hover:bg-indigo-900">
                    Save
                </button>
            </div>
        </div>
    </div>
{/if}