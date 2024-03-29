# 💳 GitHub language card
![](./profile-card.svg)

This is a profile card made in a SVG, to be imported into a GitHub profile readme (or elsewhere). It works by using a ``foreignObject`` in a SVG.

---

## Usage
To use the card, either copy the contents of [``profile-card.svg``](./profile-card.svg) or otherwise download it. Then paste it into your personal git repository, and add an image tag in your readme, displaying the SVG, like this: ``![](path/to/profile-card.svg)``

### How to modify
Simply go into the SVG and add entries accordingly. There are 6 categories, all identified by ids; see the SVG as an example.

#### Minimal example
> [!NOTE]
> This does not include the rest of the SVG, you also need the headings and style. See the SVG file.
```html
<article id="language-card">
    <section class="category-container">
        <h4><span class="emoji">🔵</span> Category</h4>
        <ul>
            <div class="proficient">
                <li>🦝 Racoon.js</li>
            </div>
            <div class="learning">
                <li>💅 Girlboss</li>
            </div>
        </ul>
    </section>

    <section class="category-container" id="legend">
        <h4><span class="emoji">🗺️</span> Legend</h4>
        <ul>
        <div class="proficient">
            <li>💪 Proficient</li>
        </div>
        <div class="good">
            <li>👍 Good</li>
        </div>
        <div class="average">
            <li>👌 Average</li>
        </div>
        <div class="belowaverage">
            <li>🤏 Below average</li>
        </div>
        <div class="accquainted">
            <li>💡 Accquainted</li>
        </div>
        <div class="learning">
            <li>🧠 Learning</li>
        </div>
        </ul>
    </section>
</article>
```

Note you may need to modify the CSS to accomodate more languages.

### Quirks
Don't forget to change the SVG height and width!

## Acknowledgements
While making this, I used [this CSS animation](https://codepen.io/alvaromontoro/pen/rNwVpdd) as reference, and [this guide](https://css-tricks.com/snippets/css/typewriter-effect/). Otherwise everything else is my own work.
