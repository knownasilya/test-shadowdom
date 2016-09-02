# test-shadowdom

This is an example at what's currently possible with v0 web components.

## Future 

Since `::shadow` and `/deep/` have been deprecated, the future (v1) alternative
is something like:

In the web component:
```css
.container {
  /* cornflowerblue is a default colour, in case the user doesn't
   * provide one. You could omit it if it's being inherited from above */
  background-color: var(--shiny-button-background, cornflowerblue);
}

.icon {
  font-size: 20px;
  @apply(--shiny-button-icon);
}
```

In user land:
```css
shiny-button.fancy {
  font-family: "Lato";
  font-weight: 300;
  color: black;
  --shiny-button-background: #E91E63;

  /* this is the mixin! the colon and the semicolon are both important */
  --shiny-button-icon: {
    color: red;
    padding: 10px;
    text-shadow: 0 1px 1px #880E4F;
  };
}
```

```html
<shiny-button class='fancy'></shiny-button>
```

Check out this nice writeup http://meowni.ca/posts/styling-the-dome/ by [@notwaldorf](https://twitter.com/notwaldorf)
from which I copied the examples.

## Good links

- https://developers.google.com/web/fundamentals/primers/shadowdom/
- https://developers.google.com/web/fundamentals/primers/customelements/
- https://docs.google.com/presentation/d/179IRXRFmDGb3P60OVsoAIsElcaOp__5EuIWLcL8oNos/edit#slide=id.p
