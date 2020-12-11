---
description: 'Hakkında daha fazla bilgi edinin: __declspec (dllimport) kullanarak bir uygulamaya aktarma'
title: __declspec(dllimport) kullanarak bir uygulamaya aktarma
ms.date: 11/04/2016
helpviewer_keywords:
- __declspec(dllimport) keyword [C++]
- importing DLLs [C++], __declspec(dllimport)
ms.assetid: edb4da4e-f83a-44cf-a668-9239d49dbe42
ms.openlocfilehash: 946ec6b4b06b22dd7dd68be2478a0b0571aa641c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97156183"
---
# <a name="import-into-an-application-using-__declspecdllimport"></a>__declspec(dllimport) kullanarak bir uygulamaya aktarma

DLL tarafından tanımlanan ortak sembolleri kullanan bir program, bunları içeri aktarmaya yönelik olarak kabul edilir. Derleme yapmak için dll 'lerinizi kullanan uygulamalar için üst bilgi dosyaları oluştururken, **`__declspec(dllimport)`** genel simgelerin bildirimlerinde kullanın. Anahtar sözcüğü, **`__declspec(dllimport)`** . def dosyaları ile veya anahtar sözcüğüyle dışa aktarıp vermeksizin işe yarar **`__declspec(dllexport)`** .

Kodunuzu daha okunabilir hale getirmek için bir makro tanımlayın **`__declspec(dllimport)`** ve ardından içeri aktarılan her sembolü bildirmek için makroyu kullanın:

```
#define DllImport   __declspec( dllimport )

DllImport int  j;
DllImport void func();
```

**`__declspec(dllimport)`** İşlevi, işlev bildirimlerinde isteğe bağlıdır, ancak bu anahtar sözcüğü kullanırsanız derleyici daha verimli kod üretir. Ancak, **`__declspec(dllimport)`** DLL 'nin ortak veri sembollerine ve nesnelerine erişmek için içeri aktarma yürütülebilir dosyası için kullanmanız gerekir. DLL 'nizin kullanıcılarının hala bir içeri aktarma kitaplığıyla bağlanması gerektiğini unutmayın.

Aynı üstbilgi dosyasını hem DLL hem de istemci uygulaması için kullanabilirsiniz. Bunu yapmak için, DLL oluşturmayı veya istemci uygulamasını oluşturmayı belirten özel bir ön işlemci sembolünü kullanın. Örneğin:

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

- [DLL 'yi başlatma](run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [Satır içi işlevleri içeri ve dışarı aktarma](importing-and-exporting-inline-functions.md)

- [Karşılıklı içeri aktarmalar](mutual-imports.md)

## <a name="see-also"></a>Ayrıca bkz.

[Bir uygulamaya aktarma](importing-into-an-application.md)
