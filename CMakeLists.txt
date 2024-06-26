cmake_minimum_required(VERSION 3.14...3.28)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
project(learnopengl LANGUAGES CXX)

# Include the FetchContent to download dependencies from git repos.
include(FetchContent)
set(FETCHCONTENT_UPDATES_DISCONNECTED TRUE)

# --- Fetch GLFW --------------------------------------------------------------
FetchContent_Declare(
    glfw
    GIT_REPOSITORY https://github.com/glfw/glfw.git
    )

# We don't need those, but feel free to comment them.
set(GLFW_BUILD_EXAMPLES OFF CACHE INTERNAL "Build the GLFW example programs")
set(GLFW_BUILD_TESTS OFF CACHE INTERNAL "Build the GLFW test programs")
set(GLFW_BUILD_DOCS OFF CACHE INTERNAL "Build the GLFW documentation")
set(GLFW_INSTALL OFF CACHE INTERNAL "Generate installation target")

FetchContent_MakeAvailable(glfw)

# --- Fetch GLAD --------------------------------------------------------------
FetchContent_Declare(
    glad
    GIT_REPOSITORY https://github.com/Dav1dde/glad.git
    )

set(GLAD_PROFILE "core" CACHE STRING "OpenGL profile")
set(GLAD_API "gl=3.3" CACHE STRING "API type/version pairs, like \"gl=3.2,gles=\", no version means latest")
set(GLAD_GENERATOR "c" CACHE STRING "Language to generate the binding for")

FetchContent_MakeAvailable(glad)

# --- Fetch GLM --------------------------------------------------------------
FetchContent_Declare(
    glm 
    GIT_REPOSITORY https://github.com/g-truc/glm.git
    )

FetchContent_MakeAvailable(glm)



# include all cpp files
file(GLOB_RECURSE sources CONFIGURE_DEPENDS "src/*")

# If you want to add more source files, add here:
add_executable(${PROJECT_NAME})

target_sources(${PROJECT_NAME} PRIVATE ${sources})
target_include_directories(${PROJECT_NAME} PRIVATE include)
target_compile_features(${PROJECT_NAME} PRIVATE cxx_std_23)
target_link_libraries(${PROJECT_NAME} PRIVATE glfw glad glm)
