# configured documentation tools and intermediate build results
set(BINARY_BUILD_DIR_EN "${CMAKE_CURRENT_BINARY_DIR}/en/_build")

# Sphinx cache with pickled ReST documents
set(SPHINX_CACHE_DIR_EN "${CMAKE_CURRENT_BINARY_DIR}/en/_doctrees")

# HTML output director
set(SPHINX_HTML_DIR_EN "${CMAKE_CURRENT_BINARY_DIR}/en/html")

configure_file(
    "${CMAKE_CURRENT_SOURCE_DIR}/../../templates/conf.py.en.in"
    "${BINARY_BUILD_DIR_EN}/conf.py"
    @ONLY)

sphinx_add_target(paddle_api_docs
                  html
                  ${BINARY_BUILD_DIR_EN}
                  ${SPHINX_CACHE_DIR_EN}
                  ${CMAKE_CURRENT_SOURCE_DIR}
                  ${SPHINX_HTML_DIR_EN})
