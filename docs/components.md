# Components

MDX Deck includes a few built-in components to help with creating presentations.

## Head

Use the `<Head />` component to set content in the document head.

```mdx
// example for twitter cards
import { Head } from 'mdx-deck'

<Head>
  <title>My Presentation</title>
  <meta name="twitter:card" content="summary_large_image" />
  <meta name="twitter:site" content="@jxnblk" />
  <meta name="twitter:title" content="My Presentation" />
  <meta name="twitter:description" content="A really great presentation" />
  <meta name="twitter:image" content="https://example.com/card.png" />
</Head>
```

## Image

Use the `<Image />` component to render a fullscreen image (using the CSS `background-image` property).

```mdx
import { Image } from 'mdx-deck'

<Image src="kitten.png" />
```

### Props

- `src` (string) image URL
- `size` (string) CSS background-size

## Appear

Use the `<Appear />` component to make its children appear one at a time within a single slide.
Use the left and right arrow keys to step through each element.

```mdx
import { Appear } from 'mdx-deck'

<ul>
  <Appear>
    <li>One</li>
    <li>Two</li>
    <li>Three</li>
  </Appear>
</ul>
```

Internally, the `<Appear />` component uses the `<Step />` component, which can be used to build custom components with similar behavior.

## Speaker Notes

Speaker notes that only show in presenter mode can be added to any slide with the Notes component.

```mdx
import { Notes } from 'mdx-deck'

# Slide Content

<Notes>Only visible in presenter mode</Notes>
```

## Layouts

MDX Deck includes a few built-in layouts for common slide variations.
Export a layout as the `default` within a slide to wrap the contents.

### Invert

Inverts the foreground and background colors from the theme.

```mdx
import { Invert } from 'mdx-deck/layouts'

# Normal

---

<Invert>

# Inverted

</Invert>
```

### Split

Creates a horizontal layout with the first child on the left and all other children on the right.

```mdx
import { Split } from 'mdx-deck/layouts'

<Split>

![](kitten.png)

## Meow

</Split>
```

### SplitRight

Same as the Split component, but renders the first child on the right.

```mdx
import { SplitRight } from 'mdx-deck/layouts'

<SplitRight>

![](kitten.png)

## Meow

</SplitRight>
```

### Horizontal

Similar to the Split components, but renders all children side-by-side

### FullScreenCode

Render fenced code blocks fullscreen.

````mdx
import { FullScreenCode } from 'mdx-deck/layouts'

<FullScreenCode>

```jsx
<Button>Beep</Button>
```

</FullScreenCode>
````
