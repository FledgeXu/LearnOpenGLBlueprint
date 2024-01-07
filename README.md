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

This command should invokes the buiding tool that you set befoe.

- Run the Executable File

```bash
./build/learnopengl
```


## Customization

Please Read [`CMakeLists.txt`](./CMakeLists.txt) for more information.
