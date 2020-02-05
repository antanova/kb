In IE, SVGs can display the wrong size, even with the `viewBox` attribute defined.
You cn fix this with the following:

    img[src$=".svg"] {
        width: 100%;
    }

That should resolve things.