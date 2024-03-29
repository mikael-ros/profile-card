# 🪪 GitHub Language Card
![](./profile-card.svg)

This is a profile card made in a SVG, that can be imported into a GitHub profile readme (or elsewhere). It works by using a ``foreignObject`` inside of an SVG, which allows you to use HTML and CSS beyond what the GitHub sanitization process allows.

---

## 🔨 Usage
To use the card, either copy the contents of [``profile-card.svg``](./profile-card.svg) or download it. Then paste it into your profile git repository, and add an image tag in your profile readme, displaying the SVG, like this: ``![](path/to/profile-card.svg)``. The path can also be to the raw file, if hosted in a seperate repository.

### 🪚 How to modify
Simply go into the SVG and add entries accordingly. There are 6 proficiencies, all identified by ids; see the SVG as an example.

#### 📁 Card
The entire thing is contained within an ``<article>`` tag, which is necessary to make it display properly on all GitHub themes. See the minimal example further down.

#### ⌨️ Typing animation
The typing animation is **implemented with keyframes**, changing the content each keyframe. You can with some effort change this text. _If your text is the same length or shorter you can get away with less editing._

> [!TIP]
> Divide 100% by the amount of letters you want to type and increment the keyframe by that. You can experiment a lot with this though.
> Also see [this code example](https://codepen.io/alvaromontoro/pen/rNwVpdd) if you want to change the type of typing marker. Default is ``_``.

#### 🗂 Categories
Every category is contained in it's own ``<section class="category-container"``, containing a ``<h4>`` element and an ``<ul>`` element.

```html
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
```

##### 😜 Emojis/icons
Either put the emoji inline, in the ``<h4>`` tag or put it inside ``<span class="emoji">😎</span>``. The ``emoji`` class will make it into it's own little "bubble".

_Unfortunately it's not trivial to include any old icon (you have to convert it into BASE64) which is why I've opted for emojis._

#### 💼 Proficiencies
There are 6 levels built-in. They are as follows:
- 💪 ``proficient``: Languages you can write in with your **eyes (almost) closed**
- 👍 ``good``: Languages you know well, **comfortably enough to be opinionated**
- 👌 ``average``: Languages you are average in, **about as competent as most people**
- 🤏 ``below average``: You aren't fully comfortable in this language, but **you can hack something together with effort**
- 💡 ``accquainted``: You have come across and had to use this language as part of a course or similar, but didn't get the hang of it. Despite, **you can still write a couple lines and read the syntax**
- 🧠 ``learning``: What it **says on the tin**

These are marked by wrapping the corresponding ``<li>`` elements in a ``<div>`` with the class set to one of the above, like:
```html
<div class="proficient">
    <li>🦝 Racoon.js</li>
</div>
```
##### 🖌 Colors
There are 6 colors corresponding to the 6 proficiencies, which you can change easily by editing CSS variables at the top of the SVG. 

### 🗒 Minimal example
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
> [!NOTE]
> Note you may need to modify the CSS to accomodate more languages, they just get cut off for now.

> [!TIP]
> Don't forget to change the SVG height and width at the top of the file, or it might either be too large or get cut off. Also set the ``language-card`` height.

## 🫡 Acknowledgements
> [!IMPORTANT]
> While making this, I used [this CSS animation](https://codepen.io/alvaromontoro/pen/rNwVpdd) as reference, and [this guide](https://css-tricks.com/snippets/css/typewriter-effect/). Otherwise **everything else is my own work.** This repository is licensed under the [MIT license](LICENSE), please accquaint yourself with it before using this code.

---
> This repository is updated in conjunction with my profile, mainly so it is easier to maintain. Not every commit is therefore relevant functionality - some are simply me updating my profile.