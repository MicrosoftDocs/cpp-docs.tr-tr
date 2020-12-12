---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2653'
title: Derleyici hatası C2653
ms.date: 11/30/2017
f1_keywords:
- C2653
helpviewer_keywords:
- C2653
ms.assetid: 3f49e731-affd-43a0-a8d0-181db7650bc3
ms.openlocfilehash: f3be7ade8a6dcfc6aa8c5a83cc8a055fc230789d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286156"
---
# <a name="compiler-error-c2653"></a>Derleyici hatası C2653

> '*Identifier*': bir sınıf veya ad alanı adı değil

Dil sözdizimi, burada bir sınıf, yapı, birleşim veya ad alanı adı gerektirir.

Bu hata, bir kapsam işlecinin önünde sınıf, yapı, birleşim veya ad alanı olarak bildirilmemiş bir ad kullandığınızda ortaya çıkabilir. Bu sorunu onarmak için adı bildirin veya kullanılmadan önce adı bildiren üstbilgiyi ekleyin.

Bir ya da daha fazla kapsam iç içe ad alanı adı içeren bir ad alanı olan bir *bileşik ad* alanı tanımlamaya çalışırsanız C2653 de mümkündür. C++ 17 ' den önceki c++ ' da bileşik ad alanı tanımlarına izin verilmez. [/Std: c + + en son](../../build/reference/std-specify-language-standard-version.md) derleyici seçeneğini belirttiğinizde, bileşik ad alanları Visual Studio 2015 güncelleştirme 3 ' te başlayarak desteklenir. Visual Studio 2017 sürüm 15,5 ' den başlayarak, derleyici [/std: c++ 17](../../build/reference/std-specify-language-standard-version.md) seçeneği belirtildiğinde bileşik ad alanı tanımlarını destekler.

## <a name="examples"></a>Örnekler

Bu örnek, bir kapsam adı kullanıldığı ancak bildirilmeyen için C2653 oluşturur. Derleyici, bir kapsam işlecinden önce bir sınıf, yapı, birleşim veya ad alanı adı bekliyor (::).

```cpp
// C2653.cpp
// compile with: /c
class yy {
   void func1(int i);
};

void xx::func1(int m) {}   // C2653, xx is not declared
void yy::func1(int m) {}   // OK
```

C++ 17 veya üzeri standartlar için derlenmediği kodda, iç içe yerleştirilmiş ad alanları her iç içe geçmiş düzeyinde açık bir ad alanı bildirimi kullanmalıdır:

```cpp
// C2653b.cpp
namespace a::b {int i;}   // C2653 prior to Visual Studio 2015 Update 3,
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
