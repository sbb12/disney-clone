<script>
    /**
     * Indicates if dot is active
     */
    export let active = false
</script>

<button
    class="h-1 w-1 sm:h-[6px] sm:w-[6px] bg-gray-300 rounded-full cursor-pointer opacity-80 sc-carousel-dot__dot transition-all
    {active? 'h-[6px] w-[6px] sm:h-2 sm:w-2 opacity-100 bg-gray-50' : ''}"
    on:click
></button>
  

  