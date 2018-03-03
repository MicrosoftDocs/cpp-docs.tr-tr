---
title: "Nasıl yapılır: C/C++ uygulamasına bildirim katıştırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- manifests [C++]
- embedding manifests
- makefiles, updating to embed manifest
ms.assetid: ec0bac69-2fdc-466c-ab0d-710a22974e5d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0950cff4cb568f0adcae5e7d523f233868da013d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-embed-a-manifest-inside-a-cc-application"></a>Nasıl Yapılır: C/C++ Uygulamasına Bildirim Katıştırma
C/C++ uygulamasına (veya kitaplığa) bu çoğu senaryoda doğru çalışma zamanı davranışı güvence altına alır çünkü içinde son ikili katıştırılmış kendi bildirimi olması önerilir. Varsayılan olarak, [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] kaynak dosyalarından proje oluşturduğunda bildirimi katıştırmak çalışır; bkz [Visual Studio'da bildirim oluşturma](../build/manifest-generation-in-visual-studio.md) daha fazla bilgi için. Ancak uygulama nmake kullanarak oluşturulursa, bazı değişiklikler mevcut derleme görevleri dosyası gereklidir. Bu bölümde, otomatik olarak son ikili içinde bildirimi katıştırmak için varolan derleme görevleri dosyaları değiştirmek gösterilmiştir.  
  
## <a name="two-approaches"></a>İki yaklaşım  
 Bir uygulama ya da kitaplık içine bildirimi katıştırmak için iki yolu vardır.  
  
-   Bir artımlı derleme yapıyorlarsa değil, doğrudan oluşturma sonrası bir adım aşağıdakine benzer bir komut satırını kullanarak bildirimi katıştırmak:  
  
     **MT.exe-MyApp.exe.manifest bildirimi-outputresource:MyApp.exe;1**  
  
     veya  
  
     **MT.exe-MyLibrary.dll.manifest bildirimi-outputresource:MyLibrary.dll;2**  
  
     bir EXE, DLL için 2 için (1.)  
  
-   Bir artımlı derleme yapıyorsanız, aşağıda gösterildiği gibi kaynak doğrudan düzenleyerek artımlı yapı devre dışı bırakın ve tam bir yeniden oluşturma neden; Bu nedenle farklı bir yaklaşım gerçekleştirilmelidir:  
  
    -   MyApp.exe.manifest dosyası oluşturmak için ikili bağlayın.  
  
    -   Bildirim kaynak dosyasına dönüştürün.  
  
    -   (Artımlı) bildirim kaynağı ikili olarak eklemek için yeniden bağlayın.  
  
 Aşağıdaki örnekler, her iki tekniği de içerecek şekilde derleme görevleri dosyaları değiştirmek nasıl gösterir.  
  
## <a name="makefiles-before"></a>Derleme görevleri dosyaları (önce)  
 Nmake betik MyApp.exe, bir dosyadan yerleşik basit bir uygulama için göz önünde bulundurun:  
  
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
  
 Bu komut dosyasını Visual C++ ile değişmeden çalıştırılırsa başarıyla MyApp.exe oluşturur. Ayrıca, çalışma zamanında bağımlı derlemeleri yüklemek için işletim sistemi tarafından kullanılacak dış bildirim dosyası MyApp.exe.manifest, oluşturur.  
  
 Nmake betik MyLibrary.dll için çok benzer:  
  
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
  
## <a name="makefiles-after"></a>Derleme görevleri dosyaları (sonra)  
 İle oluşturmak için özgün makefile dört küçük değişiklikler yapmak zorunda bildirimleri katıştırılmış. MyApp.exe derleme görevleri dosyası için:  
  
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
  
 MyLibrary.dll derleme görevleri dosyası için:  
  
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
  
 Derleme görevleri dosyaları artık gerçek iş, makefile.inc ve makefile.targ.inc iki dosya içerir.  
  
 Makefile.inc oluşturun ve aşağıdaki bu dosyaya kopyalayın:  
  
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
  
 Şimdi makefile.targ.inc oluşturun ve aşağıdaki bu dosyaya kopyalayın:  
  
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