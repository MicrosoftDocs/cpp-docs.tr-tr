---
title: Derleyici Uyarısı (düzey 4) C4460
ms.date: 11/04/2016
f1_keywords:
- C4460
helpviewer_keywords:
- C4460
ms.assetid: c97ac1c9-598d-479e-bfff-c993690c4f3d
ms.openlocfilehash: a42562a2c35bb56de4ce7147e199f4db2dddb684
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50532203"
---
# <a name="compiler-warning-level-4-c4460"></a>Derleyici Uyarısı (düzey 4) C4460

WinRT veya CLR işleci 'operator', başvuruyla parametre geçti. WinRT veya CLR 'operator 'işleci 'operator' C++ işleci farklı semantiğe sahip, değere göre geçirilecek kullanmak mı istiyordunuz?

Kullanıcı tanımlı bir Windows çalışma zamanı veya CLR işleci başvuruya göre bir değer geçirildi. İşlev içinde değeri değiştirilirse, işlev çağrısının dönüş değeri işlevin atanacak sonra döndürülen değer unutmayın. Standart C++'da, işlev çağrısından sonra değişen değeri yansıtılır.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4460 oluşturur ve bu sorunun nasıl gösterir.

```
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