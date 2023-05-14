<script lang="ts">
	import LandingNavbar from "../lib/components/LandingNavbar.svelte";
    import Accordion from "../lib/components/Accordion.svelte";

    //signup form
    let email = "";
    let formError = '';

    function scrollIntoView(id:string) {
        const el = document.getElementById(id);
        if (!el) return;
        el.scrollIntoView({
            behavior: 'smooth'
        });
    }

</script>

<bg class="bg-[#040714] fixed h-screen top-0 transition-opacity w-full z-[-3]"></bg>
<main>
    <LandingNavbar />

    <!-- hero -->
    <section class="relative lg:flex lg:items pt-[50vw] pb-[20vw] md:pt-[40vw] px-[5vw] md:pb-[10vw] lg:p-[5.6vw] min-h-screen bg-no-repeat lg:bg-cover bg-[size:100%] bg-top w-screen lg:min-h-screen bg-[url('/images/landing_bg_sm.webp')] md:bg-[url('/images/landing_bg_md.webp')] lg:bg-[url('/images/landing_bg_lg.webp')]">
        <div class="text-center my-auto max-w-[500px] md:max-w-[600px] lg:max-w-[50%] lg:text-left lg:w-[50%] lg:space-y-5 mx-auto lg:mx-0 lg:mr-auto">
            <img src="/images/logo.svg" alt="disney plus logo" class="w-32 mx-auto lg:mx-0 md:w-40 lg:w-44" loading="lazy">
            <h1 class="font-semibold text-left text-gray-50 drop-shadow-lg shadow-black text-shadow-lg w-fit text-[26px] mb-7 md:text-[32px] lg:text-[40px] lg:leading-[54px] mx-auto lg:mx-0">+ More than you'd ever imagine</h1>
            <p class="mb-5 text-base text-gray-300 shadow-black text-shadow-lg md:text-lg lg:text-xl">Enter your email to create or restart your subscription</p>
            <form action="" class="flex flex-col py-2 pace-y-2 md:flex-row">
                <div class="w-full mb-2 md:mb-0">
                    <label for="email" class="hidden">Enter email to (re)start your subscription</label>
                    <input type="text" name="email" placeholder="Email" class="w-full bg-[#31343e] focus:outline-none md:text-lg lg:text-xl text-gray-300 px-4 py-2 rounded-sm md:rounded-none md:rounded-l h-12  {formError? 'border border-red-500' : ''}">
                    {#if formError}
                        <p class="text-red-500">{formError}</p>
                    {/if}
                </div>
                <button class="bg-[#0063e5] text-gray-50 px-10 py-2 rounded-sm md:rounded-none md:rounded-r h-12 !m-0" on:click|preventDefault >CONTINUE</button>
            </form>
            <p class="text-base text-gray-300 mb md:text-lg lg:text-xl">Get 12 months for the price of 10 when you sign up for an annual Disney+ subscription, compared to paying monthly.</p>
            <button class="absolute z-10 text-gray-300 bottom-8 lg:bottom-10 animate-bounce" on:click|preventDefault={()=>{scrollIntoView('exclusives')}}>
                <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="rgb(209 213 219)" class="scale-150" viewBox="0 0 16 16">
                    <path fill-rule="evenodd" d="M1.646 4.646a.5.5 0 0 1 .708 0L8 10.293l5.646-5.647a.5.5 0 0 1 .708.708l-6 6a.5.5 0 0 1-.708 0l-6-6a.5.5 0 0 1 0-.708z"/>
                  </svg>
            </button>
        </div>
    </section>

    <!-- Disney exclusive -->
    <section class="py-[5vh] md:py-0 md:flex relative overflow-hidden" id="exclusives">
        <div class="px-[5vw] w-full md:w-[40%] md:absolute md:text-left h-full text-center pb-10 flex flex-col justify-center">
            <div class="">
                <h3 class="text-gray-50 font-semibold mb-5 text-2xl sm:text-3xl lg:text-[40px] md:w-fit md:mr-auto">Only on Disney+</h3>
                <p class="text-base text-gray-300 md:text-lg lg:text-xl">Exclusive movies, series and originals you won't find on any other streaming service.</p>
                <div class="md:mt-[30%]"></div>
            </div>
        </div>
        <picture class="w-full">
            <source media="(min-width: 768px)" srcset="/images/original_disney.webp" />
            <img src="/images/original_disney_mobile.webp" alt="original disney content" class="w-full"/>
          </picture>
    </section>

    <!-- your way -->
    <section class="px-[5vw] py-[10vh] text-center overflow-hidden">
        <h3 class="text-gray-50  font-semibold mb-5 text-2xl md:text-3xl lg:text-[40px]">Watch the way you want</h3>
        <p class="text-base text-gray-300 md:text-xl">Enjoy the world's greatest stories - anytime, anywhere</p>
        <img src="/images/anytime_bg.webp" alt="Watch the Way you Want on a Variety of Devices shown here" class="w-full" loading="lazy">
        <ul class="grid grid-cols-1 md:grid-cols-3">
            <li>
                <img src="/images/reel.webp" alt="video reel" loading="lazy" class="w-full mx-auto">
                <h4 class="m-4 text-xl font-semibold text-gray-50 md:text-2xl lg:text-4xl md:mb-7">Endless entertainment</h4>
                <p class="mb-4 text-lg text-gray-300 md:text-xl">Explore thousands of hours of TV series, movies and originals.</p>
            </li>
            <li>
                <img src="/images/multiple_devices.webp" alt="multiple devices" loading="lazy" class="w-full mx-auto">
                <h4 class="m-4 text-xl font-semibold text-gray-50 md:text-2xl lg:text-4xl md:mb-7">Available on your favourite devices</h4>
                <p class="mb-4 text-lg text-gray-300 md:text-xl">Stream on up to four screens at once on compatible devices.</p>
            </li>
            <li>
                <img src="/images/kids_icon.webp" alt="kids icon" loading="lazy" class="w-full mx-auto">
                <h4 class="m-4 text-xl font-semibold text-gray-50 md:text-2xl lg:text-4xl md:mb-7">Easy-to-use parental controls</h4>
                <p class="mb-4 text-lg text-gray-300 md:text-xl">Keep your family safe with our intuitive parental controls.</p>
            </li>
        </ul>

    </section>
    
    <!-- FAQ -->
    <section class="px-[5vw] py-[10vh] overflow-hidden">
        <h3 class="text-gray-50 text-2xl md:text-3xl lg:text-[40px] font-semibold text-center mb-5">Frequently Asked Questions</h3>
        <Accordion title={'What is Disney+?'}>
            <p class="pb-4 md:pb-6">Disney+ is the streaming home for entertainment from Disney, Pixar, Marvel, Star Wars, National Geographic, Star and more.</p>
            <p class="pb-4 md:pb-6">Disney+ has a number of benefits included in the standard subscription price:</p>
            <ul class="pb-4 pl-10 space-y-2 list-disc list-outside">
                <li>Exclusive Originals you can’t see anywhere else, blockbuster movies, bingeable shows, snackable shorts, and inspiring documentaries</li>
                <li>Unlimited downloads on up to 10 devices and up to 7 different profiles</li>
                <li>4K UHD streaming with Dolby Vision and Dolby Atmos support on compatible devices for no extra cost</li>
                <li>A robust parental controls system including dedicated profiles for children</li>
                <li>Up to 4 screens can stream simultaneously</li>
                <li>Host virtual viewing parties for up to 5 personal friends with Groupwatch</li>
            </ul>
        </Accordion>

        <Accordion title={'What can I watch on Disney+?'}>
            <p class="pb-4 md:pb-6">With thousands of films and series from the greatest storytellers around the globe and more added each month, you will always find something to watch on Disney+</p>
            <ul class="pb-4 pl-10 space-y-2 list-disc list-outside">
                <li>Timeless classics and recent hits from Walt Disney Animation Studios like Encanto and live-action blockbusters such as Jungle Cruise</li>
                <li>Heart-warming storytelling for all ages from the masterminds at Pixar including Lightyear - the definitive origin story of Buzz Lightyear, the hero who inspired the toy</li>
                <li>Experience the Marvel Cinematic Universe with box office hits like Thor: Love and Thunder and Doctor Strange in the Multiverse of Madness. Stream must-see exclusive Original series like Loki, She-Hulk, Moon Knight and more</li>
                <li>Travel to a galaxy far, far away to relive the entire Skywalker Saga or stream exclusive live-action Star Wars series such as The Mandalorian, Obi-Wan Kenobi and Andor</li>
                <li>Open your eyes to the beauty of our planet with fearless National Geographic explorers and a number of insightful documentaries</li>
                <li>Bingeable series that everyone is talking about like the exclusive final season of the global phenomenon The Walking Dead or follow the world's most famous family in The Kardashians</li>
            </ul>
        </Accordion>

        <Accordion title={"How much does Disney+ cost?"}>
            <p class="pb-4 md:pb-6">Disney+ subscription costs £7.99 a month. Alternatively, save 16%* with the annual subscription at £79.90 a year and get 12 months for the price of 10.</p>
            <p class="pb-4 md:pb-6">You can also purchase a Disney+ annual subscription for someone else as a gift, <a href="/welcome/gift-subscription" class="underline text-gray-50">here.</a></p>
            <p class="pb-4 md:pb-6">*savings compared to 12 months of the monthly price.</p>
        </Accordion>

        <Accordion title={"What devices are supported?"}>
            <p class="pb-4 md:pb-6">
                Disney+ supports mobile devices, web browsers, game consoles, set-top boxes, and smart TVs. Click <a href="https://help.disneyplus.com/csp?id=csp_article_content&article=devices-supported" class="underline text-gray-50">here</a> for the full list.
            </p>
        </Accordion>

        <Accordion title={"Is there any commitment when signing up for Disney+?"}>
            <p class="pb-4 md:pb-6">There are no commitments and you can cancel at any time, effective at the end of your current payment period. Just follow the below 5 easy steps:</p>
            <ul class="pb-4 pl-10 space-y-2 list-decimal list-outside">
                <li>Go to www.disneyplus.com and log in</li>
                <li>Select your Profile</li>
                <li>Select Account</li>
                <li>Select Cancel Subscription</li>
                <li>Select Complete Cancellation to confirm</li>
            </ul>
            <p class="pb-4 md:pb-6">For more information click <a href="https://help.disneyplus.com/csp?id=csp_article_content&article=cancel" target="_blank" class="underline text-gray-50">here.</p>
        </Accordion>

    </section>

    <!-- available on devices -->
    <section class="px-[5vw] py-[10vh] overflow-hidden" id="available-device-section">
        <h3 class="">Available on your favourite devices</h3>
        <ul class="grid items-start grid-cols-2 md:grid-cols-4">
            <li class="flex flex-col justify-center text-center">
                <img src="/images/tv.webp" alt="tv" loading="lazy">
                <h3 class="px-2 text-xl md:text-2xl">TV</h3>
                <ul>
                    <li>Amazon Fire Tv</li>
                    <li>Android Tv devices</li>
                    <li>AppleTV</li>
                    <li>Chromecast</li>
                    <li>LG TVs</li>
                    <li>Roku</li>
                    <li>Samsung</li>
                    <li>Sky Q</li>
                    <li>Panasonic</li>
                </ul>
            </li>
            <li class="flex flex-col justify-center text-center">
                <img src="/images/laptop.webp" alt="laptop" loading="lazy">
                <h3 class="px-2">Computer</h3>
                <ul>
                    <li>Chrome OS</li>
                    <li>MacOS</li>
                    <li>Windows PC</li>
                </ul>
            </li>
            <li class="flex flex-col justify-center text-center">
                <img src="/images/mobile.webp" alt="" loading="lazy">
                <h3 class="px-2">Mobile & Tablet</h3>
                <ul>
                    <li>Amazon Fire Tablets</li>
                    <li>Android Phones & Tablets</li>
                    <li>iPhone and iPad</li>
                </ul>    
            </li >
            <li class="flex flex-col justify-center text-center">
                <img src="/images/console.webp" alt="" loading="lazy">
                <h3 class="px-2">Game Consoles</h3>
                <ul>
                    <li>PS4</li>
                    <li>PS5</li>
                    <li>Xbox One</li>
                    <li>Xbox Series X</li>
                    <li>Xbox Series S</li>
                </ul>
            </li>
        </ul>
    </section>
</main>

<style lang="postcss">
    h3{
        @apply text-gray-50 font-semibold mb-5 text-center text-2xl sm:text-3xl lg:text-[40px]
    }
    
    #available-device-section ul{
       @apply text-gray-300
    }
</style>