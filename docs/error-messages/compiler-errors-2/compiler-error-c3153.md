---
title: Derleyici Hatası C3153
ms.date: 11/04/2016
f1_keywords:
- C3153
helpviewer_keywords:
- C3153
ms.assetid: d775d97e-2480-484f-81f1-88406b10f947
ms.openlocfilehash: 62b9e7499c52153183f14eae47c488da6a59b458
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50610424"
---
# <a name="compiler-error-c3153"></a>Derleyici Hatası C3153

'interface': bir arabirimin örneğini oluşturamazsınız

Bir arabirim örneği oluşturulamıyor. Bir arabirim üyelerinin kullanmak için bir arabirim sınıfından türetilir, arabirim üyeleri uygulamak ve üyeleri'ni kullanır.

Aşağıdaki örnek, C3153 oluşturur:

```
// C3153.cpp
// compile with: /clr
interface class A {
};

int main() {
   A^ a = gcnew A;   // C3153
}
```
