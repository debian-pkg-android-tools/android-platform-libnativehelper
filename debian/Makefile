NAME = libnativehelper
SOURCES = JNIHelp.cpp \
          JniConstants.cpp \
          toStringArray.cpp \
          JniInvocation.cpp
CFLAGS += -fvisibility=protected
CPPFLAGS += -Iinclude/nativehelper -I/usr/include/android
LDFLAGS +=-shared -Wl,-soname,$(NAME).so.0

build: $(SOURCES)
	$(CC) $^ -o $(NAME).so.0 $(CFLAGS) $(CPPFLAGS) $(LDFLAGS)
	ln -s $(NAME).so.0 $(NAME).so

clean:
	$(RM) *.so*