# Chisel Template

## Dependencies

Click the triangle (►) on the left to view the installation guide.

<details>
<summary> JDK </summary>

Before starting, please make sure you have a JDK >= 8 installed. You can install a JDK through the package manager that comes with your OS, or just download a prebuilt binaries such as [Temurin](https://adoptium.net) or [Oracle OpenJDK](https://jdk.java.net/19).

To install a JDK LTS:

```sh
# macOS with Homebrew
brew install openjdk@17
# Ubuntu
apt install default-jdk
```
</details>

<details>
<summary> Mill build tool </summary>

Mill is a powerful and easy-to-use build tool by [Haoyi Li](https://github.com/lihaoyi).

To install Mill:
```sh
# macOS with Homebrew
brew install mill
```

To install mill on other platforms, please visit [its documentation](https://com-lihaoyi.github.io/mill/mill/Intro_to_Mill.html).
</details>

<details>
<summary> CIRCT </summary>

CIRCT is a MLIR-based circuit IR compilation tool, which is required by chisel. 

Download binary from its [GitHub page](https://github.com/llvm/circt) and add to PATH.
</details>

## Usage

Clone this repository to your local.
```shell 
git clone git@github.com:zhutmost/chisel-template.git
cd chisel-template
rm -rf .git
```

Open a terminal in the root of your cloned repository and build. The first time it runs, the process may take some minutes to download dependencies.
```shell
mill mylib.runMain mylib.RtlEmitter
```

To open this project in an IDE (such as IDEA), please export the BSP configuration first.
```sh
mill mill.bsp.BSP/install
```

To format your code with scalafmt, run:
```sh
mill mill.scalalib.scalafmt.ScalafmtModule/reformatAll __.sources
```

You can freely add your Chisel code in `mylib` package, and have fun!
