add_library(ArgumentParserToolInfo
  ToolInfo.swift)
# NOTE: workaround for CMake not setting up include flags yet
set_target_properties(ArgumentParserToolInfo PROPERTIES
  INTERFACE_INCLUDE_DIRECTORIES ${CMAKE_Swift_MODULE_DIRECTORY})
target_compile_options(ArgumentParserToolInfo PRIVATE
  $<$<BOOL:${BUILD_TESTING}>:-enable-testing>)


_install_target(ArgumentParserToolInfo)
set_property(GLOBAL APPEND PROPERTY ArgumentParser_EXPORTS ArgumentParserToolInfo)
