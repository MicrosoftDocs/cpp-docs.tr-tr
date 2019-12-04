---
title: Derleyici hatası C3865
ms.date: 11/04/2016
f1_keywords:
- C3865
helpviewer_keywords:
- C3865
ms.assetid: 9bc62bb0-4fb8-4856-a5cf-c7cb4029a596
ms.openlocfilehash: 960c795fe934433e4e3cf79e4c01c49d00205b9b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761497"
---
# <a name="compiler-error-c3865"></a>Derleyici hatası C3865

' calling_convention ': yalnızca yerel üye işlevlerde kullanılabilir

Bir çağırma kuralı, genel bir işlev veya yönetilen üye işlevi olan bir işlevde kullanıldı. Çağırma kuralı yalnızca yerel (yönetilmeyen) üye işlevinde kullanılabilir.

Daha fazla bilgi için bkz. [çağırma kuralları](../../cpp/calling-conventions.md).

Aşağıdaki örnek C3865 oluşturur:

```cpp
// C3865.cpp
// compile with: /clr
// processor: x86
void __thiscall Func(){}   // C3865

// OK
struct MyType {
   void __thiscall Func(){}
};
```
