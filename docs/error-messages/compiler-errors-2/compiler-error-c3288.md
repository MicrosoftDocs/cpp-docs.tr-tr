---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3288'
title: Derleyici hatası C3288
ms.date: 11/04/2016
f1_keywords:
- C3288
helpviewer_keywords:
- C3288
ms.assetid: ed08a540-9751-46e1-9cbe-c51d6a49ffab
ms.openlocfilehash: 6a9de812a981909c9de3a3bb895294ea9b6968d6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144826"
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
