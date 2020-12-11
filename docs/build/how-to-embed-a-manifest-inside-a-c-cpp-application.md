---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: bir bildirimi C/C++ uygulamasına ekleme'
title: 'Nasıl Yapılır: C/C++ Uygulamasına Bildirim Katıştırma'
ms.date: 05/06/2019
helpviewer_keywords:
- manifests [C++]
- embedding manifests
- makefiles, updating to embed manifest
ms.assetid: ec0bac69-2fdc-466c-ab0d-710a22974e5d
ms.openlocfilehash: ce3bdd56b994498b223857b80989247fe9919e4c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97156352"
---
# <a name="how-to-embed-a-manifest-inside-a-cc-application"></a>Nasıl Yapılır: C/C++ Uygulamasına Bildirim Katıştırma

Çoğu senaryoda doğru çalışma zamanı davranışını garanti ettiğinden, uygulamanızın veya kitaplığınızın bildirimini son ikilinin içine katıştırmanız önerilir. Varsayılan olarak, Visual Studio bir proje oluşturduğunda bildirimi katıştırmaya çalışır. Daha fazla bilgi için bkz. [Visual Studio 'Da bildirim oluşturma](manifest-generation-in-visual-studio.md). Ancak, NMAKE kullanarak uygulamanızı derleyebilirsiniz, derleme görevleri dosyası üzerinde bazı değişiklikler yapmanız gerekir. Bu bölümde, bildirimi son ikilinin içinde otomatik olarak katıştıran derleme görevleri dosyalarını 'ın nasıl değiştirileceği gösterilmektedir.

## <a name="two-approaches"></a>İki yaklaşım

Bildirimi bir uygulama veya kitaplık içine gömmenin iki yolu vardır.

- Artımlı bir yapı gerçekleştirmeseniz, derleme sonrası bir adım olarak aşağıdakine benzer bir komut satırı kullanarak bildirimi doğrudan katıştırabilirsiniz:

   ```cmd
   mt.exe -manifest MyApp.exe.manifest -outputresource:MyApp.exe;1
   ```

   veya

   ```cmd
   mt.exe -manifest MyLibrary.dll.manifest -outputresource:MyLibrary.dll;2
   ```

   Bir EXE için 1, DLL için 2 kullanın.

- Artımlı derleme yapıyorsanız aşağıdaki adımları kullanın:

  - MyApp.exe. manifest dosyasını oluşturmak için ikiliyi bağlayın.

  - Bildirimi bir kaynak dosyasına dönüştürün.

  - Bildirim kaynağını ikiliye eklemek için yeniden bağlayın (artımlı).

Aşağıdaki örneklerde, her iki tekniği de içerecek şekilde derleme görevleri dosyalarını nasıl değiştirileceği gösterilmektedir.

## <a name="makefiles-before"></a>Makefiles (önceki)

Tek bir dosyadan oluşturulan basit bir uygulama olan MyApp.exe için nmake betiğini göz önünde bulundurun:

```
# build MyApp.exe
!if "$(DEBUG)" == "1"
CPPFLAGS=$(CPPFLAGS) /MDd
LFLAGS=$(LFLAGS) /INCREMENTAL
!else
CPPFLAGS=$(CPPFLAGS) /MD
!endif

MyApp.exe : MyApp.obj
    link $** /out:$@ $(LFLAGS)

MyApp.obj : MyApp.cpp

clean :
    del MyApp.obj MyApp.exe
```

Bu betik, Visual Studio ile değişmeden çalışıyorsa, MyApp.exe başarıyla oluşturulur. Ayrıca, çalışma zamanında bağımlı derlemeleri yüklemek için işletim sistemi tarafından kullanılmak üzere MyApp.exe. manifest dış bildirim dosyasını da oluşturur.

MyLibrary.dll için nmake betiği çok benzer şekilde görünür:

```
# build MyLibrary.dll
!if "$(DEBUG)" == "1"
CPPFLAGS=$(CPPFLAGS) /MDd
LFLAGS=$(LFLAGS) /DLL /INCREMENTAL

!else
CPPFLAGS=$(CPPFLAGS) /MD
LFLAGS=$(LFLAGS) /DLL

!endif

MyLibrary.dll : MyLibrary.obj
    link $** /out:$@ $(LFLAGS)

MyLibrary.obj : MyLibrary.cpp

clean :
    del MyLibrary.obj MyLibrary.dll
```

## <a name="makefiles-after"></a>Makefiles (sonra)

Katıştırılmış bildirimlerle derlemek için özgün makefiles üzerinde dört küçük değişiklik yapmanız gerekir. MyApp.exe makefile için:

```
# build MyApp.exe
!include makefile.inc
#^^^^^^^^^^^^^^^^^^^^ Change #1. (Add full path if necessary.)

!if "$(DEBUG)" == "1"
CPPFLAGS=$(CPPFLAGS) /MDd
LFLAGS=$(LFLAGS) /INCREMENTAL
!else
CPPFLAGS=$(CPPFLAGS) /MD
!endif

MyApp.exe : MyApp.obj
    link $** /out:$@ $(LFLAGS)
    $(_VC_MANIFEST_EMBED_EXE)
#^^^^^^^^^^^^^^^^^^^^^^^^^^^^ Change #2

MyApp.obj : MyApp.cpp

clean :
    del MyApp.obj MyApp.exe
    $(_VC_MANIFEST_CLEAN)
#^^^^^^^^^^^^^^^^^^^^^^^^ Change #3

!include makefile.targ.inc
#^^^^^^^^^^^^^^^^^^^^^^^^^ Change #4. (Add full path if necessary.)
```

MyLibrary.dll makefile için:

```
# build MyLibrary.dll
!include makefile.inc
#^^^^^^^^^^^^^^^^^^^^ Change #1. (Add full path if necessary.)

!if "$(DEBUG)" == "1"
CPPFLAGS=$(CPPFLAGS) /MDd
LFLAGS=$(LFLAGS) /DLL /INCREMENTAL

!else
CPPFLAGS=$(CPPFLAGS) /MD
LFLAGS=$(LFLAGS) /DLL

!endif

MyLibrary.dll : MyLibrary.obj
    link $** /out:$@ $(LFLAGS)
    $(_VC_MANIFEST_EMBED_DLL)
#^^^^^^^^^^^^^^^^^^^^^^^^^^^^ Change #2.

MyLibrary.obj : MyLibrary.cpp

clean :
    del MyLibrary.obj MyLibrary.dll
    $(_VC_MANIFEST_CLEAN)
#^^^^^^^^^^^^^^^^^^^^^^^^ Change #3.

!include makefile.targ.inc
#^^^^^^^^^^^^^^^^^^^^^^^^^ Change #4. (Add full path if necessary.)
```

Derleme görevleri dosyalarını artık gerçek işi yapan derleme görevleri dosyası. inc ve makefile. Targ. inc olan iki dosya içerir.

Makefile. inc oluşturun ve aşağıdakileri içine kopyalayın:

```
# makefile.inc -- Include this file into existing makefile at the very top.

# _VC_MANIFEST_INC specifies whether build is incremental (1 - incremental).
# _VC_MANIFEST_BASENAME specifies name of a temporary resource file.

!if "$(DEBUG)" == "1"
CPPFLAGS=$(CPPFLAGS) /MDd
LFLAGS=$(LFLAGS) /INCREMENTAL
_VC_MANIFEST_INC=1
_VC_MANIFEST_BASENAME=__VC90.Debug

!else
CPPFLAGS=$(CPPFLAGS) /MD
_VC_MANIFEST_INC=0
_VC_MANIFEST_BASENAME=__VC90

!endif

####################################################
# Specifying name of temporary resource file used only in incremental builds:

!if "$(_VC_MANIFEST_INC)" == "1"
_VC_MANIFEST_AUTO_RES=$(_VC_MANIFEST_BASENAME).auto.res
!else
_VC_MANIFEST_AUTO_RES=
!endif

####################################################
# _VC_MANIFEST_EMBED_EXE - command to embed manifest in EXE:

!if "$(_VC_MANIFEST_INC)" == "1"

#MT_SPECIAL_RETURN=1090650113
#MT_SPECIAL_SWITCH=-notify_resource_update
MT_SPECIAL_RETURN=0
MT_SPECIAL_SWITCH=
_VC_MANIFEST_EMBED_EXE= \
if exist $@.manifest mt.exe -manifest $@.manifest -out:$(_VC_MANIFEST_BASENAME).auto.manifest $(MT_SPECIAL_SWITCH) & \
if "%ERRORLEVEL%" == "$(MT_SPECIAL_RETURN)" \
rc /r $(_VC_MANIFEST_BASENAME).auto.rc & \
link $** /out:$@ $(LFLAGS)

!else

_VC_MANIFEST_EMBED_EXE= \
if exist $@.manifest mt.exe -manifest $@.manifest -outputresource:$@;1

!endif

####################################################
# _VC_MANIFEST_CLEAN - command to clean resources files generated temporarily:

!if "$(_VC_MANIFEST_INC)" == "1"

_VC_MANIFEST_CLEAN=-del $(_VC_MANIFEST_BASENAME).auto.res \
    $(_VC_MANIFEST_BASENAME).auto.rc \
    $(_VC_MANIFEST_BASENAME).auto.manifest

!else

_VC_MANIFEST_CLEAN=

!endif

# End of makefile.inc
####################################################
```

Şimdi **derleme görevleri dosyası. Targ. inc** oluşturun ve aşağıdakileri içine kopyalayın:

```
# makefile.targ.inc - include this at the very bottom of the existing makefile

####################################################
# Commands to generate initial empty manifest file and the RC file
# that references it, and for generating the .res file:

$(_VC_MANIFEST_BASENAME).auto.res : $(_VC_MANIFEST_BASENAME).auto.rc

$(_VC_MANIFEST_BASENAME).auto.rc : $(_VC_MANIFEST_BASENAME).auto.manifest
    type <<$@
#include <winuser.h>
1RT_MANIFEST"$(_VC_MANIFEST_BASENAME).auto.manifest"
<< KEEP

$(_VC_MANIFEST_BASENAME).auto.manifest :
    type <<$@
<?xml version='1.0' encoding='UTF-8' standalone='yes'?>
<assembly xmlns='urn:schemas-microsoft-com:asm.v1' manifestVersion='1.0'>
</assembly>
<< KEEP

# end of makefile.targ.inc
```

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ programları için bildirim oluşturmayı anlama](understanding-manifest-generation-for-c-cpp-programs.md)
