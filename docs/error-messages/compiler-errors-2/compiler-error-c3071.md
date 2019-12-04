---
title: Derleyici hatası C3071
ms.date: 11/04/2016
f1_keywords:
- C3071
helpviewer_keywords:
- C3071
ms.assetid: 69879e66-a60e-4058-9bbd-d5c5e2d8ee37
ms.openlocfilehash: 26a95b18970aef450c6fdf718910aa3f816fd778
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759418"
---
# <a name="compiler-error-c3071"></a>Derleyici hatası C3071

' operator ' işleci yalnızca bir başvuru sınıfının veya değer türünün bir örneğine uygulanabilir

CLR işleci yerel bir tür üzerinde kullanılamaz. İşleci bir başvuru sınıfında veya bir başvuru yapısı (bir değer türü) üzerinde kullanılabilir, ancak int gibi yerel bir tür veya System:: Int32 gibi yerel bir tür için bir diğer ad değil. Bu türler, yerel değişkene başvuran C++ bir şekilde koddan kutulanabilir, bu nedenle işleç kullanılamaz.

Daha fazla bilgi için bkz. [Izleme başvurusu işleci](../../extensions/tracking-reference-operator-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3071 oluşturur.

```cpp
// C3071.cpp
// compile with: /clr
class N {};
ref struct R {};

int main() {
   N n;
   %n;   // C3071

   R r;
   R ^ r2 = %r;   // OK
}
```
