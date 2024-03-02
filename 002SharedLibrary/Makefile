CC		= gcc
FLAGS	= -std=gnu99 -I$(INCDIR)
CFLAGS	= -fPIC -g # -pedantic -Wall -Wextra -ggdb3
#-soname belirtilmezse default olarak libmath.so alıyor.
LDFLAGS	= -shared -Wl,-soname,libmath.so.1

SOURCES=$(wildcard *.c)
OBJECTS=$(SOURCES:.c=.o)
TARGET=$(LIBDIR)/libmath.so.1.2.3

INCDIR=/home/huseyin/Desktop/GCC/002SharedLibrary/include
LIBDIR=/home/huseyin/Desktop/GCC/002SharedLibrary/lib

.PHONY: all
all:$(TARGET)
	@echo "Compile Done!"

$(TARGET):$(OBJECTS)
	@echo "Link Library"
	$(CC) $(CFLAGS) $(LDFLAGS) -o $@ $^ -lm

#$@ target tarafını al, $^ dependency tarafını al ; bunlar vb.leri automatic variable olarak geçer.
#% joker character olarak geçer.%.o: %.c patterni ile kullanımı yaygındır.
$(OBJECTS):$(SOURCES)
	@echo "Compiling"
	$(CC) $(FLAGS) $(CFLAGS) -c $^

.PHONY: clean
clean:
	rm -rf $(OBJECTS) $(TARGET)
