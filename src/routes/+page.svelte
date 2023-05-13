    <script>
	import Accordion from "../lib/components/Accordion.svelte";

</script>
<bg class="bg-[#040714] fixed h-screen top-0 transition-opacity w-full z-[-3]"></bg>
<main>
    <!-- hero -->
    <section class="">

    </section>


    <section class="md:flex relative">
        <div class="px-[5vw] w-full md:w-[40%] md:absolute md:text-left h-full text-center pb-10 flex flex-col justify-center">
            <div class="">
                <h3 class="text-gray-50 text-2xl font-semibold mb-5 sm:text-3xl lg:text-[40px]">Only on Disney+</h3>
                <p class="text-gray-300 text-base md:text-lg lg:text-xl">Exclusive movies, series and originals you won't find on any other streaming service.</p>
                <div class="md:mt-[30%]"></div>
            </div>
        </div>
        <picture class="w-full">
            <source media="(min-width: 768px)" srcset="/images/original_disney.webp" />
            <img src="/images/original_disney_mobile.webp" alt="original disney content" class="w-full"/>
          </picture>
    </section>

    <section class="px-[5vw] py-[10vh] text-center">
        <h3 class="text-gray-50 text-3xl font-semibold mb-5 md:text-4xl lg:5xl">Watch the way you want</h3>
        <p class="text-gray-300 text-base md:text-xl">Enjoy the world's greatest stories - anytime, anywhere</p>
        <img src="/images/anytime_bg.webp" alt="Watch the Way you Want on a Variety of Devices shown here" class="w-full" loading="lazy">
        <ul class="grid grid-cols-1 md:grid-cols-3">
            <li>
                <img src="/images/reel.webp" alt="video reel" loading="lazy" class="mx-auto w-full">
                <h4 class="text-gray-50 font-semibold text-xl md:text-2xl lg:text-4xl m-4 md:mb-7">Endless entertainment</h4>
                <p class="text-gray-300 text-lg md:text-xl mb-4">Explore thousands of hours of TV series, movies and originals.</p>
            </li>
            <li>
                <img src="/images/multiple_devices.webp" alt="multiple devices" loading="lazy" class="mx-auto w-full">
                <h4 class="text-gray-50 font-semibold text-xl md:text-2xl lg:text-4xl m-4 md:mb-7">Available on your favourite devices</h4>
                <p class="text-gray-300 text-lg md:text-xl mb-4">Stream on up to four screens at once on compatible devices.</p>
            </li>
            <li>
                <img src="/images/kids_icon.webp" alt="kids icon" loading="lazy" class="mx-auto w-full">
                <h4 class="text-gray-50 font-semibold text-xl md:text-2xl lg:text-4xl m-4 md:mb-7">Easy-to-use parental controls</h4>
                <p class="text-gray-300 text-lg md:text-xl mb-4">Keep your family safe with our intuitive parental controls.</p>
            </li>
        </ul>

    </section>

    <section class="px-[5vw] py-[10vh]">
        <h3 class="text-gray-50 text-3xl md:text-4xl lg:5xl font-semibold text-center mb-5">Frequently Asked Questions</h3>
        <Accordion title={'What is Disney+?'}>
            <p class="pb-4 md:pb-6">Disney+ is the streaming home for entertainment from Disney, Pixar, Marvel, Star Wars, National Geographic, Star and more.</p>
            <p class="pb-4 md:pb-6">Disney+ has a number of benefits included in the standard subscription price:</p>
            <ul class="list-outside list-disc pl-10 space-y-2 pb-4">
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
            <ul class="list-outside list-disc pl-10 space-y-2 pb-4">
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
            <p class="pb-4 md:pb-6">You can also purchase a Disney+ annual subscription for someone else as a gift, <a href="/welcome/gift-subscription" class="text-gray-50 underline">here.</a></p>
            <p class="pb-4 md:pb-6">*savings compared to 12 months of the monthly price.</p>
        </Accordion>

        <Accordion title={"What devices are supported?"}>
            <p class="pb-4 md:pb-6">
                Disney+ supports mobile devices, web browsers, game consoles, set-top boxes, and smart TVs. Click <a href="https://help.disneyplus.com/csp?id=csp_article_content&article=devices-supported" class="text-gray-50 underline">here</a> for the full list.
            </p>
        </Accordion>

        <Accordion title={"Is there any commitment when signing up for Disney+?"}>
            <p class="pb-4 md:pb-6">There are no commitments and you can cancel at any time, effective at the end of your current payment period. Just follow the below 5 easy steps:</p>
            <ul class="list-outside list-decimal pl-10 space-y-2 pb-4">
                <li>Go to www.disneyplus.com and log in</li>
                <li>Select your Profile</li>
                <li>Select Account</li>
                <li>Select Cancel Subscription</li>
                <li>Select Complete Cancellation to confirm</li>
            </ul>
            <p class="pb-4 md:pb-6">For more information click <a href="https://help.disneyplus.com/csp?id=csp_article_content&article=cancel" target="_blank" class="text-gray-50 underline">here.</p>
        </Accordion>

    </section>

    <section class="px-[5vw] py-[10vh] overflow-hidden">
        <h3 class="text-gray-50 text-3xl font-semibold text-center mb-5 md:text-4xl">Available on your favourite devices</h3>
        <ul class="grid grid-cols-2 md:grid-cols-4 items-start">
            <li class="flex flex-col justify-center text-center">
                <img src="/images/tv.webp" alt="tv" class="" loading="lazy">
                <h3 class="text-gray-50 text-xl sm:text-2xl lg:text-3xl my-3 font-semibold px-2">TV</h3>
                <ul class="text-gray-300">
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
                <h3 class="text-gray-50 text-xl sm:text-2xl lg:text-3xl my-3 font-semibold px-2 ">Computer</h3>
                <ul class="text-gray-300">
                    <li>Chrome OS</li>
                    <li>MacOS</li>
                    <li>Windows PC</li>
                </ul>
            </li>
            <li class="flex flex-col justify-center text-center">
                <img src="/images/mobile.webp" alt="" loading="lazy">
                <h3 class="text-gray-50 text-xl sm:text-2xl lg:text-3xl my-3 font-semibold px-2">Mobile & Tablet</h3>
                <ul class="text-gray-300">
                    <li>Amazon Fire Tablets</li>
                    <li>Android Phones & Tablets</li>
                    <li>iPhone and iPad</li>
                </ul>    
            </li >
            <li class="flex flex-col justify-center text-center">
                <img src="/images/console.webp" alt="" loading="lazy">
                <h3 class="text-gray-50 text-xl sm:text-2xl lg:text-3xl my-3 font-semibold px-2">Game Consoles</h3>
                <ul class="text-gray-300">
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
