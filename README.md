# react-mac-terminal

[![Badge Name](https://img.shields.io/npm/dw/rbash?color=%23F64C72)](https://www.npmjs.com/package/react-mac-terminal)

A customizable React component that renders a terminal-like interface. It supports various built-in commands like `ls`, `help`, `clear`, while also providing an interface for custom commands.

<img alt="example" src="https://user-images.githubusercontent.com/92326059/234421648-9b0758d6-4a62-4d35-bfbb-e2c369761543.png" width="450">

## Usage

To use the react-mac-terminal in your React project, you can install it from NPM by running `npm install react-mac-terminal` and importing it:

```
import { Terminal } from 'react-mac-terminal/main';

function App() {
  return (
    <div>
      <Terminal />
    </div>
  );
}
```

## Props

The `<Terminal />` component has 9 props that can all be edited:

- `branch = randomBranch() // if no branch is passed a random one will be selected`
- `dirs = ["pass", "in", "your", "custom", "dirs"], // default list of directories`
- `cwd = "/react-mac-terminal", // current working directory`
- `commands = {}, // custom commands`
- `bgColor = "#1e1e1e", // background color of terminal body`
- `color = "White", // font color`
- `draggable = true, // allows terminal to be dragged`
- `noFirstLine = false // removes first line completely`
- `customFirstLines = '', // lines will be added after date/time line`

It also has some built in commands:

```
builtInCommands = {
    clear: { cmd: "clear/cls", output: null, def: "clears terminal" },
    help: { cmd: "help", output: null, def: "shows list of available commands"},
    pwd: {cmd: "pwd", output: cwd, def: "outputs current working directory"},
    ls: {cmd: "ls", output: null, def: "lists contents of current working directory"},
    ...commands,
},
```

Note that while you can alter the `builtInCommands` it is not advisable to do so.

If you click the red button the terminal will close and a small icon will appear in the bottom-left of the screen in a fixed position. To reopen the terminal just click on the icon.

Note (2) that closing the terminal will erase current line.

## Adding Custom Commands

To add custom commands, pass an object to the commands prop with the command name as the key and an object with the following properties as the value:

```
import Terminal from 'react-mac-terminal/main';

function App() {
  const customCommands = {
    hello: {
      cmd: 'hello',
      def: 'Says hello to the user',
      output: 'Hello!',
    },
  };

  return (
    <div>
      <Terminal commands={customCommands} />
    </div>
  );
}
```

## Themes

There are a variety of built-in color themes to choose from. Apply a theme by passing the `theme` name as a prop (string) to the component. If a theme is not specified, the component will default to the `default` theme:

- default
- aqua
- aurora
- cafe
- candy
- cobalt
- coral
- galaxy
- iris
- mango
- ocean
- orchid
- peacock
- plum
- rust
- sage
- tangerine
- teal
- wine

If you pass a `theme` as well as `bgColor` and `color` props, the `theme` will overide the other props. If, however, the `theme` is misspelled, the other props will take effect.

## Contributing

Bug reports and pull requests are welcome, feel free to contribute in any you can.
