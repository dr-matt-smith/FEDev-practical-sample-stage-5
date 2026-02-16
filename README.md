# FEDev-practical-sample-stage-5

NOTE: A Captioned video work through of this stage has been published at:
- (coming soon)

This document summarises the steps I took when creating my solution to the sample FEDev Practial 1

The stages of development required are:
```
Stage 1. Basic HTML structure for 2 pages: “index.html” and “characters.html”
   a. No CSS
   b. No links
   c. No images

Stage 2. Add images

Stage 3. Add nav links

Stage 4. Add CSS, to make the pages look like the provided screenshots
   a. Using CSS style rules in 1 or more “.css” files

Stage 5. Refactor the website as a Svelte(kit) project
   a. Demonstrate reusable Svelte components, such as:
       i. Nav bar
       ii. page footer

Stage 6. Add a third “merchandise” page
   a. Add a link to this page in the nav bar
   b. Style this in a similar style to the other 2 pages
   c. Find images from the web for several merchandise items
   d. Add a form at the bottom of this page asking for:
       i. Name / email address / postal address
       ii. (you do NOT have to write code to process this forms submission)

Stage 7. For an ‘A’ grade illustrate some/all of the following:
   a. Replacing standard CSS rules with TailWindCSS
   b. Populating the merchandise page contents by looping through JSON data
   (rather than hard coded page content)
   c. Publish the site as static pages via GitHub Actions
```

Stage 5. Refactor the website as a Svelte(kit) project


## Make this a SvelteKit project

first, let's make this a SvelteKit project

1. at the terminal, create a new SveletKit project in the project folder, using `npx sv create`
   - agree to create in current project folder (it's not empty - it has our images and HTML files etc.)
   - create a SvelteKit minimal project
   - with JavaScript JSDoc (NOT TypeScript)
   - add TailWindCSS (typograpy and forms)
   - and user **npm** as your package manager

2. Test SvelteKit is up and running with 

   ```bash
   npm run dev -- --open
   ```

   - you should see the default `Welcome to SvelteKit` 2 lines of text

## Get the page body HTML into Svelte pages

1. copy your `/images` folder into `/static`
   - so you should now have all your images in `/static/images`
   - your images file paths should all work now in your Svelte pages

1. from `index.html` copy all the content inside `<body>` to replace the default content of `/src/routes/+page.svelte`
   
   ```html 
   <header>
      <img src="/images/title.png" alt="Rings of power logo" />
   </header>
   
   <nav>
      <ul>
         <li>
            <a href="/">HOME</a>
         </li>
         <li>
            <a href="/characters.html">CHARACTERS</a>
         </li>
      </ul>
   </nav>
   
   <main>
      <img src="/images/homeimage.jpg" alt="Rings of power - splash image" />
   </main>
   
   <footer>
      <hr>
      <img src="/images/prime_logo.png" alt="Prime logo" />
      <br>
      The Rings of Power &copy; 2024
   </footer>
   ```

1. in `<nav>` change the URL of the characters page link to just `/characters`:

   ```html
      <nav>
         <ul>
            <li>
               <a href="/">HOME</a>
            </li>
            <li>
               <a href="/characters">CHARACTERS</a>
            </li>
         </ul>
      </nav>
   ```

1. create a folder `/routes/characters`

1. create a `+page.svelte` file in your new folder, so you are creating file `/routes/characters/+page.svelte`

1. from `characters.html` copy all the content inside `<body>` into `/src/routes/+page.svelte`

   ```html
   <header>
      <img src="/images/title.png" alt="Rings of power logo" />
   </header>
   
   <nav>
      <ul>
         <li>
            <a href="/">HOME</a>
         </li>
         <li>
            <a href="/characters">CHARACTERS</a>
         </li>
      </ul>
   </nav>
   
   <main>
      <div class="row">
         <div class="col4">
            <h3>
               GALADRIEL
            </h3>
            <p>
   
               Galadriel, an Elf is a key part of the story. We meet her in the Lord of the Rings, when she
               welcomes the Fellowship to Lothlórien. In The Rings of Power, we meet a younger Galadriel who
               is a very different Galadriel: a fierce warrior who we meet on a mission to find Sauron after her
               brother died at his hands.
            </p>
         </div>
   
         <div class="col4">
            <img src="images/galadriel.jpg" alt="galadriel.jpg" class="rounded_right">
         </div>
   
         <div class="col4">
            <img src="images/halbrand.jpg" alt="halbrand.jpg" class="rounded_left">
         </div>
   
         <div class="col4">
            <h3>
               HALBRAND
            </h3>
            <p>After abandoning her ship to continue her mission to locate Sauron, she’s left adrift in the
               Sundering Seas before a broken boat full of humans rescue her. Among them is Halbrand who
               develops an uneasy alliance with Galadriel as the pair begin their journey to the island of
               Numenor.
            </p>
         </div>
      </div>
   
      <div class="row">
         <div class="col4">
            <h3>
               ELROND
            </h3>
            <p>Elrond, the half-elf and the future leader of Rivendell. We meet younger version of Elrond as a
               young politician who finds himself kept out of key discussions as he is not yet a lord. However,
               Elrond is soon tasked with another mission, helping the legendary smith Celebrimbor.
            </p>
         </div>
         <div class="col4">
            <img src="images/elrond.jpg" alt="elrond.jpg" class="rounded_right">
         </div>
         <div class="col4">
            <img src="images/durin.jpg" alt="durin.jpg"  class="rounded_left">
         </div>
   
         <div class="col4">
            <h3>
               PRINCE DURIN IV
            </h3>
            <p>
               During the Second Age, Khazad-dûm was the home to the dwarven kingdom, long before it falls
               into ruin. The kingdome is ruled over by King Durin III, who is supported by his son Prince Durin
               IV. We meet Durin IV burdened with the responsibility of keeping their kingdom thriving, and
               protecting it from outsiders.
            </p>
         </div>
      </div>
   
      <div class="row">
         <div class="col4">
            <img src="images/disa.jpg" alt="disa.jpg"  class="rounded_left">
            <h3>
               DISA
            </h3>
            <p>
               Disa is Durin IV’s wife, who lives with him and their children in Khazad-dûm. Disa is also noted for
               her beautiful singing voice and fierceness.
            </p>
         </div>
   
         <div class="col4">
            <img src="images/arondir.jpg" alt="arondir.jpg"  class="rounded_right">
   
            <h3>
               ARONDIR
            </h3>
            <p>
               Arondir is a Silvan Elf soldier stationed in the Southlands, a station set up to keep an eye on the
               humans of the realm, after they allied with Morgoth during the First Age.
            </p>
         </div>
   
         <div class="col4">
            <img src="images/gandalf.jpg" alt="gandalf.jpg"  class="rounded_left">
            <h3>
               THE STRANGER
            </h3>
            <p>
               A mysterious character for the moment. Nori spots him after a meteor lands in the woods where
               she lives. But the tall man doesn’t speak their language and is like no one they’ve ever seen
               before.
            </p>
         </div>
   
         <div class="col4">
            <img src="images/nori.jpg" alt="nori.jpg"  class="rounded_right">
            <h3>
               NORI
            </h3>
            <p>
               Nori is one of the Harfoots, the early predecessors to the Hobbits, who migrate with the seaso
            </p>
         </div>
      </div>
   </main>
   
   <footer>
      <hr>
      <img src="/images/prime_logo.png" alt="Prime logo" />
      <br>
      The Rings of Power &copy; 2024
   </footer>
   ```
   
1. again, in `/routes/characters/+page.svelte` in element `<nav>` change the URL of the characters page link to just `/characters`:
   - you should now have working links between your two pages (but no CSS yet ...)

## Implement global styles in `/routes/+layout.svelte`

We want all the pages in our website to have the same body.

We can put global styles into `/routes/+layout.svelte`.

Body is a bit special, since each Svelte page creates content for inside the body. However, Svelte gives us a special style syntax for global changes to the body element: `:global(body)`


Learn about global styles rules for Svelte at:
   - https://svelte.dev/docs/svelte/global-styles

The default content of `/routes/+layout.svelte` is a follows:

```html
<script>
   import './layout.css';
   import favicon from '$lib/assets/favicon.svg';

   let { children } = $props();
</script>

<svelte:head><link rel="icon" href={favicon} /></svelte:head>
{@render children()}
```

So we can simply add a new style rule for all body elements of our website as follows:
```html
<script>
   import './layout.css';
   import favicon from '$lib/assets/favicon.svg';

   let { children } = $props();
</script>

<svelte:head><link rel="icon" href={favicon} /></svelte:head>
{@render children()}

<style>
   :global(body) {
      background: url("/images/background.png") no-repeat center center fixed;
      background-size: cover;

      color: white;
      background-color: #a07a21;
   }
</style>
```

REMEMEBER: Style rules go inside a `<style>` element, usually at the end of a Svelte file.

## setting values for the HTML `<head>` in Svelte(Kit)

The basic HTML elements in a `.svelte` file are for the body of a page. If we want to set values for the head, we need to use `<svelte:head>`.

So to set the title for the home page (`/routes/+page.svelte`):

   ```html
   <svelte:head>
        <title>Rings of power - home page</title>
   </svelte:head>
   ```

Do the same to set the title for the characters page (`/routes/characters/+page.svelte`):

Learn more about `<svelte:head>` at:
   - https://svelte.dev/docs/svelte/svelte-head

## Making the navigation a component

We can create reusable components in `/lib/components`. A common component for most web sites is a navigation bar.

Do the following:

1. Create folder `/lib/components` (if it doesn't already exist)

1. Create Svelte file `Nav.svelte` (NOTE the capital first letter) in this folder (`/lib/components/Nav.svete`):

1. Copy the HTML for the navigation bar into our new file, also copy the CSS rules from `/css/nav.css`
   - so `/lib/components/Nav.svete` should now contain:
   
   ```html 
   <nav>
      <ul>
         <li>
            <a href="/">HOME</a>
         </li>
         <li>
            <a href="/characters">CHARACTERS</a>
         </li>
      </ul>
   </nav>
   
   <style>
      nav {
         display: flex;
   
         background-color: black;
         margin-bottom: 1rem;
      }
   
      nav ul {
         list-style-type: none;
         margin: 0 auto;
         padding: 1rem;
      }
   
      nav ul li {
         display: inline;
      }
   
      nav a {
         text-decoration: none;
         /*color: gold;*/
         color: #9e8545;
         text-align: center;
         width: 10rem;
         padding: 1rem;
      }
   
      nav a:hover {
         background: url("/images/hover.png") center center;
         background-size: cover;
      }
   </style>
   ```
   
1. Now for our Svelte index (`/routes/+page.svelte') and characters page (`/routes/characters/+page.svelte'), we need to import and use this component.
   - add a `<script>` section at the begining of the code for both these pages, to import out Nav component

   ```html
   <script>
      import Nav from '$lib/components/Nav.svelte';
   </script>
   ```

1. we can now use this component in our code. Write `<Nav />` where our `<nav>` navigation bar code used to be
   - so the code for our index page (`/routes/+page.svelte') now looks as follows:
      
   ```html
   <script>
      import Nav from '$lib/components/Nav.svelte';
   </script>
      
   <svelte:head>
      <title>Rings of power - home page</title>
   </svelte:head>
      
   <header>
      <img src="/images/title.png" alt="Rings of power logo" />
   </header>
      
   <Nav />
      
   <main>
      <img src="/images/homeimage.jpg" alt="Rings of power - splash image" />
   </main>
      
   <footer>
      <hr>
      <img src="/images/prime_logo.png" alt="Prime logo" />
      <br>
      The Rings of Power &copy; 2024
   </footer>
   ```

  - and the beginning of our characters page (`/routes/characters/+page.svelte`) looks like this;

     ````html
     <script>
         import Nav from '$lib/components/Nav.svelte';
     </script>
      
     <svelte:head>
     <title>Rings of power - characters page</title>
     </svelte:head>
      
     <header>
         <img src="/images/title.png" alt="Rings of power logo" />
     </header>
      
     <Nav />
      
     <main>
         <div class="row">
             <div class="col4">
                 <h3>
                     GALADRIEL
                 </h3>
                 <p>
     ```

  1. in the same way as above, we can create a `Header` and `Footer` Svelte components, combining their HTML and CSS:
     - so our header (`/lib/components/Header.svelte`) contains:

     ```html
     <header>
        <img src="/images/title.png" alt="Rings of power logo" />
     </header>
   
     <style>
        header {
           text-align: center;
           padding-bottom: 1rem;
        }
   
        header img {
           display: inline-block;
           width: 40%;
        }
     </style>
     ```

   - and so our footer (`/lib/components/Footer.svelte`) contains:

      ```html
      <script>
      </script>
      
      <footer>
         <hr>
         <img src="/images/prime_logo.png" alt="Prime logo" />
         <br>
         The Rings of Power &copy; 2024
      </footer>
      
      <style>
         footer {
            text-align: center;
            padding: 1rem;
         }
      
         footer img {
            display: inline-block;
            width: 5%;
         }
      </style>
      ```
  - NOTE: I had to add `display: inline-block` rules for both the header and footer, to get the images to center ...

## Styling the characters page content

The final step to complete the upgrade of our project to be a SvelteKit project is to add the CSS for styling the row and column content in the characters page

So add the following CSS rules (taken from `/css/main.css`) to the end of Svelte characters page (`/routes/characters/+page.svelte`):

   ```html
   <style>
      .row {
         padding: 0.5rem;
         display: flex;
      }
   
      .col4 {
         width: 25%;
         padding: 0.2rem;
         text-align: justify;
      }
   
      .col4 h3 {
         letter-spacing: 0.4rem;
      }
   
      .col4 p, .col4 h3 {
         padding: 0 1.5rem;
         font-size: 1cqw;
      }
   
      .rounded_left {
         border-radius: 20% 0 0 20%;
      }
   
   
      .rounded_right {
         border-radius: 0 20% 20% 0;
      }
   </style>
   ```


