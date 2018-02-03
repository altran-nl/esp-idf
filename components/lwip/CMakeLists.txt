cmake_minimum_required(VERSION 3.5)
include(CTest)

set(LWIP_SRC api apps apps/sntp apps/ping core core/ipv4 core/ipv6 netif/ppp/polarssl netif/ppp netif port/freertos port/netif port/debug port)
add_library(lwip ${LWIP_SRC})
target_include_directories(lwip
        PUBLIC include/lwip
include/lwip/port
include/lwip/posix
apps/ping )

#ifdef CONFIG_PPP_SUPPORT
#LWIP_PPP_DIRS := netif/ppp/polarssl netif/ppp
#else
#LWIP_PPP_DIRS :=
#endif


#CFLAGS += -Wno-address  # lots of LWIP source files evaluate macros that check address of stack variables
#
#api/tcpip.o apps/dhcpserver.o: CFLAGS += -Wno-unused-variable
#apps/dhcpserver.o core/pbuf.o core/tcp_in.o: CFLAGS += -Wno-unused-but-set-variable
#netif/ppp/pppos.o: CFLAGS += -Wno-type-limits



#add_test (ValueUpdate abcd_model_test update_value      )
