UNAME_S := $(shell uname -s)
ifeq ($(UNAME_S),Linux)
	OPENCV_LIBS = -L/usr/local/lib -pthread -lopencv_imgcodecs -lopencv_imgproc -lopencv_core -lopencv_highgui
	INC = -I/usr/local/include/opencv2/
	OSX_LIBS=
endif

ifeq ($(UNAME_S),Darwin)
	OPENCV_LIBS = -L../../lib/ -lIlmImf -llibtiff -lopencv_imgcodecs -lippicv -llibwebp -lopencv_imgproc -llibjasper -lopencv_core -lzlib -llibjpeg -lopencv_hal -llibpng -lopencv_highgui
	OSX_LIBS = -framework OpenCL -framework Cocoa
	INC = -I../../include/
endif

all : test.out

test: test.cpp
	$(CXX) -c test.cpp $(INC)

test.out : test
	$(CXX) -o test.out test.o $(OSX_LIBS) $(OPENCV_LIBS)

clean :
	rm *.o test*
