Objs                    = FrontEndDescription.o BeBoard.o Cbc.o Module.o Shelve.o
CC              = gcc
CXX             = g++
CCFlags         = -g -O1 -Wall -fPIC `root-config --cflags --glibs --evelibs`
#DevFlags                   = -D__CBCDAQ_DEV__
DevFlags               =

IncludeDirs     =  /opt/cactus/include ../

IncludePaths            = $(IncludeDirs:%=-I%)

%.o: %.cc %.h
	$(CXX) -std=c++11 $(DevFlags) $(CCFlags) $(UserCCFlags) $(CCDefines) $(IncludePaths) -c -o $@ $<


all: $(Objs)
	$(CC) -shared -o libPh2_Description.so $(Objs)
	mv libPh2_Description.so ../lib

clean:
	rm -f *.o
