---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3662'
title: Derleyici hatası C3662
ms.date: 11/04/2016
f1_keywords:
- C3662
helpviewer_keywords:
- C3662
ms.assetid: 61bd3e41-a86b-42c0-be89-d992d3906ff1
ms.openlocfilehash: a62ffc4d5dc6083f36bab1e4e0712d942f70facf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134296"
---
# <a name="compiler-error-c3662"></a>Derleyici hatası C3662

' üye ': geçersiz kılma belirticisi ' belirtici ' yalnızca yönetilen veya WinRT sınıflarının üye işlevlerinde izin verilir

Bir geçersiz kılma belirticisi yerel türdeki bir üyede kullanıldı, buna izin verilmez.

Daha fazla bilgi için bkz. [Açık geçersiz kılmalar](../../extensions/explicit-overrides-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3662 oluşturur.

```cpp
// C3662.cpp
// compile with: /clr /c
struct S {
   virtual void f();
};

struct S1 : S {
   virtual void f() new;   // C3662
};

ref struct T {
   virtual void f();
};

ref struct T1 : T {
   virtual void f() new;   // OK
};
```
