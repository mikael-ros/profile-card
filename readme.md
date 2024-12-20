# 🪪 GitHub Language Card
![](./profile-card.svg)

This is a profile card made inside of a SVG, that can be imported into a GitHub profile readme (or elsewhere). It works by using a ``foreignObject`` inside of an SVG, which allows you to use HTML and CSS beyond what the GitHub sanitization process allows.

<a href='https://ko-fi.com/Z8Z212GZR6' target='_blank'><img height='60' style='border:0px;height:60px;' src='https://storage.ko-fi.com/cdn/kofi1.png?v=3' border='0' alt='Buy Me a Coffee at ko-fi.com' /></a>

---

## 🔨 Usage
To use the card, either copy the contents of [``profile-card.svg``](./profile-card.svg) or download it. Then paste it into your profile git repository, and add an image tag in your profile readme, displaying the SVG, like this: ``![Profile card](path/to/profile-card.svg)``. The path can also be to the raw file, if hosted in a seperate repository.

### 🪚 How to modify
Simply go into the SVG and add entries accordingly. There are 6 proficiencies, all identified by ids; see the SVG as an example.

> [!TIP]
> When editing the SVG, open the file locally in the browser. It is a more accurate preview of how it will look in the real world.

#### 📁 Card
The entire thing is contained within an ``<figure>`` tag, which is necessary to make it display properly on all GitHub themes. See the minimal example further down.

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
    <ul class="skill-list">
        <li level="proficient">🦝 Racoon.js</li>
        <li level="learning">💅 Girlboss</li>
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

These are marked by wrapping the corresponding skill in an ``<li>`` element with the ``level`` set to one of the above, like:
```html
<li level="proficient">🦝 Racoon.js</li>
```
> [!TIP]
> As of v3, the card can now wrap lists, meaning you can add as many skills as you want. _Don't forget to set the SVG size, though_

##### 🖌 Colors
There are 6 colors corresponding to the 6 proficiencies, which you can change easily by editing CSS variables at the top of the SVG. 

### 🗒 Minimal example
> [!NOTE]
> This does not include the rest of the SVG, you also need the headings and style. See the SVG file.
```html
<figure id="language-card">
    <section class="category-container">
        <h4><span class="emoji">🔵</span> Category</h4>
        <ul class="skill-list">
            <li level="proficient">🦝 Racoon.js</li>
            <li level="learning">💅 Girlboss</li>
        </ul>
    </section>

    <section class="category-container" id="legend">
        <h4><span class="emoji">🗺️</span> Legend</h4>
        <ul class="skill-list">
            <li level="proficient">💪 Proficient</li>
            <li level="good">👍 Good</li>
            <li level="average">👌 Average</li>
            <li level="belowaverage">🤏 Below average</li>
            <li level="accquainted">💡 Accquainted</li>
            <li level="learning">🧠 Learning</li>
        </ul>
    </section>
</figure>
```

> [!TIP]
> Don't forget to change the SVG height and width at the top of the file, or it might either be too large or get cut off. Also set the ``language-card`` height.

---

## 👋 Attributing

While it is not necessary, **I would be happy if you referred** to this repo when using the card. I would also love to see what you create with it!

One way to do so is by making the image itself a link, like:
```markdown
    [![Profile card, by mikael-ros](<path to your profile card>)](https://github.com/mikael-ros/profile-card)
```

> [!IMPORTANT]
> This repository is licensed under the [MIT license](LICENSE), please accquaint yourself with it before using this code.

---

## 🫡 Acknowledgements
> [!IMPORTANT]
> While making the typing animation, I used [this CSS animation](https://codepen.io/alvaromontoro/pen/rNwVpdd) and [this guide](https://css-tricks.com/snippets/css/typewriter-effect/), for reference - though it has since strayed from those roots. Otherwise **everything else is my own work.** 

---
> This repository is updated in conjunction with my profile, mainly so it is easier to maintain. Not every commit is therefore relevant functionality - some are simply me updating my profile.