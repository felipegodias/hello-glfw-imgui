project(HelloWorld.Launcher CXX)

set(PROJECT_SRC)

add_subdirectory("Src")

list(SORT PROJECT_SRC)
message("\n::::: ${PROJECT_NAME} Source Files Start :::::")
foreach(SRC_FILE IN LISTS PROJECT_SRC)
    message(${SRC_FILE})
endforeach()

add_executable(${PROJECT_NAME} ${PROJECT_SRC})

find_package(GLEW REQUIRED)
target_link_libraries(${PROJECT_NAME} PRIVATE GLEW::GLEW)

find_package(glfw3 CONFIG REQUIRED)
target_link_libraries(${PROJECT_NAME} PRIVATE glfw)

find_package(imgui CONFIG REQUIRED)
target_link_libraries(${PROJECT_NAME} PRIVATE imgui::imgui)