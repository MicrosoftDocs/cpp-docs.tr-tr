---
title: Derleyici Uyarısı (düzey 1) C4382
ms.date: 11/04/2016
f1_keywords:
- C4382
helpviewer_keywords:
- C4382
ms.assetid: 34be9ad3-bae6-411a-8f80-0c8fd0d2c092
ms.openlocfilehash: 7b8dbf77defab2a711ad931057c740193908474b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186978"
---
# <a name="compiler-warning-level-1-c4382"></a>Derleyici Uyarısı (düzey 1) C4382

> '*Type*' oluşturuluyor: __clrcall yok edicisi veya kopya Oluşturucusu olan bir tür yalnızca/clr: Pure modülünde yakalanabilir

## <a name="remarks"></a>Açıklamalar

**/Clr: Pure** derleyici seçeneği visual Studio 2015 ' de kullanımdan kaldırılmıştır ve visual Studio 2017 ' de desteklenmez.

**/Clr** ( **/clr: Pure**değil) ile derlendiğinde, özel durum işleme yerel bir türdeki üye işlevlerinin [__clrcall](../../cpp/clrcall.md)değil [__cdecl](../../cpp/cdecl.md) olmasını bekler. `__clrcall` çağırma kuralı kullanan üye işlevleri olan yerel türler **/clr**ile derlenen bir modülde yakalanamaz.

Özel durum **/clr: Pure**ile derlenen bir modülde yakalanacaktır, bu uyarıyı yoksayabilirsiniz.

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
