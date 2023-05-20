<script lang="ts">
    import { fade, fly } from "svelte/transition";
    export let item: {cover: string, overlay:string, alt: string, text: string|null};   
    export let index: number;
    export let currentPageIndex: number;
    $: active = currentPageIndex === index;
    

</script>

<item class="relative {active ? '' : 'brightness-50' } p-1 translate-x-[5%] w-screen shadow-[0_35px_60px_-15px_rgba(0,0,0,0.3)] ">
    <img src="{item.cover}" draggable="false" alt="{item.alt}" class="bg-[rgba(0,0,0,0.5)] w-screen rounded "/>
    
    {#if active}
        {#if item.text}
            <div in:fly="{{x:100, duration:1000, delay:1000}}" out:fade="{{delay: 100}}" class="absolute top-[15%] left-[6.5%] w-[25%] ">
                <img src="{item.overlay}" alt="{item.alt}" class="w-full">
            </div>
            <h4 transition:fade="{{duration:1000, delay:1500}}" class="absolute bottom-[20%] left-[6.5%] text-gray-50">
                {item.text}
            </h4>
        {:else}
            <div in:fly="{{x:100, duration:1000, delay:1000}}" out:fade class="absolute top-0 left-0 h-[50%] ">
                <img src="{item.overlay}" alt="{item.alt}" class="w-full">
            </div>
        {/if}
    {/if}

</item>
    