---
title: __Declspec(dllimport) kullanarak bir uygulamaya aktarma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- __declspec
- dllimport
dev_langs:
- C++
helpviewer_keywords:
- __declspec(dllimport) keyword [C++]
- importing DLLs [C++], __declspec(dllimport)
ms.assetid: edb4da4e-f83a-44cf-a668-9239d49dbe42
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 08a406c8884cdcb9d4b2ead2e61d416ac580fd73
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45704092"
---
# <a name="importing-into-an-application-using-declspecdllimport"></a>__declspec(dllimport) Kullanarak Bir Uygulamaya Aktarma

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

- [DLL'yi Başlat](../build/run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [İçeri ve dışarı aktarma satır içi işlevler](../build/importing-and-exporting-inline-functions.md)

- [Karşılıklı içeri aktarmalar](../build/mutual-imports.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Bir Uygulamaya Aktarma](../build/importing-into-an-application.md)