NAME = libnativehelper
SOURCES = JNIHelp.cpp \
          JniConstants.cpp \
          toStringArray.cpp \
          JniInvocation.cpp \
          AsynchronousCloseMonitor.cpp
CXXFLAGS += -fvisibility=protected
CPPFLAGS += -Iinclude/nativehelper -I/usr/include/android/libcore
LDFLAGS += -shared -Wl,-soname,$(NAME).so.0 -ldl -lpthread \
           -Wl,-rpath=/usr/lib/$(DEB_HOST_MULTIARCH)/android \
           -L/usr/lib/$(DEB_HOST_MULTIARCH)/android -llog

build: $(SOURCES)
	$(CXX) $^ -o $(NAME).so.0 $(CXXFLAGS) $(CPPFLAGS) $(LDFLAGS)
	ln -s $(NAME).so.0 $(NAME).so

clean:
	$(RM) *.so*