---
description: :/SAFESEH hakkında daha fazla bilgi edinin (görüntü güvenli özel durum Işleyicilerine sahiptir)
title: /SAFESEH (Görüntüde Güvenli Özel Durum İşleyicileri Var)
ms.date: 11/04/2016
f1_keywords:
- /SAFESEH
helpviewer_keywords:
- /SAFESEH linker option
- -SAFESEH linker option
- SAFESEH linker option
ms.assetid: 7722ff99-b833-4c65-a855-aaca902ffcb7
ms.openlocfilehash: 723b5503bca1d98d7df0c638df1dfc8101fc116f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224991"
---
# <a name="safeseh-image-has-safe-exception-handlers"></a>/SAFESEH (Görüntüde Güvenli Özel Durum İşleyicileri Var)

```
/SAFESEH[:NO]
```

**/SafeSEH** belirtildiğinde, bağlayıcı yalnızca görüntünün güvenli özel durum işleyicilerinin bir tablosunu oluşturmak için bir görüntü oluşturur. Bu tablo, görüntü için geçerli olan özel durum işleyicilerinin hangi işletim sistemini belirtir.

**/SafeSEH** yalnızca x86 hedefleri bağlanırken geçerlidir. **/SafeSEH** , belirtilen özel durum işleyicisine zaten sahip olan platformlar için desteklenmez. Örneğin, x64 ve ARM 'de tüm özel durum işleyicileri PDATA 'da belirtilmiştir. ML64.exe, görüntüye SEH bilgilerini (XDATA ve PDATA) sunan ek açıklamalar ekleme desteğiyle, ML64 işlevlerini kullanarak geriye doğru izleme olanağı sağlar. Daha fazla bilgi için bkz. [x64 Için Masd (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md) .

**/SafeSEH** belirtilmemişse, tüm modüller güvenli özel durum işleme özelliği ile uyumluysa bağlayıcı, güvenli özel durum işleyicileri tablosu içeren bir görüntü oluşturur. Herhangi bir modül güvenli özel durum işleme özelliğiyle uyumlu değilse, sonuçta elde edilen görüntü güvenli özel durum işleyicileri tablosu içermez. [/Subsystem](subsystem-specify-subsystem.md) , WindowsCE veya EFI_ * seçeneklerinden birini belirtiyorsa, bu alt sistemlerin hiçbiri bilgileri kullanmadığı için bağlayıcı güvenli özel durum işleyicileri tablosuyla bir görüntü üretmeye çalışmaz.

**/SafeSEH: No** belirtilmişse, tüm modüller güvenli özel durum işleme özelliğiyle uyumlu olsa bile bağlayıcı güvenli özel durum işleyicileri tablosuyla bir görüntü oluşturmaz.

Bağlayıcının bir görüntü üretmemesi için en yaygın nedeni, bağlayıcının bir veya daha fazla giriş dosyasının (modüller) güvenli özel durum işleyicileri özelliğiyle uyumlu olmaması olabilir. Modülün güvenli özel durum işleyicileriyle uyumlu olmaması yaygın bir nedenden dolayı, önceki bir Visual C++ sürümünden derleyici ile oluşturulmuştur.

Ayrıca, kullanarak bir işlevi yapılandırılmış özel durum işleyicisi olarak kaydedebilirsiniz [. SAFESEH](../../assembler/masm/dot-safeseh.md).

Var olan ikiliyi, güvenli özel durum işleyicilerine sahip olacak şekilde işaretlemek mümkün değildir (veya özel durum işleyicileri yoktur); güvenli özel durum işleme hakkında bilgi oluşturma zamanında eklenmelidir.

Bağlayıcının güvenli özel durum işleyicileri tablosu oluşturma yeteneği, C çalışma zamanı kitaplığını kullanarak uygulamaya bağlıdır. [/Nodefaultlib](nodefaultlib-ignore-libraries.md) ile bağlantı oluşturursanız ve bir güvenli özel durum işleyicileri tablosu istiyorsanız, Visual C++ için tanımlanan tüm girişleri içeren bir Load config yapısı (örneğin, loadcfg. c CRT kaynak dosyasında bulunabilir) sağlamanız gerekir. Örneğin:

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

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasörünü seçin.

1. **Komut satırı** özellik sayfasını seçin.

1. **Ek seçenekler** kutusuna seçeneği girin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
