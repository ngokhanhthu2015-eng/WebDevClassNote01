# Rina's Garden 

## 1. Project Overview

**Rina's Garden** is a website introducing floriography, the language of flowers. It explores how flowers can communicate emotions, meanings, and personal stories without words.

The website combines flower symbolism, visual storytelling, and music to create a calm, journal-like experience. Users can explore the meanings of different flowers, discover a connection between a flower and a song, and use the contact form to reflect on their feelings.

### Project Goals

- Introduce users to floriography and the symbolism of flowers.
- Present flower meanings through a simple, visually organized layout.
- Connect flower symbolism with music through a Spotify embed.
- Provide a form where users can share their feelings or stories.
- Create a website that is easy to navigate on different screen sizes.

## 2. Technologies Used

- **HTML5:** Structures the website content, navigation, flower cards, embedded music, and contact form.
- **CSS3:** Controls the visual design, spacing, typography, colors, layout, and responsive behavior.
- **Google Fonts:** The HTML links to DM Sans and Playfair Display. These fonts still need to be applied consistently in the CSS.
- **Spotify Embed:** Displays a Spotify player within the website.
- **GitHub Pages:** Used to publish the website online.

## 3. Website Structure

The website is organized into the following sections:

| Section | Description |
|---|---|
| Home | Introduces Rina's Garden and its theme. |
| Your Flowers | Presents flowers and their symbolic meanings. |
| Lyrics | Connects the calla lily with the song “calla” by wave to earth. |
| Find Your Flowers | Provides a form for visitors to share their feelings and stories. |

The navigation menu uses anchor links to help users move between sections on the same page.

## 4. HTML Code Snippet: Contact Form

The contact form uses HTML form elements to collect information from visitors.

```html
<form action="#" method="post">
    <label for="name">Your name</label>
    <input
        type="text"
        id="name"
        name="name"
        required
    >

    <label for="email">Your email</label>
    <input
        type="email"
        id="email"
        name="email"
        required
    >

    <label for="story">Your story</label>
    <textarea
        id="story"
        name="story"
        rows="5"
    ></textarea>

    <button type="submit">Send Your Story</button>
</form>
```

### Explanation

- `<form>` groups the fields used to collect information.
- `<label>` describes each field so users understand what to enter.
- `<input type="text">` collects the visitor's name.
- `<input type="email">` collects an email address and provides basic email-format validation.
- `required` prevents the browser from submitting the form when a required field is empty.
- `<textarea>` gives users more space to write a personal story.
- `<button type="submit">` allows users to submit the form.

**Current limitation:** The form is a front-end feature. It does not yet send or store submissions because no back-end service or form-processing endpoint has been connected.

## 5. CSS Code Snippet: CSS Variables and Color Palette

The website uses CSS custom properties to keep its color palette consistent.

```css
:root {
    --color-background: #F8F4ED;
    --color-paper: #FFFCF7;
    --color-text: #352F2B;
    --color-muted: #756D64;
    --color-accent: #8B4B5A;
    --color-accent-dark: #683543;
    --color-border: #E3D9CC;
    --color-green: #64745B;
}
```

### Explanation

- `:root` defines variables that can be reused throughout the stylesheet.
- Each variable stores a color for a specific purpose, such as the background, text, or accent color.
- Using `var(--color-background)` instead of repeating a hex code makes the CSS easier to maintain.
- If a color needs to change, I can update its value in one place rather than searching through the entire stylesheet.

The warm background colors and muted accent tones support the website's botanical and reflective theme.

## 6. CSS Code Snippet: Box Model

```css
* {
    box-sizing: border-box;
}
```

### Explanation

This rule applies `box-sizing: border-box` to every element.

By default, an element's declared width may not include its padding and border. With `border-box`, the width includes the content, padding, and border. This makes it easier to control element sizes and align sections consistently.

## 7. CSS Code Snippet: Flexbox Layout

Flexbox is used to arrange elements in the hero section and organize the flower cards.

```css
.hero {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    gap: 40px;
    padding: 70px 6%;
}

.hero > * {
    flex: 1;
    min-width: 0;
}
```

### Explanation

- `display: flex` places the hero's child elements in a flexible layout.
- `flex-direction: row` arranges the elements horizontally.
- `justify-content: space-between` distributes space between the elements.
- `align-items: center` aligns the elements vertically.
- `gap: 40px` adds space between the elements.
- `flex: 1` allows the child elements to share available space.
- `min-width: 0` allows flex items to shrink when necessary instead of overflowing because of their content.

**Layout note:** The current flower-card section also uses Flexbox with `flex-wrap: wrap`. CSS Grid is not currently implemented; it could be explored as an alternative layout method in a future iteration.

## 8. CSS Code Snippet: Hover Effect

The navigation links change color when a visitor hovers over them.

```css
.nav-links a {
    transition: color 0.2s ease;
}

.nav-links a:hover {
    color: var(--color-accent);
}
```

### Explanation

- `:hover` applies a style when the pointer is over a navigation link.
- `color: var(--color-accent)` changes the link to the website's accent color.
- `transition: color 0.2s ease` makes the color change happen smoothly rather than instantly.

This small interaction provides visual feedback and makes the navigation feel more responsive.

## 9. Embedded Music: Spotify

The Lyrics section includes a Spotify player for “calla” by wave to earth.

The player is embedded using an HTML `<iframe>`, which allows content from Spotify to appear inside the webpage without building a music player from scratch.

The song is connected to the calla lily section through the website's theme of emotions and symbolism. This adds an audio element to the experience and supports the idea that flowers and music can both express feelings.

The embedded player depends on Spotify's availability and the visitor's device or browser settings.

## 10. Responsive Design: Media Queries

The stylesheet includes a media query for screens with a maximum width of 768 pixels.

```css
@media (max-width: 768px) {
    .nav-inner {
        flex-direction: column;
        justify-content: center;
        padding: 16px 0;
        gap: 12px;
    }

    .nav-links {
        flex-wrap: wrap;
        justify-content: center;
        gap: 12px 18px;
        font-size: 0.82rem;
    }
}
```

### Explanation

- `@media (max-width: 768px)` applies these styles when the viewport is 768 pixels wide or narrower.
- `flex-direction: column` stacks the navigation elements vertically.
- `flex-wrap: wrap` allows navigation links to move onto additional lines when space is limited.
- `justify-content: center` centers the navigation links.
- Smaller gaps and font sizes help the navigation fit on narrow screens.

The purpose of this media query is to make the navigation easier to use on mobile devices. The current responsive rules mainly address the navigation, so other sections still need additional testing and adjustments.

## 11. Current Limitations

The current version establishes the main content and visual structure, but several areas could be improved:

- The contact form does not yet connect to a service that receives submissions.
- Responsive styling is currently limited mainly to the navigation menu.
- The navigation hover effect changes color but does not yet include a transform or animation.
- Google Fonts are linked in the HTML, but the stylesheet still needs to use the intended fonts consistently.
- The flower cards could include more detailed descriptions and additional flower varieties.
- The website needs testing on an actual mobile phone to check its layout and usability.

## 12. Next Steps

If I had more time to develop Rina's Garden, I would:

1. **Improve responsive design:** Add media queries for the hero section, flower cards, music player, and contact form.
2. **Add more interactions:** Introduce subtle animations or hover effects to make the website feel more engaging.
3. **Improve positioning:** Experiment with CSS positioning to place decorative flower elements and animations more precisely.
4. **Expand flower content:** Add more flower cards, images, and detailed explanations of their symbolism.
5. **Improve navigation:** Explore a dropdown menu or a navigation bar that remains visible while scrolling.
6. **Connect the contact form:** Add a form-processing service so submissions can be received.
7. **Refine typography:** Apply the linked Google Fonts consistently throughout the website.
8. **Test across devices:** Check the layout on an actual phone and make adjustments based on the results.

## 13. Project Files

The project repository should contain:

- `index.html`: the website's HTML structure.
- `style.css`: the website's visual styling and responsive rules.
- `README.md`: project documentation.
- 
**Live Website:**

