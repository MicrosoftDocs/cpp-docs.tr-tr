---
title: 'Nasıl yapılır: C/C++ uygulamasına bildirim katıştırma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- manifests [C++]
- embedding manifests
- makefiles, updating to embed manifest
ms.assetid: ec0bac69-2fdc-466c-ab0d-710a22974e5d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7dec5377bca1cc56e2444d7466fc5107d594205a
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/14/2018
ms.locfileid: "42465166"
---
# <a name="how-to-embed-a-manifest-inside-a-cc-application"></a>Nasıl Yapılır: C/C++ Uygulamasına Bildirim Katıştırma
C/C++ uygulamasına (veya kitaplık) sahip olduğundan bu doğru çalışma zamanı davranışı Çoğu senaryoda garanti eder içinde son ikili dosyada gömülü bildirimi önerilir. Varsayılan olarak, Visual Studio kaynak dosyalarından bir proje oluştururken bildirimi katıştırmak çalışır; bkz: [Visual Studio'da bildirim oluşturma](../build/manifest-generation-in-visual-studio.md) daha fazla bilgi için. Nmake kullanarak bir uygulama oluşturulursa, ancak bazı değişiklikler mevcut derleme görevleri dosyası gereklidir. Bu bölüm, nasıl otomatik olarak son ikili bildirim katıştırma için mevcut derleme görevleri dosyalarını değiştirileceğini gösterir.  
  
## <a name="two-approaches"></a>İki yaklaşım  
 Bir uygulama veya kitaplık bildirim katıştırma iki yolu vardır.  
  
-   Artımlı derleme uygulamıyorsanız doğrudan oluşturma sonrası adımı aşağıdakine benzer bir komut satırı kullanarak bildirimi ekleyebilirsiniz:  
  
     **MT.exe-MyApp.exe.manifest bildirim-outputresource:MyApp.exe;1**  
  
     veya  
  
     **MT.exe-MyLibrary.dll.manifest bildirim-outputresource:MyLibrary.dll;2**  
  
     (1 için bir EXE, DLL için 2.)  
  
-   Artımlı derleme yapıyorsanız, doğrudan kaynak burada gösterildiği şekilde düzenleyerek artımlı oluşturmayı devre dışı bırakmak ve tam yeniden derleme neden; Bu nedenle, farklı bir yaklaşım gerçekleştirilmelidir:  
  
    -   MyApp.exe.manifest dosyası oluşturmak için ikili bağlayın.  
  
    -   Bildirim, bir kaynak dosyasına dönüştürün.  
  
    -   (Artımlı) bildirim kaynağı ikili olarak eklemek için yeniden bağlayın.  
  
 Aşağıdaki örnekler, her iki tekniği birleştirmek için derleme görevleri dosyalarını değiştirme gösterir.  
  
## <a name="makefiles-before"></a>Derleme görevleri dosyalarını (önce)  
 Nmake komut, MyApp.exe, bir dosyadaki oluşturulmuş basit bir uygulama için göz önünde bulundurun:  
  
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
  
 Bu betik, Visual C++ ile değişmeden çalıştırılırsa başarıyla MyApp.exe oluşturur. Ayrıca, çalışma zamanında bağımlı derlemeleri yüklemek için işletim sistemi tarafından kullanılacak dış bildirim dosyası MyApp.exe.manifest, oluşturur.  
  
 Nmake betik MyLibrary.dll için çok benzer görünür:  
  
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
  
## <a name="makefiles-after"></a>Derleme görevleri dosyalarını (sonra)  
 İle derlemek için orijinal derleme görevleri dosyaları için dört küçük değişiklikler yapmanız bildirimleri katıştırılmış. MyApp.exe için derleme görevleri dosyası:  
  
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
  
 MyLibrary.dll için derleme görevleri dosyası:  
  
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
  
 Derleme görevleri dosyası artık gerçek iş, makefile.inc ve makefile.targ.inc iki dosya içerir.  
  
 Makefile.inc oluşturun ve içine aşağıdaki kopyalayın:  
  
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
  
 Artık makefile.targ.inc oluşturun ve içine aşağıdaki kopyalayın:  
  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C/C++ Programları Bildirim Üretimini Anlama](../build/understanding-manifest-generation-for-c-cpp-programs.md)