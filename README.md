# Divinitus

# Notes
[to not forget that uname & passwd can be stored locally]
git config credential.helper store

During SFML debug compilation
the following should added to CMakeLists.txt

>#ensure c++14

>set(CXX_STANDARD_REQUIRED ON)

>set(CMAKE_CXX_STANDARD 14)

>set(CMAKE_BUILD_TYPE Debug)

>if(CXX_STANDARD_REQUIRED)

>  message("A meme to be sure!")

>endif(CXX_STANDARD_REQUIRED)

>

>if(CMAKE_CXX_STANDARD)

>  message("But a welcome one")

>endif(CMAKE_CXX_STANDARD)

Build & Run sample:

clang++ -c -std=c++14 main.cpp

clang++ -std=c++14 main.o -o sfml-app -lsfml-grphics -lsfml-window -lsfml-system

export LD_LIBRARY_PATH=/usr/local/lib

./sfml-app
