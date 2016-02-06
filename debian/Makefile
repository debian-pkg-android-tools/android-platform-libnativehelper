NAME = libnativehelper
SOURCES = JNIHelp.cpp \
          JniConstants.cpp \
          toStringArray.cpp \
          JniInvocation.cpp
CFLAGS += -fPIC -fvisibility=protected
CPPFLAGS += -include android/arch/AndroidConfig.h \
            -Iinclude/nativehelper -I/usr/include/android
LDFLAGS += -fPIC -shared -Wl,-soname,$(NAME).so.0

build: $(SOURCES)
	$(CC) $^ -o $(NAME).so.0 $(CFLAGS) $(CPPFLAGS) $(LDFLAGS)
	ln -s $(NAME).so.0 $(NAME).so

clean:
	$(RM) *.so*