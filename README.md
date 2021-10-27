# Unofficial ONNX Runtime Mobile Releases

The repository hosts the Unofficial ONNX Runtime Mobile Release for
- Android
- iOS (work in progress)

## Disclaimer

The mobile packages published here is built from the official [ONNX Runtime](https://github.com/microsoft/onnxruntime) project. They are unofficial ONNX Runtime packages for Mobile devices.

For any issues or questions, please use the official [ONNX Runtime](https://github.com/microsoft/onnxruntime) repository.

## Motivation

The official ONNX Runtime Mobile packages published at
- Android, at [MavenCentral](https://mvnrepository.com/artifact/com.microsoft.onnxruntime/onnxruntime-mobile)
- iOS, at [CocoaPods](https://cocoapods.org/)

These official packages target reduced disk footprint for mobile platforms, however they have certain limitations, such as
- Limited Operators, Opsets and Types support, see [ONNX Runtime Mobile Pre-Built Package](https://onnxruntime.ai/docs/reference/mobile/prebuilt-package/), if your model has unsupported operators, you may see error message like, `"AssignNodesToEpsFromHashesImpl Failed to find kernel def hash (8090321298879394920) in kernel registries for MaxPool(8) node with name 'layer3/pool_3/MaxPool'."`
- Support only ORT file format, but not the ONNX file format. You will need to convert your ONNX model, see [ONNX Model Conversion](https://onnxruntime.ai/docs/tutorials/mobile/model-conversion.html)

The ONNX Runtime Mobile packages published here are full ONNX Runtime packages which do not have the above limitation. The drawback is that the packages publish here has large disk footprint, for example,

|Package|Binary Size|
|-------|-----------|
|Official onnxruntime-mobile-1.9.1.aar | 4.4 MB |
|Unofficial onnxruntime-mobile-1.9.1.aar | 14.0 MB|

You may use these packages to try out ONNX Runtime. And decide later whether you want to use the official packages or [custom build your own packages](https://onnxruntime.ai/docs/tutorials/mobile/custom-build.html).

## How to use
### Android
- Download the Android AAR package `onnxruntime-mobile-<release number>.aar` for your preferred ONNX Runtime Release
- Extract the package
- Copy the AAR package to `app/libs` of your Android Project
- Add the following line to the `build.gradle` of your root project
```
allprojects {
    repositories {
        flatDir{dirs 'libs'}
        ...
```
- Add the following line to the `build.gradle` of your app module
```
dependencies {
    implementation(name: "onnxruntime-release-1.7.0", ext: "aar")
    ...
```

### iOS
Work in progress
