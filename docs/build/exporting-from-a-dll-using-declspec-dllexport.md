---
title: __declspec(dllexport) Kullanarak DLL'den Dışarı Aktarma
ms.date: 11/04/2016
f1_keywords:
- dllexport
- __declspec
helpviewer_keywords:
- __declspec(dllexport) keyword [C++]
- names [C++], DLL exports by
- export directives [C++]
- exporting DLLs [C++], __declspec(dllexport) keyword
ms.assetid: a35e25e8-7263-4a04-bad4-00b284458679
ms.openlocfilehash: effefa2c370634c450b03ed18187769e12e40adf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50500392"
---
# <a name="exporting-from-a-dll-using-declspecdllexport"></a>__declspec(dllexport) Kullanarak DLL'den Dışarı Aktarma

Microsoft gelen **__export** derleyicinin, dışa aktarma adlarını otomatik olarak oluşturmak ve bunları .lib dosyasına yerleştirmek Visual C++ 16 bitlik derleyici sürümü. Bu .lib dosyası daha sonra yalnızca statik bir .lib gibi bir DLL ile bağlamak için kullanılabilir.

Yeni derleyici sürümlerinde, veri, İşlevler, sınıflar veya sınıf üyesi işlevleri kullanarak bir DLL'nin dışa aktarabilirsiniz **__declspec(dllexport)** anahtar sözcüğü. **__declspec(dllexport)** bir .def dosyası kullanmanıza gerek yoktur nesne dosyasına dışarı aktarma yönergesi ekler.

Bu kolaylık, tasarlanan C++ işlev adlarını dışarı aktarılmaya çalışılırken zaman belirgin. Ad düzenlemesi için standart bir belirtim olmadığından dışa aktarılan bir işlevin adı derleyici sürümlerine göre değişebilir. Kullanırsanız **__declspec(dllexport)**, DLL ve .exe dosyalarını yeniden derlenmesi için adlandırma kuralı değişikliklerinin yalnızca hesabına gerekli.

Sıra sayıları, NONAME ve PRIVATE gibi yalnızca .def dosyasında yapılabilir ve bu öznitelikleri .def dosyası olmadan belirtmek için bir yolu yoktur gibi birçok yönergeleri verin. Ancak, **__declspec(dllexport)** .def kullanmanın yanı sıra dosya derleme hatalarına neden olmaz.

İşlevleri dışarı aktarmak için **__declspec(dllexport)** anahtar sözcüğü bir anahtar sözcük belirtilmişse çağırma kuralı anahtar sözcüğünün solunda görünmesi gerekir. Örneğin:

```
__declspec(dllexport) void __cdecl Function1(void);
```

Tüm genel veri üyeleri ve üye işlevler sınıfında dışarı aktarmak için anahtar sözcüğü sola sınıf adının şu şekilde görünmelidir:

```
class __declspec(dllexport) CExampleExport : public CObject
{ ... class definition ... };
```

> [!NOTE]
>  `__declspec(dllexport)` bulunan bir fonksiyona uygulanamaz `__clrcall` çağırma kuralı.

DLL'nizi oluştururken genellikle işlev prototiplerini ve/veya veriyorsunuz ve ekleme sınıfları içeren üstbilgi dosyası oluşturduğunuz **__declspec(dllexport)** başlık dosyasındaki bildirimlere. Kodunuzu daha okunabilir hale getirmek için makro tanımlayın **__declspec(dllexport)** ve dışarı aktardığınız her sembol ile makroyu kullanın:

```
#define DllExport   __declspec( dllexport )
```

**__declspec(dllexport)** işlev adlarını DLL'nin dışa aktarma tablosunda depolar. Tablonun boyutunu en iyi duruma getirmek istiyorsanız, bkz. [yerine sıra adına göre bir DLL işlevlerini dışa aktarma](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md).

> [!NOTE]
>  Win32 DLL kaynak kodunu Win16 taşırken her örneğini değiştirin **__export** ile **__declspec(dllexport)**.

Bir başvuru, Win32 Winbase.h üstbilgi dosyasında arayın. Örnekler içeren **__declspec(dllimport)** kullanım.

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [.Def dosyalarını kullanarak DLL'den dışarı aktarma](../build/exporting-from-a-dll-using-def-files.md)

- [AFX_EXT_CLASS kullanarak içeri ve dışarı aktarma](../build/exporting-and-importing-using-afx-ext-class.md)

- [C dili çalıştırılabilirlerinde kullanmak için C++ işlevlerini dışa aktarma](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)

- [C veya C++ dili çalıştırılabilirlerinde kullanmak için C işlevlerini dışa aktarma](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [Hangi dışa aktarma yönteminin kullanılacağını belirleme](../build/determining-which-exporting-method-to-use.md)

- [__Declspec(dllimport) kullanarak bir uygulamayı içeri aktarın](../build/importing-into-an-application-using-declspec-dllimport.md)

- [DLL'yi Başlat](../build/run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [__Declspec anahtar sözcüğü](../cpp/declspec.md)

- [İçeri ve dışarı aktarma satır içi işlevler](../build/importing-and-exporting-inline-functions.md)

- [Karşılıklı içeri aktarmalar](../build/mutual-imports.md)

## <a name="see-also"></a>Ayrıca Bkz.

[DLL'den Dışarı Aktarma](../build/exporting-from-a-dll.md)