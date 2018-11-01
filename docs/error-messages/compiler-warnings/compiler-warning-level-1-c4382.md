---
title: Derleyici Uyarısı (düzey 1) C4382
ms.date: 11/04/2016
f1_keywords:
- C4382
helpviewer_keywords:
- C4382
ms.assetid: 34be9ad3-bae6-411a-8f80-0c8fd0d2c092
ms.openlocfilehash: cca2f8cc13cc8317bac3736e142ef58e126ed994
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50629222"
---
# <a name="compiler-warning-level-1-c4382"></a>Derleyici Uyarısı (düzey 1) C4382

> özel durum atma '*türü*': __clrcall yok Edicisi veya kopya Oluşturucusu olan bir tür yalnızca/CLR yakalanabilir: pure modülünde

## <a name="remarks"></a>Açıklamalar

**/CLR: pure** derleyici seçeneğini Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de desteklenmiyor.

İle derlendiğinde **/CLR** (değil **/CLR: pure**), özel durum işleme üye işlevleri bir yerel türe olmasını bekliyor [__cdecl](../../cpp/cdecl.md) ve [__clrcall](../../cpp/clrcall.md). Üye işlevlerini kullanarak ile yerel türler `__clrcall` çağırma kuralı olamaz yakalandı ile derlenmiş bir modülde **/CLR**.

Özel durum ile derlenmiş bir modülde yakalandı, **/CLR: pure**, bu uyarıyı yoksayabilirsiniz.

Daha fazla bilgi için [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4382 oluşturur.

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