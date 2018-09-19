---
title: Derleyici Hatası C2107 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2107
dev_langs:
- C++
helpviewer_keywords:
- C2107
ms.assetid: 2866a121-884e-4bb5-8613-36de5817000e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: df81df38758cfdd9b3f62d9e0d241f0bf8578746
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46097919"
---
# <a name="compiler-error-c2107"></a>Derleyici Hatası C2107

Geçersiz dizin, yöneltmeye izin verilmiyor

Bir alt simge işaretçisi değerlendirmez ifade uygulanır.

## <a name="example"></a>Örnek

Yanlış kullanırsanız C2107 oluşabilir `this` türün varsayılan dizin oluşturucu erişmek için bir değer türünün işaretçisi. Daha fazla bilgi için [semantiği Bu işaretçi](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Semantics_of_the_this_pointer).

Aşağıdaki örnek, C2107 oluşturur.

```
// C2107.cpp
// compile with: /clr
using namespace System;

value struct B {
   property String ^ default[String ^] {
      String ^ get(String ^ data) {
         return "abc";
      }
   }
   void Test() {
      Console::WriteLine("{0}", this["aa"]);   // C2107
      Console::WriteLine("{0}", this->default["aa"]);   // OK
   }
};

int main() {
   B ^ myb = gcnew B();
   myb->Test();
}
```