# Rust Android Gradle Plugin (Deprecated)

> This project is now deprecated in favor of https://github.com/mozilla/rust-android-gradle

Cross compiles rust cargo projects for Android

# Usage

To begin you must first install the rust toolchains for your target platforms.

```
rustup target add arm-linux-androideabi     # for arm
rustup target add i686-linux-android        # for x86
...
```

Next add the `cargo` configuration to android project. Point to your cargo project using `module` and add targets.
Currently supported targets are `arm`, `arm64`, `mips`, and `x86`, `x86_64`.

```
cargo {
    module = "../rust"
    targets = ["arm", "x84"]
}

```

Run the `cargoBuild` task to cross compile

```
./gradlew cargoBuild
```

Generated static libraries will be added to your android `jniLibs` source-sets.
