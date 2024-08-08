set(FILES "")
set(SUBDIRECTORIES "")
set(RELATIVE_PATH "include")

#Add all subdirectories
foreach(VAR ${SUBDIRECTORIES})
	add_subdirectory(${VAR})
endforeach()

if(FILES)
  #Add source files to targer
  targer_sources("$PROJECT_NAME}" PRIVATE ${FILES})

  #Install our source files
  install(FILES $(FILES) DESTINATION ${RELATIVE_PATH})
endif()
