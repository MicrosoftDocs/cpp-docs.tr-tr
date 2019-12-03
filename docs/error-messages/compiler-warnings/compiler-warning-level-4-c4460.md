---
title: Derleyici Uyarısı (düzey 4) C4460
ms.date: 11/04/2016
f1_keywords:
- C4460
helpviewer_keywords:
- C4460
ms.assetid: c97ac1c9-598d-479e-bfff-c993690c4f3d
ms.openlocfilehash: 7f394af9dc0362035b9361981fdca077a3a915d5
ms.sourcegitcommit: d0504e2337bb671e78ec6dd1c7b05d89e7adf6a7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2019
ms.locfileid: "74682926"
---
# <a name="compiler-warning-level-4-c4460"></a>Derleyici Uyarısı (düzey 4) C4460

WinRT veya CLR işleci ' operator ', başvuruya göre geçti parametresi içeriyor. WinRT veya CLR işleci ' operator ', ' operator ' C++ işlecinden farklı semantiğe sahip, değere göre geçiş yapmak mı istiyordunuz?

Bir değeri Kullanıcı tanımlı Windows Çalışma Zamanı veya CLR işlecine başvuruya göre geçirtiniz. Değer, işlev içinde değiştirilirse, işlev çağrısından sonra döndürülen değere işlevin dönüş değeri atanır. Standart C++olarak, değiştirilen değer işlev çağrısından sonra yansıtılır.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4460 oluşturur ve nasıl düzeltileceğini gösterir.

```cpp
// C4460.cpp
// compile with: /W4 /clr
#include <stdio.h>

public value struct V {
   static V operator ++(V& me) {   // C4460
   // try the following line instead
   // static V operator ++(V me) {

      printf_s(__FUNCSIG__ " called\n");
      V tmp = me;
      me.m_i++;
      return tmp;
   }
   int m_i;
};

int main() {
   V v;
   v.m_i = 0;

   printf_s("%d\n", v.m_i);   // Should print 0
   v++;   // Translates to "v = V::operator ++(v)"
   printf_s("%d\n", v.m_i);   // will print 0, hence the warning
}
```