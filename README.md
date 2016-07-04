# img2term

Display any image in your terminal, using ANSI color codes

![Iron-Man](./docs/screenshot.png)

This is greatly inspired by [catimg](https://github.com/posva/catimg). `catimg`
is way faster, but it did not handle the `.ico` files so I quickly wrote my own
version in Ruby. It handles any filetype `convert` (ImageMagick) can handle.

## How does it work?

I use the output of `convert ./path/to/file.jpg txt:-` to get the list of all
pixels in the file with their rgb value. It is then just a matter of converting
rgb values to ANSI codes and displaying it.

I also use the special UTF8 character `▄` to display two pixels at once (the top
one uses the background color and the bottom one the foreground color) to keep
the ratio. If the file is too big to be displayed in the terminal screen,
 resize if first.
