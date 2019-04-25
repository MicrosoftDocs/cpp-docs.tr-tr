---
title: Derleyici Hatası C3865
ms.date: 11/04/2016
f1_keywords:
- C3865
helpviewer_keywords:
- C3865
ms.assetid: 9bc62bb0-4fb8-4856-a5cf-c7cb4029a596
ms.openlocfilehash: 846657d3598e268d78ff3c39f2bfc901756ad370
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62302026"
---
# <a name="compiler-error-c3865"></a>Derleyici Hatası C3865

'calling_convention': yalnızca yerel üye işlevlerde kullanılabilir

Çağırma kuralı, genel bir işlev olan bir işlev veya yönetilen bir üye işlevi kullanıldı. Çağırma kuralı yalnızca bir yerel (yönetilmeyen) üye işlev üzerinde kullanılabilir.

Daha fazla bilgi için [çağırma kuralları](../../cpp/calling-conventions.md).

Aşağıdaki örnek, C3865 oluşturur:

```
// C3865.cpp
// compile with: /clr
// processor: x86
void __thiscall Func(){}   // C3865

// OK
struct MyType {
   void __thiscall Func(){}
};
```