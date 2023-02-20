---
layout: post
title: Flutter vs 리액트 네이티브 비교
---

# Flutter vs 리액트 네이티브 비교

## 개요

Flutter로 앱을 개발하면서 자주 들었던 질문 중 하나는 리액트 네이티브와 무슨 차이점을 가지고 있냐는 것이였다. 개인적으로 리액트에 대해 알아보면서, 리액트 기반으로 동작하는 리액트 네이티브 와 Flutter를 비교하여 정리해보았다.

## Flutter 란?

Flutter 는 single codebase에서 네이티브하게(natively) 컴파일되는, 크로스 플랫폼 애플리케이션을 만들기 위한 구글의 오픈 소스 프레임워크이다.

Flutter 로 모바일 앱을 개발하는 것 이외에도 Web, Windows, Mac, Linux 앱을 single codebase 로 개발하는 게 가능해졌다.

Flutter 의 위젯을 그리는 dart code는 native code로 컴파일되어 스키아 엔진을 통해 렌더링된다.

## 리액트 네이티브 란?

리액트 네이티브는 리액트와 앱 플랫폼의 네이티브 기능을 사용하여, 안드로이드와 iOS 애플리케이션을 sigle codebase로 만들기 위한 페이스북에서 만든 오픈 소스 프레임워크이다.

리액트 네이티브는 자바스크립트로 작성된 코드베이스를 사용하여, 자바스크립트 개발자의 모바일 앱 개발 진입 장벽을 낮춘다.

리액트 네이티브 애플리케이션은 자바스크립트 런타임 환경을 가지고 있다.

## 앱 파일 사이즈

Flutter 로 만들어진 앱은 60 mb 정도 크기를 기본적으로 차지한다.
리액트 네이티브 로 만들어진 앱은 26 mb ~ 3.1 mb 정도의 크기 기본적으로 차지한다. (Hermes / ProGuard) 옵션에 따라 달라진다.

Flutter 앱의 파일 크기가 더 큰 경향이 있다.

## Hot reload

두 프레임워크 모두 Hot reload 를 사용하여 변경 사항을 즉시 확인할 수 있으므로 개발이 효율적이다.
하지만, 리액트 네이티브에서는 제대로 작동하지 않을 때가 있다고 한다.

## 레이아웃
Flutter 와 리액트 네이티브는 레이아웃을 구성하기 위해 CSS flexbox를 사용한다.

## Flutter Rendering

Flutter가 사용하는 Dart 코드는 native 로 직접 컴파일된다.

Flutter 렌더링은 Skia 라는 내부 그래픽 엔진을 사용하여, 위젯을 캔버스에 직접 그리는 방식이라 볼 수 있다.

![alt](https://miro.medium.com/v2/resize:fit:720/format:webp/1*ZR698zwJZfRSLgUCO1aoHA.png)

Flutter 는 플랫폼 간에 브리지나 Context switching 이 필요하지 않다. (리액트 네이티브보다 렌더링 속도에 우위에 있다고 볼 수 있다)

## 리액트 네이티브 Rendering

리액트 네이티브는 자바스크립트와 네이티브의 두 부분으로 구성되어 있기 때문에 프레임워크는 네이티브 요소와 상호 작용하기 위해 자바스크립트 브리지를 필요로 한다. 브리지는 앱 성능을 저하시킬 수 있다.

![alt](https://miro.medium.com/v2/resize:fit:720/format:webp/1*331KENPILKOregPuYFbzZw.png)

리액트 네이티브는 페이스북 Flux 아키텍처를 사용한다. 이는 자바스크립트 코드는 런타임에 네이티브 코드로 컴파일된다는 것이다.

![alt](https://cdn.brocoders.com/react_native_architecture_03fcb17f85.png)

자바스크립트 브리지로 인한 성능 문제를 해결하기 위해, 리액트 네이티브의 새로운 아키텍처는 자바스크립트 브리지를 자바스크립트 인터페이스(JSI)로 대체하였다. JSI는 브리지를 사용하지 않고 네이티브 모듈을 직접 호출할 수 있게 한다.

리액트 네이티브는 Component 에 해당하는 Android 및 iOS View 를 생성한다.

![alt](https://d33wubrfki0l68.cloudfront.net/52fa87723ab70fcc1bbe555f8832af34da5ac3ee/48301/docs/assets/diagram_ios-android-views.svg)

## vs 네이티브 앱

네이티브 앱은 모바일 장치에서 원활하게 작동한다. 네이티브 앱의 그래픽 전환은 크로스 플랫폼 앱에 비해 UI 렌더링에 걸리는 시간이 적다. code가 모바일 OS 코어와 직접 통신할 수 있는 UI 렌더링 방식이 가능하기 때문이다.

Flutter 와 리액트 네이티브 가 진정으로 네이티브 앱 인지에 대한 논쟁이 있다. 100% 네이티브 앱으로 간주되기 위해서는 플랫폼에 의해 설계된 방식으로 작성되어야 한다.

리액트 네이티브 와 Flutter의 단점은 이 두 프레임워크 모두 네이티브가 아니기 때문에 많은 공통점을 가지고 있으며, 네이티브 앱 보다 제한된 도구와 라이브러리를 가지게 되는 단점이 있다.

## 참조

https://www.browserstack.com/guide/flutter-vs-react-native
https://levelup.gitconnected.com/flutter-vs-react-native-comparing-the-features-of-each-framework-f61bfd146a90
https://brocoders.com/blog/react-native-vs-flutter-which-one-better/
https://fireart.studio/blog/flutter-vs-react-native-what-app-developers-should-know-about-cross-platform-mobile-development/
https://reactnative.dev/docs/intro-react-native-components
