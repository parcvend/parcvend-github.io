<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tickle My Funny Bone</title>
    <link href="https://fonts.googleapis.com/css2?family=Comic+Neue:wght@700&family=Roboto:wght@400&display=swap" rel="stylesheet">
    <style>
        /* Base Styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            line-height: 1.6;
            color: #333; /* Darker, more readable default text color */
            background: linear-gradient(135deg, #ffe082, #ffb74d); /* A softer yellow-orange gradient */
            overflow-x: hidden;
            font-family: 'Roboto', sans-serif; /* More consistent body font */
        }

        /* Navigation Styles */
        nav {
            background: #f4511e; /* A warmer orange that complements the background */
            color: white;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2); /* Slightly less intense shadow */
        }

        nav ul {
            display: flex;
            justify-content: center;
            list-style: none;
            padding: 1.2rem 0;
            max-width: 1200px;
            margin: 0 auto;
        }

        nav ul li {
            margin: 0 1.5rem; /* Slightly reduced margin */
        }

        nav ul li a {
            color: white;
            text-decoration: none;
            font-family: 'Comic Neue', cursive;
            font-size: 1.1rem; /* Slightly smaller initial size */
            text-transform: uppercase;
            transition: color 0.3s;
        }

        nav ul li a:hover,
        nav ul li a:focus { /* Adding focus state for accessibility */
            color: #ffe082; /* Lighter yellow for hover/focus */
        }

        /* Section Styles */
        section {
            min-height: 100vh;
            padding: 6rem 2rem;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            max-width: 1200px;
            margin: 2rem auto;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.08); /* Softer shadow */
            border-radius: 15px; /* Consistent border-radius */
            background-color: rgba(255, 255, 255, 0.85); /* Slightly less opaque */
        }

        #home {
            /* Specific styles for home */
        }

        #about {
            background-color: rgba(255, 193, 7, 0.75); /* A different shade of yellow */
        }

        #projects {
            /* Specific styles for projects */
        }

        #contact {
            background-color: rgba(255, 193, 7, 0.75); /* Consistent with about for now */
        }

        h1 {
            font-family: 'Comic Neue', cursive;
            font-size: 3.5rem; /* Slightly reduced size */
            color: #f4511e; /* Consistent accent color */
            margin-bottom: 1.2rem;
            text-shadow: 1px 1px #ffe082; /* Subtler text shadow */
        }

        .tickle-heading {
            display: inline-block;
            animation: bounceAndRotate 2s infinite;
        }

        h2 {
            font-family: 'Roboto', sans-serif; /* Using Roboto for better consistency */
            font-size: 2.4rem;
            color: #222;
            margin-bottom: 1rem;
        }

        p {
            max-width: 800px;
            font-size: 1.15rem; /* Slightly smaller font size */
            margin-bottom: 1.5rem;
            color: #444; /* Slightly darker text */
            line-height: 1.7;
        }

        /* Project Grid Styles */
        .project-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 1.5rem; /* Slightly reduced gap */
            max-width: 100%;
            width: 100%;
            padding: 1rem; /* Add some padding inside the grid */
        }

        .project-card {
            background: #fff;
            padding: 1.5rem; /* Reduced padding */
            border-radius: 10px; /* Consistent border-radius */
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.15); /* Softer shadow */
            transition: transform 0.3s, box-shadow 0.3s;
            border: 1px solid #f4511e; /* More subtle border */
        }

        .project-card:hover,
        .project-card:focus-within { /* Adding focus state */
            transform: scale(1.03);
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.2);
            background: #ffe082; /* Lighter yellow on hover/focus */
        }

        .project-card h3 {
            font-family: 'Comic Neue', cursive;
            color: #f4511e;
            font-size: 1.3rem;
            margin-bottom: 0.4rem;
        }

        /* Contact Links Styles */
        .contact-links {
            display: flex;
            gap: 1rem; /* Reduced gap */
            margin-top: 1rem;
        }

        .contact-links a {
            color: #f4511e;
            text-decoration: none;
            font-family: 'Comic Neue', cursive;
            font-size: 1rem; /* Slightly smaller font */
            transition: color 0.3s;
        }

        .contact-links a:hover,
        .contact-links a:focus { /* Adding focus state */
            color: #d81b60; /* Keeping a similar accent color */
        }

        /* Cartoon Character Styles - Refined */
        .cartoon-character {
            width: 100px; /* Slightly smaller */
            height: 100px; /* Slightly smaller */
            margin-bottom: 1rem;
        }

        #home .cartoon-character {
            animation: wave 3s infinite;
        }

        #about .cartoon-character {
            animation: blink 4s infinite;
        }

        #projects .cartoon-character {
            animation: bounce 2s infinite;
        }

        #contact .cartoon-character {
            animation: spin 5s infinite linear;
        }

        /* Keyframe Animations */
        @keyframes slideIn {
            from {
                opacity: 0;
                transform: translateY(50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes bounceAndRotate {
            0%, 100% {
                transform: translateY(0) rotate(0deg);
            }
            25% {
                transform: translateY(-10px) rotate(3deg);
            }
            50% {
                transform: translateY(0) rotate(0deg);
            }
            75% {
                transform: translateY(-10px) rotate(-3deg);
            }
        }

        @keyframes wave {
            0%, 100% {
                transform: rotate(0deg);
            }
            50% {
                transform: rotate(15deg);
            }
        }

        @keyframes blink {
            0%, 10%, 100% {
                transform: scaleY(1);
            }
            5% {
                transform: scaleY(0.2);
            }
        }

        @keyframes bounce {
            0%, 100% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-8px);
            }
        }

        @keyframes spin {
            0% {
                transform: rotate(0deg);
            }
            100% {
                transform: rotate(360deg);
            }
        }

        /* Large Screen Optimizations */
        @media (min-width: 1200px) {
            nav ul {
                padding: 1.5rem 0;
            }

            nav ul li a {
                font-size: 1.2rem;
            }

            section {
                padding: 8rem 3rem;
                margin: 3rem auto;
                border-radius: 20px;
            }

            h1 {
                font-size: 4rem;
            }

            h2 {
                font-size: 2.8rem;
            }

            p {
                font-size: 1.2rem;
                max-width: 900px;
            }

            .cartoon-character {
                width: 120px;
                height: 120px;
            }

            .project-grid {
                grid-template-columns: repeat(3, 1fr);
                gap: 2rem;
            }

            .project-card {
                padding: 2rem;
            }
        }

        @media (max-width: 768px) {
            nav ul {
                flex-direction: column;
                align-items: center;
            }

            nav ul li {
                margin: 0.6rem 0;
            }

            h1 {
                font-size: 2.2rem;
            }

            h2 {
                font-size: 1.8rem;
            }

            section {
                padding: 4rem 1rem;
                margin: 1rem;
            }

            .cartoon-character {
                width: 70px;
                height: 70px;
            }

            .project-grid {
                grid-template-columns: 1fr;
            }

            .project-card {
                padding: 1rem;
            }

            .project-card h3 {
                font-size: 1.4rem;
            }

            .contact-links a {
                font-size: 1rem;
            }
        }
    </style>
</head>
<body>
    <nav>
        <ul>
            <li><a href="#home">Home: The Humor Hub</a></li>
            <li><a href="#about">About the Humorist</a></li>
            <li><a href="#projects">Satirical Works</a></li>
            <li><a href="#contact">Contact the Jester</a></li>
        </ul>
    </nav>

    <section id="home">
        <svg class="cartoon-character" viewBox="0 0 100 100">
            <circle cx="50" cy="50" r="35" fill="#ffeb3b" stroke="#f4511e" stroke-width="4"/>
            <circle cx="38" cy="40" r="4" fill="#222"/>
            <circle cx="62" cy="40" r="4" fill="#222"/>
            <path d="M38 60 Q50 68 62 60" fill="none" stroke="#222" stroke-width="3"/>
            <path d="M25 25 L15 15 M75 25 L85 15 M50 15 L50 5" fill="none" stroke="#f4511e" stroke-width="3"/>
            <path d="M30 30 A15 10 0 0 0 70 30" fill="none" stroke="#d81b60" stroke-width="2"/>
        </svg>
        <h1><span class="tickle-heading">Tickle My Funny Bone</span></h1>
        <p>Prepare for a Comedy Cauldron! [Your Name] stirs up satirical takes on the daily absurdities, guaranteed to make you chuckle (or maybe snort).</p>
    </section>

    <section id="about">
        <svg class="cartoon-character" viewBox="0 0 100 100">
            <rect x="30" y="30" width="40" height="45" fill="#ffb74d" stroke="#222" stroke-width="3" rx="5"/>
            <circle cx="40" cy="40" r="5" fill="#222"/>
            <circle cx="60" cy="40" r="5" fill="#222"/>
            <path d="M40 58 Q50 65 60 58" fill="none" stroke="#222" stroke-width="3"/>
            <path d="M35 75 L30 90 M65 75 L70 90" fill="none" stroke="#222" stroke-width="3"/>
            <path d="M35 35 L25 20 M65 35 L75 20" fill="none" stroke="#222" stroke-width="2"/>
        </svg>
        <h2>About the Chief Jester</h2>
        <p>[Your Name] here, navigating the chaotic comedy of life with a keyboard and a mischievous grin. I dissect the ridiculous – from boardroom babble to influencer antics – serving up satirical slices that are both hilarious and (sometimes) a little too real. My goal is simple: to tickle your funny bone until it begs for mercy.</p>
    </section>

    <section id="projects">
        <svg class="cartoon-character" viewBox="0 0 100 100">
            <circle cx="50" cy="50" r="35" fill="#fff" stroke="#f4511e" stroke-width="4"/>
            <circle cx="38" cy="40" r="4" fill="#222"/>
            <circle cx="62" cy="40" r="4" fill="#222"/>
            <circle cx="50" cy="58" r="7" fill="#d81b60"/>
            <path d="M20 25 Q50 5 80 25" fill="none" stroke="#d81b60" stroke-width="3"/>
            <rect x="40" y="70" width="20" height="10" fill="#f4511e" rx="3"/>
        </svg>
        <h2>My Satirical Shenanigans</h2>
        <div class="project-grid">
            <div class="project-card">
                <h3>The Corporate Compost</h3>
                <p>Dive into 'The Corporate Compost,' my ongoing blog where buzzwords like 'synergy' and 'disrupt' are hilariously repurposed into fertile ground for satire. Prepare for a weekly dose of corporate comedy that's 100% organic (and slightly toxic).</p>
            </div>
            <div class="project-card">
                <h3>Absurdville Chronicles</h3>
                <p>Escape to 'Absurdville Chronicles,' a novella where common sense has packed its bags and left town. Witness the uproarious chaos as residents engage in heated debates over the optimal composting techniques in a logic-free landscape.</p>
            </div>
            <div class="project-card">
                <h3>Social Media Roast</h3>
                <p>Brace yourself for 'Social Media Roast,' a collection of sharp and silly skits that skewer the curated realities of online personalities. No filter is safe as we hilariously dissect the 'authentic' avocado toast chronicles and other influencer absurdities.</p>
            </div>
        </div>
    </section>

    <section id="contact">
        <svg class="cartoon-character" viewBox="0 0 100 100">
            <ellipse cx="50" cy="60" rx="35" ry="25" fill="#d81b60" stroke="#222" stroke-width="4"/>
            <circle cx="40" cy="40" r="5" fill="#222"/>
            <circle cx="60" cy="40" r="5" fill="#222"/>
            <path d="M40 55 Q50 60 60 55" fill="none" stroke="#222" stroke-width="3"/>
            <rect x="45" y="70" width="10" height="10" fill="#fff" rx="2"/>
            <rect x="30" y="75" width="10" height="5" fill="#fff"/>
            <rect x="60" y="75" width="10" height="5" fill="#fff"/>
        </svg>
        <h2>Throw Me a Bone</h2>
        <p>Got a comedic concept that's too ludicrous to ignore? Or perhaps a collaboration of satirical genius is brewing? Don't be shy, drop me a line and let the hilarity ensue!</p>
        <div class="contact-links">
            <a href="mailto:your.email@example.com">Email</a>
            <a href="https://github.com/yourusername" target="_blank">GitHub</a>
            <a href="https://linkedin.com/in/yourusername" target="_blank">LinkedIn</a>
        </div>
    </section>

    <script>
        // Smooth scrolling for nav links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });

        // Add a fun hover/focus effect on project cards
        document.querySelectorAll('.project-card').forEach(card => {
            card.addEventListener('mouseover', () => {
                card.style.backgroundColor = '#ffe082';
            });
            card.addEventListener('mouseout', () => {
                card.style.backgroundColor = '#fff';
            });
            card.addEventListener('focusin', () => {
                card.style.backgroundColor = '#ffe082';
            });
            card.addEventListener('focusout', () => {
                card.style.backgroundColor = '#fff';
            });
        });
    </script>
</body>
</html>
