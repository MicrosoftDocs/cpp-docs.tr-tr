---
title: /SAFESEH (Görüntüde Güvenli Özel Durum İşleyicileri Var)
ms.date: 11/04/2016
f1_keywords:
- /SAFESEH
helpviewer_keywords:
- /SAFESEH linker option
- -SAFESEH linker option
- SAFESEH linker option
ms.assetid: 7722ff99-b833-4c65-a855-aaca902ffcb7
ms.openlocfilehash: 62784933cbecd4f312c52ae98cab7d232b893f35
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62318647"
---
# <a name="safeseh-image-has-safe-exception-handlers"></a>/SAFESEH (Görüntüde Güvenli Özel Durum İşleyicileri Var)

```
/SAFESEH[:NO]
```

Zaman **SAFESEH** belirtildiğinde, bağlayıcı yalnızca ilişkilendiren bir görüntü, görüntünün güvenli özel durum işleyicileri tablosu oluşturabilir. Bu tabloda görüntüye ait geçerli özel durum işleyicilerine işletim sistemini belirtir.

**/ SAFESEH** x86 için bağlanırken yalnızca geçerli olan hedefler. **/ SAFESEH** zaten belirtilen özel durum işleyicileri var platformlar için desteklenmiyor. Örneğin, x64 ve ARM, tüm özel durum işleyicileri PDATA içinde belirtilmiştir. ML64.exe ml64 işlevleri aracılığıyla geriye doğru izleme olanak tanıyan, görüntüye (XDATA ve PDATA) SEH bilgileri yayma ek açıklamaları ekleme desteği vardır. Bkz: [x64 (ml64.exe) için MASM](../../assembler/masm/masm-for-x64-ml64-exe.md) daha fazla bilgi için.

Varsa **SAFESEH** belirtilmezse, tüm modüller güvenli özel durum işleme özelliği ile uyumlu değilse, bağlayıcı görüntünün güvenli özel durum işleyicileri tablosu ile üretir. Modüllerin özellik Güvenli özel durum işleme ile uyumlu değilse, elde edilen görüntü güvenli özel durum işleyicileri tablosu içermez. Varsa [/Subsystem](subsystem-specify-subsystem.md) WINDOWSCE veya EFI_ * seçeneklerden birini belirtir bağlayıcı görüntünün güvenli özel durum işleyicileri tablosu ile üretmek yazılmayacak söz konusu alt sistemlerde hiçbirine değişiklik bilgilerini kullanın.

Varsa **/SAFESEH:NO** belirtildiğinde, bağlayıcı olmayan ilişkilendiren görüntünün güvenli özel durum işleyicileri tablosu ile özellik Güvenli özel durum işleme ile uyumlu olan tüm modülleri olsa bile.

Görüntü üretmek yükleyemeyecektir bağlayıcı en yaygın nedeni, bir veya daha fazla bağlayıcı giriş dosyaları (modülleri) güvenli özel durum işleyicileri özelliği ile uyumlu olmadığından olmasıdır. Visual C++'ın önceki bir sürümden bir derleyici ile oluşturulduğundan bir modül, güvenli özel durum işleyicileri ile uyumlu olmaması için yaygın bir nedeni var.

Kullanarak bir yapılandırılmış özel durum işleyici bir işlev kaydedebilirsiniz [. SAFESEH](../../assembler/masm/dot-safeseh.md).

Mevcut bir işaretlemek mümkün değildir ikili olarak güvenli özel durum işleyicileri (veya hiçbir özel durum işleyicileri); oluşturma zamanında güvenli özel durum işleme hakkında bilgi eklenmesi gerekir.

Bağlayıcı'nın Güvenli özel durum işleyicileri tablosu oluşturma olanağı, C çalışma zamanı kitaplığı kullanarak uygulamaya bağlıdır. İle bağlarsanız [/nodefaultlıb](nodefaultlib-ignore-libraries.md) ve, güvenli özel durum işleyicileri tablosu istiyorsanız, bir yük yapılandırma yapısı (loadcfg.c CRT kaynak dosyasında bulunan gibi) sağlamak gereken Visual C++ için tanımlanmış olan tüm girişleri içerir. Örneğin:

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

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **bağlayıcı** klasör.

1. Seçin **komut satırı** özellik sayfası.

1. Seçeneğini girin **ek seçenekler** kutusu.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
