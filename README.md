# CCTensorFlow
TensorFlow C++ Bindings for Swift

##Using CCTensorFlow
Add that dependency to your Package.swift file.
That module makes bridge to libtensorflow library.
```
let package = Package(
name: "YourProject",
    dependencies: [
        .package(url: "git@github.com:Octadero/CCTensorFlow.git", from: "0.0.9")
    ]
)
```

### Linux
On Linux OS you could install library from [sources](https://www.tensorflow.org/install/).


### mac OS
On mac OS you could install library from [sources](https://www.tensorflow.org/install/).

Some tips you could find on [Octadero site](https://www.octadero.com/2017/08/27/tensorflow-c-environment/).

### PkgConfig
*In case, installing from sources:*
To make interaction more easy, copy `tensorflow_cc.pc` file to your pkgconfig folder. That is way to avoid setting all compile flags at build phase.

Before that, set *tensorflow_path* property in `tensorflow_cc.pc` file to your tensorflow library path.

```
sudo copy tensorflow_cc.pc /usr/local/lib/pkgconfig/
```

### Building your project
Don't forget to use `-std=c++11` flag at building your project phase:
```
swift build -Xcxx -std=c++11
```

### Troubleshooting
If you use apt or brew package manager, make shure that your `tensorflow.pc` file contains only [whitelisted flags](https://github.com/apple/swift-package-manager/blob/740b6667d8dfbea579927045c038d2d885543316/Sources/PackageLoading/Module%2BPkgConfig.swift#L159).
