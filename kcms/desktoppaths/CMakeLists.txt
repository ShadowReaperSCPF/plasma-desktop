# KI18N Translation Domain for this library
add_definitions(-DTRANSLATION_DOMAIN=\"kcm_desktoppaths\")

set(kcm_desktoppaths_PART_SRCS
   globalpaths.cpp
   desktoppathssettings.cpp
)

ki18n_wrap_ui(kcm_desktoppaths_PART_SRCS globalpaths.ui)

add_library(kcm_desktoppaths MODULE ${kcm_desktoppaths_PART_SRCS})

target_link_libraries(kcm_desktoppaths
    KF5::KCMUtils
    KF5::I18n
    KF5::KIOCore
    KF5::KIOWidgets
)

install(TARGETS kcm_desktoppaths DESTINATION ${KDE_INSTALL_PLUGINDIR})
install(FILES desktoppath.desktop DESTINATION ${KDE_INSTALL_KSERVICES5DIR})

