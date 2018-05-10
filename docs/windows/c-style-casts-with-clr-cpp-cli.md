---
title: C-Style - clr ile çevirir (C + +/ CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- C-style casts and /clr
ms.assetid: d2a4401a-156a-4da9-8d12-923743e26913
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 384aa6d1d7a4329f52157f1d002dcda2feb5cb8a
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="c-style-casts-with-clr-ccli"></a>/clr ile C Türü Atamalar (C++/CLI)
Aşağıdaki konu yalnızca ortak dil çalışma zamanı için geçerlidir.  
  
 CLR Türleri ile kullanıldığında, derleyicinin C tarzı aşağıdaki sırayla aşağıda listelenen atamaları birine dönüştürme eşlemeye çalışır:  
  
1.  const_cast  
  
2.  safe_cast  
  
3.  safe_cast artı const_cast  
  
4.  static_cast  
  
5.  static_cast artı const_cast  
  
 Yukarıda listelenen atamaları hiçbiri geçerli olup olmadığını ve ifade türü ve hedef türü CLR başvuru türleri ise, bir çalışma zamanı denetim için (castclass MSIL yönergesi) C stili cast eşler. Aksi halde, bir C tarzı cast geçersiz olarak kabul edilir ve derleyici bir hata verir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir C tarzı cast önerilmez. İle derleme yapılırken [/CLR (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md), kullanın [safe_cast](../windows/safe-cast-cpp-component-extensions.md).  
  
 Aşağıdaki örnek, bir C eşleyen tarzı dönüştürme gösterir bir `const_cast`.  
  
```  
// cstyle_casts_1.cpp  
// compile with: /clr  
using namespace System;  
  
ref struct R {};  
int main() {  
   const R^ constrefR = gcnew R();  
   R^ nonconstR = (R^)(constrefR);   
}  
```  
  
 Aşağıdaki örnek, bir C eşleyen tarzı dönüştürme gösterir bir `safe_cast`.  
  
```  
// cstyle_casts_2.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   Object ^ o = "hello";  
   String ^ s = (String^)o;  
}  
```  
  
 Aşağıdaki örnek, bir C eşleyen tarzı dönüştürme gösterir bir `safe_cast` artı `const_cast`.  
  
```  
// cstyle_casts_3.cpp  
// compile with: /clr  
using namespace System;  
  
ref struct R {};  
ref struct R2 : public R {};  
  
int main() {  
   const R^ constR2 = gcnew R2();  
   try {  
   R2^ b2DR = (R2^)(constR2);  
   }  
   catch(InvalidCastException^ e) {  
      System::Console::WriteLine("Invalid Exception");  
   }  
}  
```  
  
 Aşağıdaki örnek, bir C eşleyen tarzı dönüştürme gösterir bir `static_cast`.  
  
```  
// cstyle_casts_4.cpp  
// compile with: /clr  
using namespace System;  
  
struct N1 {};  
struct N2 {  
   operator N1() {  
      return N1();  
   }  
};  
  
int main() {  
   N2 n2;  
   N1 n1 ;  
   n1 = (N1)n2;  
}  
```  
  
 Aşağıdaki örnek, bir C eşleyen tarzı dönüştürme gösterir bir `static_cast` artı `const_cast`.  
  
```  
// cstyle_casts_5.cpp  
// compile with: /clr  
using namespace System;  
struct N1 {};  
  
struct N2 {  
   operator const N1*() {  
      static const N1 n1;  
      return &n1;  
   }  
};  
  
int main() {  
   N2 n2;  
   N1* n1 = (N1*)(const N1*)n2;   // const_cast + static_cast  
}  
```  
  
 Aşağıdaki örnek, bir C çalışma zamanı denetlemek için eşleşen tarzı dönüştürme gösterir.  
  
```  
// cstyle_casts_6.cpp  
// compile with: /clr  
using namespace System;  
  
ref class R1 {};  
ref class R2 {};  
  
int main() {  
   R1^ r  = gcnew R1();  
   try {  
      R2^ rr = ( R2^)(r);  
   }  
   catch(System::InvalidCastException^ e) {  
      Console::WriteLine("Caught expected exception");  
   }  
}  
```  
  
 Aşağıdaki örnek, bir geçersiz C, derleyici neden olan hata verecek tarzı dönüştürme gösterir.  
  
```  
// cstyle_casts_7.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   String^s = S"hello";  
   int i = (int)s;   // C2440  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği:   **/CLR**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma Zamanı Platformları için Bileşen Uzantıları](../windows/component-extensions-for-runtime-platforms.md)