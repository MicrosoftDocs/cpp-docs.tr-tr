---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3071'
title: Derleyici hatası C3071
ms.date: 11/04/2016
f1_keywords:
- C3071
helpviewer_keywords:
- C3071
ms.assetid: 69879e66-a60e-4058-9bbd-d5c5e2d8ee37
ms.openlocfilehash: f99175021b87cb9c27982121567bbb0dd97b0163
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320416"
---
# <a name="compiler-error-c3071"></a>Derleyici hatası C3071

' operator ' işleci yalnızca bir başvuru sınıfının veya değer türünün bir örneğine uygulanabilir

CLR işleci yerel bir tür üzerinde kullanılamaz. İşleci bir başvuru sınıfında veya bir başvuru yapısı (bir değer türü) üzerinde kullanılabilir, ancak int gibi yerel bir tür veya System:: Int32 gibi yerel bir tür için bir diğer ad değil. Bu türler, yerel değişkene başvuran bir şekilde C++ kodundan kutulanabilir, bu nedenle işleç kullanılamaz.

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
