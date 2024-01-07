**For now, this blueprint only be tested on macOS.**

## Dependencies

You need those tools:

- `cmake >= 3.14`

- `Git`

### macOS

```bash
brew install git cmake
```


## Usage

- Create a build folder:

```bash
cmake -B build
```

if you want to use other build tools, like Ninja:

```bash
cmake -B build -G Ninja
```

- Build Project:

```bash
cmake -B build
```

This command should invokes the building tool that you set before.

- Run the Executable File

```bash
./build/learnopengl
```

## Utilities

Your Text Ediotr may need the `compile_commands.json` to do autocompleting, you can build projects first then copy `compile_commands.json` from the `build` folder.

## Customization

Please Read [`CMakeLists.txt`](./CMakeLists.txt) for more information.
