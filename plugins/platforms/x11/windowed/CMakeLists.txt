set(X11BACKEND_SOURCES
    logging.cpp
    egl_x11_backend.cpp
    scene_qpainter_x11_backend.cpp
    x11windowed_backend.cpp
)

include_directories(${CMAKE_SOURCE_DIR}/platformsupport/scenes/opengl)
add_library(KWinWaylandX11Backend MODULE ${X11BACKEND_SOURCES})
target_link_libraries(KWinWaylandX11Backend eglx11common kwin kwinxrenderutils X11::XCB SceneQPainterBackend SceneOpenGLBackend)

install(
    TARGETS
        KWinWaylandX11Backend
    DESTINATION
        ${PLUGIN_INSTALL_DIR}/org.kde.kwin.waylandbackends/
)
