---
title: Derleyici Hatası C3288
ms.date: 11/04/2016
f1_keywords:
- C3288
helpviewer_keywords:
- C3288
ms.assetid: ed08a540-9751-46e1-9cbe-c51d6a49ffab
ms.openlocfilehash: d076dabe0df91cefb90be5ec9e90f371331a51f1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62300632"
---
# <a name="compiler-error-c3288"></a>Derleyici Hatası C3288

'type': geçersiz başvuru bir tanıtıcı türü

Derleyici, bir tanıtıcı türü geçersiz bir başvuru algılandı. Tanıtıcı türüne başvuru ve başvuru atayın. Daha fazla bilgi için [Tracking Reference Operator](../../extensions/tracking-reference-operator-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3288 oluşturur.

```
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