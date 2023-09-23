# a short makefile

Target		:= main
CC			:= g++
LD			:= LD
CXXFLAGS	:= -std=c++14 -g -O2 -Wall

INC			:= -I. -I./include -I${ROOTSYS}/include
LIB			:= $(shell root-config --glibs)

INC_FILES	:= $(wildcard include/*.h)
SRC_FILES	:= $(wildcard src/*.cpp)

OBJ_FILES	:= $(patsubst %.cpp, %.o, ${SRC_FILES})
OBJS		:= $(notdir ${OBJ_FILES})
DIR_OBJS	:= $(addprefix obj/, ${OBJS})
OBJ_DIR		:= obj/
SRC_DIR		:= src/
INC_DIR		:= include/

${OBJ_DIR}%.o: ${SRC_DIR}%.cpp
	${CC} ${CXXFLAGS} ${INC} ${LIB} -c -o $@ $<

${Target}: ${DIR_OBJS}
	${CC} ${CXXFLAGS} ${INC} ${LIB} -o $@ $^

clean:
	rm -rf main main.dSYM obj/*

test:
	echo ${OBJS}
