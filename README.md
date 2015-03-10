# libdvdread-vgtmpeg
libdvdread is a dvd reading and parsing library based on the original libdvdread. It offers some bug fixes over the original library, as well as some additional features. libdvdread-vgtmpeg is the dvd reading library used by [vgtmpeg]
####features
- Reads from VIDEO_TS folder, ISO image, or folder files
- has hooks for a possible CSS library (not included, library can't read encrypted folders)
- full DVD navigation, titles, and chapter information.

####logging
The original libdvdread lacks a proper logging mechanism and by default messages are send to stderr/stdout. libdvdread-vgtmpeg has a hook to provide your own function for logging so you can redirect all messaging from the library to your application.

The additional APIs are defined in `dvd_reader.h`. The relevant APIs for logging are the following:

```c
#define DVDREAD_LOGLEVEL_NORMAL 1
#define DVDREAD_LOGLEVEL_VERBOSE 5

typedef void (*dvd_reader_logf)(const char *);

dvd_reader_t *DVDOpenEx( const char *, dvd_reader_logf log, int loglevel );

```

Define your own `dvd_reader_logf` function in your user code. This function will get called to output all the log messages from inside libdvdread-vgtmpeg. The logging function is provided when you open the DVD library with `DVDOpenEx`. The parameter `loglevel` specifies the verbosity of the logging messages.

####license
libdvdread-vgtmpeg is released under the GPL license

####author
Alberto Vigata. Learn more [about me](http://vigata.com/about)




[vgtmpeg]:http://github.com/concalma/vgtmpeg


