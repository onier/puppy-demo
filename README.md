次项目为演示编译工程的项目

puppy-demo为子项目的目录，该项目下有三个子模块，component1 component2 uicomponent，依赖关系为uicomponent
依赖component2，component2依赖component1,component1依赖于boost glog opencv ，记住这个依赖关系。


https://github.com/onier/puppy-demo/blob/master/component1/CMakeLists.txt
其CMakeLists.txt瑞安

set(DEPENDS  boost glog opencv )

include(library)

https://github.com/onier/puppy-demo/blob/master/component2/CMakeLists.txt

set(DEPENDS puppy-demo.component1 )

include(library)



https://github.com/onier/puppy-demo/blob/master/uicomponent/CMakeLists.txt

set(DEPENDS puppy-demo.component2)

set(QT_LIBS Qt5Core Qt5Gui Qt5Widgets)

include(executable)

非常简单，可以很直观的看到依赖关系
