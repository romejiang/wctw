include theos/makefiles/common.mk

LDFLAGS += -F. -framework Cycript -framework JavaScriptCore

TWEAK_NAME = wctw
wctw_FILES = Tweak.xm fishhook/fishhook.c
wctw_LDFLAGS =  -Wtautological-pointer-compare
wctw_CFLAGS =  -Wno-error=format-security -Wno-error=unused-function -Wno-error=unused-variable
wctw_FRAMEWORKS = Foundation  CoreGraphics UIKit


LOCAL_INSTALL_PATH = /usr/lib
#指定版本
_THEOS_TARGET_LDFLAGS += -current_version 1.0.0
_THEOS_TARGET_LDFLAGS += -compatibility_version 1.0.0

include $(THEOS_MAKE_PATH)/tweak.mk

after-install::
	install.exec "killall -9 SpringBoard"
