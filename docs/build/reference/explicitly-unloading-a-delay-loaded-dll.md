---
description: "Daha fazla bilgi edinin: Gecikmeli yüklenen DLL 'i açıkça kaldırma"
title: Gecikmeli yüklenen DLL 'i açıkça kaldırma
ms.date: 01/19/2021
helpviewer_keywords:
- /DELAY:UNLOAD linker option
- DELAY:UNLOAD linker option
- __FUnloadDelayLoadedDLL2
- delayed loading of DLLs, unloading
ms.openlocfilehash: b4e137f293c6497e234a7bb93bd16b5bb6887741
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/21/2021
ms.locfileid: "98666894"
---
# <a name="explicitly-unload-a-delay-loaded-dll"></a>Gecikmeli yüklenen DLL 'i açıkça kaldırma

[`/delay:unload`](delay-delay-load-import-settings.md)Bağlayıcı seçeneği, kodunuzun, Gecikmeli yüklenen BIR DLL 'yi açıkça kaldırmasına izin verir. Varsayılan olarak, kodunuz DLL 'yi kaldırdığında, Gecikmeli yüklenen içeri aktarmalar içeri aktarma adresi tablosunda (ıAT) kalır. Ancak, **`/delay:unload`** bağlayıcı komut satırında kullanırsanız, yardımcı işlevi, dll 'nin açıkça kaldırılmasını bir çağrı ile destekler `__FUnloadDelayLoadedDLL2` ve IAT 'yi özgün biçimine sıfırlar. Şimdi geçersiz işaretçiler üzerine yazılır. IAT, bir, varsa [`ImgDelayDescr`](calling-conventions-parameters-and-return-type.md) orijinal IAT öğesinin bir kopyasının adresini içeren bir alandır.

## <a name="example"></a>Örnek

### <a name="code"></a>Kod

```C
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

### <a name="comments"></a>Yorumlar

Gecikmeli yüklenen DLL 'yi kaldırma hakkında önemli notlar:

- `__FUnloadDelayLoadedDLL2`İşlevin uygulamasını *`delayhlp.cpp`* , VC dizininde, dosyasında bulabilirsiniz *`include`* .

- *`name`* İşlevin parametresi, `__FUnloadDelayLoadedDLL2` içeri aktarma kitaplığı 'nın içerdiği, tam olarak eşleşmelidir (örneğin, büyük/küçük harf). (Bu dize görüntüdeki içeri aktarma tablosunda da bulunur.) Kullanarak içeri aktarma kitaplığının içeriğini görüntüleyebilirsiniz [`DUMPBIN /DEPENDENTS`](dependents.md) . Büyük/küçük harfe duyarsız bir dize eşleşmesi tercih ediyorsanız, `__FUnloadDelayLoadedDLL2` büyük/küçük harfe DUYARSıZ CRT dize işlevlerinden birini veya bir WINDOWS API çağrısını kullanmak için ' yi güncelleştirebilirsiniz.

Daha fazla bilgi için bkz. [Gecikmeli yüklenen dll 'ı kaldırma](unloading-a-delay-loaded-dll.md).

## <a name="see-also"></a>Ayrıca bkz.

[Gecikmeli yüklenen DLL'ler için bağlayıcı desteği](linker-support-for-delay-loaded-dlls.md)
