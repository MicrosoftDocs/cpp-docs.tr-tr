---
title: Derleyici hatası C3288
ms.date: 11/04/2016
f1_keywords:
- C3288
helpviewer_keywords:
- C3288
ms.assetid: ed08a540-9751-46e1-9cbe-c51d6a49ffab
ms.openlocfilehash: a7b87fdbd2e15906ebc0c669f0b9a74ebf97f0b3
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760185"
---
# <a name="compiler-error-c3288"></a>Derleyici hatası C3288

' Type ': tanıtıcı türünün geçersiz başvurusu

Derleyici bir tanıtıcı türü için geçersiz bir başvuru algıladı. Bir tanıtıcı türüne başvurabilir ve bir başvuruya atayabilirsiniz. Daha fazla bilgi için bkz. [Izleme başvurusu işleci](../../extensions/tracking-reference-operator-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3288 oluşturur.

```cpp
// C3288.cpp
// compile with: /clr
ref class R {};
int main() {
   *(System::Object^) nullptr;   // C3288

// OK
   (System::Object^) nullptr;   // OK
   R^ r;
   R% pr = *r;
}
```
