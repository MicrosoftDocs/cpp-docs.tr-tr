---
title: __declspec(dllexport) Kullanarak DLL'den Dışarı Aktarma
ms.date: 05/06/2019
f1_keywords:
- dllexport
helpviewer_keywords:
- __declspec(dllexport) keyword [C++]
- names [C++], DLL exports by
- export directives [C++]
- exporting DLLs [C++], __declspec(dllexport) keyword
ms.assetid: a35e25e8-7263-4a04-bad4-00b284458679
ms.openlocfilehash: 77dc6dc14efe2a7ccf46c41477ed4fd6d1956856
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224038"
---
# <a name="exporting-from-a-dll-using-__declspecdllexport"></a>__declspec(dllexport) Kullanarak DLL'den Dışarı Aktarma

Anahtar sözcüğünü kullanarak bir DLL 'den verileri, işlevleri, sınıfları veya sınıf üye işlevlerini dışarı aktarabilirsiniz **`__declspec(dllexport)`** . **`__declspec(dllexport)`**. def dosyası kullanmanıza gerek kalmaması için, nesne dosyasına dışarı aktarma yönergesini ekler.

Bu kolaylık, düzenlenmiş C++ işlev adlarını dışa aktarmaya çalışırken en belirgin şekilde görünür. Ad dekorasyonu için standart belirtim olmadığından, bir içe aktarılmış işlevin adı derleyici sürümleri arasında değişebilir. Kullanırsanız **`__declspec(dllexport)`** , dll ve Dependent. exe dosyalarını yeniden derleme yalnızca adlandırma kuralı değişikliklerinin hesabında gereklidir.

Sıra sayısı, NONAME ve PRIVATE gibi birçok dışarı aktarma yönergesi yalnızca bir. def dosyasında yapılabilir ve bu öznitelikleri. def dosyası olmadan belirtmenin bir yolu yoktur. Ancak, **`__declspec(dllexport)`** bir. def dosyası kullanmanın yanı sıra derleme hatalarına neden olmaz.

İşlevleri dışarı aktarmak için anahtar sözcük **`__declspec(dllexport)`** belirtilmişse, çağırma kuralı anahtar sözcüğünün sol tarafında görünür olmalıdır. Örnek:

```
__declspec(dllexport) void __cdecl Function1(void);
```

Bir sınıftaki tüm ortak veri üyelerini ve üye işlevlerini dışarı aktarmak için anahtar sözcüğünün aşağıdaki gibi sınıf adının solunda görünmesi gerekir:

```
class __declspec(dllexport) CExampleExport : public CObject
{ ... class definition ... };
```

> [!NOTE]
> `__declspec(dllexport)`çağırma kuralına sahip bir işleve uygulanamaz `__clrcall` .

DLL 'nizi oluştururken genellikle, dışarı aktardığınız işlev prototiplerini ve/veya sınıflarını içeren bir üst bilgi dosyası oluşturun ve **`__declspec(dllexport)`** üstbilgi dosyasındaki bildirimlere ekleyin. Kodunuzu daha okunabilir hale getirmek için bir makro tanımlayın **`__declspec(dllexport)`** ve dışarı aktardığınız her sembol ile makroyu kullanın:

```
#define DllExport   __declspec( dllexport )
```

**`__declspec(dllexport)`** işlev adlarını DLL 'nin dışarı aktarma tablosunda depolar. Tablonun boyutunu iyileştirmek istiyorsanız, bkz. [BIR DLL 'Den Işlevleri ad yerine sıraya göre dışarı aktarma](exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md).

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [. Def dosyalarını kullanarak DLL 'den dışarı aktarma](exporting-from-a-dll-using-def-files.md)

- [AFX_EXT_CLASS kullanarak dışarı ve içeri aktarma](exporting-and-importing-using-afx-ext-class.md)

- [C Dili Çalıştırılabilirlerinde kullanmak için C++ işlevlerini dışa aktarma](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [C veya C++ Dili Çalıştırılabilirlerinde kullanmak için C işlevlerini dışarı aktarma](exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [Hangi dışarı aktarma yönteminin kullanılacağını belirleme](determining-which-exporting-method-to-use.md)

- [__declspec(dllimport) kullanarak bir uygulamaya aktarma](importing-into-an-application-using-declspec-dllimport.md)

- [DLL 'yi başlatma](run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [__Declspec anahtar sözcüğü](../cpp/declspec.md)

- [Satır içi işlevleri içeri ve dışarı aktarma](importing-and-exporting-inline-functions.md)

- [Karşılıklı içeri aktarmalar](mutual-imports.md)

## <a name="see-also"></a>Ayrıca bkz.

[DLL'den Dışarı Aktarma](exporting-from-a-dll.md)
