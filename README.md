# ruby-syntax-replacer

## Features

Replace your old syntax...

```ruby
@data = [
  {:location => "Lebanon", :title => "K Frame", :place => "Based in Beirut"},
  {:location => "Germany", :title => "Xolo", :place => "Based in Berlin"},
  {:location => "Germany", :title => "Lichtecht", :place => "Based in Hamburg"}
]
```
```haml
%div{:data => {:someValue => "Hello world", :"other-value" => 123, :"some-really-long-attr" => true}}
```

... With the new!

```ruby
@data = [
  {location: "Lebanon", title: "K Frame", place: "Based in Beirut"},
  {location: "Germany", title: "Xolo", place: "Based in Berlin"},
  {location: "Germany", title: "Lichtecht", place: "Based in Hamburg"}
]
```
```haml
%div{data: {someValue: "Hello world", "other-value": 123, "some-really-long-attr": true}}
```

And as an added bonus, it also removes trailing `/`s from self-closing tags in HAML.

```haml
%link{href: asset_path(:images, "favicon/apple-touch-icon-57x57.png"), :rel => "apple-touch-icon-precomposed", :sizes => "57x57"}/
```
Into
```haml
%link{href: asset_path(images:, "favicon/apple-touch-icon-57x57.png"), rel: "apple-touch-icon-precomposed", sizes: "57x57"}
```

## Release Notes

### 1.0.0

Initial release of `ruby-syntax-replacer`

### 1.0.1

Added support for dashed attributes

### 1.0.2

Added removal of trailling `/`s of self-closing tags