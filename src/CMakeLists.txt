add_executable(
    my_app
    main.cpp
    # all .c/.cpp files here
)

target_link_libraries(
    my_app
    PUBLIC project_warnings
           project_options
           # any external libraries or CONAN_PKG::<pkg>
)
