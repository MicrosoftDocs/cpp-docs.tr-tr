---
title: "Visual Basic uygulamasından DLL işlevi çağırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- functions [C++], calling DLL functions from Visual Basic
- DLL functions [C++]
- function calls [C++], DLL functions
- DLLs [C++], calling
- calling DLL functions from VB applications [C++]
- __stdcall keyword [C++]
- DLL functions [C++], calling
ms.assetid: 282f7fbf-a0f2-4b9f-b277-1982710be56c
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 471f0b2b89d8c44f17567dd9af6add535be7fbcf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="calling-dll-functions-from-visual-basic-applications"></a>Visual Basic Uygulamasından DLL İşlevi Çağırma
Visual Basic uygulamalarını (veya Pascal ya da Fortran gibi diğer dillerde uygulamalar için) bir C/C++ DLL işlevleri çağırmak, İşlevler derleyici tarafından yapılan herhangi bir ad düzenleme olmadan doğru çağırma kullanarak dışarı aktarılmalıdır.  
  
 `__stdcall`işlev için doğru çağırma kuralı oluşturur (çağrılan işlev yığını temizler ve parametreler sağdan sola geçirilir) ancak işlev adı farklı şekilde düzenler. Bu nedenle, zaman **__declspec(dllexport)** kullanılan üzerinde dışarı aktarılan bir işlevin DLL'de düzenlenmiş adı verilir.  
  
 `__stdcall` Ad düzenlemesi sembol adı bir alt çizgi (_) ile önekleri ve simgesiyle ekler bir at işareti (@) karakter ardından (gerekli yığın alanı) bağımsız değişken listesinde bayt sayısı. Sonuç olarak, olarak bildirildiğinde işlev:  
  
```  
int __stdcall func (int a, double b)  
```  
  
 şöyle tasarlanmıştır:  
  
```  
_func@12  
```  
  
 C çağırma kuralı (`__cdecl`) adı olarak süsler `_func`.  
  
 Düzenlenmiş adı almak için [/MAP](../build/reference/map-generate-mapfile.md). Kullanımı **__declspec(dllexport)** şunları yapar:  
  
-   İşlev C çağırma kuralı ile dışarı varsa (**_cdecl**), ad dışarı aktarılırken başında alt çizgi (_) kaldırır.  
  
-   Dışarı aktarılan işlev C çağırma kuralı kullanmıyorsa (örneğin, `__stdcall`), düzenlenmiş adı dışarı aktarır.  
  
 Yığın temizleme oluştuğu geçersiz kılmak için hiçbir şekilde olduğundan kullanmalısınız `__stdcall`. Adlarıyla bilgilerini kaldırmak için `__stdcall`, .def dosyası dışarı bölümünde diğer adları kullanarak belirtmelisiniz. Bu, aşağıdaki işlev bildirimi için aşağıdaki gibi gösterilir:  
  
```  
int  __stdcall MyFunc (int a, double b);  
void __stdcall InitCode (void);  
```  
  
 İçinde. DEF dosyası:  
  
```  
EXPORTS  
   MYFUNC=_MyFunc@12  
   INITCODE=_InitCode@0  
```  
  
 Visual Basic'te yazılmış programlar tarafından çağrılacak dll dosyaları için bu konu başlığı altında gösterilen diğer teknik .def dosyası gereklidir. Diğer Visual Basic programında yapıldıysa .def dosyası takma kullanımını gerekli değildir. Visual Basic programında, yapılabilir bir alias tümcesi ekleyerek [Declare](/dotnet/visual-basic/language-reference/statements/declare-statement) deyimi.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?  
  
-   [DLL'den dışarı aktarma](../build/exporting-from-a-dll.md)  
  
-   [Kullanarak bir DLL dışarı aktarma. DEF dosyaları](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [__Declspec(dllexport) kullanarak DLL'den dışarı aktarma](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [C dili yürütülebilir öğelerinde kullanmak için C++ işlevlerini dışarı aktarma](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [Hangi dışarı aktarma yöntemini kullanacağınızı belirleme](../build/determining-which-exporting-method-to-use.md)  
  
-   [Düzenlenmiş adlar](../build/reference/decorated-names.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++'ta DLL'leri](../build/dlls-in-visual-cpp.md)