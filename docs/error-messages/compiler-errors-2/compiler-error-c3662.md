---
title: Derleyici Hatası C3662
ms.date: 11/04/2016
f1_keywords:
- C3662
helpviewer_keywords:
- C3662
ms.assetid: 61bd3e41-a86b-42c0-be89-d992d3906ff1
ms.openlocfilehash: 28d8df02d63fc1b16a392a2df83524cd616d5ab3
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58769049"
---
# <a name="compiler-error-c3662"></a>Derleyici Hatası C3662

'member': geçersiz kılma belirticisi 'yalnızca üye işlevleri üzerinde belirticisi' yönetilen veya WinRT sınıfları

Bir geçersiz kılma belirticisi bir izin yerel türdür, üye üzerinde kullanıldı.

Daha fazla bilgi için [açık geçersiz kılmalar](../../extensions/explicit-overrides-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3662 oluşturur.

```
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