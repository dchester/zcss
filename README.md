# zcss

Minimal nested css preprocessor in ~30 lines of pure bash!

```scss
:root {
  --blue: #8098d4;
}

.button {
  background: var(--blue);
  border-radius: 4px;
  font-size: 18px;

  &:hover {
    transform: scale(1.1);
  }

  &[disabled] {
    opacity: 0.5
  }

  .icon {
    margin-right: 1em;
  }
}
```

Compile zcss to css:

```bash
$ cat button.zcss | zcss > button.css
```

### Syntax

This preprocessor implements just two core features inspired by scss / less / and the `css-nesting` spec: implicit nesting, and the ampersand selector.

##### Implicit nesting

```scss
section {
  p {
    line-height: 2;
  }
}

/* section p {
 *   line-height: 2;
 * }
 */
```

##### Ampersand selector

```scss
section {
  &:hover {
    color: purple;
  }
}

/* secion:hover {
 *  color: purple;
 * }
 */
```

The ampersand must appear exclusively at the beginning of the selector.

