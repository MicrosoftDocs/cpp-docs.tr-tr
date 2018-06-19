---
title: Derleyici Hatası C2653 | Microsoft Docs
ms.custom: ''
ms.date: 11/30/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2653
dev_langs:
- C++
helpviewer_keywords:
- C2653
ms.assetid: 3f49e731-affd-43a0-a8d0-181db7650bc3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a8e1df7dd6337b1a3e363a5744181b12d94c879b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33234973"
---
# <a name="compiler-error-c2653"></a>Derleyici Hatası C2653

> '*tanımlayıcısı*': bir sınıf veya ad alanı adı değil

Sınıfı, yapısı, UNION veya ad alanı adını buraya dili sözdizimi gerektirir.

Sınıfı, yapısı, UNION veya ad alanı bir kapsam işleci önünde olarak bildirilmedi bir ad kullandığınızda bu hata oluşabilir. Bu sorunu gidermek için ad bildirme veya adı kullanılmadan önce bildiren üstbilgisini.

C2653 tanımlamak çalışırsanız olası ayrıca bir *bileşik ad alanı*, bir veya daha fazla kapsam iç içe geçmiş ad alanı adlarını içeren bir ad alanı. Bileşik ad alanı tanımları C++ C ++ 17 önce izin verilmez. Bileşik ad alanları, Visual Studio 2015 güncelleştirme 3'te belirttiğiniz başlatılmasını desteklenir [/Std: c ++ Son](../../build/reference/std-specify-language-standard-version.md) derleyici seçeneği. Visual C++ 2017 sürüm 15,5 başlayarak, derleyici bileşik ad alanı tanımları destekler, [/Std: c ++ 17](../../build/reference/std-specify-language-standard-version.md) seçeneği belirtildi.

## <a name="examples"></a>Örnekler

Kapsam adı kullanılan ancak bildirilmemiş olduğundan bu örnek C2653 oluşturur. Derleyici sınıf, yapı, UNION veya kapsam işleci (:) önce ad alanı adı bekliyor.

```cpp
// C2653.cpp
// compile with: /c
class yy {
   void func1(int i);
};

void xx::func1(int m) {}   // C2653, xx is not declared
void yy::func1(int m) {}   // OK
```

C ++ 17 veya üzeri standartları derlenmemiş kodda, iç içe geçmiş her düzeyde bir açık ad alanı bildiriminin iç içe geçmiş ad alanları kullanmanız gerekir:

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
