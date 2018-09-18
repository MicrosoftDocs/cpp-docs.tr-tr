---
title: Derleyici Hatası C2743 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2743
dev_langs:
- C++
helpviewer_keywords:
- C2743
ms.assetid: 644cd444-21d2-471d-a176-f5f52c5a0b73
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4217a1e7a8475362c654ac34b6a345846341ec35
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46056501"
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