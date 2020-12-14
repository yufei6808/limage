TARGET = liblimage.so

PROJECT_DIR = .

INCLUDES = -I$(PROJECT_DIR)/include \
		-I$(PROJECT_DIR)/src

LUA_INC=-I/usr/local/include

LUA_LIBS=-L/usr/local/lib \
		-lluajit-5.1 \


CC = gcc
CXX = g++
AR = ar  
CC_FLAGS += -g -Wall -fPIC

SRCS = ./limage.c

OBJS=$(SRCS:.c=.o)

.PHONY: all clean

all:$(TARGET)

$(TARGET):$(OBJS)
	$(CXX) -shared -o $@ $^ $(INCLUDES) $(LUA_INC) $(LUA_LIBS)

%.o:%.c
	$(CXX) -c $(CC_FLAGS) $(INCLUDES) $< -o $@

clean:
	rm -f $(SRCS:.c=.o) $(TARGET)