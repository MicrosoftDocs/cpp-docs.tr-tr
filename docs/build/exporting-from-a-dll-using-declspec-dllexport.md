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
ms.openlocfilehash: 075962758773660085ae0b98b668c264524cc6aa
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328590"
---
# <a name="exporting-from-a-dll-using-__declspecdllexport"></a>__declspec(dllexport) Kullanarak DLL'den Dışarı Aktarma

**__declspec(dllexport)** anahtar sözcük kullanarak verileri, işlevleri, sınıfları veya sınıf üye işlevlerini Bir DLL'den dışa aktarabilirsiniz. **__declspec(dllexport)** bir .def dosyası kullanmanız gerekmez böylece nesne dosyasına dışa aktarma yönergesi ekler.

Bu kolaylık en çok dekore edilmiş C++ işlev adlarını dışa aktarmaya çalışırken belirgindir. Ad süslemesi için standart bir belirtim olmadığından, dışa aktarılan işlevin adı derleyici sürümleri arasında değişebilir. **__declspec(dllexport)** kullanıyorsanız, DLL ve bağımlı .exe dosyalarını yeniden derlemek yalnızca adlandırma kuralı değişikliklerini hesaba katmak için gereklidir.

Ordinals, NONAME ve PRIVATE gibi birçok dışa aktarma yönergeleri yalnızca bir .def dosyasında yapılabilir ve bu öznitelikleri bir .def dosyası olmadan belirtmenin bir yolu yoktur. Ancak, .def dosyası kullanmanın yanı sıra **__declspec(dllexport)** kullanmak yapı hatalarına neden olmaz.

Işlevleri dışa aktarmak için, bir anahtar kelime belirtilmişse, **__declspec(dllexport)** anahtar kelimesinin çağrı kuralı anahtar sözcüğünün solunda görünmesi gerekir. Örneğin:

```
__declspec(dllexport) void __cdecl Function1(void);
```

Bir sınıftaki tüm ortak veri üyelerini ve üye işlevleri dışa aktarmak için anahtar kelimenin sınıf adının solunda aşağıdaki gibi görünmesi gerekir:

```
class __declspec(dllexport) CExampleExport : public CObject
{ ... class definition ... };
```

> [!NOTE]
> `__declspec(dllexport)`çağrı kuralı olan `__clrcall` bir işleve uygulanamaz.

DLL'nizi oluştururken, genellikle dışa aktardığınız işlev prototiplerini ve/veya sınıfları içeren bir üstbilgi dosyası oluşturur ve üstbilgi dosyasındaki bildirimlere **__declspec (dllexport)** eklersiniz. Kodunuzu daha okunabilir hale getirmek için __declspec için bir makro **tanımlayın (dllexport)** ve dışa aktardığınız her sembolle makroyu kullanın:

```
#define DllExport   __declspec( dllexport )
```

**__declspec(dllexport)** adları DLL'nin dışa aktarma tablosunda depolar. Tablonun boyutunu optimize etmek istiyorsanız, Ad [Yerine Ordinal Tarafından Bir DLL'den İşlev Ler Dışa Aktarma'ya](exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md)bakın.

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [.def dosyalarını kullanarak Bir DLL'den dışa aktarma](exporting-from-a-dll-using-def-files.md)

- [AFX_EXT_CLASS kullanarak ihracat ve ithalat](exporting-and-importing-using-afx-ext-class.md)

- [C dili çalıştırılabilir cihazlarda kullanılmak üzere C++ işlevlerini dışa aktarma](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [C veya C++dil deki yürütülebilir cihazlarda kullanılmak üzere C işlevlerini dışa aktarma](exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [Hangi dışa aktarma yönteminin kullanılacağını belirleme](determining-which-exporting-method-to-use.md)

- [__declspec(dllimport) kullanarak bir uygulamaya aktarma](importing-into-an-application-using-declspec-dllimport.md)

- [Bir DLL'yi başlatma](run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla şey bilmek istiyorsun?

- [__declspec anahtar kelime](../cpp/declspec.md)

- [Satır İçi işlevleri alma ve dışa aktarma](importing-and-exporting-inline-functions.md)

- [Karşılıklı ithalat](mutual-imports.md)

## <a name="see-also"></a>Ayrıca bkz.

[DLL'den Dışarı Aktarma](exporting-from-a-dll.md)
