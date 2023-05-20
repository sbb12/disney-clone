<script lang>
    import { onMount } from 'svelte';
    import Carousel from 'svelte-carousel';
    import { browser } from '$app/environment';

	import HeroCarouselItem from './HeroCarouselItem.svelte';
    import CustomDot from './CustomDot.svelte';

    // these are just hardcoded values for the sake of the demo
    const items = [
        {
        "cover":"https://prod-ripcut-delivery.disney-plus.net/v1/variant/disney/BB1BDF4F8ADD4C8E49DFDB20C8E2F9C343DC027D3DB5198D116E032C1019CEC8/scale?width=1440&aspectRatio=3.91&format=jpeg",
        "overlay":"https://prod-ripcut-delivery.disney-plus.net/v1/variant/disney/C1E5298754052334E4277C8FBAE575A44502B7D5F9F00227700DDFEFED927779/scale?width=1440&aspectRatio=3.91&format=png",
        "alt":"The Simpsons",
        "text":null
        },
        {
        "cover":"https://prod-ripcut-delivery.disney-plus.net/v1/variant/disney/1AB21E25154FE4CAEFC6FF77E37C8B5262003E7C3C438F4EDAA4ED62F36890E9/scale?width=1440&aspectRatio=3.91&format=jpeg",
        "overlay":"https://prod-ripcut-delivery.disney-plus.net/v1/variant/disney/C637B7AF44B23AB1C02E9A9E52D5A7AA0FABC0529D37EAB04EBF82B7C203B173/scale?width=1440&aspectRatio=3.91&format=png",
        "alt":"Ant-Man and the Wasp: Quantumania",
        "text":null
        },
        {
        "cover":"https://prod-ripcut-delivery.disney-plus.net/v1/variant/disney/DE325617FD38682D67E7B207B515D928FD133B4E42CE82DAC6097482CD80B560/compose?width=1440&aspectRatio=3.91&format=jpeg&label=391_scrim",
        "overlay":"https://prod-ripcut-delivery.disney-plus.net/v1/variant/disney/598278D132168A6B36B39F07B16228E34082649B19A7CF7642689588C767B909/scale?width=800&aspectRatio=1.78&format=png",
        "alt":"Avatar: The Way of Water",
        "text":"Coming to Disney+ on 7 June"
        },
        {
        "cover":"https://prod-ripcut-delivery.disney-plus.net/v1/variant/disney/67B27D4EDEF96F2A0073B8ABA9C94539DC2D27E2F3CCBE9280A04AD198698953/scale?width=1440&aspectRatio=3.91&format=jpeg",
        "overlay":"https://prod-ripcut-delivery.disney-plus.net/v1/variant/disney/A2C35874659F04F41AEA7A020D2ECD36D2278AB069872043DC303F7014A9424B/scale?width=1440&aspectRatio=3.91&format=png",
        "alt":"Avatar",
        "text":null
        },
        {
        "cover":"https://prod-ripcut-delivery.disney-plus.net/v1/variant/disney/AB9E01ED565F5B53278F0B0C9B0D0434B2AA969C41D32FCDB99E555392281999/scale?width=1440&aspectRatio=3.91&format=jpeg",
        "overlay":"https://prod-ripcut-delivery.disney-plus.net/v1/variant/disney/0580281D0B3758C45354D67CDEB282EBE31920CA118EEEE0115AE37816AE7CBD/scale?width=1440&aspectRatio=3.91&format=png",
        "alt":"Deadpool 2",
        "text":null
        },
        {
        "cover":"https://prod-ripcut-delivery.disney-plus.net/v1/variant/disney/7AE87D0DE8F8D8B744F6CA9C6E38374F84373C405131615B16056E55461379DC/compose?width=1440&aspectRatio=3.91&format=jpeg&label=staroriginal_391",
        "overlay":"https://prod-ripcut-delivery.disney-plus.net/v1/variant/disney/1041E46F1677FC2CCBFA443FF494FBC2CFE78B57DFC4F91021E318E591F28CDE/scale?width=1440&aspectRatio=3.91&format=png",
        "alt":"White Men Can't Jump",
        "text":null
        },
        {
        "cover":"https://prod-ripcut-delivery.disney-plus.net/v1/variant/disney/FF13271896E93A503EDCFD03D6936652C90A335D6B2299146D1BA3AF2A734E50/compose?width=1440&aspectRatio=3.91&format=jpeg&label=staroriginal_391_scrim",
        "overlay":"https://prod-ripcut-delivery.disney-plus.net/v1/variant/disney/13DD8B9FB4D90B2740EBDDEA960180B5DB7279D5C33F95741AA731B5E802AC93/scale?width=800&aspectRatio=1.78&format=png",
        "alt":"The Kardashians",
        "text":"Season 3 Coming on 25 MayCatch Up on the Series"
        },
        {
        "cover":"https://prod-ripcut-delivery.disney-plus.net/v1/variant/disney/E02F135A538319F0C3700B074517A2FAD6D1BDE948D349C44446BC224764D2E4/scale?width=1440&aspectRatio=3.91&format=png",
        "overlay":"https://prod-ripcut-delivery.disney-plus.net/v1/variant/disney/5B6D172D5122106A946A5BBEBFE6042BD3A6B4D5A87157C6959BBF3D8F440C6F/scale?width=1440&aspectRatio=3.91&format=png",
        "alt":"Ant-Man",
        "text":null
        },
        {
        "cover":"https://prod-ripcut-delivery.disney-plus.net/v1/variant/disney/94F760397069800B94BE9958AA809585BA28F8EA33E8724F1F40D6D918975733/scale?width=1440&aspectRatio=3.91&format=jpeg",
        "overlay":"https://prod-ripcut-delivery.disney-plus.net/v1/variant/disney/5063F6330A99ED2F48FAD35EECC7C9BAFF1E6CE7C254B9D801EB2194170F687B/scale?width=1440&aspectRatio=3.91&format=png",
        "alt":"Hummingbird",
        "text":null
        },
        {
        "cover":"https://prod-ripcut-delivery.disney-plus.net/v1/variant/disney/8DC7ACAE7A0D9ABA5820EAEB5D7DEDF1102865BFE576247CF9D7857AB9416B4E/compose?width=1440&aspectRatio=3.91&format=jpeg&label=staroriginal_391_scrim",
        "overlay":"https://prod-ripcut-delivery.disney-plus.net/v1/variant/disney/C5E5153C0B1008F56861327D3C1C69B073CF6834CFD744D275ECC41B0DE74E1B/scale?width=800&aspectRatio=1.78&format=png",
        "alt":"11. Read-a-Thon",
        "text":"New Episodes Now Streaming"
        },
        {
        "cover":"https://prod-ripcut-delivery.disney-plus.net/v1/variant/disney/3F6DBDAED587F88E512B96FE76C1CCF18BBCDE1134171BE071C5EF20760D2D76/compose?width=1440&aspectRatio=3.91&format=jpeg&label=disneyplusoriginal_391_scrim",
        "overlay":"https://prod-ripcut-delivery.disney-plus.net/v1/variant/disney/E1FA96A63566E3D65D3D1FC9FD135D2A063EECFE8B7C1E090CC9F7ECAB2ACE3E/scale?width=800&aspectRatio=1.78&format=png",
        "alt":"Ed Sheeran: The Sum of It All",
        "text":"All Episodes Now Streaming"
        },
        {
        "cover":"https://prod-ripcut-delivery.disney-plus.net/v1/variant/disney/117A5488ED0F897A6720C854267EC3ED17AA2AD5E86731559AB03C18DE9F0BF5/compose?width=1440&aspectRatio=3.91&format=jpeg&label=staroriginal_391_scrim",
        "overlay":"https://prod-ripcut-delivery.disney-plus.net/v1/variant/disney/A845CAFF722B43E8813AA90AB6A6391633F158258AAEBEFB888582FDF9A593CD/scale?width=800&aspectRatio=1.78&format=png",
        "alt":"Not Dead Yet",
        "text":"All Episodes Now Streaming"
        },
        {
        "cover":"https://prod-ripcut-delivery.disney-plus.net/v1/variant/disney/BC0986AC51377D75F9F3A139AD30783377137D015702BF09C14B5B381E479587/compose?width=1440&aspectRatio=3.91&format=jpeg&label=391_scrim",
        "overlay":"https://prod-ripcut-delivery.disney-plus.net/v1/variant/disney/B3737B1FCC2FC82D025F30374AADBBE7B45A71853FC8462AF8805E916744680F/scale?width=800&aspectRatio=1.78&format=png",
        "alt":"A Small Light",
        "text":"New Episodes Every Tuesday"
        },
        {
        "cover":"https://prod-ripcut-delivery.disney-plus.net/v1/variant/disney/8BD7C83567DFA88DFAD9917B18C46BA8C83A27A5B511CAFFEBA90A44DD598590/compose?width=1440&aspectRatio=3.91&format=jpeg&label=staroriginal_391_scrim",
        "overlay":"https://prod-ripcut-delivery.disney-plus.net/v1/variant/disney/8DDA7D88CFEF0D36DF4D69EA943FE4BC983D446B3CBDE01FFDFF4651182ED22C/scale?width=800&aspectRatio=1.78&format=png",
        "alt":"Will Trent",
        "text":"New Episode Every Wednesday"
        },
        {
        "cover":"https://prod-ripcut-delivery.disney-plus.net/v1/variant/disney/16261743A7521389FC924972CE318F36F191321747E55DC52ECE7AB96E7CD080/scale?width=1440&aspectRatio=3.91&format=png",
        "overlay":"https://prod-ripcut-delivery.disney-plus.net/v1/variant/disney/3CF089FE445C9F656DAF3D401786F113F8E207963A9EB0A4C99A6AA7BC119C45/scale?width=1440&aspectRatio=3.91&format=png",
        "alt":"Made in the UK",
        "text":null
        },
        
    ]
     
    let carousel
    
</script>

<container class="relative w-screen my-5">
    {#if browser}
        <Carousel bind:this={carousel}
            let:currentPageIndex
            let:showNextPage
            let:showPrevPage
            let:pagesCount
            let:showPage
            
            autoplay={false}
            pauseOnFocus={true}
            duration=500
            autoplayDuration=5000
            particlesToShow=1.1
            initialPageIndex=1
            >
            <div slot="prev" on:click={showPrevPage} on:keydown={showPrevPage}
                class="absolute left-0 z-30 flex items-center justify-center h-full text-gray-50 w-[4.5%] opacity-0 hover:opacity-100 transition-opacity duration-500">
                <svg xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 16 16" class="w-[50%]">
                    <path fill-rule="evenodd" d="M11.354 1.646a.5.5 0 0 1 0 .708L5.707 8l5.647 5.646a.5.5 0 0 1-.708.708l-6-6a.5.5 0 0 1 0-.708l6-6a.5.5 0 0 1 .708 0z"/>
                </svg>
            </div>
            
            {#each items as item, index}
                <HeroCarouselItem {item} {index} {currentPageIndex}/>
            {/each}
            
            <div slot="next" on:click={showNextPage} on:keydown={showNextPage}
                class="absolute right-0 z-30 flex items-center justify-center h-full text-gray-50 w-[4.5%] opacity-0 hover:opacity-100 transition-opacity duration-500">
                <svg xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 16 16" class="w-[50%]">
                    <path fill-rule="evenodd" d="M4.646 1.646a.5.5 0 0 1 .708 0l6 6a.5.5 0 0 1 0 .708l-6 6a.5.5 0 0 1-.708-.708L10.293 8 4.646 2.354a.5.5 0 0 1 0-.708z"/>
                </svg>
            </div>

            <div slot="dots" class="absolute bottom-[4%] right-[6%] flex items-center justify-center wrap space-x-1 md:space-x-2 h-2">
                {#each Array(pagesCount) as _, pageIndex (pageIndex)}
                    <CustomDot
                        active={currentPageIndex === pageIndex}
                        on:click={() => showPage(pageIndex)}
                    ></CustomDot>
                {/each}
            </div>
        </Carousel>
    {/if}
</container>



