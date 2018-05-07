---
title: Derleyici Uyarısı (Düzey 2) C4412'yi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4412
dev_langs:
- C++
helpviewer_keywords:
- C4412
ms.assetid: f28dc531-1a98-497b-a366-0a13e1bc81c7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3d186a237c7eb21cdcdc51a896d58d11bc19c5b2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-2-c4412"></a>Derleyici Uyarısı (Düzey 2) C4412'yi
'function': işlev imzası içeren türü 'type'; Saf kod arasında geçirmek için güvenli ve karma veya yerel C++ nesneleri.  
  
 **/CLR: pure** derleyici seçeneği Visual Studio 2015'te kullanım dışıdır. "Saf" olması gereken kodu varsa, bu C# bağlantı noktasının öneririz.  
  
 Bir çalışma zamanı hatası sonuçlanabilir güvensiz bir durum derleyici algılandı: gelen çağrısı yapılıyor bir **/CLR: Saf** dllimport ve işlev imzası aracılığıyla içeri aktarılmış bir işleve derlenecek güvenli olmayan bir tür içerir . Üye işlevini içeriyorsa veya güvenli olmayan bir tür ya da bir yöneltme güvenli olmayan bir tür için bir veri üyesi olan bir tür güvenli değildir.  
  
 Bu varsayılan çağırma kuralları saf ve yerel kodu arasında fark nedeniyle güvenli olmayan (veya yerel ve yönetilen karma). İçe aktarma sırasında (aracılığıyla `dllimport`) bir işlevdeki bir **/CLR: Saf** derlenecek, her tür imzada bildirimleri (hakkında özellikle dikkatli olarak işlevi dışarı aktarır derlenecek de aynı olduğundan emin olun farkları örtük çağırma kurallarını).  
  
 Beklenmeyen sonuçlara vermek özellikle yatkın bir sanal üyesi işlevdir.  Ancak, sanal olmayan bir işlev doğru sonuçlar aldığından emin olmak için test edilmelidir. Doğru sonuçlar alma eminseniz bu uyarıyı yoksayabilirsiniz.  
  
  
 Varsayılan olarak C4412'yi kapalıdır. Bkz: [derleyici uyarıları emin olduğunuz kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) ve [dllexport, dllimport](../../cpp/dllexport-dllimport.md) daha fazla bilgi için.  
  
 Bu uyarıyı çözmek için tüm işlevleri türünden kaldırın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4412'yi oluşturur.  
  
```  
// C4412.cpp  
// compile with: /c /W2 /clr:pure  
#pragma warning (default : 4412)  
  
struct Unsafe {  
   virtual void __cdecl Test();  
};  
  
struct Safe {  
   int i;  
};  
  
__declspec(dllimport) Unsafe * __cdecl func();  
__declspec(dllimport) Safe * __cdecl func2();  
  
int main() {  
   Unsafe *pUnsafe = func();   // C4412  
   // pUnsafe->Test();  
  
   Safe *pSafe = func2();   // OK  
}  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, iki tür bildiren bir üstbilgi dosyasıdır. `Unsafe` Türüdür güvenli olmayan bir üye işlevi içerdiğinden.  
  
```  
// C4412.h  
struct Unsafe {  
   // will be __clrcall if #included in pure compilation  
   // defaults to __cdecl in native or mixed mode compilation  
   virtual void Test(int * pi);  
  
   // try the following line instead  
   // virtual void __cdecl Test(int * pi);  
};  
  
struct Safe {  
   int i;  
};  
```  
  
## <a name="example"></a>Örnek  
 Bu örnek üstbilgi dosyasında tanımlanan türleriyle işlevleri dışa aktarır.  
  
```  
// C4412_2.cpp  
// compile with: /LD  
#include "C4412.h"  
  
void Unsafe::Test(int * pi) {  
   *pi++;  
}  
  
__declspec(dllexport) Unsafe * __cdecl func() { return new Unsafe; }  
__declspec(dllexport) Safe * __cdecl func2() { return new Safe; }  
```  
  
## <a name="example"></a>Örnek  
 Çağırma kuralı varsayılan bir **/CLR: pure** derleme, yerel bir derlemeden farklıdır.  C4412.h dahil olduğunda `Test` varsayılan olarak `__clrcall`. Derleme ve bu programı çalıştır (kullanmayın **/c**), programın bir özel durum oluşturur.  
  
 Aşağıdaki örnek C4412'yi oluşturur.  
  
```  
// C4412_3.cpp  
// compile with: /W2 /clr:pure /c /link C4412_2.lib  
#pragma warning (default : 4412)  
#include "C4412.h"  
  
__declspec(dllimport) Unsafe * __cdecl func();  
__declspec(dllimport) Safe * __cdecl func2();  
  
int main() {  
   int n = 7;  
   Unsafe *pUnsafe = func();   // C4412  
   pUnsafe->Test(&n);  
  
   Safe *pSafe = func2();   // OK  
}  
```