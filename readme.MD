Design System with CSS by Kevin Powell


RESET STYLES

Good reset.css styles: https://github.com/Andy-set-studio/modern-css-reset/blob/master/src/reset.css


BASE UTILITY CLASSES

1) "Do one thing and do it very well"

2) 'flex', 'grid', 'container' classes

3) sr-only (This is for hidden text for accessability)

.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  white-space: nowrap; /* added line */
  border: 0;
}

4) We can set default props in such way: .grid { display: grid; gap: var(--gap, 1rem); }

   - To change it, we can use inline css: style="--gap: 2rem;"

   - Or another class .cta { --gap: 2rem; }


COLOR UTILITIES

1) It is recommended to use rgb or hsl. It is easy to tweak the alpha value then

2) Put all your colors in constants as hsl value: :root { --color-dark: 230 35% 7%; }

3) Make utilities for background and text colors:

  - bg-dark { background-color: hsl( var(--color-dark) ); } ...

  - text-dark { color: hsl( var(--color-dark) ); } ...

  
TYPOGRAPHY

1) Use rem units for better user accessability

2) Make constants for font-size in rem. EXAMPLE: :root { --fs-400: 1.125rem; }

3) Make constants for font-family. EXAMPLE: :root { --ff-serif: "Bellefair", serif; }

4) Make utils for properties: font-size, letter-spacing, font-family, uppercase. If you wish for font-weight, line-height as well.

5) Set default font settings in the body tag: font-size, font-family, line-height, color

6) It is important to find balance between utilities and components

7) Personally think that it is a good idea to add:
  
  - 'u-' prefix for utility classes. EXAMPLE:  "u-text-white"

  - 'c-' prefix for component classes.  EXAMPLE:  "c-button" 

  - 'js-' prefix for classes which are queried in js scripts.  EXAMPLE:  "js-popup__title"


SPACING

1) .flow > * + * { margin-top: var(--flow-space, 1rem); }  every child except the first one will be with margin-top: 1rem;  (useful utility)


INTERACTIVE ELEMENTS

1) It is a good idea to set all the existing utility classes for the element and then add class to fill all the gaps 

  - EXAMPLE: <a href="#" class="super-button text-white bg-dark ff-serif uppercase">Explore</a>

  - "super-button" is a main component class and with the help of utilities 

  - you can easily create similar components with small differences

2) Button must have :hover and :focus states

3) If you notice repeated styles in different components, 

   move these styles to separate class and set it to these components (DRY principle for CSS)


