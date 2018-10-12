---
title: Visual Basic uygulamalarından DLL işlevleri çağırma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- functions [C++], calling DLL functions from Visual Basic
- DLL functions [C++]
- function calls [C++], DLL functions
- DLLs [C++], calling
- calling DLL functions from VB applications [C++]
- __stdcall keyword [C++]
- DLL functions [C++], calling
ms.assetid: 282f7fbf-a0f2-4b9f-b277-1982710be56c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 47504b7a471dc38f30e4ceb59b5feeffcc53db6d
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49161846"
---
# <a name="calling-dll-functions-from-visual-basic-applications"></a>Visual Basic Uygulamasından DLL İşlevi Çağırma

Visual Basic uygulamaları (veya Pascal ya da Fortran gibi diğer dillerdeki) C/C++ DLL'deki işlevleri çağırmak, İşlevler derleyici tarafından yapılan herhangi bir ad düzenleme olmadan doğru çağrı kuralı kullanarak dışarı aktarılmalıdır

`__stdcall` işlev için doğru çağrı kuralını oluşturur (çağrılan işlev yığını temizler ve parametreler sağdan sola geçirilir) ancak işlev adını farklı şekilde düzenler. Bu nedenle **__declspec(dllexport)** kullanılan üzerinde dışa aktarılan bir işlevin bir DLL içinde düzenlenmiş adı dışarı aktarılır.

`__stdcall` Ad düzenlemesi simge adının alt çizgi ekler ( **\_** ) ve simgesiyle ekler bir at işareti (**\@**) karakter sayısına göre ve ardından (gerekli yığın boşluğu) bağımsız değişken listesindeki bayt sayısı. Sonuç olarak, şu şekilde bildirildiğinde işlev:

```C
int __stdcall func (int a, double b)
```

şöyle tasarlanmıştır `_func@12` çıktı.

C çağırma kuralı (`__cdecl`) adı olarak düzenler `_func`.

Düzenlenmiş adı almak için kullanın [/MAP](../build/reference/map-generate-mapfile.md). Kullanım **__declspec(dllexport)** şunları yapar:

- İşlev C çağırma kuralı ile dışarı aktarılıyorsa (`__cdecl`), başındaki altçizgiyi kaldırır ( **\_** ) adı ne zaman aktarılır.

- Dışarı aktarılan işlev C çağırma kuralı kullanmıyorsa (örneğin, `__stdcall`), bunu düzenlenmiş adı dışarı aktarır.

Yığın temizlemenin oluştuğu geçersiz kılmanın bir yolu olmadığından, kullanmalısınız `__stdcall`. Adlarla bilgilerini kaldırmak için `__stdcall`, .def dosyasının EXPORTS bölümünde diğer adlar kullanarak belirtmelisiniz. Bu, aşağıdaki işlev bildirimi için şu şekilde gösterilir:

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

Visual Basic'te yazılan programlar tarafından çağrılacak dll dosyaları için bu konuda gösterilen diğer ad tekniği .def dosyasında gereklidir. Diğer Visual Basic programında yapıldıysa, .def dosyasında diğer adlandırma kullanımı gerekli değildir. Visual Basic programında, yapılabilir bir diğer ad yan tümcesi ekleyerek [Declare](/dotnet/visual-basic/language-reference/statements/declare-statement) deyimi.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [DLL'den Dışarı Aktarma](../build/exporting-from-a-dll.md)

- [Kullanarak bir DLL'nin dışa aktarma. DEF dosyaları](../build/exporting-from-a-dll-using-def-files.md)

- [__Declspec(dllexport) kullanarak DLL'den dışarı aktarma](../build/exporting-from-a-dll-using-declspec-dllexport.md)

- [C dili çalıştırılabilirlerinde kullanmak için C++ işlevlerini dışarı aktarma](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)

- [Hangi dışa aktarma yönteminin kullanılacağını belirleme](../build/determining-which-exporting-method-to-use.md)

- [Düzenlenmiş adlar](../build/reference/decorated-names.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Visual C++'ta DLL'ler](../build/dlls-in-visual-cpp.md)
