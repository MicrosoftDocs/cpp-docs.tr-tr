---
title: Derleyici Hatası C2743
ms.date: 11/04/2016
f1_keywords:
- C2743
helpviewer_keywords:
- C2743
ms.assetid: 644cd444-21d2-471d-a176-f5f52c5a0b73
ms.openlocfilehash: 03cd7c13e093be5073b3df7e7cf29dda870bc47a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50531007"
---
# <a name="compiler-error-c2743"></a>Derleyici Hatası C2743

'type': __clrcall yok Edicisi veya kopya Oluşturucusu olan bir yerel tür catch yapılamaz

Bir modül ile derlenmiş **/CLR** yerel tür ve burada türün yok Edicisi veya kopya Oluşturucusu kullanan bir özel durum yakalamak çalışıldı `__clrcall` çağırma kuralı.

İle derlendiğinde **/CLR**, özel durum işleme üye işlevleri bir yerel türe olmasını bekliyor [__cdecl](../../cpp/cdecl.md) değil [__clrcall](../../cpp/clrcall.md). Üye işlevlerini kullanarak ile yerel türler `__clrcall` çağırma kuralı olamaz yakalandı ile derlenmiş bir modülde **/CLR**.

Daha fazla bilgi için [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2743 oluşturur.

```
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