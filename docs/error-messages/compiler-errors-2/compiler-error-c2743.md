---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2743'
title: Derleyici hatası C2743
ms.date: 11/04/2016
f1_keywords:
- C2743
helpviewer_keywords:
- C2743
ms.assetid: 644cd444-21d2-471d-a176-f5f52c5a0b73
ms.openlocfilehash: 2619d4a0dd2b89d36f11944b59c2ab4993d95fd0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123064"
---
# <a name="compiler-error-c2743"></a>Derleyici hatası C2743

' Type ': __clrcall yıkıcısı veya kopya Oluşturucusu ile yerel bir tür yakalayamaz

**/Clr** ile derlenen bir modül yerel türde bir özel durum yakalamak denendi ve türün yıkıcı veya kopya oluşturucusunun `__clrcall` çağırma kuralını kullandığı yer.

**/Clr** ile derlendiğinde, özel durum işleme yerel bir türdeki üye işlevlerinin [__clrcall](../../cpp/clrcall.md)değil [__cdecl](../../cpp/cdecl.md) olmasını bekler. Çağırma kuralını kullanan üye işlevleri olan yerel türler `__clrcall` **/clr** ile derlenen bir modülde yakalanamaz.

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
