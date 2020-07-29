---
title: Derleyici Uyarısı (düzey 1) C4540
ms.date: 11/04/2016
f1_keywords:
- C4540
helpviewer_keywords:
- C4540
ms.assetid: 8085e748-5f4d-43c2-b06d-eaf794edbf72
ms.openlocfilehash: 13935e7eebdf3e7b7e89fad8c55d410cf2788e4d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230655"
---
# <a name="compiler-warning-level-1-c4540"></a>Derleyici Uyarısı (düzey 1) C4540

dynamic_cast erişilemeyen veya belirsiz tabana dönüştürmek için kullanılır; çalışma zamanı testi başarısız olacak (' type1 '-' type2 ')

**`dynamic_cast`** Bir türden diğerine dönüştürmek için kullandınız. Derleyici, taban sınıfına erişilemediğinden (örneğin **NULL** **`private`** ,) veya belirsiz (örneğin, sınıf hiyerarşisinde birden çok kez görünür) olduğundan, dönüştürmenin her zaman başarısız olacağını (null döndürecek) belirledi.

Aşağıda bu uyarının bir örneği gösterilmektedir. **B** sınıfı, **A**sınıfından türetilir. Program, **`dynamic_cast`** b sınıfından olduğu ve bu nedenle erişilemeyen için her zaman başarısız olacak şekilde, **b** sınıfından (türetilmiş sınıf) sınıf **B** **A**'ya dönüştürmek için kullanır **`private`** . ' **A** erişiminin değiştirilmesi **`public`** uyarıyı çözmeyecektir.

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
