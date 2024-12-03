include $(MAKE_INCLUDE_GEN)

.PHONY: all clean

#*****************************************************************************#
#                               VARIABLES	                              #
#*****************************************************************************#
DIR = $(BASEDIR)/component/common/application/aws_iotshd
vpath %.c $(DIR)

AWS_IOTSHD_DIR = $(DIR)/IoT-Smarthome-Device-SDK
IFLAGS += -I$(AWS_IOTSHD_DIR)/commonDependencies/core_pkcs11/corePKCS11/source/dependency/3rdparty/pkcs11/published/2-40-errata-1
IFLAGS += -I$(AWS_IOTSHD_DIR)/commonDependencies/core_pkcs11/corePKCS11/source/include
IFLAGS += -I$(AWS_IOTSHD_DIR)/commonDependencies/core_pkcs11
IFLAGS += -I$(AWS_IOTSHD_DIR)/commonDependencies/coreJSON/source/include
IFLAGS += -I$(AWS_IOTSHD_DIR)/commonDependencies/core_mqtt/coreMQTT/source/include
IFLAGS += -I$(AWS_IOTSHD_DIR)/commonDependencies/core_mqtt/coreMQTT/source/interface
IFLAGS += -I$(AWS_IOTSHD_DIR)/commonDependencies/core_mqtt
IFLAGS += -I$(AWS_IOTSHD_DIR)/commonDependencies/coreMQTT-Agent/source/include
IFLAGS += -I$(AWS_IOTSHD_DIR)/commonDependencies/Jobs-for-AWS-IoT-embedded-sdk/source/include
IFLAGS += -I$(AWS_IOTSHD_DIR)/commonDependencies/utilities/logging
IFLAGS += -I$(AWS_IOTSHD_DIR)/components/jobs_handler/source/include
IFLAGS += -I$(AWS_IOTSHD_DIR)/components/mqtt_agent/source/include
IFLAGS += -I$(AWS_IOTSHD_DIR)/components/provisionee/source/include
IFLAGS += -I$(AWS_IOTSHD_DIR)/examples/iotshd_device_dm_air_purifier/example_clusters
IFLAGS += -I$(AWS_IOTSHD_DIR)/examples/device_config
IFLAGS += -I$(AWS_IOTSHD_DIR)/examples/dm
IFLAGS += -I$(AWS_IOTSHD_DIR)/include
IFLAGS += -I$(AWS_IOTSHD_DIR)/platform/include

#*****************************************************************************#
#                               Source FILE LIST                              #
#*****************************************************************************#
CSRC += $(DIR)/iotshd_main.c
CSRC += $(DIR)/iotshd_pal_Clock.c
CSRC += $(DIR)/iotshd_pal_FatalAssert.c
CSRC += $(DIR)/iotshd_pal_Heap.c
CSRC += $(DIR)/iotshd_pal_Log.c
CSRC += $(DIR)/iotshd_pal_Mutex.c
CSRC += $(DIR)/iotshd_pal_Nvm.c
CSRC += $(DIR)/iotshd_pal_Random.c
CSRC += $(DIR)/iotshd_pal_SyncEvent.c
CSRC += $(DIR)/iotshd_pal_SyncQueue.c
CSRC += $(DIR)/iotshd_pal_Thread.c

#*****************************************************************************#
#                               Object FILE LIST                              #
#*****************************************************************************#
OBJS = $(notdir $(CSRC:.c=.o))

#*****************************************************************************#
#                               Include Dependency                            #
#*****************************************************************************#
-include $(OBJS:.o=.d)

#*****************************************************************************#
#                        RULES TO GENERATE TARGETS                            #
#*****************************************************************************#
all: CORE_TARGETS COPY_RAM_OBJS

#*****************************************************************************#
#              GENERATE OBJECT FILE
#*****************************************************************************#
CORE_TARGETS: $(OBJS)

#*****************************************************************************#
#              CLEAN GENERATED FILES                                          #
#*****************************************************************************#
clean: CLEAN_OBJS
	$(REMOVE) *.o
	$(REMOVE) *.i
	$(REMOVE) *.s
	$(REMOVE) *.d
	$(REMOVE) *.c

-include $(DEPS)	
