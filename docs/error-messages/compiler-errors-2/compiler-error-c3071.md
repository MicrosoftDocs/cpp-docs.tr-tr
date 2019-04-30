---
title: Derleyici Hatası C3071
ms.date: 11/04/2016
f1_keywords:
- C3071
helpviewer_keywords:
- C3071
ms.assetid: 69879e66-a60e-4058-9bbd-d5c5e2d8ee37
ms.openlocfilehash: 1debe431711681a98b9472c85864d84373ec42d6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406645"
---
# <a name="compiler-error-c3071"></a>Derleyici Hatası C3071

' operator 'işleci yalnızca bir başvuru sınıfının veya değer türü örneğine uygulanabilir

Yerel bir tür bir CLR işleci kullanılamaz. İşleci bir başvuru sınıfının veya bir başvuru yapısı (bir değer türü) ancak değil yerel bir tür int veya diğer ad gibi System::Int32 gibi yerel bir tür için kullanılabilir. Bu tür yerel değişkene, bu nedenle işleci kullanılamaz başvuran bir şekilde C++ kodundan Kutulu olamaz.

Daha fazla bilgi için [Tracking Reference Operator](../../extensions/tracking-reference-operator-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3071 oluşturur.

```
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