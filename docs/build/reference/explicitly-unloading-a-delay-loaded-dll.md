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
ms.openlocfilehash: 171acf9689c01649b86c2383d17136c926e25c57
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="explicitly-unloading-a-delay-loaded-dll"></a>Gecikmeli Yüklenen DLL'i Açıkça Kaldırma
[/Delay](../../build/reference/delay-delay-load-import-settings.md): unload bağlayıcı seçeneği gecikme yüklü olduğu bir DLL dosyası olanak tanır. Varsayılan olarak, kodunuzu DLL bellekten kaldırıldığında, (/ DELAY: Unload kullanarak ve **__FUnloadDelayLoadedDLL2**), alma adresi tablosunda (IAT) Gecikmeli yüklenen içeri aktarmalar kalır. Ancak, / DELAY: Unload bağlayıcı komut satırında kullanırsanız, yardımcı işlevini IAT özgün formuna sıfırlama DLL açık kaldırılması destekler; Şimdi geçersiz işaretçileri üzerine yazılır. Bir alandır IAT [ImgDelayDescr](../../build/reference/calling-conventions-parameters-and-return-type.md) içeren bir kopyasını özgün IAT adresini (varsa).  
  
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
 Gecikmeli yüklenen DLL'i kaldırma üzerinde önemli notlar:  
  
-   Uygulaması bulabilirsiniz **__FUnloadDelayLoadedDLL2** dosyasında işlevi \VC7\INCLUDE\DELAYHLP. CPP.  
  
-   Name parametresi **__FUnloadDelayLoadedDLL2** işlevi tam olarak eşleşmelidir (harf dahil olmak üzere) ne içeri aktarma kitaplığı (yani dize da görüntü alma tablosunda) içerir. İle içeri aktarma kitaplığını içindekileri görüntüleyebilirsiniz [/DEPENDENTS DUMPBIN](../../build/reference/dependents.md). Büyük küçük harf duyarlı dize eşleştirme isterseniz güncelleştirebilirsiniz **__FUnloadDelayLoadedDLL2** CRT dize işlevleri veya bir Windows API çağrısı birini kullanmak için.  
  
 Bkz: [Delay-Loaded DLL'i kaldırma](../../build/reference/unloading-a-delay-loaded-dll.md) daha fazla bilgi için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Gecikmeli Yüklenen DLL'ler için Bağlayıcı Desteği](../../build/reference/linker-support-for-delay-loaded-dlls.md)