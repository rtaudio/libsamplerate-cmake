cmake_minimum_required(VERSION 3.1)
project(libsamplerate)

include_directories(libsamplerate/src)

if(WIN32)
	include_directories(libsamplerate/Win32)
endif(WIN32)

set(COEFF_HDRS libsamplerate/src/fastest_coeffs.h libsamplerate/src/mid_qual_coeffs.h libsamplerate/src/high_qual_coeffs.h)

set(noinst_HEADERS libsamplerate/src/common.h libsamplerate/src/float_cast.h ${COEFF_HDRS})

set(SRC_SOURCES libsamplerate/src/samplerate.c libsamplerate/src/src_sinc.c ${COEFF_HDRS} libsamplerate/src/src_zoh.c libsamplerate/src/src_linear.c)


add_library(libsamplerate STATIC ${SRC_SOURCES})
