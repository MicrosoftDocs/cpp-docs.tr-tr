---
title: Gecikmeli Yüklenen DLL'i Açıkça Kaldırma
ms.date: 11/04/2016
helpviewer_keywords:
- /DELAY:UNLOAD linker option
- DELAY:UNLOAD linker option
- __FUnloadDelayLoadedDLL2
- delayed loading of DLLs, unloading
ms.assetid: 1c4c5172-fd06-45d3-9e4f-f12343176b3c
ms.openlocfilehash: 9909a3e179aa6c0af3a622c7bf1b545326f90bbd
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57818446"
---
# <a name="explicitly-unloading-a-delay-loaded-dll"></a>Gecikmeli Yüklenen DLL'i Açıkça Kaldırma

[/Delay](delay-delay-load-import-settings.md): unload bağlayıcı seçeneği Gecikmeli yüklendi olan bir DLL dosyası olanak tanır. Varsayılan olarak, kodunuzun DLL kaldırdığında (/ DELAY: Unload kullanarak ve **__FUnloadDelayLoadedDLL2**), içeri aktarma adres tablosunda (IAT) Gecikmeli yüklenen içeri aktarmalar kalır. Bununla birlikte, / DELAY: Unload bağlayıcı komut satırına kullanırsanız, yardımcı işlevini IAT için özgün biçimlerinde sıfırlama DLL açık kaldırma desteği: artık geçersiz işaretçileri üzerine yazılır. Bir alandır IAT [ImgDelayDescr](calling-conventions-parameters-and-return-type.md) içeren özgün IAT bir kopyasını adresini (varsa).

## <a name="example"></a>Örnek

### <a name="code"></a>Kod

```
// link with /link /DELAYLOAD:MyDLL.dll /DELAY:UNLOAD
#include <windows.h>
#include <delayimp.h>
#include "MyDll.h"
#include <stdio.h>

#pragma comment(lib, "delayimp")
#pragma comment(lib, "MyDll")
int main()
{
    BOOL TestReturn;
    // MyDLL.DLL will load at this point
    fnMyDll();

    //MyDLL.dll will unload at this point
    TestReturn = __FUnloadDelayLoadedDLL2("MyDll.dll");

    if (TestReturn)
        printf_s("\nDLL was unloaded");
    else
        printf_s("\nDLL was not unloaded");
}
```

### <a name="comments"></a>Açıklamalar

Bir Gecikmeli yüklenen DLL'i kaldırma üzerinde önemli notlar:

- Uygulamasını bulabilirsiniz **__FUnloadDelayLoadedDLL2** işlevi dosyasındaki \VC7\INCLUDE\DELAYHLP. CPP.

- Name parametresi **__FUnloadDelayLoadedDLL2** işlevi tam olarak eşleşmesi gerekir (çalışması gibi) ne içeri aktarma kitaplığına (yani dize da görüntü içeri aktarma tablosunda) içerir. İçeri aktarma kitaplığı ile içeriğini görüntüleyebilirsiniz [DUMPBIN/DEPENDENTS](dependents.md). Büyük küçük harf duyarlı dize eşleştirme isteniyorsa güncelleştirebilirsiniz **__FUnloadDelayLoadedDLL2** CRT dize işlevleri veya bir Windows API çağrısı birini kullanmak için.

Bkz: [Delay-Loaded DLL'i kaldırma](unloading-a-delay-loaded-dll.md) daha fazla bilgi için.

## <a name="see-also"></a>Ayrıca bkz.

[Gecikmeli Yüklenen DLL'ler için Bağlayıcı Desteği](linker-support-for-delay-loaded-dlls.md)
