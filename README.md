# Unofficial ONNX Runtime Mobile Releases

The repository hosts the **Unofficial** [ONNX Runtime](https://github.com/microsoft/onnxruntime) Mobile Release for
- Android
- iOS (work in progress)

## Disclaimer

The mobile packages published here are built from the official [ONNX Runtime](https://github.com/microsoft/onnxruntime) project. They are **Unofficial** ONNX Runtime packages for Mobile devices.

For any issues or questions, please visit the official [ONNX Runtime](https://github.com/microsoft/onnxruntime) repository.

As for now, there is no plan to publish these unofficial packages to public package managers such as Maven or CocoaPods.

## Motivation

The official ONNX Runtime Mobile packages are published at
- Android, at [MavenCentral](https://mvnrepository.com/artifact/com.microsoft.onnxruntime/onnxruntime-mobile)
- iOS, at [CocoaPods](https://cocoapods.org/)

These official packages target reduced disk footprint for mobile platforms, however they have certain limitations, such as
- Limited Operators, Opsets and Types support, see [ONNX Runtime Mobile Pre-Built Package](https://onnxruntime.ai/docs/reference/mobile/prebuilt-package/), if your model has unsupported operators, you may see error message like, `"AssignNodesToEpsFromHashesImpl Failed to find kernel def hash (8090321298879394920) in kernel registries for MaxPool(8) node with name 'layer3/pool_3/MaxPool'."`
- Support only ORT file format, but not the ONNX file format. You will need to convert your ONNX model, see [ONNX Model Conversion](https://onnxruntime.ai/docs/tutorials/mobile/model-conversion.html)

The ONNX Runtime Mobile packages published here are full ONNX Runtime packages which do not have the above limitations. The drawback is that the packages publish here has large disk footprint, for example,

|Package|Binary Size|
|-------|-----------|
|Official onnxruntime-mobile-1.9.1.aar | 4.4 MB |
|Unofficial onnxruntime-mobile-1.9.1.aar | 14.0 MB|

You may use these packages to try out ONNX Runtime, and decide later whether you want to use the official packages or [custom build your own packages](https://onnxruntime.ai/docs/tutorials/mobile/custom-build.html).

## How to use
### Android
- Download the Android AAR package archive `onnxruntime-mobile-<release number>-Android.zip` for your preferred ONNX Runtime Release from [Releases](https://github.com/gwang-msft/unofficial_onnxruntime_mobile_releases/releases)
- Extract the AAR package `onnxruntime-mobile-<release number>.aar`
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
    implementation(name: "onnxruntime-mobile-<release number>", ext: "aar")
    ...
```

### iOS
Work in progress

## [Changelog](./CHANGELOG.md)
