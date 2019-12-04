---
title: Derleyici hatası C2743
ms.date: 11/04/2016
f1_keywords:
- C2743
helpviewer_keywords:
- C2743
ms.assetid: 644cd444-21d2-471d-a176-f5f52c5a0b73
ms.openlocfilehash: d679ce0df0d43772a6c32aa8e00869ac1a4a082b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759652"
---
# <a name="compiler-error-c2743"></a>Derleyici hatası C2743

' Type ': __clrcall yıkıcısı veya kopya Oluşturucusu ile yerel bir tür yakalayamaz

**/Clr** ile derlenen bir modül yerel türde bir özel durum yakalamak denendi ve türün yıkıcı veya kopya oluşturucusunun `__clrcall` çağırma kuralını kullandığı yer.

**/Clr**ile derlendiğinde, özel durum işleme yerel bir türdeki üye işlevlerinin [__clrcall](../../cpp/clrcall.md)değil [__cdecl](../../cpp/cdecl.md) olmasını bekler. `__clrcall` çağırma kuralı kullanan üye işlevleri olan yerel türler **/clr**ile derlenen bir modülde yakalanamaz.

Daha fazla bilgi için bkz. [/clr (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C2743 oluşturur.

```cpp
// C2743.cpp
// compile with: /clr
public struct S {
   __clrcall ~S() {}
};

public struct T {
   ~T() {}
};

int main() {
   try {}
   catch(S) {}   // C2743
   // try the following line instead
   // catch(T) {}

   try {}
   catch(S*) {}   // OK
}
```
