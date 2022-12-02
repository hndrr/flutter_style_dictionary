# Style Dictionary

A Flutter package project to show the usage of styled-dictionary's flutter support.
If you have the style-dictionary module installed globally, you can `cd` into this directory and run:

```bash
style-dictionary build
```

You should see something like this output:

```txt
├── lib/
│     ├── main.dart
│     ├── style_dictionary_color.dart
│     ├── style_dictionary_sizes.dart
│     ├── unique_file/
│          ├── unique_file/style_dictionary.dart
├── style_dictionary/
│     ├── README.md
│     ├── config.json
│     ├── tokens/
│   　  ├── color/
│           ├── base.json
│           ├── font.json
│       ├── size/
│           ├── font.json
```

Pretty nifty! This shows a few things happening:

1. The build system does a deep merge of all the token JSON files defined in the `source` attribute of `config.json`. This allows you to split up the token JSON files however you want. There are 2 JSON files with `color` as the top level key, but they get merged properly.
1. The build system resolves references to other design tokens. `{size.font.medium.value}` gets resolved properly.
1. The build system handles references to token values in other files as well as you can see in `tokens/color/font.json`.

Now let's make a change and see how that affects things. Open up `tokens/color/base.json` and change `"#111111"` to `"#000000"`. After you make that change, save the file and re-run the build command `style-dictionary build`. Open up the build files and take a look.

**Huzzah!**

Now go forth and create! Take a look at all the built-in [transforms](https://amzn.github.io/style-dictionary/#/transforms?id=pre-defined-transforms) and [formats](https://amzn.github.io/style-dictionary/#/formats?id=pre-defined-formats).
