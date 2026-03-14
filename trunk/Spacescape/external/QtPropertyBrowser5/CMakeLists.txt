MESSAGE(STATUS "Configuring QtPropertyBrowser")

SET(QTPROPERTYBROWSER_SRCS
    src/qtpropertybrowser.cpp
    src/qtpropertymanager.cpp
    src/qteditorfactory.cpp
    src/qtvariantproperty.cpp
    src/qttreepropertybrowser.cpp
    src/qtbuttonpropertybrowser.cpp
    src/qtgroupboxpropertybrowser.cpp
    src/qtpropertybrowserutils.cpp
    src/qtpropertybrowser.qrc
)

SET(QTPROPERTYBROWSER_HDRS
    src/qtpropertybrowser.h
    src/qtpropertymanager.h
    src/qteditorfactory.h
    src/qtvariantproperty.h
    src/qttreepropertybrowser.h
    src/qtbuttonpropertybrowser.h
    src/qtgroupboxpropertybrowser.h
    src/qtpropertybrowserutils_p.h
)

ADD_LIBRARY(QtPropertyBrowser STATIC ${QTPROPERTYBROWSER_SRCS} ${QTPROPERTYBROWSER_HDRS})
SET_TARGET_PROPERTIES(QtPropertyBrowser PROPERTIES AUTOMOC ON AUTORCC ON POSITION_INDEPENDENT_CODE ON OUTPUT_NAME "QtSolutions_PropertyBrowser-head")
TARGET_COMPILE_DEFINITIONS(QtPropertyBrowser PRIVATE QT_DISABLE_DEPRECATED_BEFORE=0)
TARGET_INCLUDE_DIRECTORIES(QtPropertyBrowser PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/src)
TARGET_LINK_LIBRARIES(QtPropertyBrowser PUBLIC Qt5::Widgets)
