EXES_CLIENT = CmdParser
EXES_RealName = DBDeployer

FPNN_DIR = ../../../fpnn
DEPLOYMENT_DIR = ../../../deployment/dbproxy

CFLAGS +=
CXXFLAGS +=
CPPFLAGS += -I$(FPNN_DIR)/core -I$(FPNN_DIR)/proto -I$(FPNN_DIR)/base -I$(FPNN_DIR)/proto/msgpack -I$(FPNN_DIR)/proto/rapidjson `mysql_config --cflags` -Wp,-U_FORTIFY_SOURCE
LIBS += -L$(FPNN_DIR)/extends -L$(FPNN_DIR)/core -L$(FPNN_DIR)/proto -L$(FPNN_DIR)/base -lfpnn `mysql_config --libs_r`

OBJS_CLIENT = DBDeployer.o DBDeployer.TableOperations.o DBDeployer.Confuser.o MySQLClient.o linenoise.o CmdParser.o CommandProcessor.o

all: $(EXES_CLIENT)
	mv $(EXES_CLIENT) $(EXES_RealName)


deploy:
	cp -rf $(EXES_RealName) $(DEPLOYMENT_DIR)/tools/

clean:
	$(RM) *.o $(EXES_RealName)

include $(FPNN_DIR)/def.mk
