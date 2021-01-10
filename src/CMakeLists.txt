
aux_source_directory(./ MAIN_SRC)

set(EXECUTABLE_OUTPUT_PATH ${PROJECT_BINARY_DIR}/bin)

add_executable(testDemo ${MAIN_SRC})
