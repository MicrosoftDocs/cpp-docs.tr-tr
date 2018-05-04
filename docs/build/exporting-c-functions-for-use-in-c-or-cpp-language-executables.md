---
title: C veya C++ dili çalıştırılabilir öğelerinde kullanmak için C işlevlerini dışarı aktarma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- functions [C], exporting
- functions [C], C or C++ executables and
- __cplusplus macro
- exporting DLLs [C++], C functions in C++ executables
- exporting functions [C++], C functions in C++ executables
ms.assetid: b51d6e5e-37cf-4c1c-b0bf-fcf188c82f00
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ee1d572bbfaa31ac626bfeb2b6ed7f61604628c8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="exporting-c-functions-for-use-in-c-or-c-language-executables"></a>C ya da C++ Dili Çalıştırılabilir Öğelerinde Kullanmak için C İşlevlerini Dışarı Aktarma  
  
C'de yazılmış C ya da C++ dili modülünden erişmek istediğiniz, kullanmanız gereken bir DLL işlevleri varsa **__cplusplus** dili belirlemek için önişlemci makrosu derleniyor ve bunlar bildirme C++ dili modülünden kullanılıyorlarsa C bağlantısı ile çalışır. Bu teknik kullanıyorsanız ve için DLL üstbilgi dosyaları sağlamak, bu işlevler değişiklik olmadan C ve C++ kullanıcılar tarafından kullanılabilir.  
  
Aşağıdaki kod C ve C++ istemci uygulamaları tarafından kullanılabilecek bir üstbilgi dosyası gösterir:  
  
```h  
// MyCFuncs.h  
#ifdef __cplusplus  
extern "C" {  // only need to export C interface if  
              // used by C++ source code  
#endif  
  
__declspec( dllimport ) void MyCFunc();  
__declspec( dllimport ) void AnotherCFunc();  
  
#ifdef __cplusplus  
}  
#endif  
```  
  
C++ yürütülebilir C işlevlerini bağlamanız gerekir ve işlev bildirim başlık dosyaları yukarıdaki tekniği C++ kaynak dosyasına kullanmamış, C işlev adlarını dekorasyon derleyici önlemek için aşağıdakileri yapın:  
  
```cpp  
extern "C" {  
#include "MyCHeader.h"  
}  
```  
  
## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?  
  
-   [.Def dosyaları kullanarak DLL'den dışarı aktarma](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [__Declspec(dllexport) kullanarak DLL'den dışarı aktarma](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [AFX_EXT_CLASS kullanarak içeri ve dışarı aktarmak](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [Hangi dışarı aktarma yöntemini kullanacağınızı belirleme](../build/determining-which-exporting-method-to-use.md)  
  
-   [__Declspec(dllimport) kullanarak bir uygulama içeri aktarmak için](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [DLL başlatma](../build/run-time-library-behavior.md#initializing-a-dll)  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?  
  
-   [Düzenlenmiş adlar](../build/reference/decorated-names.md)  
  
-   [Bağlantıyı Belirtmek için extern Kullanma](../cpp/using-extern-to-specify-linkage.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DLL'den Dışarı Aktarma](../build/exporting-from-a-dll.md)