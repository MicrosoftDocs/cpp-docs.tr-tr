---
title: Derleyici Uyarısı (düzey 1) C4540
ms.date: 11/04/2016
f1_keywords:
- C4540
helpviewer_keywords:
- C4540
ms.assetid: 8085e748-5f4d-43c2-b06d-eaf794edbf72
ms.openlocfilehash: 8e514f4f3cf0cc3ee95ff709eda307b143ab3b1c
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73965695"
---
# <a name="compiler-warning-level-1-c4540"></a>Derleyici Uyarısı (düzey 1) C4540

dynamic_cast erişilemeyen veya belirsiz tabana dönüştürmek için kullanılır; çalışma zamanı testi başarısız olacak (' type1 '-' type2 ')

Bir türden diğerine dönüştürmek için `dynamic_cast` kullandınız. Derleyici, bir temel sınıf erişilemez olduğu (örneğin, örneğin`private`) veya belirsiz olduğu (örneğin, sınıf hiyerarşisinde birden çok kez göründüğü) için dönüştürmenin her zaman başarısız olacağını ( **null**döndürecek) belirledi.

Aşağıda bu uyarının bir örneği gösterilmektedir. **B** sınıfı, **A**sınıfından türetilir. Program, b **sınıfı `private`** ve bu nedenle erişilemez olduğu için her zaman başarısız olacak şekilde **b** sınıfından (türetilmiş sınıf) **bir sınıf A**'ya dönüştürmek için `dynamic_cast` kullanır. **A** erişiminin **genel** olarak değiştirilmesi, uyarıyı çözmeyecektir.

```cpp
// C4540.cpp
// compile with: /W1

struct A {
   virtual void g() {}
};

struct B : private A {
   virtual void g() {}
};

int main() {
   B b;
   A * ap = dynamic_cast<A*>(&b);   // C4540
}
```