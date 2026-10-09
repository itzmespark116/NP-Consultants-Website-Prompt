# NP Consultants Website - Prompt
---


## Pre-Prompt
---

### References 

![Reference Image #01](Steel%20Structure%20Reference%20Drawing.jpg)


### Pre-Prompt 

- Make a website for a Structural Enginnering Company named "NP Consultants"
- The website must be in a structured file format as following

    ```
    Website/
    ├── index.html                  # Redirects to /home/
    ├── readme.md
    ├── home/index.html
    ├── lander/index.html
    ├── 404/index.html
    ├── <page>/index.html           # Other pages and files
    ├── admin/index.html            # Local editor
    │
    └── resources/
        ├── css/
        │   ├── root.css
        │   ├── body.css
        │   ├── nav.css
        │   ├── footer.css
        │   ├── buttons/...
        │   └── ...
        ├── js/
        │   ├── theme-init.js
        │   ├── theme-toggle.js
        │   └── ...
        ├── img/
        │   ├── team/...
        │   ├── placeholders/
        │   │   ├── project-light.jpg
        │   │   ├── project-dark.jpg
        │   │   ├── profile-light.jpg
        │   │   ├── profile-dark.jpg
        │   │   └── ...
        │   └── ...
        ├── icons/
        │   ├── dark-mode.svg
        │   ├── light-mode.svg
        │   ├── facebook.svg
        │   ├── instagram.svg
        │   ├── telephone.svg
        │   ├── location.svg
        │   ├── mail.svg
        │   ├── submit.svg
        │   └── ...
        ├── vid/...
        ├── data/...                # JSON files
        └── ...
    ```

- The website Include 4 pages as
    - home
        - banner - [Information](#homepage--banner)
        - about us - [Information](#homepage--about-us)
        - our services - [Information](#homepage--our-services)
        - our projects (Breif - Introduce to the page) - [Information](#homepage--our-projects)
        - our team - [Information](#homepage--our-team)
        - Contact us (A little text and a button to the contact page) - [Information](#homepage---contact-us)
    - services
    - projects
    - contact



---

## Rules to implement on every file
- Use a systemwise, clear and simple code with clarity with human-style writing to make it easier to understand
- for every file use a header kind of thing with the character ─ for eample (The Following CSS example),
    ```css
    /* ────────────────────────────────────────────────────────────────────── */
    /* ──────────────────────────── Project Name ──────────────────────────── */
    /* ────────────────────────────── root.css ────────────────────────────── */
    /* ────────────────────────────────────────────────────────────────────── */
    ```
    The character ─ is repeated 80 times per line, with overlays of the texts perfectly or rounded offly centered. 
    Each like is converted into a comment line by line afterwards.
- If it is a file which requires its own way to implement the feature of it, include a comment after the heading of example codes with breif explainations. Example,
    ```js
    // <button id="ThemeToggle"></button>
    // The Theme Toggle button : Require to add the id to implement

    // <nav></nav>
    // Only <nav> is required to implement, Written the contents using InnerHTML

    // ...
    ```
- Before submission of a file, add the file to the file sturcture in the readme.md

---

## CSS
- keep the code minimalistic and systematc with the systematic file structure.
- Use root.css to store color pallettes, font sizes, border-radius, transition ime, etc.
    - for root.css
        - use `:root`, `:root.light` & `:root.dark`
        - add the dark color palettes to the `:root` with the `border-radius`, etc.
        - instead of using seperate colors for gradients, use vars from the colors assigned earlier.
        - for colors use,
            - `--base`
            - `--color`
            - `--color-mute`
            - `--background`
            - `--accent`
            - etc...
        - for font-sizes, (Try to use rem more often than others)
            - `font-large`
            - `font-medium`
            - `font-small`
            - ...
        - for border-radius,
            - `border-radius-small`
            - `border-radius-medium`
            - `border-radius-large`
            - ...
        - for margins, gaps, paddings, etc, use (consider n as the element)
            - `n-small`
            - `n-medium`
            - `n-large`
        - example basic `root.css` file

            ```css
            /* ──────────────────────────────────────────────────────────────────────────────── */
            /* ──────────────────────────────── NP Consultants ──────────────────────────────── */
            /* ─────────────────────────────────── root.css ─────────────────────────────────── */
            /* ──────────────────────────────────────────────────────────────────────────────── */
            /* Theme  : :root and :root.dark hold the dark palette and every shared token.  */
            /* :root.light only overrides what changes (colors, glass, shadows, tint).      */
            /* Toggle : add the class "light" or "dark" to <html> (see theme-init.js).      */
            /* Use    : var(--name) everywhere. Never hardcode a color, size or timing.     */
            /* Size   : n-small / n-medium / n-large (gap, padding, margin, border-radius). */

            :root,
            :root.dark {
                /* Colors (dark palette) */
                color-scheme          : dark;
                --base                : #000000;
                --background          : #000000;
                --color               : #f4f5f8;
                --color-mute          : #9ca3af;
                --accent              : #4077ee;
                --border              : rgba(255, 255, 255, 0.12);

                /* Glass */
                --glass               : rgba(255, 255, 255, 0.06);
                --glass-strong        : rgba(24, 24, 28, 0.82);
                --glass-edge          : inset 0 1px 0 rgba(255, 255, 255, 0.08);
                --glass-drop          : 0 8px 24px -8px rgba(0, 0, 0, 0.55);
                --glass-blur          : blur(14px) saturate(140%);
                --glass-rim           : 0 0 8px rgba(0, 0, 0, .015), 0 2px 6px rgba(0, 0, 0, .04),
                    inset 3px 3px .5px -3.5px rgba(255, 255, 255, .045), inset -3px -3px .5px -3.5px rgba(255, 255, 255, .425),
                    inset 1px 1px 1px -.5px rgba(255, 255, 255, .3), inset -1px -1px 1px -.5px rgba(255, 255, 255, .3),
                    inset 0 0 6px 6px rgba(255, 255, 255, .06), inset 0 0 2px 2px rgba(255, 255, 255, .03),
                    0 0 12px rgba(0, 0, 0, .075);

                /* Shadows */
                --shadow-small        : 0 6px 18px rgba(0, 0, 0, 0.35);
                --shadow-large        : 0 22px 48px rgba(0, 0, 0, 0.6);

                /* Banner and gradients (built from the colors above) */
                --banner-tint         : rgba(0, 0, 0, 0.7);
                --banner-fade         : linear-gradient(180deg, var(--base), transparent 20% 96%, var(--base));
                --splitter            : linear-gradient(90deg, transparent, var(--color) 3% 95%, transparent);

                /* Fonts */
                --font-family         : system-ui, -apple-system, "Segoe UI", sans-serif;
                --font-small          : 0.9rem;
                --font-medium         : clamp(1rem, 1.2vw, 1.15rem);
                --font-large          : clamp(1rem, 1.5vw, 1.3rem);
                --font-xlarge         : clamp(2rem, 4vw, 3.2rem);
                --font-weight-light   : 300;
                --font-weight-normal  : 400;
                --font-weight-bold    : 600;
                --line-height-tight   : 1;
                --line-height-base    : 1.85;
                --letter-spacing      : 0.01em;

                /* Border radius */
                --border-radius-small : 0.25rem;
                --border-radius-medium: 0.5rem;
                --border-radius-large : 1rem;

                /* Gaps */
                --gap-xsmall          : 0.5rem;
                --gap-small           : clamp(0.875rem, 1.8vw, 1.5rem);
                --gap-medium          : clamp(1.75rem, 5vw, 3rem);
                --gap-large           : clamp(2rem, 4vw, 4rem);

                /* Paddings */
                --padding-xsmall      : 0.625rem;
                --padding-small       : clamp(1rem, 2.2vw, 1.75rem);
                --padding-medium      : clamp(1.5rem, 5vw, 3.75rem);
                --padding-large       : clamp(2rem, 6vw, 5rem);

                /* Margins */
                --margin-small        : 0.375rem;
                --margin-medium       : clamp(2rem, 5vw, 3.5rem);

                /* Motion */
                --ease                : cubic-bezier(0.4, 0, 0.2, 1);
                --transition-small    : 0.35s;
                --transition-large    : 0.8s;
                --stagger             : 0.1s;
                --offset-small        : 1.5rem;
                --offset-large        : 2.5rem;
                --zoom-small          : 1.08;
                --zoom-large          : 1.18;
                --dim                 : 0.6;

                /* Layout */
                --grid-height-large   : 25rem;
                --grid-height-medium  : 14rem;
                --grid-height-small   : 10rem;
            }

            /* ───────────────────────────────── Light Theme ────────────────────────────────── */

            :root.light {
                color-scheme          : light;
                --base                : #ffffff;
                --background          : #ffffff;
                --color               : #0f172a;
                --color-mute          : #475569;
                --border              : rgba(15, 23, 42, 0.1);

                --glass               : rgba(255, 255, 255, 0.7);
                --glass-strong        : rgba(255, 255, 255, 0.92);
                --glass-edge          : inset 0 1px 0 rgba(255, 255, 255, 0.9);
                --glass-drop          : 0 8px 24px -8px rgba(15, 23, 42, 0.18);
                --glass-rim           : 0 0 6px rgba(0, 0, 0, .015), 0 2px 6px rgba(0, 0, 0, .04),
                    inset 3px 3px .5px -3px rgba(0, 0, 0, .45), inset -3px -3px .5px -3px rgba(0, 0, 0, .425),
                    inset 1px 1px 1px -.5px rgba(0, 0, 0, .3), inset -1px -1px 1px -.5px rgba(0, 0, 0, .3),
                    inset 0 0 6px 6px rgba(0, 0, 0, .06), inset 0 0 2px 2px rgba(0, 0, 0, .03),
                    0 0 12px rgba(255, 255, 255, .075);

                --shadow-small        : 0 6px 18px rgba(15, 23, 42, 0.12);
                --shadow-large        : 0 22px 48px rgba(15, 23, 42, 0.25);

                --banner-tint         : rgba(10, 10, 10, 0.5);
            }
            ```

    - for `body.css`
        - include all the body related things.
    - for `nav.css`
        - include the nav, adaptive to wide and mobile viewports, adaptive to everything.
        - the menu icon should be animated smoothly between menu icon adn the close icon
        - the sturcture should be as followed
            ```
            LOGO(left)        Theme Button(Leaning to the links)    Menu Links/ Menu Icon(right)
            ```
        - the nav should be simple and clear and clean
    - for `footer.css`
        - do the structure as
            ```
            LOGO BIG (grid:left)    Contact Info(grid:center)   NavLinks(grid:right)
            [Copyright & etc lines at the bottom, all columns of the row 2]
            ```
- make a custom scrollbar that adapts to themes, etc.
- Do not use numbers, etc for elements, instead use from :root to keep things consistent
- For intro animations, do not implement it directly to the element. instead use wrappers

---
## JS

- keep the code minimalistic and systematc with the systematic file structure.
- Detect the preferred-color scheme to implement the root.css correctly.
- Detect scrolls to manage the Navigation Bar
- After the heading, state the file type clearly. Example
    ```js
    // File Type : Init

    // File Type : Writer (InnerHTML)

    // File Type : Event Listener

    ...
    ```
- For every image, add a fallback from `/resources/img/placeholders/` depending on the type.

---

## JSON
- Do not include any sort of comments including the ehader, etc. (Only applies to .json file format)

---

## HTML

- When linking css, js, etc file, instead of doing back and forth paths, start from root everytime. Example
    ```html
        Instead of 
        <link type="stylesheet" href="../resources/css/root.css">

        Do
        <link type="stylesheet" href="/resources/css/root.css">
    ```
    This applies to all file types such as css, js, html, img, etc.
- Add redirection rules to the folder to prevent the users from seeing index.html in their url bars. Add this to the
- Every text visible must be editable through .json in /resources/data/...
- the root index.html will redirect the user to `/home/`


---
# Webpage Information
---

## Navigation Bar
- Prints the links automatically and highlights the relevent page the user is in automatically.
- Prints the links through the `/resources/data/nav.json` file
    - The file includes every data in the nav. Example
        ```json
        {
            "LinkName" : "LinkPath",
            "Home"    : "/home/"
        }
        ```
- This is sticky to the top with `position: absolute` css - Not with `position: sticky` beacure the banner/hero starts from 0 and not below.
- Use a glass effect as background.

---

## Footer
- Prints the contact info though `/resources/data/contact-info.json`
    - data format example:
    ```json
    type: email
    icon: /resources/icons/mail.svg
    text: email@domain.com
    action: mailto:email@domain.com
    ```
- Prints the NavLinks through `/resources/data/nav.json`

---

## Homepage &bull; Banner/Hero
- Use the uploaded video.
- include the file in ` /resources/vid/`
- add text with `position:absolute`
    ```html
    <div class="homepage-banner-content">
        <p class="homepage-banner-label">NP CONSULTANTS</p>
        <h1 class="homepage-banner-title">
            Engineering Excellence.<br>
            <span>Built on Experience.</span>
        </h1>
        <p class="homepage-banner-description">
            A team of chartered engineers and architects committed to delivering
            innovative, reliable, and precise engineering solutions.
        </p>
        <a href="#about-us" class="homepage-banner-button">
            Discover Our Story <span>↗</span>
        </a>
    </div>
    ```
---

## Homepage &bull; About Us
- Write the paragraph as 
    
    > NP Consultants is a structural design and engineering consultancy established in 2010, providing comprehensive solutions across Sri Lanka and extending its services to international projects. With expertise in structural design, structural detailing, architectural and interior design, project management, and electrical and mechanical consultancy, we serve a diverse range of projects, from residential buildings to industrial facilities and specialised structures. Our experienced team is committed to delivering practical, reliable, and cost-effective solutions tailored to each client's requirements, with a strong focus on quality, structural integrity, and client satisfaction.

- apart from it use a grid to show the paragraph at left and a photo grid from `/resources/data/projects.json` which has the `"show-in-about": true`
- use the grid such as (example) : 

    ```html
    <section class="homepage-about">
        <div class="homepage-about-title-wrapper">
            <div class="title">
                <h2>About Us</h2>
            </div>
        </div>

        <div class="homepage-about-content">
            <div class="homepage-about-text-wrapper">
                <div class="homepage-about-text">
                    <p>
                        NP Consultants is a structural design and engineering consultancy established in 2010, providing comprehensive solutions across Sri Lanka and extending its services to international projects. With expertise in structural design, structural detailing, architectural and interior design, project management, and electrical and mechanical consultancy, we serve a diverse range of projects, from residential buildings to industrial facilities and specialised structures. Our experienced team is committed to delivering practical, reliable, and cost-effective solutions tailored to each client's requirements, with a strong focus on quality, structural integrity, and client satisfaction.
                    </p>
                </div>
            </div>

            <div class="homepage-about-grid-wrapper">
                <div class="homepage-about-grid">
                    <div class="homepage-about-card-wrapper">
                        <a href="/projects/#projects1" class="homepage-about-card">
                            <img src="/img/projects/project-1.jpg" alt="Structural Design">
                            <div class="homepage-about-card-overlay">
                                <h3>Structural Design</h3>
                                <p>Innovative structural solutions focused on strength, safety, and precision.</p>
                            </div>
                        </a>
                    </div>

                    <div class="homepage-about-card-wrapper">
                        <a href="/projects/#projects2" class="homepage-about-card">
                            <img src="/img/projects/project-2.jpg" alt="Structural Detailing">
                            <div class="homepage-about-card-overlay">
                                <h3>Structural Detailing</h3>
                                <p>Detailed structural drawings supporting accurate and efficient construction.</p>
                            </div>
                        </a>
                    </div>

                    <div class="homepage-about-card-wrapper">
                        <a href="/projects/#projects3" class="homepage-about-card">
                            <img src="/img/projects/project-3.jpg" alt="Architectural Design">
                            <div class="homepage-about-card-overlay">
                                <h3>Architectural Design</h3>
                                <p>Coordinated design and project management from concept to completion.</p>
                            </div>
                        </a>
                    </div>

                    <div class="homepage-about-card-wrapper">
                        <a href="/projects/#projects4" class="homepage-about-card">
                            <img src="/img/projects/project-4.jpg" alt="Engineering Consultancy">
                            <div class="homepage-about-card-overlay">
                                <h3>Engineering Consultancy</h3>
                                <p>Practical engineering and architectural consultancy tailored to project requirements.</p>
                            </div>
                        </a>
                    </div>

                    <div class="homepage-about-card-wrapper">
                        <a href="/projects/" class="homepage-about-card">
                            <img src="/img/projects/project-5.jpg" alt="Structural Engineering">
                            <div class="homepage-about-card-overlay">
                                <h3>Structural Engineering</h3>
                                <p>Reliable engineering solutions designed around each project's requirements.</p>
                            </div>
                        </a>
                    </div>

                    <div class="homepage-about-card-wrapper">
                        <a href="/projects/" class="homepage-about-card">
                            <img src="/img/projects/project-6.jpg" alt="Project Consultancy">
                            <div class="homepage-about-card-overlay">
                                <h3>Project Consultancy</h3>
                                <p>Experienced guidance throughout the project lifecycle.</p>
                            </div>
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </section>
    ```

    ```css
    /* ──────────────────────────────────────────────────────────────────────────────── */
    /* ──────────────────────────────── NP Consultants ──────────────────────────────── */
    /* ────────────────────────────── homepage-about.css ────────────────────────────── */
    /* ──────────────────────────────────────────────────────────────────────────────── */
    /* <section class="homepage-about"> ... </section>                              */
    /* Needs the class "animate" added to .homepage-about (e.g. on scroll into view) */
    /* to start the entrance animations. Each card wrapper needs --i (0, 1, 2...)   */
    /* for its stagger delay (the JS writer sets it). Any number of cards works.    */
    /* Content is written by homepage-about.js (about.json, projects.json).  */
    /* Every value comes from root.css, nothing is hardcoded in this file.          */

    .homepage-about {
        width: 100%;
        height: 100vh;
        height: 100dvh;
        padding: var(--padding-large) var(--padding-medium);

        display: flex;
        flex-direction: column;
        overflow: hidden;
        scroll-snap-align: start;

        background: var(--background);
        opacity: 0;
    }

    .homepage-about.animate {
        animation: about-enter var(--transition-large) ease forwards;
    }

    /* ──────────────────────────────────── Title ───────────────────────────────────── */

    .homepage-about .title {
        position: relative;
        padding-bottom: var(--padding-small);
        margin-bottom: var(--margin-medium);
    }

    .homepage-about .title::after {
        content: "";
        position: absolute;
        inset: auto 0 0;
        height: var(--border-width);
        background: var(--splitter);
    }

    .homepage-about h2 {
        margin: 0;
        padding-inline: var(--padding-small);

        font-size: var(--font-xlarge);
        font-weight: var(--font-weight-light);
        line-height: var(--line-height-tight);
        color: var(--color);

        opacity: 0;
        transform: translateY(calc(var(--offset-large) * -1));
        animation: text-enter var(--transition-large) ease forwards;
        animation-play-state: paused;
    }

    .homepage-about.animate h2 {
        animation-delay: calc(var(--stagger) * 2);
        animation-play-state: running;
    }

    /* ─────────────────────────────────── Content ──────────────────────────────────── */

    .homepage-about-content {
        flex: 1;
        min-width: 0;
        min-height: 0;

        display: grid;
        grid-template-columns: minmax(0, 1fr) minmax(0, 2fr);
        grid-template-rows: minmax(0, 1fr);
        gap: var(--gap-large);
        align-items: center;
    }

    .homepage-about-text {
        min-width: 0;
        padding-inline: var(--padding-small);

        opacity: 0;
        transform: translateX(calc(var(--offset-large) * -1));
        animation: text-slide var(--transition-large) ease forwards;
        animation-play-state: paused;
    }

    .homepage-about.animate .homepage-about-text {
        animation-delay: calc(var(--stagger) * 3);
        animation-play-state: running;
    }

    .homepage-about-text p {
        margin: 0;
        font-size: var(--font-medium);
        line-height: var(--line-height-base);
        letter-spacing: var(--letter-spacing);
        color: var(--color-mute);
    }

    /* ──────────────────────────────────── Cards ───────────────────────────────────── */

    .homepage-about-grid-wrapper {
        min-width: 0;
        min-height: 0;
        height: 100%;
    }

    .homepage-about-grid {
        width: 100%;
        height: 100%;
        min-width: 0;

        display: grid;
        grid-template-columns: repeat(3, minmax(0, 1fr));
        grid-auto-rows: minmax(0, 1fr);
        gap: var(--gap-small);
    }

    .homepage-about-card-wrapper {
        min-width: 0;
        min-height: 0;

        opacity: 0;
        transform: translateY(var(--offset-large));
        animation: card-enter var(--transition-large) var(--ease) forwards;
        animation-delay: calc(var(--stagger) * var(--i, 0));
        animation-play-state: paused;
    }

    .homepage-about.animate .homepage-about-card-wrapper {
        animation-play-state: running;
    }


    .homepage-about-card {
        position: relative;
        display: block;
        height: 100%;
        overflow: hidden;
        isolation: isolate;

        border-radius: var(--border-radius-medium);
        background: var(--base);
        box-shadow: var(--shadow-small);
        transition: box-shadow var(--transition-small) ease;
    }

    .homepage-about-card:hover,
    .homepage-about-card:focus-visible {
        box-shadow: var(--shadow-large);
    }

    .homepage-about-card:focus-visible {
        outline: var(--outline);
        outline-offset: var(--outline-offset);
    }

    .homepage-about-card img {
        display: block;
        width: 100%;
        height: 100%;
        object-fit: cover;

        transform: scale(var(--zoom-small));
        transition: transform var(--transition-small) var(--ease),
                    filter var(--transition-small) ease;
    }

    .homepage-about-card:hover img,
    .homepage-about-card:focus-visible img {
        transform: scale(var(--zoom-large));
        filter: brightness(var(--dim));
    }

    /* ───────────────────────────────── Card Overlay ───────────────────────────────── */

    .homepage-about-card-overlay {
        position: absolute;
        inset: 0;

        display: flex;
        flex-direction: column;
        justify-content: flex-end;
        padding: var(--padding-small);

        background: linear-gradient(
            to top,
            var(--background) 0%,
            color-mix(in srgb, var(--background) 40%, transparent) 55%,
            transparent 100%
        );

        opacity: 0;
        transform: translateY(var(--offset-small));
        transition: opacity var(--transition-small) ease,
                    transform var(--transition-small) var(--ease);
    }

    .homepage-about-card:hover .homepage-about-card-overlay,
    .homepage-about-card:focus-visible .homepage-about-card-overlay {
        opacity: 1;
        transform: translateY(0);
    }

    .homepage-about-card-overlay h3 {
        margin: 0;
        font-size: var(--font-large);
        font-weight: var(--font-weight-normal);
        letter-spacing: var(--letter-spacing);
        color: var(--color);
    }

    .homepage-about-card-overlay p {
        margin: var(--margin-small) 0 0;
        font-size: var(--font-small);
        line-height: var(--line-height-base);
        color: var(--color-mute);
    }

    /* ────────────────────────────────── Animations ────────────────────────────────── */

    @keyframes about-enter { to { opacity: 1; } }
    @keyframes text-enter  { to { opacity: 1; transform: translateY(0); } }
    @keyframes text-slide  { to { opacity: 1; transform: translateX(0); } }
    @keyframes card-enter  { to { opacity: 1; transform: translateY(0); } }

    /* ────────────────────────────────── Responsive ────────────────────────────────── */

    @media (max-width: 68.75rem) {
        .homepage-about {
            height: auto;
            min-height: 100vh;
            min-height: 100dvh;
            overflow: visible;
            scroll-snap-align: none;
        }

        .homepage-about-content {
            grid-template-columns: minmax(0, 1fr);
            grid-template-rows: auto auto;
            gap: var(--gap-medium);
        }

        .homepage-about-text { padding-inline: 0; }
        .homepage-about-grid-wrapper { height: auto; }
        .homepage-about-grid { min-height: var(--grid-height-large); }
    }

    /* When 3 columns no longer fit cleanly, show one row of 3 cards.               */
    @media (max-width: 43.75rem) {
        .homepage-about-grid {
            min-height: var(--grid-height-medium);
        }

        .homepage-about-card-wrapper:nth-child(n + 4) { display: none; }
    }

    @media (max-width: 30rem) {
        .homepage-about-grid {
            gap: var(--gap-xsmall);
            min-height: var(--grid-height-small);
        }

        .homepage-about-card-overlay { padding: var(--padding-xsmall); }
        .homepage-about-card-overlay p { display: none; }
    }

    /* Touch screens have no hover, so keep the overlay visible.                    */
    @media (hover: none) {
        .homepage-about-card-overlay { opacity: 1; transform: none; }
    }

    /* ──────────────────────────────── Reduced Motion ──────────────────────────────── */

    @media (prefers-reduced-motion: reduce) {
        .homepage-about,
        .homepage-about h2,
        .homepage-about-text,
        .homepage-about-card-wrapper {
            animation: none;
            opacity: 1;
            transform: none;
        }

        .homepage-about-card,
        .homepage-about-card img,
        .homepage-about-card-overlay { transition: none; }
    }
    ```

---

## Homepage &bull; Our Services
- Data from `/resources/data/home-srevices.json`
- Button linking to `/srevices/`

---

## Homepage &bull; Q&A 
- use a card-style system with a glass effect.
- x-axis scroll with snap
- 3 cards on normal viewport (Laptop), single card on mobile
- show a numbered navigation for user to navigate easily
- add arrows to navigate thrugh too 
- make the cards at edges slightly smaller, blurrier but readable & dynamic than the middle card
- write the contents through `/resources/data/qna.json`

---

## Homepage &bull; Our Projects
- use cards style of the [Homepage &bull; About Us](#homepage--about-us)
- use the hover based information reveal system/module from [Homepage &bull; About Us](#homepage--about-us)
- show the projects with the `"featured": true` in the `/resources/data/projects.json` file
- Texts taken from the `/resources/data/home-projects.json`
- the grid shows 3 projects at every viewport setting, can expand into 4 or 4+ at larger screens upto 6
- if the display size doesn't make the grid show mroe than 3 projects, do not show the rest projects in this section
- button linking to `/projects/`
--- 

## Homepage &bull; Our Team
- shows the roles - Manager, Director & Assistant directors and managers at the topmost row
- the rest of the employees are shown in the rest of the lines.
- shows the diector in the topmmost layer's leftmost, this can expand depending on the space available in the row
- shows the manager, assistant managers, etc to the rightmost using a single cell of the grid.
- if there is space left after showing the management, expand the director's cell to fill the grid in.
- At mobile view, all the cells are foced to show row-wise, therefore show the management's profile pictures slightly larger than the employees profile pictures
- data from `/resources/data/team.json`

--- 

## Homepage  &bull; Contact Us
- This is a reminder-style of a block, this has a tagline and a button linking to `/contact/`
- has the top & bottom border images as `var(--splitter)` as given in the example code

---

## Our Services
- Data from `/resources/data/srevices.json`
- Use a blocwise system with a block per each service.
- scroll direction : y-axis

---

## Our Projects
- Data from `/resources/data/srevices.json`
- A gridwise representation of projects usig cards.
- cars show the Project name, project type & the project year with a related images swicthing randomly in a smooth manner.
- show finished projects in an accent based color border
- show the projects in progress in a amber based border
- write the ongoing projects before the finished projects
- when a project card is clicked, it opens a pop-up with its Topic(project Name), Project Type, Year, relevent images in a grid.
- in json, the basic stats are to be assigned using 
    ```json
    {
        "featured": true,
        "ongoing": true
    }
    ```

---

## Contact Us &bull; Map
- 100vw/ 100dvw map with around 80vh/80dvh - 100vh-100dvh depending on the viewoport
- data from `/resources/data/contact.json`

---

## Contact Us &bull; Form
- Form information from `/resources/data/contact-form.json`
- every field input is printed from .json
- has a google-style form fields. Example CSS:

    ```html
    ...
    ```

    ```css
    ...
    ```

---