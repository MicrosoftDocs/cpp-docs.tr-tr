---
title: "-SAFESEH (görüntüde güvenli özel durum işleyicileri vardır) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /SAFESEH
dev_langs: C++
helpviewer_keywords:
- /SAFESEH linker option
- -SAFESEH linker option
- SAFESEH linker option
ms.assetid: 7722ff99-b833-4c65-a855-aaca902ffcb7
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 430991838245e258a8f1b4bffe16a2f559019901
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="safeseh-image-has-safe-exception-handlers"></a>/SAFESEH (Görüntüde Güvenli Özel Durum İşleyicileri Var)
```  
/SAFESEH[:NO]  
```  
  
 Zaman **SAFESEH** belirtilirse, bağlayıcı yalnızca oluşturacak bir görüntü, görüntünün güvenli özel durum işleyicileri oluşan bir tablo oluşturabilir. Bu tablo hangi özel durum işleyicileri yansıma için geçerli işletim sistemini belirtir.  
  
 **/ SAFESEH** için x86 bağlanırken yalnızca geçerli olan hedefler. **/ SAFESEH** not ettiğiniz özel durum işleyicileri zaten platformlar için desteklenmiyor. Örneğin, [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] ve ARM, tüm özel durum işleyicileri PDATA belirtilmiştir. ML64.exe aracılığıyla ml64 işlevleri bırakma olanak tanıyan görüntüye SEH bilgileri (XDATA ve PDATA) yayma ek açıklamaları eklemek için desteğe sahiptir. Bkz: [x64 (ml64.exe) için MASM](../../assembler/masm/masm-for-x64-ml64-exe.md) daha fazla bilgi için.  
  
 Varsa **SAFESEH** belirtilmezse, tüm modüllerin güvenli özel durum işleme özelliğiyle uyumlu olup olmadıklarını bağlayıcı güvenli özel durum işleyicileri tablosu görüntüyle oluşturacak. Hiçbir modül özelliği güvenli özel durum işleme ile uyumlu değil, elde edilen görüntü güvenli özel durum işleyicileri tablosu içermez. Varsa [/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) WINDOWSCE veya EFI_ * seçeneklerden birini belirtir bağlayıcı güvenli özel durum işleyicileri olarak bir tablo olan bir görüntü oluşturmak çalışmaz bu alt sistemleri hiçbiri yapabilirsiniz gibi bilgileri kullanın.  
  
 Varsa **/SAFESEH:NO** belirtilirse, bağlayıcı olmayan oluşturacak güvenli özel durum işleyicileri tablosu görüntüyle özelliği güvenli özel durum işleme ile uyumlu olan tüm modülleri olsa bile.  
  
 Bir veya daha fazla bağlayıcı için girdi dosyaları (modüller) güvenli özel durum işleyicileri özelliği ile uyumlu olmadığı için bir görüntü oluşturmak mümkün olmaması bağlayıcı en yaygın nedeni. Önceki sürümünden Visual C++ derleyicisi ile oluşturulduğundan güvenli özel durum işleyicileri ile uyumlu olmadığı bir modül ortak bir nedeni.  
  
 Kullanarak yapılandırılmış özel durum işleyici olarak bir işlev kaydedebilirsiniz [. SAFESEH](../../assembler/masm/dot-safeseh.md).  
  
 Var olan işaretlemek mümkün değil ikili olarak güvenli özel durum işleyicileri (veya hiçbir özel durum işleyicileri); derleme zamanında güvenli özel durum işleme hakkında bilgi eklenmesi gerekir.  
  
 Bağlayıcı'nın Güvenli özel durum işleyicileri tablosunu yeteneği C çalışma zamanı kitaplığını kullanarak uygulamaya bağlıdır. İle bağlantı varsa [/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) ve güvenli özel durum işleyicileri tablosu istediğiniz, yük config yapı (loadcfg.c CRT kaynak dosyasında bulunan gibi) sağlamanız gereken Visual C++ için tanımlanan tüm girişleri içerir. Örneğin:  
  
```  
#include <windows.h>  
extern DWORD_PTR __security_cookie;  /* /GS security cookie */  
  
/*  
 * The following two names are automatically created by the linker for any  
 * image that has the safe exception table present.  
*/  
  
extern PVOID __safe_se_handler_table[]; /* base of safe handler entry table */  
extern BYTE  __safe_se_handler_count;  /* absolute symbol whose address is  
                                           the count of table entries */  
typedef struct {  
    DWORD       Size;  
    DWORD       TimeDateStamp;  
    WORD        MajorVersion;  
    WORD        MinorVersion;  
    DWORD       GlobalFlagsClear;  
    DWORD       GlobalFlagsSet;  
    DWORD       CriticalSectionDefaultTimeout;  
    DWORD       DeCommitFreeBlockThreshold;  
    DWORD       DeCommitTotalFreeThreshold;  
    DWORD       LockPrefixTable;            // VA  
    DWORD       MaximumAllocationSize;  
    DWORD       VirtualMemoryThreshold;  
    DWORD       ProcessHeapFlags;  
    DWORD       ProcessAffinityMask;  
    WORD        CSDVersion;  
    WORD        Reserved1;  
    DWORD       EditList;                   // VA  
    DWORD_PTR   *SecurityCookie;  
    PVOID       *SEHandlerTable;  
    DWORD       SEHandlerCount;  
} IMAGE_LOAD_CONFIG_DIRECTORY32_2;  
  
const IMAGE_LOAD_CONFIG_DIRECTORY32_2 _load_config_used = {  
    sizeof(IMAGE_LOAD_CONFIG_DIRECTORY32_2),  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    &__security_cookie,  
    __safe_se_handler_table,  
    (DWORD)(DWORD_PTR) &__safe_se_handler_count  
};  
```  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Seçin **bağlayıcı** klasör.  
  
3.  Seçin **komut satırı** özellik sayfası.  
  
4.  Seçeneğini girin **ek seçenekler** kutusu.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı seçenekleri](../../build/reference/linker-options.md)