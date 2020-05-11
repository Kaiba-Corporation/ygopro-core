project (ocgcore)

set (AUTO_FILES_RESULT)
AutoFiles("." "src" "\\.(cpp|c|h)$")

include_directories ( ../lua )

add_library (ocgcore STATIC ${AUTO_FILES_RESULT})

if (MSVC)
    target_link_libraries (ocgcore lua)
else ()
    target_link_libraries (ocgcore ${LUA_LIBRARIES})
endif ()
