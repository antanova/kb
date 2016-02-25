As outlined [here](https://css-tricks.com/almanac/properties/a/appearance/)
Safari and other webkit browsers ignore styling on Search input boxes, i.e.

````html
<input type="search">
````

We can get them to behave by styling with `-webkit-appearance: none;`, like so

````css
input[type=search] {
  -webkit-appearance: none;
}
````

Worked for border radius and height.