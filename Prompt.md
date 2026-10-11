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
- Example button CSS file :
    ```css
    /* ──────────────────────────────────────────────────────────────────────────────── */
    /* ──────────────────────────────── NP Consultants ──────────────────────────────── */
    /* ────────────────────────────────── button-1.css ──────────────────────────────── */
    /* ──────────────────────────────────────────────────────────────────────────────── */
    /* Button  : <a href="..." class="button-1">Label</a>                           */
    /* Use     : works anywhere, link it after root.css. Position it from the       */
    /*           section CSS (margin, align-self), never from here.                 */
    /* Tokens  : root.css only. Nothing is hardcoded in this file.                  */

    .button-1 {
        position: relative;
        display: inline-block;
        overflow: hidden;
        padding: var(--padding-xsmall) var(--padding-medium);

        background: color-mix(in srgb, var(--accent) var(--mix-large), transparent);
        border: var(--border-width) solid var(--border);
        border-radius: var(--border-radius-full);

        color: var(--color-mute);
        text-decoration: none;
        font-family: var(--font-family);
        font-size: var(--font-medium);
        font-weight: var(--font-weight-bold);
        letter-spacing: var(--letter-spacing);
        user-select: none;
        cursor: pointer;

        transition:
            background var(--transition-small) var(--ease),
            box-shadow var(--transition-small) var(--ease),
            transform var(--transition-small) var(--ease);
    }

    /* Shine that sweeps across the button on hover. */
    .button-1::before {
        content: "";
        position: absolute;
        inset: 0;

        background: linear-gradient(
            120deg,
            transparent,
            color-mix(in srgb, var(--color) var(--mix-small), transparent),
            transparent
        );

        transform: translateX(calc(var(--shine-offset) * -1));
        transition: transform var(--transition-large) var(--ease);
        pointer-events: none;
    }

    .button-1:focus-visible {
        outline: var(--outline);
        outline-offset: var(--outline-offset);
    }

    .button-1:active {
        transform: scale(var(--press-scale));
    }

    /* ──────────────────────────────────── Hover ───────────────────────────────────── */

    @media (hover: hover) {
        .button-1:hover {
            background: var(--glass);
            box-shadow:
                var(--shadow-small),
                0 0 var(--gap-small) color-mix(in srgb, var(--accent) var(--mix-large), transparent);
            transform: translateY(var(--hover-lift)) scale(var(--hover-scale));
        }

        .button-1:hover::before {
            transform: translateX(var(--shine-offset));
        }
    }

    /* ───────────────────────────────── Reduced Motion ─────────────────────────────── */

    @media (prefers-reduced-motion: reduce) {
        .button-1,
        .button-1::before {
            transition: none;
        }
    }
    ```

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
- Example code:

    ```html
    <section class="homepage-services" id="homepage-services">
        <div class="homepage-services-title-wrapper">
            <header class="homepage-services-title">
                <h2 class="homepage-services-heading">Our Services</h2>
            </header>
        </div>

        <div class="homepage-services-description-wrapper">
            <p class="homepage-services-description">We Provide Various Engineering Services from the Initial Planning Stage to the Full Completion</p>
        </div>

        <div class="homepage-services-grid" style="--rows:4">
            <div class="homepage-services-image-wrapper">
                <figure class="homepage-services-image">
                    <img src="/resources/images/services.jpg" alt="Our engineering services" loading="lazy">
                </figure>
            </div>

            <div class="homepage-services-panel-wrapper" style="--i:0;--dir:-1">
                <article class="homepage-services-panel">
                    <h3>Structural Designing</h3>
                    <p>Cost-effective, space-saving, future-proof building structures that comply with industry standards.</p>
                </article>
            </div>

            <div class="homepage-services-panel-wrapper" style="--i:1;--dir:-1">
                <article class="homepage-services-panel">
                    <h3>Steel Structural Detailing</h3>
                    <p>Detailed drawings, for steel fabrication and steel erections with technical specifications</p>
                </article>
            </div>

            <div class="homepage-services-panel-wrapper" style="--i:2;--dir:-1">
                <article class="homepage-services-panel">
                    <h3>Consulting Engineers</h3>
                    <p>Learn how to utilize your available resources effectively and determine the best strategies for your project.</p>
                </article>
            </div>

            <div class="homepage-services-panel-wrapper" style="--i:3;--dir:-1">
                <article class="homepage-services-panel">
                    <h3>Chartered Architects</h3>
                    <p>Experienced, professional architectural services with years of industry experience for your next project.</p>
                </article>
            </div>

            <div class="homepage-services-panel-wrapper" style="--i:0;--dir:1">
                <article class="homepage-services-panel">
                    <h3>Quantity Surveyors</h3>
                    <p>Our quantity surveying service will provide far more accuracy in estimations, budgeting, and planning.</p>
                </article>
            </div>

            <div class="homepage-services-panel-wrapper" style="--i:1;--dir:1">
                <article class="homepage-services-panel">
                    <h3>Green Building Consultants</h3>
                    <p>Implement energy-efficient, eco-friendly strategies and minimize your carbon footprint as well as energy costs.</p>
                </article>
            </div>

            <div class="homepage-services-panel-wrapper" style="--i:2;--dir:1">
                <article class="homepage-services-panel">
                    <h3>Project Management</h3>
                    <p>Make sure your project is on the right path to successful completion with our expert service.</p>
                </article>
            </div>

            <div class="homepage-services-panel-wrapper" style="--i:3;--dir:1">
                <article class="homepage-services-panel">
                    <h3>Interior Designing</h3>
                    <p>We design functional, safe, attractive &amp; pleasant interiors</p>
                </article>
            </div>
        </div>
    </section>
    ```

    ```css
    /* ──────────────────────────────────────────────────────────────────────────────── */
    /* ──────────────────────────────── NP Consultants ──────────────────────────────── */
    /* ──────────────────────────── homepage-services.css ───────────────────────────── */
    /* ──────────────────────────────────────────────────────────────────────────────── */
    /* Section : <section class="homepage-services" id="homepage-services"></section> */
    /* Intro   : every block sits in a "-wrapper". Wrappers play the entrance       */
    /*           animation, the inner elements handle hover (no transform clashes). */
    /* Start   : add the class "homepage-services-animate" to the section (e.g. on  */
    /*           scroll into view) to play the intro.                               */
    /* Tokens  : root.css only. Set --i (stagger), --dir (-1 left / 1 right) on     */
    /*           each panel wrapper and --rows (panels per side) on the grid.       */

    .homepage-services {
        width: 100%;
        height: 100vh;
        height: 100dvh;
        padding: var(--padding-large) var(--padding-medium);

        display: flex;
        flex-direction: column;
        overflow: hidden;
        scroll-snap-align: start;

        background: var(--background);
    }

    /* ─────────────────────────────────── Intro ────────────────────────────────────── */

    /* Start state: hidden and offset. Each wrapper has its own direction. */

    .homepage-services-title-wrapper,
    .homepage-services-description-wrapper,
    .homepage-services-image-wrapper,
    .homepage-services-panel-wrapper {
        min-width: 0;
        min-height: 0;
        opacity: 0;
    }

    .homepage-services-title-wrapper       { transform: translateY(calc(var(--offset-large) * -1)); }
    .homepage-services-description-wrapper { transform: translateX(calc(var(--offset-large) * -1)); }
    .homepage-services-image-wrapper       { transform: scale(var(--enter-scale)); }
    .homepage-services-panel-wrapper       { transform: translateX(calc(var(--dir) * var(--offset-small))); }

    /* Play: one shared animation, different delays. */

    .homepage-services-animate .homepage-services-title-wrapper,
    .homepage-services-animate .homepage-services-description-wrapper,
    .homepage-services-animate .homepage-services-image-wrapper,
    .homepage-services-animate .homepage-services-panel-wrapper {
        animation: homepage-services-enter var(--transition-large) var(--ease) both;
    }

    .homepage-services-animate .homepage-services-title-wrapper       { animation-delay: var(--stagger); }
    .homepage-services-animate .homepage-services-description-wrapper { animation-delay: calc(var(--stagger) * 2); }
    .homepage-services-animate .homepage-services-image-wrapper       { animation-delay: calc(var(--stagger) * 2); }
    .homepage-services-animate .homepage-services-panel-wrapper       { animation-delay: calc(var(--stagger) * (var(--i) + 2)); }

    /* ─────────────────────────────────── Header ───────────────────────────────────── */

    .homepage-services-title {
        padding-bottom: var(--padding-xsmall);
        margin-bottom: var(--margin-medium);

        border-bottom: var(--border-width) solid var(--color);
        border-image: var(--splitter) 1;
    }

    .homepage-services-heading {
        margin: 0;
        padding: 0 var(--padding-xsmall);

        color: var(--color);
        font-size: var(--font-xlarge);
        font-weight: var(--font-weight-light);
        line-height: var(--line-height-tight);
    }

    .homepage-services-description {
        max-width: 45rem;
        margin: 0 0 var(--margin-medium);
        padding: 0 var(--padding-xsmall);

        color: var(--color-mute);
        font-size: var(--font-medium);
        line-height: var(--line-height-base);
    }

    /* ──────────────────────────────────── Grid ────────────────────────────────────── */

    .homepage-services-grid {
        flex: 1;
        min-width: 0;
        min-height: 0;

        display: grid;
        grid-auto-flow: column;
        grid-template-columns: minmax(0, 1fr) minmax(0, 1.4fr) minmax(0, 1fr);
        grid-template-rows: repeat(var(--rows), minmax(0, 1fr));
        gap: var(--gap-small);
    }

    .homepage-services-image-wrapper {
        grid-column: 2;
        grid-row: 1 / -1;
    }

    .homepage-services-image {
        height: 100%;
        margin: 0;
        overflow: hidden;

        border-radius: var(--border-radius-medium);
        box-shadow: var(--shadow-small);
        transition: box-shadow var(--transition-small) var(--ease);
    }

    .homepage-services-image img {
        display: block;
        width: 100%;
        height: 100%;
        object-fit: cover;

        transform: scale(var(--zoom-small));
        transition: transform var(--transition-small) var(--ease), filter var(--transition-small) var(--ease);
    }

    /* ─────────────────────────────────── Panels ───────────────────────────────────── */

    .homepage-services-panel {
        position: relative;

        display: flex;
        flex-direction: column;
        justify-content: center;

        height: 100%;
        padding: var(--padding-xsmall);

        background: var(--glass);
        border: var(--border-width) solid var(--border);
        border-radius: var(--border-radius-medium);
        box-shadow: var(--shadow-small);

        transition:
            background var(--transition-small) var(--ease),
            border-color var(--transition-small) var(--ease),
            box-shadow var(--transition-small) var(--ease),
            transform var(--transition-small) var(--ease);
    }

    .homepage-services-panel h3,
    .homepage-services-panel p {
        transition: transform var(--transition-small) var(--ease), color var(--transition-small) var(--ease);
    }

    .homepage-services-panel h3 {
        margin: 0 0 var(--margin-small);

        color: var(--color);
        font-size: var(--font-large);
        font-weight: var(--font-weight-normal);
    }

    .homepage-services-panel p {
        margin: 0;

        color: var(--color-mute);
        font-size: var(--font-small);
        line-height: var(--line-height-base);
    }

    /* ──────────────────────────────────── Hover ───────────────────────────────────── */

    @media (hover: hover) {
        /* Image: zoom in, dim a little, deeper shadow. */
        .homepage-services-image:hover {
            box-shadow: var(--shadow-large);
        }

        .homepage-services-image:hover img {
            transform: scale(var(--zoom-large));
            filter: brightness(var(--dim));
        }

        /* Panel: lift, accent tint and glow, text nudges in. */
        .homepage-services-panel:hover {
            background: color-mix(in srgb, var(--glass) 85%, var(--accent) var(--mix-small));
            border-color: color-mix(in srgb, var(--accent) var(--mix-large), transparent);
            box-shadow:
                var(--shadow-large),
                0 0 var(--gap-small) color-mix(in srgb, var(--accent) var(--mix-large), transparent);
            transform: translateY(var(--hover-lift)) scale(var(--hover-scale));
        }

        .homepage-services-panel:hover h3 {
            color: var(--accent);
            transform: translateX(var(--text-shift));
        }

        .homepage-services-panel:hover p {
            color: var(--color);
            transform: translateX(var(--text-shift));
        }
    }

    /* ─────────────────────────────────── Keyframes ────────────────────────────────── */

    @keyframes homepage-services-enter {
        to { opacity: 1; transform: none; }
    }

    /* ────────────────────────────────── Responsive ────────────────────────────────── */

    @media (max-width: 68.75rem) {
        .homepage-services {
            height: auto;
            min-height: 100vh;
            min-height: 100dvh;
        }

        .homepage-services-grid {
            grid-auto-flow: row;
            grid-template-columns: 1fr 1fr;
            grid-template-rows: none;
            grid-auto-rows: auto;
            min-height: var(--grid-height-large);
        }

        .homepage-services-image-wrapper {
            grid-column: 1 / -1;
            grid-row: 1;
            min-height: var(--grid-height-medium);
        }

        .homepage-services-panel-wrapper {
            transform: translateY(var(--offset-small));
        }
    }

    @media (max-width: 43.75rem) {
        .homepage-services-grid {
            grid-template-columns: 1fr;
        }

        .homepage-services-image-wrapper {
            grid-column: 1;
        }
    }

    /* ───────────────────────────────── Reduced Motion ─────────────────────────────── */

    @media (prefers-reduced-motion: reduce) {
        .homepage-services *,
        .homepage-services *::before,
        .homepage-services *::after {
            animation: none;
            transition: none;
        }

        .homepage-services .homepage-services-title-wrapper,
        .homepage-services .homepage-services-description-wrapper,
        .homepage-services .homepage-services-image-wrapper,
        .homepage-services .homepage-services-panel-wrapper {
            opacity: 1;
            transform: none;
        }
    }
    ```

---

## Homepage &bull; Structureal Design
- For now keep a 100vh block with a text telling 503

---

## Homepage &bull; Our Projects
- use cards style of the [Homepage &bull; About Us](#homepage--about-us)
- use the hover based information reveal system/module from [Homepage &bull; About Us](#homepage--about-us)
- show the projects with the `"featured": true` in the `/resources/data/projects.json` file
- Texts taken from the `/resources/data/home-projects.json`
- the grid shows 3 projects at every viewport setting, can expand into 4 or 4+ at larger screens upto 6
- if the display size doesn't make the grid show mroe than 3 projects, do not show the rest projects in this section
- button linking to `/projects/`
- Example code: 

    ```html
    <section class="homepage-projects" id="homepage-projects">
        <div class="homepage-projects-title-wrapper">
            <header class="homepage-projects-title">
                <h2 class="homepage-projects-heading">Our Projects</h2>
            </header>
        </div>

        <div class="homepage-projects-description-wrapper">
            <p class="homepage-projects-description">Short description of your projects.</p>
        </div>

        <div class="homepage-projects-grid">
            <div class="homepage-projects-card-wrapper" style="--i:0">
                <a href="/projects/#projects1" class="homepage-projects-card">
                    <div class="homepage-projects-image">
                        <img src="/img/projects/project-1.jpg" alt="Project 1" loading="lazy">
                    </div>
                    <div class="homepage-projects-overlay"></div>
                    <div class="homepage-projects-info">
                        <h3>Project 1</h3>
                        <p>Short project description.</p>
                    </div>
                </a>
            </div>

            <div class="homepage-projects-card-wrapper" style="--i:1">
                <a href="/projects/#projects2" class="homepage-projects-card">
                    <div class="homepage-projects-image">
                        <img src="/img/projects/project-2.jpg" alt="Project 2" loading="lazy">
                    </div>
                    <div class="homepage-projects-overlay"></div>
                    <div class="homepage-projects-info">
                        <h3>Project 2</h3>
                        <p>Short project description.</p>
                    </div>
                </a>
            </div>

            <div class="homepage-projects-card-wrapper" style="--i:2">
                <a href="/projects/#projects3" class="homepage-projects-card">
                    <div class="homepage-projects-image">
                        <img src="/img/projects/project-3.jpg" alt="Project 3" loading="lazy">
                    </div>
                    <div class="homepage-projects-overlay"></div>
                    <div class="homepage-projects-info">
                        <h3>Project 3</h3>
                        <p>Short project description.</p>
                    </div>
                </a>
            </div>
        </div>

        <div class="homepage-projects-button-wrapper">
            <a href="/projects/" class="button-1">View All Projects</a>
        </div>
    </section>
    ```

    ```css
    /* ──────────────────────────────────────────────────────────────────────────────── */
    /* ──────────────────────────────── NP Consultants ──────────────────────────────── */
    /* ──────────────────────────── homepage-projects.css ───────────────────────────── */
    /* ──────────────────────────────────────────────────────────────────────────────── */
    /* Section : <section class="homepage-projects" id="homepage-projects"></section> */
    /* Intro   : every block sits in a "-wrapper". Wrappers play the entrance       */
    /*           animation, the inner elements handle hover (no transform clashes). */
    /* Start   : add the class "homepage-projects-animate" to the section (e.g. on  */
    /*           scroll into view) to play the intro.                               */
    /* Cards   : any number; set --i (0, 1, 2...) on each card wrapper for stagger. */
    /* Button  : use <a class="button-1"> (button-1.css), styled separately.        */
    /* Tokens  : root.css only. Nothing is hardcoded in this file.                  */

    .homepage-projects {
        width: 100%;
        height: 100vh;
        height: 100dvh;
        padding: var(--padding-large) var(--padding-medium);

        display: flex;
        flex-direction: column;
        overflow: hidden;
        scroll-snap-align: start;

        background: var(--background);
    }

    /* ─────────────────────────────────── Intro ────────────────────────────────────── */

    .homepage-projects-title-wrapper,
    .homepage-projects-description-wrapper,
    .homepage-projects-card-wrapper,
    .homepage-projects-button-wrapper {
        min-width: 0;
        min-height: 0;
        opacity: 0;
    }

    .homepage-projects-title-wrapper       { transform: translateY(calc(var(--offset-large) * -1)); }
    .homepage-projects-description-wrapper { transform: translateY(calc(var(--offset-small) * -1)); }
    .homepage-projects-card-wrapper        { transform: translateY(var(--offset-large)); }
    .homepage-projects-button-wrapper      { transform: translateY(var(--offset-small)); }

    .homepage-projects-animate .homepage-projects-title-wrapper,
    .homepage-projects-animate .homepage-projects-description-wrapper,
    .homepage-projects-animate .homepage-projects-card-wrapper,
    .homepage-projects-animate .homepage-projects-button-wrapper {
        animation: homepage-projects-enter var(--transition-large) var(--ease) both;
    }

    .homepage-projects-animate .homepage-projects-title-wrapper       { animation-delay: var(--stagger); }
    .homepage-projects-animate .homepage-projects-description-wrapper { animation-delay: calc(var(--stagger) * 2); }
    .homepage-projects-animate .homepage-projects-card-wrapper        { animation-delay: calc(var(--stagger) * (var(--i) + 2)); }
    .homepage-projects-animate .homepage-projects-button-wrapper      { animation-delay: calc(var(--stagger) * 6); }

    /* ─────────────────────────────────── Header ───────────────────────────────────── */

    .homepage-projects-title {
        padding-bottom: var(--padding-xsmall);

        border-bottom: var(--border-width) solid var(--color);
        border-image: var(--splitter) 1;
    }

    .homepage-projects-heading {
        margin: 0;
        padding: 0 var(--padding-xsmall);

        color: var(--color);
        font-size: var(--font-xlarge);
        font-weight: var(--font-weight-light);
        line-height: var(--line-height-tight);
    }

    .homepage-projects-description {
        max-width: 45rem;
        margin: var(--margin-medium) 0 0;
        padding: 0 var(--padding-xsmall);

        color: var(--color-mute);
        font-size: var(--font-medium);
        line-height: var(--line-height-base);
    }

    /* ──────────────────────────────────── Grid ────────────────────────────────────── */

    .homepage-projects-grid {
        flex: 1;
        min-height: 0;
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        gap: var(--gap-small);
        margin-top: var(--margin-medium);
    }

    /* ─────────────────────────────────── Cards ────────────────────────────────────── */

    .homepage-projects-card {
        position: relative;
        display: block;
        height: 100%;
        overflow: hidden;
        isolation: isolate;

        background: var(--glass);
        border: var(--border-width) solid var(--border);
        border-radius: var(--border-radius-medium);
        box-shadow: var(--shadow-small);

        transition:
            background var(--transition-small) var(--ease),
            border-color var(--transition-small) var(--ease),
            box-shadow var(--transition-small) var(--ease),
            transform var(--transition-small) var(--ease);
    }

    .homepage-projects-image {
        position: absolute;
        inset: 0;
    }

    .homepage-projects-image img {
        display: block;
        width: 100%;
        height: 100%;
        object-fit: cover;

        transition: transform var(--transition-large) var(--ease), filter var(--transition-small) var(--ease);
    }

    .homepage-projects-overlay {
        position: absolute;
        inset: 0;

        background: linear-gradient(
            to top,
            color-mix(in srgb, var(--base) var(--mix-xlarge), transparent),
            transparent
        );
    }

    .homepage-projects-info {
        position: absolute;
        bottom: 0;
        z-index: 2;
        width: 100%;
        padding: var(--padding-small);
    }

    .homepage-projects-info h3 {
        margin: 0 0 var(--margin-small);

        color: var(--color);
        font-size: var(--font-large);
        font-weight: var(--font-weight-normal);
        transition: transform var(--transition-small) var(--ease);
    }

    .homepage-projects-info p {
        margin: 0;

        color: var(--color-mute);
        font-size: var(--font-small);
        line-height: var(--line-height-base);
        transition: transform var(--transition-small) var(--ease);
    }

    .homepage-projects-card:focus-visible {
        outline: var(--outline);
        outline-offset: var(--outline-offset);
    }

    /* ─────────────────────────────────── Button ───────────────────────────────────── */

    /* Only the position lives here. The button itself is styled in button-1.css. */

    .homepage-projects-button-wrapper {
        align-self: flex-start;
        margin-top: var(--margin-medium);
    }

    /* ──────────────────────────────────── Hover ───────────────────────────────────── */

    @media (hover: hover) {
        .homepage-projects-card:hover,
        .homepage-projects-card:focus-visible {
            z-index: 2;
            background: color-mix(in srgb, var(--glass) 85%, var(--accent) var(--mix-small));
            border-color: color-mix(in srgb, var(--accent) var(--mix-large), transparent);
            box-shadow:
                var(--shadow-large),
                0 0 var(--gap-small) color-mix(in srgb, var(--accent) var(--mix-large), transparent);
            transform: translateY(var(--hover-lift)) scale(var(--hover-scale));
        }

        .homepage-projects-card:hover .homepage-projects-image img,
        .homepage-projects-card:focus-visible .homepage-projects-image img {
            transform: scale(var(--zoom-large));
            filter: brightness(var(--bright));
        }

        .homepage-projects-card:hover h3,
        .homepage-projects-card:focus-visible h3,
        .homepage-projects-card:hover p,
        .homepage-projects-card:focus-visible p {
            transform: translateX(var(--text-shift));
        }
    }

    /* ─────────────────────────────────── Keyframes ────────────────────────────────── */

    @keyframes homepage-projects-enter {
        to { opacity: 1; transform: none; }
    }

    /* ────────────────────────────────── Responsive ────────────────────────────────── */

    @media (max-width: 56.25rem) {
        .homepage-projects {
            height: auto;
            min-height: 100vh;
            min-height: 100dvh;
        }

        .homepage-projects-grid {
            grid-template-columns: 1fr;
            overflow-y: auto;
        }

        .homepage-projects-card-wrapper {
            min-height: var(--grid-height-large);
        }
    }

    /* ───────────────────────────────── Reduced Motion ─────────────────────────────── */

    @media (prefers-reduced-motion: reduce) {
        .homepage-projects *,
        .homepage-projects *::before,
        .homepage-projects *::after {
            animation: none;
            transition: none;
        }

        .homepage-projects .homepage-projects-title-wrapper,
        .homepage-projects .homepage-projects-description-wrapper,
        .homepage-projects .homepage-projects-card-wrapper,
        .homepage-projects .homepage-projects-button-wrapper {
            opacity: 1;
            transform: none;
        }
    }
    ```
--- 

## Homepage &bull; Our Team
- shows the roles - Manager, Director & Assistant directors and managers at the topmost row
- the rest of the employees are shown in the rest of the lines.
- shows the diector in the topmmost layer's leftmost, this can expand depending on the space available in the row
- shows the manager, assistant managers, etc to the rightmost using a single cell of the grid.
- if there is space left after showing the management, expand the director's cell to fill the grid in.
- make it adapt to multi-role per single person
- At mobile view, all the cells are foced to show row-wise, therefore show the management's profile pictures slightly larger than the employees profile pictures
- data from `/resources/data/team.json`
- Example code: 

    ```html
    <section class="homepage-team" id="homepage-team">
        <div class="homepage-team-title-wrapper">
            <header class="homepage-team-title">
                <h2 class="homepage-team-heading">Our Team</h2>
            </header>
        </div>

        <div class="homepage-team-description-wrapper">
            <p class="homepage-team-description">The people behind every design, drawing and site visit.</p>
        </div>

        <div class="homepage-team-management">
            <div class="homepage-team-director-wrapper" style="--i:0">
                <div class="director-card">
                    <div class="director-card-photo">
                        <img class="director-card-image" src="/img/team/director.jpg" alt="Director Name" loading="lazy">
                    </div>
                    <div class="director-card-info">
                        <h3>Director Name</h3>
                        <h4>Director &amp; Manager</h4>
                        <ul>
                            <li style="--n:0">Qualification one</li>
                            <li style="--n:1">Qualification two</li>
                            <li style="--n:2">Qualification three</li>
                        </ul>
                    </div>
                </div>
            </div>
            <div class="homepage-team-manager-wrapper" style="--i:1">
                <div class="team-card team-card-management">
                    <div class="team-card-photo">
                        <img class="team-card-image" src="/img/team/assistant-director.jpg" alt="Assistant Director" loading="lazy">
                    </div>
                    <div class="team-card-info">
                        <h3>Assistant Director</h3>
                        <h4>Assistant Director</h4>
                        <ul>
                            <li style="--n:0">Qualification one</li>
                            <li style="--n:1">Qualification two</li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>

        <div class="homepage-team-grid">
            <div class="homepage-team-card-wrapper" style="--i:2">
                <div class="team-card">
                    <div class="team-card-photo">
                        <img class="team-card-image" src="/img/team/employee-1.jpg" alt="Employee One" loading="lazy">
                    </div>
                    <div class="team-card-info">
                        <h3>Employee One</h3>
                        <h4>Structural Engineer</h4>
                        <ul>
                            <li style="--n:0">Qualification one</li>
                            <li style="--n:1">Qualification two</li>
                        </ul>
                    </div>
                </div>
            </div>
            <div class="homepage-team-card-wrapper" style="--i:3">
                <div class="team-card">
                    <div class="team-card-photo">
                        <img class="team-card-image" src="/img/team/employee-2.jpg" alt="Employee Two" loading="lazy">
                    </div>
                    <div class="team-card-info">
                        <h3>Employee Two</h3>
                        <h4>Draughtsman</h4>
                        <ul>
                            <li style="--n:0">Qualification one</li>
                            <li style="--n:1">Qualification two</li>
                        </ul>
                    </div>
                </div>
            </div>
            <!-- ...one homepage-team-card-wrapper per remaining employee, --i keeps counting up -->
        </div>
    </section>
    ```

    ```css
    /* ──────────────────────────────────────────────────────────────────────────────── */
    /* ──────────────────────────────── NP Consultants ──────────────────────────────── */
    /* ────────────────────────────── homepage-team.css ─────────────────────────────── */
    /* ──────────────────────────────────────────────────────────────────────────────── */
    /* Section : <section class="homepage-team" id="homepage-team"></section>       */
    /* Content : written by /resources/js/homepage-team.js from team.json.          */
    /* Rows    : 1) management row: director (left, expands) + manager cells,      */
    /*              each manager takes exactly one grid cell.                       */
    /*           2) employees fill the grid below, same cell width as the managers. */
    /* Expand  : the director cell grows to fill whatever the managers leave free.  */
    /* Columns : --team-columns is set per screen size here, and drives both rows.  */
    /* Mobile  : 1 column, so every card is its own row.                            */
    /* Intro   : every block sits in a "-wrapper". Wrappers play the entrance       */
    /*           animation, the cards inside only handle hover. Inside a card the   */
    /*           photo frame and the info block are wrappers too: card rises, photo */
    /*           pops in, then the text rises.                                      */
    /* Start   : JS adds "homepage-team-animate" to the section on scroll.          */
    /* Cards   : director-card.css and team-card.css.                               */
    /* Tokens  : root.css only. JS sets --i (stagger) on every wrapper.             */

    .homepage-team {
        --team-columns: 5;

        width: 100%;
        min-height: 100vh;
        min-height: 100dvh;
        padding: var(--padding-large) var(--padding-medium);

        display: flex;
        flex-direction: column;
        scroll-snap-align: start;

        background: var(--background);
    }

    /* ─────────────────────────────────── Intro ────────────────────────────────────── */

    .homepage-team-title-wrapper,
    .homepage-team-description-wrapper,
    .homepage-team-director-wrapper,
    .homepage-team-manager-wrapper,
    .homepage-team-card-wrapper {
        min-width: 0;
        opacity: 0;
    }

    .homepage-team-title-wrapper       { transform: translateY(calc(var(--offset-large) * -1)); }
    .homepage-team-description-wrapper { transform: translateY(calc(var(--offset-small) * -1)); }
    .homepage-team-director-wrapper,
    .homepage-team-manager-wrapper,
    .homepage-team-card-wrapper        { transform: translateY(var(--offset-large)); }

    .homepage-team-animate .homepage-team-title-wrapper,
    .homepage-team-animate .homepage-team-description-wrapper,
    .homepage-team-animate .homepage-team-director-wrapper,
    .homepage-team-animate .homepage-team-manager-wrapper,
    .homepage-team-animate .homepage-team-card-wrapper {
        animation: homepage-team-enter var(--transition-large) var(--ease) both;
    }

    .homepage-team-animate .homepage-team-title-wrapper       { animation-delay: var(--stagger); }
    .homepage-team-animate .homepage-team-description-wrapper { animation-delay: calc(var(--stagger) * 2); }
    .homepage-team-animate .homepage-team-director-wrapper,
    .homepage-team-animate .homepage-team-manager-wrapper,
    .homepage-team-animate .homepage-team-card-wrapper        { animation-delay: calc(var(--stagger) * (var(--i) + 3)); }

    /* Inside the cards: photo frame and info block are wrappers too. */

    .director-card-photo,
    .team-card-photo {
        opacity: 0;
        transform: scale(var(--enter-scale));
    }

    .director-card-info,
    .team-card-info {
        opacity: 0;
        transform: translateY(var(--offset-small));
    }

    .homepage-team-animate .director-card-photo,
    .homepage-team-animate .team-card-photo,
    .homepage-team-animate .director-card-info,
    .homepage-team-animate .team-card-info {
        animation: homepage-team-enter var(--transition-large) var(--ease) both;
    }

    .homepage-team-animate .director-card-photo,
    .homepage-team-animate .team-card-photo { animation-delay: calc(var(--stagger) * (var(--i) + 4)); }

    .homepage-team-animate .director-card-info,
    .homepage-team-animate .team-card-info  { animation-delay: calc(var(--stagger) * (var(--i) + 5)); }

    /* ─────────────────────────────────── Header ───────────────────────────────────── */

    .homepage-team-title {
        padding-bottom: var(--padding-xsmall);
        margin-bottom: var(--margin-medium);

        border-bottom: var(--border-width) solid var(--color);
        border-image: var(--splitter) 1;
    }

    .homepage-team-heading {
        margin: 0;
        padding: 0 var(--padding-xsmall);

        color: var(--color);
        font-size: var(--font-xlarge);
        font-weight: var(--font-weight-light);
        line-height: var(--line-height-tight);
    }

    .homepage-team-description {
        max-width: 45rem;
        margin: 0 0 var(--margin-medium);
        padding: 0 var(--padding-xsmall);

        color: var(--color-mute);
        font-size: var(--font-medium);
        line-height: var(--line-height-base);
    }

    /* ───────────────────────────────── Management row ─────────────────────────────── */

    .homepage-team-management {
        /* Width of one grid cell, so managers line up with the employee grid below. */
        --team-cell: calc((100% - (var(--team-columns) - 1) * var(--gap-small)) / var(--team-columns));

        display: flex;
        flex-wrap: wrap;
        gap: var(--gap-small);
        margin-bottom: var(--margin-medium);
    }

    /* Director: takes one cell at least, then grows to fill the free space. */
    .homepage-team-director-wrapper {
        flex: 1 1 var(--team-cell);
        container-type: inline-size;
    }

    /* Managers: exactly one cell each. */
    .homepage-team-manager-wrapper {
        flex: 0 0 var(--team-cell);
    }

    /* ─────────────────────────────── Employee grid ────────────────────────────────── */

    .homepage-team-grid {
        width: 100%;
        display: grid;
        grid-template-columns: repeat(var(--team-columns), 1fr);
        gap: var(--gap-small);
        align-items: stretch;
    }

    /* Wrappers stretch to the row height, the card inside fills the wrapper. */
    .homepage-team-director-wrapper,
    .homepage-team-manager-wrapper,
    .homepage-team-card-wrapper {
        display: flex;
    }

    .homepage-team-director-wrapper > *,
    .homepage-team-manager-wrapper > *,
    .homepage-team-card-wrapper > * {
        flex: 1;
        min-width: 0;
    }

    /* ─────────────────────────────────── Keyframes ────────────────────────────────── */

    @keyframes homepage-team-enter {
        to { opacity: 1; transform: none; }
    }

    /* ────────────────────────────────── Responsive ────────────────────────────────── */

    @media (max-width: 100rem)   { .homepage-team { --team-columns: 4; } }
    @media (max-width: 75rem)    { .homepage-team { --team-columns: 3; } }
    @media (max-width: 53.125rem) { .homepage-team { --team-columns: 2; } }
    @media (max-width: 31.25rem) { .homepage-team { --team-columns: 1; } }

    /* ───────────────────────────────── Reduced Motion ─────────────────────────────── */

    @media (prefers-reduced-motion: reduce) {
        .homepage-team *,
        .homepage-team *::before,
        .homepage-team *::after {
            animation: none;
            transition: none;
        }

        .homepage-team .homepage-team-title-wrapper,
        .homepage-team .homepage-team-description-wrapper,
        .homepage-team .homepage-team-director-wrapper,
        .homepage-team .homepage-team-manager-wrapper,
        .homepage-team .homepage-team-card-wrapper,
        .homepage-team .director-card-photo,
        .homepage-team .team-card-photo,
        .homepage-team .director-card-info,
        .homepage-team .team-card-info {
            opacity: 1;
            transform: none;
        }
    }
    ```

    ```css
    /* ──────────────────────────────────────────────────────────────────────────────── */
    /* ──────────────────────────────── NP Consultants ──────────────────────────────── */
    /* ────────────────────────────── director-card.css ─────────────────────────────── */
    /* ──────────────────────────────────────────────────────────────────────────────── */
    /* Card    : <div class="director-card"> .director-card-photo > img,            */
    /*           .director-card-info </div>                                         */
    /* Use     : works anywhere, link it after root.css. Position and intro         */
    /*           animation come from the section CSS, never from here.              */
    /* Layout  : picture beside the text. When the card's own width gets small      */
    /*           (container query on its wrapper) it stacks and centres instead.    */
    /* Hover   : motion only, no colour tints. Same moves as team-card.css.         */
    /* Tokens  : root.css only. Nothing is hardcoded in this file.                  */

    .director-card {
        display: flex;
        align-items: center;
        gap: var(--gap-large);
        padding: var(--padding-medium);

        background: var(--glass);
        border: var(--border-width) solid var(--border);
        border-radius: var(--border-radius-medium);
        box-shadow: var(--shadow-small);

        transition:
            box-shadow var(--transition-small) var(--ease),
            transform var(--transition-small) var(--ease);
    }

    /* Frame: clips the photo to a circle so the photo can zoom inside it. */
    .director-card-photo {
        width: var(--avatar-large);
        height: var(--avatar-large);
        flex-shrink: 0;
        overflow: hidden;

        border-radius: var(--border-radius-full);
        border: var(--border-width) solid var(--border);
        background: var(--photo-background);

        /* Ring, closed. Gap in the page colour, then a thin accent line. */
        box-shadow:
            0 0 0 0 var(--background),
            0 0 0 0 var(--accent);

        transition: box-shadow var(--transition-small) var(--ease);
    }

    .director-card-image {
        display: block;
        width: 100%;
        height: 100%;

        object-fit: contain;
        object-position: top center;

        transition: transform var(--transition-large) var(--ease);
    }

    .director-card-info {
        min-width: 0;
    }

    .director-card-info h3 {
        position: relative;
        display: inline-block;
        margin: 0 0 var(--gap-xsmall);
        padding-bottom: var(--margin-small);

        color: var(--color);
        font-size: var(--font-title);
    }

    /* Line that draws under the name from the left. */
    .director-card-info h3::after {
        content: "";
        position: absolute;
        inset: auto 0 0;
        height: var(--border-width);

        background: var(--accent);
        transform: scaleX(0);
        transform-origin: left;
        transition: transform var(--transition-large) var(--ease);
    }

    .director-card-info h4 {
        margin: 0 0 var(--gap-small);

        color: var(--accent);
        font-size: var(--font-medium);
    }

    .director-card-info ul {
        margin: 0;
        padding: 0;
        list-style: none;

        color: var(--color-mute);
        line-height: var(--line-height-base);
    }

    .director-card-info li {
        transition: transform var(--transition-small) var(--ease);
        transition-delay: calc(var(--stagger) * var(--n, 0));
    }

    /* ──────────────────────────────────── Hover ───────────────────────────────────── */

    @media (hover: hover) {
        .director-card:hover {
            box-shadow: var(--shadow-large);
            transform: translateY(var(--hover-lift));
        }

        .director-card:hover .director-card-photo {
            box-shadow:
                0 0 0 var(--ring-gap) var(--background),
                0 0 0 calc(var(--ring-gap) + var(--border-width)) var(--accent);
        }

        .director-card:hover .director-card-image {
            transform: scale(var(--zoom-small));
        }

        .director-card:hover .director-card-info h3::after {
            transform: scaleX(1);
        }

        .director-card:hover .director-card-info li {
            transform: translateY(var(--hover-lift));
        }
    }

    /* ────────────────────────────────── Stacked ───────────────────────────────────── */

    @container (max-width: 37.5rem) {
        .director-card {
            flex-direction: column;
            justify-content: center;
            text-align: center;
        }

        .director-card-info h3::after {
            transform-origin: center;
        }
    }

    /* ───────────────────────────────── Reduced Motion ─────────────────────────────── */

    @media (prefers-reduced-motion: reduce) {
        .director-card,
        .director-card-photo,
        .director-card-image,
        .director-card-info h3::after,
        .director-card-info li {
            transition: none;
        }
    }
    ```

    ```css
    /* ──────────────────────────────────────────────────────────────────────────────── */
    /* ──────────────────────────────── NP Consultants ──────────────────────────────── */
    /* ──────────────────────────────── team-card.css ───────────────────────────────── */
    /* ──────────────────────────────────────────────────────────────────────────────── */
    /* Card    : <div class="team-card"> .team-card-photo > img, .team-card-info </div> */
    /* Variant : add "team-card-management" for managers and assistants. Same card, */
    /*           but on mobile their picture is slightly larger than employees'.    */
    /* Use     : works anywhere, link it after root.css. Position and intro         */
    /*           animation come from the section CSS, never from here.              */
    /* Hover   : motion only, no colour tints. The card lifts, the photo zooms     */
    /*           inside its circle, a ring opens around it, a line draws under the  */
    /*           name and the details ripple in one after another (--n from JS).    */
    /* Tokens  : root.css only. Nothing is hardcoded in this file.                  */

    .team-card {
        position: relative;
        height: 100%;
        min-height: var(--card-height);

        display: flex;
        flex-direction: column;
        align-items: center;
        padding: var(--padding-small);

        text-align: center;
        background: var(--glass);
        border: var(--border-width) solid var(--border);
        border-radius: var(--border-radius-medium);
        box-shadow: var(--shadow-small);

        transition:
            box-shadow var(--transition-small) var(--ease),
            transform var(--transition-small) var(--ease);
    }

    /* Frame: clips the photo to a circle so the photo can zoom inside it. */
    .team-card-photo {
        width: var(--avatar-small);
        height: var(--avatar-small);
        margin-bottom: var(--gap-small);
        flex-shrink: 0;
        overflow: hidden;

        border-radius: var(--border-radius-full);
        border: var(--border-width) solid var(--border);
        background: var(--photo-background);

        /* Ring, closed. Gap in the page colour, then a thin accent line. */
        box-shadow:
            0 0 0 0 var(--background),
            0 0 0 0 var(--accent);

        transition: box-shadow var(--transition-small) var(--ease);
    }

    .team-card-image {
        display: block;
        width: 100%;
        height: 100%;

        object-fit: contain;
        object-position: top center;

        transition: transform var(--transition-large) var(--ease);
    }

    .team-card-info {
        flex: 1;
        width: 100%;

        display: flex;
        flex-direction: column;
    }

    .team-card-info h3 {
        position: relative;
        align-self: center;
        margin: 0 0 var(--gap-xsmall);
        padding-bottom: var(--margin-small);

        color: var(--color);
        font-size: var(--font-large);
    }

    /* Line that draws under the name from the centre outwards. */
    .team-card-info h3::after {
        content: "";
        position: absolute;
        inset: auto 0 0;
        height: var(--border-width);

        background: var(--accent);
        transform: scaleX(0);
        transition: transform var(--transition-large) var(--ease);
    }

    .team-card-info h4 {
        margin: 0 0 var(--gap-small);

        color: var(--accent);
        font-size: var(--font-small);
    }

    .team-card-info ul {
        margin: 0;
        padding: 0;
        list-style: none;

        color: var(--color-mute);
        font-size: var(--font-small);
        line-height: var(--line-height-base);
    }

    .team-card-info li {
        transition: transform var(--transition-small) var(--ease);
        transition-delay: calc(var(--stagger) * var(--n, 0));
    }

    /* ──────────────────────────────────── Hover ───────────────────────────────────── */

    @media (hover: hover) {
        .team-card:hover {
            box-shadow: var(--shadow-large);
            transform: translateY(var(--hover-lift));
        }

        .team-card:hover .team-card-photo {
            box-shadow:
                0 0 0 var(--ring-gap) var(--background),
                0 0 0 calc(var(--ring-gap) + var(--border-width)) var(--accent);
        }

        .team-card:hover .team-card-image {
            transform: scale(var(--zoom-small));
        }

        .team-card:hover .team-card-info h3::after {
            transform: scaleX(1);
        }

        .team-card:hover .team-card-info li {
            transform: translateY(var(--hover-lift));
        }
    }

    /* ────────────────────────────────── Responsive ────────────────────────────────── */

    @media (max-width: 31.25rem) {
        .team-card {
            min-height: auto;
        }

        .team-card-management .team-card-photo {
            width: var(--avatar-medium);
            height: var(--avatar-medium);
        }
    }

    /* ───────────────────────────────── Reduced Motion ─────────────────────────────── */

    @media (prefers-reduced-motion: reduce) {
        .team-card,
        .team-card-photo,
        .team-card-image,
        .team-card-info h3::after,
        .team-card-info li {
            transition: none;
        }
    }
    ```

    ```js
    // ────────────────────────────────────────────────────────────────────────────────
    // ──────────────────────────────── NP Consultants ────────────────────────────────
    // ─────────────────────────────── homepage-team.js ───────────────────────────────
    // ────────────────────────────────────────────────────────────────────────────────
    // File Type : Writer (InnerHTML)
    // Data      : /resources/data/team.json  (members[].group = director | management | employee)
    // Target    : <section class="homepage-team" id="homepage-team"></section>

    const section = document.getElementById("homepage-team");

    // Escape text before it goes into innerHTML
    const escapeHTML = (text) =>
        String(text).replace(/[&<>"']/g, (c) => ({ "&": "&amp;", "<": "&lt;", ">": "&gt;", '"': "&quot;", "'": "&#39;" })[c]);

    // Picture + name, role and details. cardClass is "director-card", "team-card" or "team-card team-card-management".
    // --n on each detail = its step in the hover ripple.
    function writeCard(member, cardClass) {
        const base = cardClass.split(" ")[0];
        const details = (member.details || []).map((item, n) => `<li style="--n:${n}">${escapeHTML(item)}</li>`).join("");
        return `
            <div class="${cardClass}">
                <div class="${base}-photo">
                    <img class="${base}-image" src="${escapeHTML(member.image)}" alt="${escapeHTML(member.name)}" loading="lazy">
                </div>
                <div class="${base}-info">
                    <h3>${escapeHTML(member.name)}</h3>
                    <h4>${escapeHTML(member.role)}</h4>
                    <ul>${details}</ul>
                </div>
            </div>`;
    }

    async function writeTeam() {
        const data = await (await fetch("/resources/data/team.json")).json();
        const pick = (group) => data.members.filter((member) => member.group === group);
        let step = 0; // --i: one stagger step per card, in reading order

        const directors = pick("director").map((member) => `
            <div class="homepage-team-director-wrapper" style="--i:${step++}">${writeCard(member, "director-card")}</div>`).join("");

        const managers = pick("management").map((member) => `
            <div class="homepage-team-manager-wrapper" style="--i:${step++}">${writeCard(member, "team-card team-card-management")}</div>`).join("");

        const employees = pick("employee").map((member) => `
            <div class="homepage-team-card-wrapper" style="--i:${step++}">${writeCard(member, "team-card")}</div>`).join("");

        section.innerHTML = `
            <div class="homepage-team-title-wrapper">
                <header class="homepage-team-title">
                    <h2 class="homepage-team-heading">${escapeHTML(data.title)}</h2>
                </header>
            </div>
            <div class="homepage-team-description-wrapper">
                <p class="homepage-team-description">${escapeHTML(data.description)}</p>
            </div>
            <div class="homepage-team-management">${directors}${managers}</div>
            <div class="homepage-team-grid">${employees}</div>`;

        // Play the entrance animation once, when the section scrolls into view
        new IntersectionObserver((entries, observer) => {
            if (entries[0].isIntersecting) {
                section.classList.add("homepage-team-animate");
                observer.disconnect();
            }
        }, { threshold: 0.1 }).observe(section);
    }

    writeTeam();
    ```


--- 

## Homepage  &bull; Contact Us
- This is a reminder-style of a block, this has a tagline and a button linking to `/contact/`
- has the top & bottom border images as `var(--splitter)` as given in the example code
- Example code:

    ```html
    <section class="homepage-contact" id="homepage-contact">
        <div class="homepage-contact-title-wrapper">
            <h2 class="homepage-contact-heading">Contact Us</h2>
        </div>

        <div class="homepage-contact-description-wrapper">
            <p class="homepage-contact-description">Tell us about your project and our team will get back to you with a plan.</p>
        </div>

        <div class="homepage-contact-button-wrapper">
            <a href="/contact/" class="button-1">Get in Touch</a>
        </div>
    </section>
    ```

    ```css
    /* ──────────────────────────────────────────────────────────────────────────────── */
    /* ──────────────────────────────── NP Consultants ──────────────────────────────── */
    /* ───────────────────────────── homepage-contact.css ───────────────────────────── */
    /* ──────────────────────────────────────────────────────────────────────────────── */
    /* Section : <section class="homepage-contact" id="homepage-contact"></section> */
    /* Content : written by /resources/js/homepage-contact.js from contact.json.    */
    /* Layout  : text left (title over description), button right, centred.         */
    /*           Mobile: one column, centred, button last.                          */
    /* Intro   : every block sits in a "-wrapper". Wrappers play the entrance.      */
    /* Start   : JS adds "homepage-contact-animate" to the section on scroll.       */
    /* Button  : <a class="button-1"> (button-1.css), styled separately.            */
    /* Tokens  : root.css only. Nothing is hardcoded in this file.                  */

    .homepage-contact {
        width: 100%;
        min-height: var(--grid-height-medium);
        margin: 0;
        padding: var(--padding-medium);

        display: grid;
        grid-template-columns: 1fr auto;
        grid-template-rows: auto auto;
        column-gap: var(--gap-medium);
        row-gap: var(--gap-xsmall);

        scroll-snap-align: start;

        background: var(--background);
        border-top: var(--border-width) solid var(--color);
        border-bottom: var(--border-width) solid var(--color);
        border-image: var(--splitter) 1;
    }

    /* ─────────────────────────────────── Intro ────────────────────────────────────── */

    .homepage-contact-title-wrapper,
    .homepage-contact-description-wrapper,
    .homepage-contact-button-wrapper {
        min-width: 0;
        opacity: 0;
    }

    .homepage-contact-title-wrapper       { transform: translateX(calc(var(--offset-large) * -1)); }
    .homepage-contact-description-wrapper { transform: translateX(calc(var(--offset-small) * -1)); }
    .homepage-contact-button-wrapper      { transform: scale(var(--enter-scale)); }

    .homepage-contact-animate .homepage-contact-title-wrapper,
    .homepage-contact-animate .homepage-contact-description-wrapper,
    .homepage-contact-animate .homepage-contact-button-wrapper {
        animation: homepage-contact-enter var(--transition-large) var(--ease) both;
    }

    .homepage-contact-animate .homepage-contact-title-wrapper       { animation-delay: var(--stagger); }
    .homepage-contact-animate .homepage-contact-description-wrapper { animation-delay: calc(var(--stagger) * 2); }
    .homepage-contact-animate .homepage-contact-button-wrapper      { animation-delay: calc(var(--stagger) * 3); }

    /* ─────────────────────────────────── Layout ───────────────────────────────────── */

    .homepage-contact-title-wrapper {
        grid-row: 1;
        grid-column: 1;
        align-self: end;
    }

    .homepage-contact-description-wrapper {
        grid-row: 2;
        grid-column: 1;
        align-self: start;
    }

    .homepage-contact-button-wrapper {
        grid-row: 1 / 3;
        grid-column: 2;
        align-self: center;
        margin-right: var(--margin-medium);
    }

    .homepage-contact-heading {
        margin: 0;

        color: var(--color);
        font-size: var(--font-xlarge);
        font-weight: var(--font-weight-bold);
        line-height: var(--line-height-tight);
    }

    .homepage-contact-description {
        max-width: 45rem;
        margin: 0;

        color: var(--color-mute);
        font-size: var(--font-medium);
        line-height: var(--line-height-base);
    }

    /* ─────────────────────────────────── Keyframes ────────────────────────────────── */

    @keyframes homepage-contact-enter {
        to { opacity: 1; transform: none; }
    }

    /* ────────────────────────────────── Responsive ────────────────────────────────── */

    @media (max-width: 37.5rem) {
        .homepage-contact {
            grid-template-columns: 1fr;
            grid-template-rows: auto auto auto;
            text-align: center;
            justify-items: center;
        }

        .homepage-contact-button-wrapper {
            grid-row: 3;
            grid-column: 1;
            margin: var(--margin-medium) 0 0;
        }
    }

    /* ───────────────────────────────── Reduced Motion ─────────────────────────────── */

    @media (prefers-reduced-motion: reduce) {
        .homepage-contact *,
        .homepage-contact *::before,
        .homepage-contact *::after {
            animation: none;
            transition: none;
        }

        .homepage-contact .homepage-contact-title-wrapper,
        .homepage-contact .homepage-contact-description-wrapper,
        .homepage-contact .homepage-contact-button-wrapper {
            opacity: 1;
            transform: none;
        }
    }
    ```

    ```css
    /* ──────────────────────────────────────────────────────────────────────────────── */
    /* ──────────────────────────────── NP Consultants ──────────────────────────────── */
    /* ───────────────────────────────── button-1.css ───────────────────────────────── */
    /* ──────────────────────────────────────────────────────────────────────────────── */
    /* Button  : <a href="..." class="button-1">Label</a>                           */
    /* Use     : works anywhere, link it after root.css. Position it from the       */
    /*           section CSS (margin, align-self), never from here.                 */
    /* Tokens  : root.css only. Nothing is hardcoded in this file.                  */

    .button-1 {
        position: relative;
        display: inline-block;
        overflow: hidden;
        padding: var(--padding-xsmall) var(--padding-medium);

        background: color-mix(in srgb, var(--accent) var(--mix-large), transparent);
        border: var(--border-width) solid var(--border);
        border-radius: var(--border-radius-full);

        color: var(--color-mute);
        text-decoration: none;
        font-family: var(--font-family);
        font-size: var(--font-medium);
        font-weight: var(--font-weight-bold);
        letter-spacing: var(--letter-spacing);
        user-select: none;
        cursor: pointer;

        transition:
            background var(--transition-small) var(--ease),
            box-shadow var(--transition-small) var(--ease),
            transform var(--transition-small) var(--ease);
    }

    /* Shine that sweeps across the button on hover. */
    .button-1::before {
        content: "";
        position: absolute;
        inset: 0;

        background: linear-gradient(
            120deg,
            transparent,
            color-mix(in srgb, var(--color) var(--mix-small), transparent),
            transparent
        );

        transform: translateX(calc(var(--shine-offset) * -1));
        transition: transform var(--transition-large) var(--ease);
        pointer-events: none;
    }

    .button-1:focus-visible {
        outline: var(--outline);
        outline-offset: var(--outline-offset);
    }

    .button-1:active {
        transform: scale(var(--press-scale));
    }

    /* ──────────────────────────────────── Hover ───────────────────────────────────── */

    @media (hover: hover) {
        .button-1:hover {
            background: var(--glass);
            box-shadow:
                var(--shadow-small),
                0 0 var(--gap-small) color-mix(in srgb, var(--accent) var(--mix-large), transparent);
            transform: translateY(var(--hover-lift)) scale(var(--hover-scale));
        }

        .button-1:hover::before {
            transform: translateX(var(--shine-offset));
        }
    }

    /* ───────────────────────────────── Reduced Motion ─────────────────────────────── */

    @media (prefers-reduced-motion: reduce) {
        .button-1,
        .button-1::before {
            transition: none;
        }
    }
    ```

    ```js
    // ────────────────────────────────────────────────────────────────────────────────
    // ──────────────────────────────── NP Consultants ────────────────────────────────
    // ───────────────────────────── homepage-contact.js ──────────────────────────────
    // ────────────────────────────────────────────────────────────────────────────────
    // File Type : Writer (InnerHTML)
    // Data      : /resources/data/contact.json
    // Target    : <section class="homepage-contact" id="homepage-contact"></section>

    const section = document.getElementById("homepage-contact");

    // Escape text before it goes into innerHTML
    const escapeHTML = (text) =>
        String(text).replace(/[&<>"']/g, (c) => ({ "&": "&amp;", "<": "&lt;", ">": "&gt;", '"': "&quot;", "'": "&#39;" })[c]);

    async function writeContact() {
        const data = await (await fetch("/resources/data/contact.json")).json();

        section.innerHTML = `
            <div class="homepage-contact-title-wrapper">
                <h2 class="homepage-contact-heading">${escapeHTML(data.title)}</h2>
            </div>
            <div class="homepage-contact-description-wrapper">
                <p class="homepage-contact-description">${escapeHTML(data.text)}</p>
            </div>
            <div class="homepage-contact-button-wrapper">
                <a href="${escapeHTML(data.button.href)}" class="button-1">${escapeHTML(data.button.label)}</a>
            </div>`;

        // Play the entrance animation once, when the section scrolls into view
        new IntersectionObserver((entries, observer) => {
            if (entries[0].isIntersecting) {
                section.classList.add("homepage-contact-animate");
                observer.disconnect();
            }
        }, { threshold: 0.3 }).observe(section);
    }

    writeContact();
    ```


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