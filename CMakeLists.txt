cmake_minimum_required(VERSION 3.17)
project(pcap_lookupdev)
add_executable(main main.cpp)

find_package(PkgConfig REQUIRED)
pkg_check_modules(PCAP REQUIRED libpcap)

target_include_directories(main PRIVATE ${PCAP_INCLUDE_DIRS})
target_link_libraries(main PRIVATE ${PCAP_LIBRARIES})
