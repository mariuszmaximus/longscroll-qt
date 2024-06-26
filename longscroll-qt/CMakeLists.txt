cmake_minimum_required(VERSION 3.14)

project(longscroll LANGUAGES CXX)

set(CMAKE_AUTOUIC ON)
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(QT NAMES Qt6 Qt5 REQUIRED COMPONENTS Core Widgets)
find_package(Qt${QT_VERSION_MAJOR} REQUIRED COMPONENTS Core Widgets)

add_library(longscroll 
    contentiteminfo.cpp
    contentwidget.cpp contentwidget.h
    contentwidgetitemfactory.cpp
    imageinfowidget.cpp imageinfowidget.h   imageinfowidget.ui
    imageitemwidget.cpp imageitemwidget.h
    imagewidget.cpp imagewidget.h
    longscrollwidget.cpp longscrollwidget.h
    navigatorwidget.cpp navigatorwidget.h navigatorwidget.ui
    notifyablescrollcontentwidget.cpp notifyablescrollcontentwidget.h
    notifyingscrollarea.cpp notifyingscrollarea.h
)

target_link_libraries(longscroll PRIVATE Qt${QT_VERSION_MAJOR}::Core Qt${QT_VERSION_MAJOR}::Widgets)

target_include_directories(longscroll PUBLIC ../)

# target_compile_definitions(longscroll PRIVATE LONGSCROLL_LIBRARY)
