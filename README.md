# String Image Format

The string image format is a utf-8 based plain text image format.
This means it can be easily modified with any text-editor.


## Specification

- Must start with a [YAML frontend matter](http://jekyllrb.com/docs/frontmatter)
	- Should contain a `syntaxVersion` string
	- Should contain `width` and `height` fields
	- May contain a `viewport: <x> <y> <width> <height>` field
- Each pixel must be one graphical UTF-8 character
- Each pixel may have a following UTF-8 character to improve readability
	- Set `pixelSeparator: true` to use the default space separator
	- Set `pixelSeparator: <character>` to use the `<character>` as separator
- Image lines are newline `\n` separated
- May contain a `palette` field
	- Only specified characters may be used for pixels then (others are ignored)
- May have an `encoding` field which specifies if pixels are only ASCII
	or also UTF-8 characters.
