#-------------------------------------------------------------------------------
# theora
#-------------------------------------------------------------------------------

SET(theora_sources
    lib/apiwrapper.c
	lib/bitpack.c
	lib/decapiwrapper.c
    lib/decinfo.c
	lib/decode.c
	lib/dequant.c
	lib/fragment.c
    lib/huffdec.c
    lib/idct.c
    lib/info.c
    lib/internal.c
    lib/quant.c
    lib/state.c
)
SOURCE_GROUP(theora FILES ${theora_sources})

ADD_LIBRARY(theora STATIC ${theora_sources})
TARGET_INCLUDE_DIRECTORIES(theora PUBLIC include ${Nebula3_SOURCE_DIR}/code/extlibs/ogg/include )
SET_TARGET_PROPERTIES(theora PROPERTIES FOLDER "extlibs")

N_SET_COMPILER_DEFAULTS(theora)
IF(MSVC)
    ADD_DEFINITIONS(/D_CRT_SECURE_NO_WARNINGS)
ENDIF()
