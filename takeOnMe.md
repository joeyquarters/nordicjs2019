# Take on me

by Eva Ferreira

Slides: https://speakerdeck.com/evaferreira

## Rotoscoping Effect

- Record a video
- Draw on top (15 to 25 images per second)

Can we do rotoscoping on the web? **No.**

But, we can take its soul onto the web.

### Making an invisibility cloak

1. Take user's camera input
2. Draw the input onto a `canvas` tag
3. Make chroma key happen by asking for pixel data
4. Check each pixel (millions!) and if the green value is high, turn the alpha value of that pixel to `0`
