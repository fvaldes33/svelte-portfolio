<svelte:head>
    <title>Work | Franco Valdes | Full Stack Developer | Charlotte NC</title>
    <meta property="og:title" content="Work | Franco Valdes | Full Stack Developer | Charlotte NC" />
    <meta property="og:description" content="I am a full stack developer (for hire), husband and dog dad living in Charlotte, NC." />
    <meta property="og:type" content="website" />
    <meta property="og:url" content="http://francovaldes.dev/work" />
    <meta property="og:image" content="favicon/icon.png" />
</svelte:head>

<style>
    .work {
        display: flex;
        flex-wrap: wrap;
        justify-content: flex-start;
        height: 100%;
        width: 100%;
        max-width: 1440px;
        margin: 0 auto;
        padding: 20vh 0;
    }
    .work__back {
		position: fixed;
		top: 16px;
		left: 16px;
		z-index: 999;
	}
	.work__back svg {
    	fill: currentColor;
	}
    .work_list {
        flex-basis: 33%;
        list-style-type: none;
        position: relative;
        padding: 0 20px;
        min-width: 400px;
    }
    .work_list > li.heading {
        font-size: 48px;
        line-height: 1;
        color: rgba(0, 0, 0, 0.25);
        margin-bottom: 24px;
    }
    .work_list li {
        font-size: 36px;
    }
    .work_list li a {
        text-decoration: none;
    }
</style>
<div class="work">
    <a href="/" class="work__back">
        <svg width="60px" height="60px" version="1.1" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
            <g>
                <path
                    d="m31.262 53c-1.6562-1.6562-1.6562-4.3438 0-6l27-27v15l-13.5 13.5c-0.82812 0.82812-0.82812 2.1719 0 3l13.5 13.5v15z" />
                <path d="m69.98 42.5v15h-12.148l-6.793-6.793c-0.39062-0.39062-0.39062-1.0234 0-1.4141l6.793-6.793z" />
            </g>
        </svg>
    </a>
    <ul class="work_list">
        <li class="heading">Union</li>
        <li><a href="https://union.co" title="Union" target="_blank" rel="noopener noreferrer">Union</a></li>
        <li><a href="https://www.charlottesgotalot.com" title="Charlottes Got a lot" target="_blank"
                rel="noopener noreferrer">Charlottes Got A Lot</a></li>
        <li><a href="https://www.nascarhall.com" title="Nascar Hall" target="_blank" rel="noopener noreferrer">Nascar Hall
                of Fame</a></li>
        <li><a href="https://www.autobell.com" title="Autobell Car Wash" target="_blank" rel="noopener noreferrer">Autobell
                Car Wash</a></li>
        <li><a href="https://science.discoveryplace.org" title="Discovery Place" target="_blank"
                rel="noopener noreferrer">Discovery Place</a></li>
    </ul>
    <ul class="work_list">
        <li class="heading">Freelance</li>
        <li><a href="https://www.gymjournalapp.com" title="Gym Journal App" target="_blank" rel="noopener noreferrer">Gym
                Journal App</a></li>
        <li><a href="https://www.blackstoneshooting.com" title="Blackstone Shooting" target="_blank"
                rel="noopener noreferrer">Blackstone Shooting</a></li>
        <li><a href="https://toscomusic.org" title="Tosco Music" target="_blank" rel="noopener noreferrer">Tosco Music</a>
        </li>
    </ul>
    <ul class="work_list">
        <li class="heading">Open Source</li>
        <li><a href="https://github.com/unionco/cra11y" title="Cra11y" target="_blank" rel="noopener noreferrer">Cra11y</a></li>
        <li><a href="https://github.com/unionco/calendarize" title="Calendarize" target="_blank" rel="noopener noreferrer">Craft Calendarize</a></li>
        <li><a href="https://github.com/fvaldes33/enhanced-element-links" title="Element Links" target="_blank" rel="noopener noreferrer">Craft Element Links</a></li>
        <li><a href="https://github.com/unionco/craft-super-button" title="Super Button" target="_blank" rel="noopener noreferrer">Craft Super Button</a></li>
        <li><a href="https://twohands.fvaldes33.now.sh" title="Two hands game" target="_blank" rel="noopener noreferrer">Twohands RPS</a></li>
        <li><a href="https://www.geobarriers.io" title="Geobarriers" target="_blank" rel="noopener noreferrer">Geobarriers</a></li>
    </ul>
</div>
