
list(APPEND SOURCE
    fdo.c
    pci.c
    pdo.c
    pci.h)

add_library(pci SHARED ${SOURCE} pci.rc)
set_module_type(pci kernelmodedriver)
add_importlibs(pci ntoskrnl hal)
add_pch(pci pci.h SOURCE)
add_cd_file(TARGET pci DESTINATION reactos/system32/drivers NO_CAB FOR all)
