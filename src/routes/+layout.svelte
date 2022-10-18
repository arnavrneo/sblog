<script>
    import '../tailwind.css';
    import Nav from '../components/Nav.svelte';
    import { MY_TWITTER_HANDLE, MY_YOUTUBE, REPO_URL, SITE_TITLE } from '$lib/siteConfig';
    import { onMount } from 'svelte';

    // Getting The Current Date & Time And Setting It
    let currentDateTime = new Date();

    onMount(() => {
        const interval = setInterval(() => {
            currentDateTime = new Date();
        }, 1000);

        return () => {
            clearInterval(interval);
        };
    });

    function getWeekDay(c) {
        let daysList = [
            "Sunday",
            "Monday",
            "Tuesday",
            "Wednesday",
            "Thursday",
            "Friday",
            "Saturday"
        ];
        return daysList[c.getUTCDay()];
    }
    function getMonth(c) {
        let monthsList = [
            "January",
            "February",
            "March",
            "April",
            "May",
            "June",
            "July",
            "August",
            "September",
            "October",
            "November",
            "December"
        ];
        return monthsList[c.getUTCMonth()];
    }
    function getDate(c) {
        return c.getUTCDate();
    }
    function getHour(c) {
        return c.getUTCHours() % 12 || 12;
    }
    function getMinute(c) {
        return c.getUTCMinutes() < 10 ? "0" + c.getUTCMinutes() : c.getUTCMinutes();
    }
    function getMeridiem(c) {
        return c.getUTCHours() < 12 ? "AM" : "PM";
    }
    function getSeconds(c) {
        return c.getUTCSeconds();
    }
</script>

<svelte:head>
    <link rel="alternate" type="application/rss+xml" title={'RSS Feed for ' + SITE_TITLE}
		href="/rss.xml"
	/>
</svelte:head>

<div class="flex flex-col justify-center bg-gray-50 px-4 dark:bg-[#111111] sm:px-8">
	<Nav />
</div>
<main class="flex flex-col justify-center bg-gray-50 px-4 dark:bg-[#111111] sm:px-8">
	<slot />
</main>

<footer class="mx-auto mb-8 flex w-full max-w-2xl flex-col items-start justify-center dark:bg-[#282828]">
	<hr class="border-1 mb-8 w-full border-gray-200 dark:border-gray-800" />
	<div class="grid w-full max-w-2xl grid-cols-1 gap-4 px-4 pb-16 sm:grid-cols-2 sm:px-8">
		<div class="flex flex-col space-y-4">
			<a class="text-gray-500 transition hover:text-gray-300" href="/">Home</a>
			<a class="text-gray-500 transition hover:text-gray-300" href="/about">About</a>
		</div>
		<div class="flex flex-col space-y-4">
			<a
				class="text-gray-500 transition hover:text-gray-300"
				target="_blank"
				rel="noopener noreferrer"
				href={REPO_URL}
			>
				GitHub
			</a>
		</div>
	</div>
	<p class="prose px-4 dark:prose-invert sm:px-8">
		<small>&copy; Copyright 2022, Cosmos</small>
		<br/><br/>
	International Space Station Time now: <br/>	
        <span class="date">{getWeekDay(currentDateTime).substr(0, 3)} {getMonth(currentDateTime).substr(0, 3)} {getDate(currentDateTime)}</span><br/>
        <span class="time">{getHour(currentDateTime)}:{getMinute(currentDateTime)}:{getSeconds(currentDateTime)} {getMeridiem(currentDateTime)}</span>
	</p>
</footer>
