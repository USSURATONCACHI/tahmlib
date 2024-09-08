cmake_minimum_required(VERSION 3.10)

project(tahm VERSION 0.1.0 LANGUAGES CXX)
set(CMAKE_CXX_STANDARD 20)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON) # For seamless VSCode extensions integraion

find_package(SDL2 REQUIRED)
find_package(SDL_ttf REQUIRED)

message("Sdl2 TTF: " ${SDL_TTF_INCLUDE_DIRS})
message("Sdl2 TTF: " ${SDL_TTF_LIBRARIES})

add_executable(tahm
    tahm/main.cpp
    tahm/engine.cpp
    
    tahm/tahm/audio.cpp
    tahm/tahm/font.cpp
    tahm/tahm/graphics.cpp
    tahm/tahm/renderer.cpp
    tahm/tahm/sound.cpp
    tahm/tahm/tahm.cpp
    tahm/tahm/window.cpp
)
target_include_directories(tahm PUBLIC include)
target_include_directories(tahm PRIVATE ${SDL2_INCLUDE_DIRS} ${SDL_TTF_INCLUDE_DIRS})
target_link_libraries(tahm ${SDL2_LIBRARIES} ${SDL_TTF_LIBRARIES})