A collection of random CSS snippets to use with custom Discord clients such as Vencord, to make using Discord just a little but more bearable.
> This is more of a personal archive/backup but I figured someone may have a use for it as well.

---

Hide "Nitro", "Shop" and "Quests" buttons at the top of the DMs list:
```css
li:has(div > [href="/shop"]),
li:has(div > [href="/store"]),
li:has(div > [href="/quest-home"]){
    display: none;
}
```

Hide "Send Gift" button in the chat text input:
```css
[aria-label="Send a gift"]{
    display: none;
}
```

Hide App launcher button in the chat text input:
```css
[aria-label="Apps"]{
	display: none;
}
```

Hide reaction suggestions when hovering a message:
```css
[aria-label^="Click to react with"] {
    display: none;
}
```

hide Checkpoint button:
```css
[aria-label="Checkpoint"]{
    display: none;
}
```

Hide user backgrounds in the member list:
```css
*[class*="nameplated"]{
    & div[style*="background"]{
    outline: white solid 1px;
    display: none;
    }
}
```
Remove custom user fonts on servers:
```css
*[class*="username"]{
    font-family: var(--font-primary) !important;
}
```

Remove avatar decorations:
```css
*[class*="avatarDecoration"]{
    display: none !important;
}
```

Remove user backgrounds in DMs list:
```css
li[role="listitem"]{
    & div[style*="background"]{
        background: none !important;
    }
    & div[class*="videoContainer"]{
        display: none !important;
    }
}
```

Hide Profile effects
```css
*[class*="profileEffect"]{
    display: none !important;
}
```

Attempt at removing hover effects on usernames in DMs list, works but could probably be improved:
```css
div:has(span[data-username-with-effects]){
    --custom-display-name-styles-main-color: var(--text-tertiary) !important;
    --custom-display-name-styles-light-1-color: var(--text-tertiary)!important;
    --custom-display-name-styles-light-2-color: var(--text-tertiary)!important;
    --custom-display-name-styles-dark-1-color: var(--text-tertiary)!important;
    --custom-display-name-styles-dark-2-color: var(--text-tertiary)!important;
}
span[data-username-with-effects]{
    font-family: var(--font-primary) !important;
    color: var(--text-tertiary) !important;
    animation: none paused !important;
    -webkit-text-stroke-color: transparent !important;
    -webkit-text-stroke-width: 0px !important;
}
div[aria-roledescription="Message"] > div > h3 > span:first-child > span:first-child{
    font-family: var(--font-primary) !important;
    animation: none !important;
}
```
  
"Amp up your profile" container on popup profile:
```css
aside[class*="upsellContainer"]{
    display: none;
}
```
"Unlock every emoji with Nitro" popup in Emoji selector: 
```css
#emoji-picker-grid{
    & [class*="upsellContainer"]{
        display: none;
    }
}
```