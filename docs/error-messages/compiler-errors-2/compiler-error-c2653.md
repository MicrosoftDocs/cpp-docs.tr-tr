---
title: Derleyici Hatası C2653
ms.date: 11/30/2017
f1_keywords:
- C2653
helpviewer_keywords:
- C2653
ms.assetid: 3f49e731-affd-43a0-a8d0-181db7650bc3
ms.openlocfilehash: d4a3a8a74483317b87e16458f44016f0aeca1379
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50471155"
---
# <a name="compiler-error-c2653"></a>Derleyici Hatası C2653

> '*tanımlayıcı*': bir sınıf veya ad alanı adı değil

Dil sözdiziminin sınıf, yapı, birleşim veya ad alanı adı gerektirir.

Sınıfı, yapı, birleşim veya ad alanı kapsamı işleci önünde olarak bildirilmedi bir ad kullandığınızda bu hata oluşabilir. Bu sorunu gidermek için ad bildirmek veya adı kullanılmadan önce bildiren üst bilgisi ekleyin.

C2653 tanımlamak çalışırsanız olası ayrıca bir *bileşik ad alanı*, bir veya daha fazla kapsam iç içe geçmiş ad alanı adlarını içeren bir ad alanı. Bileşik. ad alanı tanımları c++'ta C ++ 17 önce izin verilmez. Bileşik ad alanları, belirttiğiniz zaman, Visual Studio 2015 güncelleştirme 3'te başlayarak desteklenir [/Std: c ++ Son](../../build/reference/std-specify-language-standard-version.md) derleyici seçeneği. Visual C++ 2017 15.5 sürümünden itibaren derleyici bileşik ad alanı tanımlarını destekler, [/Std: c ++ 17](../../build/reference/std-specify-language-standard-version.md) seçeneği belirtildi.

## <a name="examples"></a>Örnekler

Bu örnek, bir kapsam adı kullanılır ancak bildirilmemiş C2653 oluşturur. Derleyici, sınıf, yapı, birleşim veya kapsam işleci (:) önce ad alanı adı bekliyor.

```cpp
// C2653.cpp
// compile with: /c
class yy {
   void func1(int i);
};

void xx::func1(int m) {}   // C2653, xx is not declared
void yy::func1(int m) {}   // OK
```

C ++ 17 veya üzeri standartları için derlenmedi kodda, iç içe geçmiş her düzeyde bir açık ad alanı bildirimi iç içe geçmiş ad alanları kullanmanız gerekir:

```cpp
// C2653b.cpp
namespace a::b {int i;}   // C2653 prior to Visual C++ 2015 Update 3,
                          // C2429 thereafter. Use /std:c++17 or /std:c++latest to fix.

namespace a {             // Use this form for compliant code under /std:c++14 (the default)
   namespace b {          // or when using compilers before Visual Studio 2015 update 3.
      int i;
   }
}

int main() {
   a::b::i = 2;
}
```
