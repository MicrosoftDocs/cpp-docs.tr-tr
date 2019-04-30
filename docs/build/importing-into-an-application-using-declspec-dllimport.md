---
title: __Declspec(dllimport) kullanarak bir uygulamayı içeri aktarın
ms.date: 11/04/2016
f1_keywords:
- __declspec
- dllimport
helpviewer_keywords:
- __declspec(dllimport) keyword [C++]
- importing DLLs [C++], __declspec(dllimport)
ms.assetid: edb4da4e-f83a-44cf-a668-9239d49dbe42
ms.openlocfilehash: 30e0f6517f2d749962c5cf49dddb1662c9ccf129
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64341652"
---
# <a name="import-into-an-application-using-declspecdllimport"></a>__Declspec(dllimport) kullanarak bir uygulamayı içeri aktarın

Bir DLL tarafından tanımlanan ortak semboller kullanan bir program içeri aktarılacak. Oluşturduğunuzda, üst bilgi dosyaları, oluşturmak için DLL kullanan uygulamaları kullanmak için **__declspec(dllimport)** bildirimlerinde genel simgeleri. Anahtar sözcüğü **__declspec(dllimport)** .def dosyaları veya ile dışarı aktarma olmadığını çalışır **__declspec(dllexport)** anahtar sözcüğü.

Kodunuzu daha okunabilir hale getirmek için makro tanımlayın **__declspec(dllimport)** ve makro içeri aktarılan her simge bildirmek için kullanın:

```
#define DllImport   __declspec( dllimport )

DllImport int  j;
DllImport void func();
```

Kullanarak **__declspec(dllimport)** İşlev bildirimlerinde isteğe bağlıdır, ancak bu anahtar sözcük kullanırsanız derleyici daha verimli kod üretir. Ancak, kullanmalısınız **__declspec(dllimport)** DLL'nin genel veri simgeleri ve nesnelere erişmek içeri aktarma yürütülebilir dosyası için. DLL'niz kullanıcıları hala içeri aktarma kitaplığı ile bağlantı gerektiğini unutmayın.

DLL ve istemci uygulaması için aynı üstbilgi dosyasını kullanabilirsiniz. Bunu yapmak için DLL oluşturma veya istemci uygulaması oluşturma olup olmadığını gösteren özel bir önişlemci sembolü kullanın. Örneğin:

```
#ifdef _EXPORTING
   #define CLASS_DECLSPEC    __declspec(dllexport)
#else
   #define CLASS_DECLSPEC    __declspec(dllimport)
#endif

class CLASS_DECLSPEC CExampleA : public CObject
{ ... class definition ... };
```

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [DLL'yi Başlat](run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [Satır içi işlevleri içeri ve dışarı aktarma](importing-and-exporting-inline-functions.md)

- [Karşılıklı içeri aktarmalar](mutual-imports.md)

## <a name="see-also"></a>Ayrıca bkz.

[Bir Uygulamaya Aktarma](importing-into-an-application.md)
