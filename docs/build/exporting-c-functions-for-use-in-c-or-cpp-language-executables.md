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
ms.openlocfilehash: 0b7347ee29e973e1043a153f8284baa47b674a4d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50631824"
---
# <a name="exporting-c-functions-for-use-in-c-or-c-language-executables"></a>C ya da C++ Dili Çalıştırılabilir Öğelerinde Kullanmak için C İşlevlerini Dışarı Aktarma

C için yazılmış C ya da C++ dili modülünden erişmek istiyorsanız, kullanmanız gereken bir DLL'de işlevleri varsa **__cplusplus** hangi dil belirlemek için önişlemci makrosu derleniyor ve bunlar bildirme C++ dil modülünden kullanılıyorlarsa C bağlaması olan işlevler. Bu tekniği kullanın ve başlık dosyaları için DLL dosyanızı sağlamak, bu işlevler, değişikliğe sahip C ve C++ kullanıcılar tarafından kullanılabilir.

Aşağıdaki kod, C ve C++ istemci uygulamaları tarafından kullanılabilecek bir üstbilgi dosyası gösterir:

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

C işlevlerinin C++ yürütülebilir bağlamanız gerekir ve C++ kaynak dosyada işlev bildirimi üst bilgi dosyaları yukarıdaki tekniği kullanmadığınız, derleyicinin C işlev adlarını dekorasyon gelen önlemek için aşağıdakileri yapın:

```cpp
extern "C" {
#include "MyCHeader.h"
}
```

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [.Def dosyalarını kullanarak DLL'den dışarı aktarma](../build/exporting-from-a-dll-using-def-files.md)

- [__Declspec(dllexport) kullanarak DLL'den dışarı aktarma](../build/exporting-from-a-dll-using-declspec-dllexport.md)

- [AFX_EXT_CLASS kullanarak içeri ve dışarı aktarma](../build/exporting-and-importing-using-afx-ext-class.md)

- [Hangi dışa aktarma yönteminin kullanılacağını belirleme](../build/determining-which-exporting-method-to-use.md)

- [__Declspec(dllimport) kullanarak bir uygulamayı içeri aktarın](../build/importing-into-an-application-using-declspec-dllimport.md)

- [DLL'yi Başlat](../build/run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [Düzenlenmiş adlar](../build/reference/decorated-names.md)

- [Bağlantıyı Belirtmek için extern Kullanma](../cpp/using-extern-to-specify-linkage.md)

## <a name="see-also"></a>Ayrıca Bkz.

[DLL'den Dışarı Aktarma](../build/exporting-from-a-dll.md)