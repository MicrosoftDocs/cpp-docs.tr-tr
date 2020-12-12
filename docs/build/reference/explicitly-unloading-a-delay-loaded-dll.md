---
description: "Hakkında daha fazla bilgi edinin: Delay-Loaded DLL 'yi açıkça kaldırma"
title: Gecikmeli Yüklenen DLL'i Açıkça Kaldırma
ms.date: 11/04/2016
helpviewer_keywords:
- /DELAY:UNLOAD linker option
- DELAY:UNLOAD linker option
- __FUnloadDelayLoadedDLL2
- delayed loading of DLLs, unloading
ms.assetid: 1c4c5172-fd06-45d3-9e4f-f12343176b3c
ms.openlocfilehash: 03df08487acc1be05226021d6b7c1593eb0f031b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192388"
---
# <a name="explicitly-unloading-a-delay-loaded-dll"></a>Gecikmeli Yüklenen DLL'i Açıkça Kaldırma

[/Delay](delay-delay-load-import-settings.md): Unload bağlayıcı seçeneği, Gecikmeli yüklenen bir dll 'yi kaldırmanızı sağlar. Varsayılan olarak, kodunuz DLL 'yi kaldırdığında (/Delay: Unload ve **__FUnloadDelayLoadedDLL2** kullanarak), Gecikmeli yüklenen içeri aktarmalar içeri aktarma adresi tablosunda (IAT) kalır. Ancak, bağlayıcı komut satırında/delay: unload kullanırsanız, yardımcı işlev DLL 'nin açıkça kaldırılmasını destekleyecektir ve ıAT 'yi özgün biçimine sıfırlıyor; Şimdi geçersiz işaretçiler üzerine yazılacak. IAT, [ImgDelayDescr](calling-conventions-parameters-and-return-type.md) içinde orijinal IAT 'nin bir kopyasının adresini içeren bir alandır (varsa).

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

### <a name="comments"></a>Yorumlar

Gecikmeli yüklenen DLL 'yi kaldırma hakkında önemli notlar:

- **__FUnloadDelayLoadedDLL2** işlevinin uygulamasını \vc7\include\delayhlpfile dosyasında bulabilirsiniz. CPP.

- **__FUnloadDelayLoadedDLL2** işlevinin name parametresi, içeri aktarma kitaplığı 'nın (Bu dize görüntüdeki içeri aktarma tablosunda da bulunur) tam olarak eşleşmelidir (büyük/küçük harf). İçeri aktarma kitaplığının içeriğini [dumpbin/BAĞıMLıLARı](dependents.md)ile görüntüleyebilirsiniz. Büyük/küçük harfe duyarsız dize eşleşmesi isteniyorsa, CRT dize işlevlerinden birini veya bir Windows API çağrısını kullanmak için **__FUnloadDelayLoadedDLL2** güncelleştirebilirsiniz.

Daha fazla bilgi için bkz. [Delay-Loaded dll 'Yi kaldırma](unloading-a-delay-loaded-dll.md) .

## <a name="see-also"></a>Ayrıca bkz.

[Delay-Loaded dll 'Ler için bağlayıcı desteği](linker-support-for-delay-loaded-dlls.md)
