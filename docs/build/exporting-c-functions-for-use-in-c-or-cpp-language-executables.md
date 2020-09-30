---
title: C ya da C++ Dili Çalıştırılabilir Öğelerinde Kullanmak için C İşlevlerini Dışarı Aktarma
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C], exporting
- functions [C], C or C++ executables and
- __cplusplus macro
- exporting DLLs [C++], C functions in C++ executables
- exporting functions [C++], C functions in C++ executables
ms.assetid: b51d6e5e-37cf-4c1c-b0bf-fcf188c82f00
ms.openlocfilehash: 4dcf46e6bdde66a303afc2c4ec94fc8aefdd5e5d
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91506638"
---
# <a name="exporting-c-functions-for-use-in-c-or-c-language-executables"></a>C ya da C++ Dili Çalıştırılabilir Öğelerinde Kullanmak için C İşlevlerini Dışarı Aktarma

C dilinde veya C++ dil modülünden erişmek istediğiniz DLL 'de yazılmış işlevleriniz varsa, hangi dilin derlenmekte olduğunu belirleyebilmek için **__cplusplus** önişlemci makrosunu kullanmanız ve ardından C++ dil modülünden kullanılıyorsa bu işlevleri c bağlantısı ile bildirmeniz gerekir. Bu tekniği kullanır ve DLL 'niz için üstbilgi dosyaları sağlarsanız, bu işlevler C ve C++ kullanıcıları tarafından değişiklik olmadan kullanılabilir.

Aşağıdaki kod, C ve C++ istemci uygulamaları tarafından kullanılabilen bir üst bilgi dosyasını gösterir:

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

C işlevlerini C++ yürütülebilir dosyanıza bağlamanız gerekiyorsa ve işlev bildirimi üstbilgi dosyaları yukarıdaki tekniği kullanmadıysanız, C++ kaynak dosyasında derleyicinin C işlev adlarını süslemesini engellemek için aşağıdakileri yapın:

```cpp
extern "C" {
#include "MyCHeader.h"
}
```

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [. Def dosyalarını kullanarak DLL 'den dışarı aktarma](exporting-from-a-dll-using-def-files.md)

- [__Declspec (dllexport) kullanarak DLL 'den dışarı aktarma](exporting-from-a-dll-using-declspec-dllexport.md)

- [AFX_EXT_CLASS kullanarak dışarı ve içeri aktarma](exporting-and-importing-using-afx-ext-class.md)

- [Hangi dışarı aktarma yönteminin kullanılacağını belirleme](determining-which-exporting-method-to-use.md)

- [__declspec(dllimport) kullanarak bir uygulamaya aktarma](importing-into-an-application-using-declspec-dllimport.md)

- [DLL 'yi başlatma](run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [Düzenlenmiş adlar](reference/decorated-names.md)

- [Bağlantıyı Belirtmek için extern Kullanma](../cpp/extern-cpp.md)

## <a name="see-also"></a>Ayrıca bkz.

[DLL'den Dışarı Aktarma](exporting-from-a-dll.md)
