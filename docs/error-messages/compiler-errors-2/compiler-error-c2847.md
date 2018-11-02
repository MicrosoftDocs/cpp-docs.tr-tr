---
title: Derleyici Hatası C2847
ms.date: 11/04/2016
f1_keywords:
- C2847
helpviewer_keywords:
- C2847
ms.assetid: 9ad9a0e0-8b16-49d9-a5be-f8eda2372aa9
ms.openlocfilehash: 99c49be746cea6fb80c5e24667bcd97556a0ad04
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50481490"
---
# <a name="compiler-error-c2847"></a>Derleyici Hatası C2847

Yönetilen için sizeof veya WinRT türü 'class' uygulanamaz

[Sizeof](../../cpp/sizeof-operator.md) işleci, derleme zamanında bir nesnenin değerini alır. Yönetilen boyutunu veya WinRT sınıf, arabirim veya değer türü dinamiktir ve bu nedenle derleme zamanında bilinen olamaz.

Örneğin, aşağıdaki örnek C2847 oluşturur:

```
// C2847.cpp
// compile with: /clr
ref class A {};

int main() {
   A ^ xA = gcnew A;
   sizeof(*xA);   // C2847 cannot use sizeof on managed object
}
```
