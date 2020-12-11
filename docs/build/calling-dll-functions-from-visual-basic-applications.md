---
description: 'Hakkında daha fazla bilgi edinin: Visual Basic uygulamalardan DLL Işlevleri çağırma'
title: Visual Basic Uygulamasından DLL İşlevi Çağırma
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C++], calling DLL functions from Visual Basic
- DLL functions [C++]
- function calls [C++], DLL functions
- DLLs [C++], calling
- calling DLL functions from VB applications [C++]
- __stdcall keyword [C++]
- DLL functions [C++], calling
ms.assetid: 282f7fbf-a0f2-4b9f-b277-1982710be56c
ms.openlocfilehash: 3c9a66a4d6dc9a8e3cc6e8b8a80584d430f12562
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97156989"
---
# <a name="calling-dll-functions-from-visual-basic-applications"></a>Visual Basic Uygulamasından DLL İşlevi Çağırma

C/C++ DLL içindeki işlevleri çağırmak için Visual Basic uygulamalar (veya Pascal veya Fortran gibi diğer dillerdeki uygulamalar) için, işlevler, derleyici tarafından gerçekleştirilen herhangi bir ad düzenlemesi olmadan doğru çağırma kuralı kullanılarak aktarılmalıdır

**`__stdcall`** işlev için doğru çağrı kuralını oluşturur (çağrılan işlev yığını temizler ve parametreler sağdan sola geçirilir), ancak işlev adını farklı şekilde süslerler. Bu nedenle, **`__declspec(dllexport)`** DLL içindeki bir dışarıya aktarılmış işlevde kullanıldığında, düzenlenmiş ad verilir.

**`__stdcall`** Ad dekorasyonu, simge adını bir alt çizgi () ile, sonra da **\_** **\@** bağımsız değişken listesindeki bayt sayısı (gerekli yığın alanı) ile birlikte bir at işareti () karakteriyle ekler. Sonuç olarak, şu şekilde bildirildiğinde işlevi:

```C
int __stdcall func (int a, double b)
```

çıktıda olduğu gibi düzenlenmiş `_func@12` .

C çağırma kuralı ( **`__cdecl`** ), adı olarak tasarlaştırır `_func` .

Düzenlenmiş adı almak için [/Map](reference/map-generate-mapfile.md)kullanın. Öğesinin kullanımı **`__declspec(dllexport)`** şunları yapar:

- İşlev C çağırma kuralına ( **`__cdecl`** ) aktarılıyorsa, ad verildiğinde önde gelen alt çizgi () şeritleri olur **\_** .

- Dışarı aktarılan işlev C çağırma kuralını kullanmıyorsa (örneğin, **`__stdcall`** ), düzenlenmiş adı dışarı aktarır.

Yığın Temizleme işleminin gerçekleştiği yeri geçersiz kılmanın bir yolu olmadığından, kullanmanız gerekir **`__stdcall`** . Adları ile süslemek için **`__stdcall`** . def dosyasının dışarı aktarmalar bölümünde diğer adları kullanarak bunları belirtmeniz gerekir. Bu, aşağıdaki işlev bildirimi için aşağıdaki şekilde gösterilmiştir:

```C
int  __stdcall MyFunc (int a, double b);
void __stdcall InitCode (void);
```

İçinde. DEF dosyası:

```
EXPORTS
   MYFUNC=_MyFunc@12
   INITCODE=_InitCode@0
```

Visual Basic yazılan programlar tarafından çağrılacak DLL 'Ler için, bu konuda gösterilen diğer ad tekniği. def dosyasında gereklidir. Diğer ad Visual Basic programında yapıldıysa,. def dosyasında diğer ad kullanımı gerekli değildir. [Declare](/dotnet/visual-basic/language-reference/statements/declare-statement) bildirimine bir Alias yan tümcesi eklenerek, Visual Basic programında yapılabilir.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [DLL'den Dışarı Aktarma](exporting-from-a-dll.md)

- [Kullanarak DLL 'den dışarı aktarma. DEF dosyaları](exporting-from-a-dll-using-def-files.md)

- [__declspec(dllexport) kullanarak DLL'den dışarı aktarma](exporting-from-a-dll-using-declspec-dllexport.md)

- [C dili yürütülebilir öğelerinde kullanmak için C++ işlevlerini dışarı aktarma](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [Hangi dışarı aktarma yönteminin kullanılacağını belirleme](determining-which-exporting-method-to-use.md)

- [Düzenlenmiş adlar](reference/decorated-names.md)

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio 'da C/C++ dll 'Leri oluşturma](dlls-in-visual-cpp.md)
