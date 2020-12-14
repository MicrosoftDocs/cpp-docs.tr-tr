---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4382'
title: Derleyici Uyarısı (düzey 1) C4382
ms.date: 11/04/2016
f1_keywords:
- C4382
helpviewer_keywords:
- C4382
ms.assetid: 34be9ad3-bae6-411a-8f80-0c8fd0d2c092
ms.openlocfilehash: 038225aea9592070b44af138be9deb5076e2f5f7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311311"
---
# <a name="compiler-warning-level-1-c4382"></a>Derleyici Uyarısı (düzey 1) C4382

> '*Type*' oluşturuluyor: __clrcall yok edicisi veya kopya Oluşturucusu olan bir tür yalnızca/clr: Pure modülünde yakalanabilir

## <a name="remarks"></a>Açıklamalar

**/Clr: Pure** derleyici seçeneği visual Studio 2015 ' de kullanımdan kaldırılmıştır ve visual Studio 2017 ' de desteklenmez.

**/Clr** ( **/clr: Pure** değil) ile derlendiğinde, özel durum işleme yerel bir türdeki üye işlevlerinin [__clrcall](../../cpp/clrcall.md)değil [__cdecl](../../cpp/cdecl.md) olmasını bekler. Çağırma kuralını kullanan üye işlevleri olan yerel türler `__clrcall` **/clr** ile derlenen bir modülde yakalanamaz.

Özel durum **/clr: Pure** ile derlenen bir modülde yakalanacaktır, bu uyarıyı yoksayabilirsiniz.

Daha fazla bilgi için bkz. [/clr (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C4382 oluşturur.

```cpp
// C4382.cpp
// compile with: /clr /W1 /c
struct S {
   __clrcall ~S() {}
};

struct T {
   ~T() {}
};

int main() {
   S s;
   throw s;   // C4382

   S * ps = &s;
   throw ps;   // OK

   T t;
   throw t;   // OK
}
```
