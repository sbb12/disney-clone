<script lang="ts">
    import { slide } from 'svelte/transition'

    let open = false
    export let title: string

</script>

<div class="text-gray-50 text-base md:text-2xl px-4 md:px-6 bg-[#13151d] my-4">
    <button class="inline-flex justify-between items-center w-full p-4 md:p-6 text-left" on:click={() => {open = !open}}> 
        <span>{title}</span>   
        <div class="pl-8 md:scale-150">
            {#if open}
            <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" fill="currentColor" class="bi bi-dash" viewBox="0 0 16 16">
                <path d="M4 8a.5.5 0 0 1 .5-.5h7a.5.5 0 0 1 0 1h-7A.5.5 0 0 1 4 8z"/>
            </svg>
            {:else}
            <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" fill="currentColor" class="bi bi-plus" viewBox="0 0 16 16">
                <path d="M8 4a.5.5 0 0 1 .5.5v3h3a.5.5 0 0 1 0 1h-3v3a.5.5 0 0 1-1 0v-3h-3a.5.5 0 0 1 0-1h3v-3A.5.5 0 0 1 8 4z"/>
            </svg>
            {/if}
        </div>
    </button>
    {#if open}
        <div transition:slide class="text-gray-300 px-4 pb-4 md:px-6 md:pb-6">
            <slot />
        </div>
    {/if}
</div>


<style>
    p{
        font-size: 15rem;
    }
</style>