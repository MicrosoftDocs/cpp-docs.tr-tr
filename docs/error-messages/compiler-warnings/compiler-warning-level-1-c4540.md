---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4540'
title: Derleyici Uyarısı (düzey 1) C4540
ms.date: 11/04/2016
f1_keywords:
- C4540
helpviewer_keywords:
- C4540
ms.assetid: 8085e748-5f4d-43c2-b06d-eaf794edbf72
ms.openlocfilehash: 8bd65d09abf48fc3653f160ebdf109235f3e1471
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97212265"
---
# <a name="compiler-warning-level-1-c4540"></a>Derleyici Uyarısı (düzey 1) C4540

dynamic_cast erişilemeyen veya belirsiz tabana dönüştürmek için kullanılır; çalışma zamanı testi başarısız olacak (' type1 '-' type2 ')

**`dynamic_cast`** Bir türden diğerine dönüştürmek için kullandınız. Derleyici, taban sınıfına erişilemediğinden (örneğin  **`private`** ,) veya belirsiz (örneğin, sınıf hiyerarşisinde birden çok kez görünür) olduğundan, dönüştürmenin her zaman başarısız olacağını (null döndürecek) belirledi.

Aşağıda bu uyarının bir örneği gösterilmektedir. **B** sınıfı, **A** sınıfından türetilir. Program, **`dynamic_cast`** b sınıfından olduğu ve bu nedenle erişilemeyen için her zaman başarısız olacak şekilde, **b** sınıfından (türetilmiş sınıf) sınıf  **A**'ya dönüştürmek için kullanır **`private`** . ' **A** erişiminin değiştirilmesi **`public`** uyarıyı çözmeyecektir.

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
