cmake_minimum_required(VERSION 3.5)

project(simple-form-snodec LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(snodec COMPONENTS http-server-express db-mariadb core-socket-stream-legacy net-in-stream-legacy)

add_executable(rest-server rest_server.cpp api_router.cpp)
target_link_libraries(rest-server PRIVATE snodec::http-server-express snodec::db-mariadb snodec::core-socket-stream-legacy snodec::net-in-stream-legacy)
