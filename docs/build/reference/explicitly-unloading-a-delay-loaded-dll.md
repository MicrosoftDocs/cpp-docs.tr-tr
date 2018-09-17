---
title: Gecikmeli yüklenen DLL'i açıkça kaldırma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- /DELAY:UNLOAD linker option
- DELAY:UNLOAD linker option
- __FUnloadDelayLoadedDLL2
- delayed loading of DLLs, unloading
ms.assetid: 1c4c5172-fd06-45d3-9e4f-f12343176b3c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ad52e8efde017ce7be6132594552e13584b38dc
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45705334"
---
# <a name="explicitly-unloading-a-delay-loaded-dll"></a>Gecikmeli Yüklenen DLL'i Açıkça Kaldırma

[/Delay](../../build/reference/delay-delay-load-import-settings.md): unload bağlayıcı seçeneği Gecikmeli yüklendi olan bir DLL dosyası olanak tanır. Varsayılan olarak, kodunuzun DLL kaldırdığında (/ DELAY: Unload kullanarak ve **__FUnloadDelayLoadedDLL2**), içeri aktarma adres tablosunda (IAT) Gecikmeli yüklenen içeri aktarmalar kalır. Bununla birlikte, / DELAY: Unload bağlayıcı komut satırına kullanırsanız, yardımcı işlevini IAT için özgün biçimlerinde sıfırlama DLL açık kaldırma desteği: artık geçersiz işaretçileri üzerine yazılır. Bir alandır IAT [ImgDelayDescr](../../build/reference/calling-conventions-parameters-and-return-type.md) içeren özgün IAT bir kopyasını adresini (varsa).

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

- Name parametresi **__FUnloadDelayLoadedDLL2** işlevi tam olarak eşleşmesi gerekir (çalışması gibi) ne içeri aktarma kitaplığına (yani dize da görüntü içeri aktarma tablosunda) içerir. İçeri aktarma kitaplığı ile içeriğini görüntüleyebilirsiniz [DUMPBIN/DEPENDENTS](../../build/reference/dependents.md). Büyük küçük harf duyarlı dize eşleştirme isteniyorsa güncelleştirebilirsiniz **__FUnloadDelayLoadedDLL2** CRT dize işlevleri veya bir Windows API çağrısı birini kullanmak için.

Bkz: [Delay-Loaded DLL'i kaldırma](../../build/reference/unloading-a-delay-loaded-dll.md) daha fazla bilgi için.

## <a name="see-also"></a>Ayrıca Bkz.

[Gecikmeli Yüklenen DLL'ler için Bağlayıcı Desteği](../../build/reference/linker-support-for-delay-loaded-dlls.md)