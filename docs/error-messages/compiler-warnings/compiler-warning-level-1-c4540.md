---
title: Derleyici Uyarısı (düzey 1) C4540
ms.date: 11/04/2016
f1_keywords:
- C4540
helpviewer_keywords:
- C4540
ms.assetid: 8085e748-5f4d-43c2-b06d-eaf794edbf72
ms.openlocfilehash: 86f6cd866f7708277ebba436ba7c076086dc9c8c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50473677"
---
# <a name="compiler-warning-level-1-c4540"></a>Derleyici Uyarısı (düzey 1) C4540

erişilemeyen veya belirsiz tabanı dönüştürmek için kullanılan dynamic_cast; test çalışma zamanı ('type2' öğesine ' type1') başarısız olur

Kullanılan `dynamic_cast` bir türden diğerine dönüştürme. Derleyici, atama her zaman başarısız olacağı belirlenen (dönüş **NULL**) bir taban sınıfına erişilemez olduğundan (`private`, örneği için) veya belirsiz (birden çok kez sınıf hiyerarşisini, örneğin görünür).

Bu uyarı örneği aşağıda gösterilmiştir. Sınıf **B** sınıfından türetilen **A**. Programın kullandığı `dynamic_cast` sınıftan dönüştürme için **B** (türetilmiş sınıf) sınıfı için **A**, her zaman başarısız olur çünkü sınıfı **B** olduğu `private` ve bu nedenle erişilemez. Erişimi değiştirme **A** için **genel** uyarı çözülecektir.

```
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