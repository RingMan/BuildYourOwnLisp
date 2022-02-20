cmake_minimum_required (VERSION 3.15)
project (BuildYourOwnLisp LANGUAGES C)

# set(CMAKE_CXX_STANDARD 17)
# set(CMAKE_CXX_STANDARD_REQUIRED ON)
# set(CMAKE_CXX_EXTENSIONS OFF)

if(CMAKE_INSTALL_PREFIX_INITIALIZED_TO_DEFAULT)
  message("Setting CMAKE_INSTALL_PREFIX to ../_install")
  set(CMAKE_INSTALL_PREFIX "../_install" CACHE PATH "..." FORCE)
endif()

function(add_example _targ)
  add_executable(${_targ} ${_targ}.c)
endfunction()

add_example(hello_world)
add_example(hand_rolled_parser)
add_example(prompt)
add_example(prompt_windows)

function(add_mpc_example _targ)
  add_executable(${_targ} ${_targ}.c mpc.c mpc.h)
endfunction()

add_mpc_example(conditionals)
add_mpc_example(doge_code)
add_mpc_example(doge_grammar)
add_mpc_example(error_handling)
add_mpc_example(evaluation)
add_mpc_example(functions)
add_mpc_example(parsing)
add_mpc_example(q_expressions)
add_mpc_example(s_expressions)
add_mpc_example(strings)
add_mpc_example(variables)

