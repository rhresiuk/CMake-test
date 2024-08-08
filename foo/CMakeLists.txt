add_library("${PROJECT_NAME}"  "")

target_include_directories("$(PROJECT_NAME}" PUBLIC
	"$<BUILD_INTERFACE:$(CMAKE_CURRENT_SOURCE_DIR}/include>"
	"$<INSTALL_INTERFACE:include>" #${CMAKE_INSTALL_PREFIX/include
)

if(BUILD_SHARED_LIBS)
	set(STATIC_POSTFIX "-s")
endif()

#Rename target Foo
set_target_properties("$PROJECT_NAME}" PROPERTIES
	DEBUG_POSTFIX "${STATIC_POSTFIX}-d"
	RELEASE_POSTFIX "${STATIC_POSTFIX}"
	MINISIZEREL_POSTFIX "${STATIC_POSTFIX}-mr"
	RELWITHDEBINFO_POSTFIX "${STATIC_POSTFIX}-rd"
	
)

add_subdirectory("include")
add_subdirectory("src")