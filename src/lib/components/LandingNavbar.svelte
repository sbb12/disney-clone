<script lang="ts">
    import { fade } from "svelte/transition";
    
    let open:boolean = false;    
    let scrollY: number 
    $: scrollY && scrollY > 0 ? open = true : open = false

</script>

<svelte:window bind:scrollY />

<nav class="fixed top-0 left-0 z-50 w-full py-3" >
    {#if open}
        <bg class="absolute top-0 left-0 bg-[#040714] h-full w-full z-[-1]" transition:fade/>
    {/if}

    <ul class="inline-flex items-center w-full space-x-2 lg:space-x-3 pl-[5vw] pr-[2vw]">
        {#if open}
            <li class="mr-auto"  transition:fade>
                <a href="/">
                    <img src="/images/logo.svg" alt="disney logo" class="w-16 md:w-20">
                </a>
            </li>
            <li>
                <button class="bg-[#0063e5]"  transition:fade>
                    <a href="/signup">
                        SIGN UP NOW
                    </a>
                </button>
            </li>
        {/if}
        <li class="ml-auto" >
            <button class="bg-[#040714] border border-gray-50">
                <a href="/login">
                    LOG IN
                </a>
            </button>
        </li>
    </ul>
</nav>


<style lang="postcss">
    button {
        @apply text-gray-50 rounded px-2 md:px-5 h-10 md:h-12 text-sm sm:text-base md:text-xl tracking-wide
    }
</style>