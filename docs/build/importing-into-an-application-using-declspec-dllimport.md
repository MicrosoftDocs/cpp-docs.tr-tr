---
title: __declspec(dllimport) kullanarak bir uygulamaya aktarma
ms.date: 11/04/2016
helpviewer_keywords:
- __declspec(dllimport) keyword [C++]
- importing DLLs [C++], __declspec(dllimport)
ms.assetid: edb4da4e-f83a-44cf-a668-9239d49dbe42
ms.openlocfilehash: fd7d42ec5a76b92aa789a3a20f38e6b2c0fd2cb1
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440414"
---
# <a name="import-into-an-application-using-__declspecdllimport"></a>__declspec(dllimport) kullanarak bir uygulamaya aktarma

DLL tarafından tanımlanan ortak sembolleri kullanan bir program, bunları içeri aktarmaya yönelik olarak kabul edilir. Derleme yapmak için dll 'lerinizi kullanan uygulamalar için üst bilgi dosyaları oluştururken, genel simgelerin bildirimlerinde **__declspec (dllimport)** kullanın. **__Declspec (dllimport)** anahtar sözcüğü,. def dosyaları ile veya **__declspec (dllexport)** anahtar sözcüğüyle dışa aktarıp vermeksizin işe yarar.

Kodunuzu daha okunabilir hale getirmek için **__declspec (dllimport)** için bir makro tanımlayın ve ardından içeri aktarılan her simgeyi bildirmek için makroyu kullanın:

```
#define DllImport   __declspec( dllimport )

DllImport int  j;
DllImport void func();
```

İşlev bildirimlerinde **__declspec (dllimport)** kullanmak isteğe bağlıdır, ancak bu anahtar sözcüğü kullanırsanız derleyici daha verimli kod üretir. Ancak, DLL 'nin ortak veri sembolleri ve nesnelerine erişmek için içeri aktarma yürütülebilir dosyası için **__declspec (dllimport)** kullanmanız gerekir. DLL 'nizin kullanıcılarının hala bir içeri aktarma kitaplığıyla bağlanması gerektiğini unutmayın.

Aynı üstbilgi dosyasını hem DLL hem de istemci uygulaması için kullanabilirsiniz. Bunu yapmak için, DLL oluşturmayı veya istemci uygulamasını oluşturmayı belirten özel bir ön işlemci sembolünü kullanın. Örnek:

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

[Bir Uygulamaya Aktarma](importing-into-an-application.md)
