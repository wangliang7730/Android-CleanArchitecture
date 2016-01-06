Android-CleanArchitecture [![Build Status](https://travis-ci.org/android10/Android-CleanArchitecture.svg?branch=master)](https://travis-ci.org/android10/Android-CleanArchitecture)
=========================

著作权归作者所有。
商业转载请联系作者获得授权，非商业转载请注明出处。
作者：豆沙包
链接：http://www.zhihu.com/question/21406685/answer/61122814
来源：知乎

这个是我们团队一直推崇而且现在正在使用的架构
android10/Android-CleanArchitecture · GitHub

说说用下来的优缺点，如有纰漏，还请指正。

无论从架构还是代码上看，分层都是三层：视图层(Presentation Layer)、控制层(Domain Layer)、数据流层(Data Layer)。
层级之间通过添加接口层作为分隔实现解耦。

简单来说，优点有以下
1.层次分明，各层级之间都不管对方如何实现，只关注结果；
2.在视图层(Presentation Layer)使用MVP架构，使原本臃肿的Activity(或Fragment)变得简单，其处理方法都交给了Presenter。
3.易于做测试，只要基于每个模块单独做好单元测试就能确保整体的稳定性。
4.易于快速迭代，基于代码的低耦合，只需在业务逻辑上增加接口，然后在相应的层级分别实现即可，丝毫不影响其他功能。
....等等

目前发现的缺点：
1.由于视图层(Presentation Layer)使用MVP模式，每个有独立逻辑的Activity(Fragment)都拥有独立的Presenter，当View多起来时候Presenter维护起来就显得略麻烦
2.上手难度比较大，学习曲线比较陡峭

This is a sample app that is part of a blog post I have written about how to architect android application using the Uncle Bob's clean architecture approach. 

[Architecting Android…The clean way?](http://fernandocejas.com/2014/09/03/architecting-android-the-clean-way/)

[Architecting Android…The evolution](http://fernandocejas.com/2015/07/18/architecting-android-the-evolution/)

[Tasting Dagger 2 on Android](http://fernandocejas.com/2015/04/11/tasting-dagger-2-on-android/)

[Demo video of this sample](http://youtu.be/XSjV4sG3ni0)

Clean architecture
-----------------
![http://fernandocejas.com/2015/07/18/architecting-android-the-evolution/](http://fernandocejas.com/wp-content/uploads/2014/09/clean_architecture1.png)

Architectural approach
-----------------
![http://fernandocejas.com/2015/07/18/architecting-android-the-evolution/](http://fernandocejas.com/wp-content/uploads/2014/09/clean_architecture_android.png)

Architectural reactive approach
-----------------
![http://fernandocejas.com/2015/07/18/architecting-android-the-evolution/](http://fernandocejas.com/wp-content/uploads/2015/07/clean_architecture_evolution.png)

Local Development
-----------------

Here are some useful Gradle/adb commands for executing this example:

 * `./gradlew clean build` - Build the entire example and execute unit and integration tests plus lint check.
 * `./gradlew installDebug` - Install the debug apk on the current connected device.
 * `./gradlew runUnitTests` - Execute domain and data layer tests (both unit and integration).
 * `./gradlew runAcceptanceTests` - Execute espresso and instrumentation acceptance tests.

Code style
-----------

Here you can download and install the java codestyle.
https://github.com/android10/java-code-styles


License
--------

    Copyright 2014 Fernando Cejas

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.


![http://www.fernandocejas.com](http://www.android10.org/myimages/android10_logo_big_github.png)

[![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-Android--CleanArchitecture-brightgreen.svg?style=flat)](https://android-arsenal.com/details/3/909)
