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
ms.openlocfilehash: b7ba2ed30615efb3b05e71cecf0ea69898feb8ba
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62273579"
---
# <a name="exporting-c-functions-for-use-in-c-or-c-language-executables"></a>C ya da C++ Dili Çalıştırılabilir Öğelerinde Kullanmak için C İşlevlerini Dışarı Aktarma

Bir DLL'de işlevleri varsa bir C dili erişmek istediğiniz C dilinde yazılır veya C++ Dil modülü kullanmalıdır **__cplusplus** hangi dil belirlemek için önişlemci makrosu derleniyor ve bunlar bildirme gelen kullanılıyorlarsa C bağlaması işlevler bir C++ Dil modülü. Bu tekniği kullanın ve başlık dosyaları için DLL dosyanızı sağlamak, bu işlevler, değişikliğe sahip C ve C++ kullanıcılar tarafından kullanılabilir.

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

- [.Def dosyalarını kullanarak DLL'den dışarı aktarma](exporting-from-a-dll-using-def-files.md)

- [__Declspec(dllexport) kullanarak DLL'den dışarı aktarma](exporting-from-a-dll-using-declspec-dllexport.md)

- [AFX_EXT_CLASS kullanarak içeri ve dışarı aktarma](exporting-and-importing-using-afx-ext-class.md)

- [Hangi dışa aktarma yönteminin kullanılacağını belirleme](determining-which-exporting-method-to-use.md)

- [__declspec(dllimport) kullanarak bir uygulamaya aktarma](importing-into-an-application-using-declspec-dllimport.md)

- [DLL'yi Başlat](run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [Düzenlenmiş adlar](reference/decorated-names.md)

- [Bağlantıyı Belirtmek için extern Kullanma](../cpp/using-extern-to-specify-linkage.md)

## <a name="see-also"></a>Ayrıca bkz.

[DLL'den Dışarı Aktarma](exporting-from-a-dll.md)
