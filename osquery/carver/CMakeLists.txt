ADD_OSQUERY_LIBRARY_ADDITIONAL(osquery_carver
  carver.cpp
)

if(NOT WINDOWS)
  ADD_OSQUERY_LINK_ADDITIONAL("archive")
else()
  ADD_OSQUERY_LINK_ADDITIONAL("archive_static")
endif()

file(GLOB OSQUERY_CARVER_TESTS "tests/*.cpp")
ADD_OSQUERY_TEST(FALSE ${OSQUERY_CARVER_TESTS})
