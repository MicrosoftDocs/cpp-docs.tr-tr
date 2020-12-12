---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3865'
title: Derleyici hatası C3865
ms.date: 11/04/2016
f1_keywords:
- C3865
helpviewer_keywords:
- C3865
ms.assetid: 9bc62bb0-4fb8-4856-a5cf-c7cb4029a596
ms.openlocfilehash: 956cbfeb5bac97cae7e9a9a411c29326062e15b2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222885"
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
