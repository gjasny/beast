#
# Copyright (c) 2016-2017 Vinnie Falco (vinnie dot falco at gmail dot com)
#
# Distributed under the Boost Software License, Version 1.0. (See accompanying
# file LICENSE_1_0.txt or copy at http://www.boost.org/LICENSE_1_0.txt)
#
# Official repository: https://github.com/boostorg/beast
#

GroupSources (include/boost/beast beast)
GroupSources (example/common common)
GroupSources (test/extras/include/boost/beast extras)
GroupSources (test/bench/wsload "/")

remove_definitions (-DBOOST_BEAST_INCLUDE_TEST_MAIN)
remove_definitions (-DBOOST_ASIO_SEPARATE_COMPILATION)
remove_definitions (-DBOOST_BEAST_SPLIT_COMPILATION)

add_executable (bench-wsload
    ${BOOST_BEAST_FILES}
    ${COMMON_FILES}
    ${EXTRAS_FILES}
    Jamfile
    wsload.cpp
    )

set_property(TARGET bench-wsload PROPERTY FOLDER "tests-bench")
