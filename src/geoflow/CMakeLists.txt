add_items(
    SOURCES
    geoflow_wrap_apbs.cpp
)

add_items(
    EXTERNAL_HEADERS
    geoflow_wrap_apbs.h
)

add_sublibrary(geoflow_apbs)
target_link_libraries(apbs_geoflow_apbs
  PUBLIC apbs_generic
)
