SHENANGO_PATH=../shenango
include $(SHENANGO_PATH)/shared.mk

librt_libs = $(SHENANGO_PATH)/bindings/cc/librt++.a
INC += -I$(SHENANGO_PATH)/bindings/cc -I$(SHENANGO_PATH)/ksched -Iinc \
       -IDataFrame/AIFM/include/

#test_pointer_noswap_src = test/test_pointer_noswap.cpp
#test_pointer_noswap_obj = $(test_pointer_noswap_src:.cpp=.o)

#test_pointer_swap_src = test/test_pointer_swap.cpp
#test_pointer_swap_obj = $(test_pointer_swap_src:.cpp=.o)

#test_pointer_swap_rw_api_src = test/test_pointer_swap_rw_api.cpp
test_pointer_swap_rw_api_obj = $(test_pointer_swap_rw_api_src:.cpp=.o)

test_tcp_pointer_swap_src = test/test_tcp_pointer_swap.cpp
test_tcp_pointer_swap_obj = $(test_tcp_pointer_swap_src:.cpp=.o)

test_pointer_concurrent_src = test/test_pointer_concurrent.cpp
test_pointer_concurrent_obj = $(test_pointer_concurrent_src:.cpp=.o)

test_array_add_src = test/test_array_add.cpp
test_array_add_obj = $(test_array_add_src:.cpp=.o)

test_array_add_rw_api_src = test/test_array_add_rw_api.cpp
test_array_add_rw_api_obj = $(test_array_add_rw_api_src:.cpp=.o)

test_tcp_array_add_src = test/test_tcp_array_add.cpp
test_tcp_array_add_obj = $(test_tcp_array_add_src:.cpp=.o)

test_array_clock_replacement_src = test/test_array_clock_replacement.cpp
test_array_clock_replacement_obj = $(test_array_clock_replacement_src:.cpp=.o)

test_hashtable_clock_replacement_src = test/test_hashtable_clock_replacement.cpp
test_hashtable_clock_replacement_obj = $(test_hashtable_clock_replacement_src:.cpp=.o)

test_array_nt_src = test/test_array_nt.cpp
test_array_nt_obj = $(test_array_nt_src:.cpp=.o)

test_hopscotch_serial_src = test/test_hopscotch_serial.cpp
test_hopscotch_serial_obj = $(test_hopscotch_serial_src:.cpp=.o)

test_local_hopscotch_serial_src = test/test_local_hopscotch_serial.cpp
test_local_hopscotch_serial_obj = $(test_local_hopscotch_serial_src:.cpp=.o)

test_hopscotch_parallel_src = test/test_hopscotch_parallel.cpp
test_hopscotch_parallel_obj = $(test_hopscotch_parallel_src:.cpp=.o)

test_hopscotch_gc_serial_src = test/test_hopscotch_gc_serial.cpp
test_hopscotch_gc_serial_obj = $(test_hopscotch_gc_serial_src:.cpp=.o)

test_hopscotch_gc_parallel_src = test/test_hopscotch_gc_parallel.cpp
test_hopscotch_gc_parallel_obj = $(test_hopscotch_gc_parallel_src:.cpp=.o)

test_tcp_hopscotch_gc_serial_src = test/test_tcp_hopscotch_gc_serial.cpp
test_tcp_hopscotch_gc_serial_obj = $(test_tcp_hopscotch_gc_serial_src:.cpp=.o)

test_tcp_hopscotch_gc_parallel_src = test/test_tcp_hopscotch_gc_parallel.cpp
test_tcp_hopscotch_gc_parallel_obj = $(test_tcp_hopscotch_gc_parallel_src:.cpp=.o)

test_slab_src = test/test_slab.cpp
test_slab_obj = $(test_slab_src:.cpp=.o)

test_local_skiplist_serial_src = test/test_local_skiplist_serial.cpp
test_local_skiplist_serial_obj = $(test_local_skiplist_serial_src:.cpp=.o)

test_local_list_src = test/test_local_list.cpp
test_local_list_obj = $(test_local_list_src:.cpp=.o)

test_list_src = test/test_list.cpp
test_list_obj = $(test_list_src:.cpp=.o)

test_queue_gc_src = test/test_queue_gc.cpp
test_queue_gc_obj = $(test_queue_gc_src:.cpp=.o)

test_stack_gc_src = test/test_stack_gc.cpp
test_stack_gc_obj = $(test_stack_gc_src:.cpp=.o)

test_list_gc_src = test/test_list_gc.cpp
test_list_gc_obj = $(test_list_gc_src:.cpp=.o)

test_dataframe_vector_src = test/test_dataframe_vector.cpp
test_dataframe_vector_obj = $(test_dataframe_vector_src:.cpp=.o)

test_csv_reader_src = test/test_csv_reader.cpp
test_csv_reader_obj = $(test_csv_reader_src:.cpp=.o)

test_shared_pointer_src = test/test_shared_pointer.cpp
test_shared_pointer_obj = $(test_shared_pointer_src:.cpp=.o)

test_embedded_pointer_src = test/test_embedded_pointer.cpp
test_embedded_pointer_obj = $(test_embedded_pointer_src:.cpp=.o)

lib_src = $(wildcard src/*.cpp)
lib_src := $(filter-out src/tcp_device_server.cpp,$(lib_src))
lib_obj = $(lib_src:.cpp=.o)

test_src = $(test_pointer_noswap_src) $(test_pointer_swap_src) $(test_pointer_concurrent_src)  \
$(test_tcp_pointer_swap_src) $(test_array_add_src) $(test_array_nt_src) \
$(test_array_clock_replacement_src) $(test_tcp_array_add_src) $(test_hopscotch_serial_src) \
$(test_slab_src) $(test_local_hopscotch_serial) $(test_hopscotch_gc_serial_src) \
$(test_hopscotch_parallel_src) $(test_hopscotch_gc_parallel_src) $(test_tcp_hopscotch_gc_serial_src) \
$(test_tcp_hopscotch_gc_parallel_src) $(test_hashtable_clock_replacement_src) $(test_local_list) \
$(test_list) $(test_list_gc) $(test_queue_gc) $(test_stack_gc) $(test_pointer_swap_rw_api_src) \
$(test_array_add_rw_api_src) $(test_dataframe_vector_src) $(test_csv_reader_src) $(test_shared_pointer_src) \
$(test_embedded_pointer_src)
test_obj = $(test_src:.cpp=.o)

src = $(lib_src) $(test_src)
obj = $(src:.cpp=.o)
dep = $(obj:.o=.d)

tcp_device_server_src = src/tcp_device_server.cpp
tcp_device_server_obj = $(tcp_device_server_src:.cpp=.o)

override CXXFLAGS += -std=gnu++2a -fconcepts -Wno-unused-function
CXXFLAGS := $(filter-out -std=gnu++17,$(CXXFLAGS))
override LDFLAGS += -lnuma

all: libaifm.a


$(tcp_device_server_obj): $(tcp_device_server_src)
	$(CXX) $(CXXFLAGS) -c $< -o $@

libaifm.a: $(lib_obj)
	$(AR) rcs $@ $^

#rule to generate a dep file by using the C preprocessor
#(see man cpp for details on the - MM and - MT options)
%.d: %.cpp
	@$(CXX) $(CXXFLAGS) $< -MM -MT $(@:.d=.o) >$@
%.o: %.cpp
	$(CXX) $(CXXFLAGS) -c $< -o $@

ifneq ($(MAKECMDGOALS),clean)
-include $(dep)   # include all dep files in the makefile
endif

.PHONY: clean
clean:
	rm -f src/*.o test/*.o $(dep) bin/* lib*.a
