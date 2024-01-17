macro(add_script target script)
    add_custom_command(TARGET ${target} POST_BUILD
        COMMAND python scripts/${script} ${CMAKE_BUILD_TYPE}
        WORKING_DIRECTORY ${CMAKE_SOURCE_DIR}
    )
endmacro()

add_executable(game src/main.cpp)

add_script(game test.py)