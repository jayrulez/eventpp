set(TARGET_TEST unittest)

set(SRC_TEST
	testmain.cpp
	tutorial_callbacklist.cpp
	tutorial_eventdispatcher.cpp
	tutorial_eventqueue.cpp
	tutorial_hetercallbacklist.cpp
	test_callbacklist_basic.cpp
	test_callbacklist_ctors.cpp
	test_callbacklist_multithread.cpp
	test_dispatcher_basic.cpp
	test_dispatcher_ctors.cpp
	test_dispatcher_multithread.cpp
	test_queue_basic.cpp
	test_queue_multithread.cpp
	test_hetercallbacklist_basic.cpp
	test_heterdispatcher_basic.cpp
	test_heterqueue_basic.cpp
	test_eventutil.cpp
	test_eventmaker.cpp
	test_conditionalremover.cpp
	test_counterremover.cpp
	test_scopedremover.cpp
)

add_executable(
	${TARGET_TEST}
	${SRC_TEST}
)

set(THREADS_PREFER_PTHREAD_FLAG ON)
find_package(Threads REQUIRED)
target_link_libraries(${TARGET_TEST} Threads::Threads)

set_target_properties(${TARGET_TEST} PROPERTIES CXX_STANDARD 14)
