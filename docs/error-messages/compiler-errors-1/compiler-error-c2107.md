---
title: Derleyici hatası C2107
ms.date: 11/04/2016
f1_keywords:
- C2107
helpviewer_keywords:
- C2107
ms.assetid: 2866a121-884e-4bb5-8613-36de5817000e
ms.openlocfilehash: 1be2ebb82aca481df9efbbc4ccdd54466ae60a3f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214795"
---
# <a name="compiler-error-c2107"></a>Derleyici hatası C2107

Geçersiz dizin, yöneltmeye izin verilmiyor

Bir simge, işaretçi sonucunu olmayan bir ifadeye uygulanır.

## <a name="example"></a>Örnek

**`this`** Türün varsayılan dizin oluşturucusuna erişmek için bir değer türünün işaretçisini yanlış kullanırsanız C2107 oluşabilir. Daha fazla bilgi için [Bu Işaretçinin semantiğini](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Semantics_of_the_this_pointer)inceleyin.

Aşağıdaki örnek C2107 oluşturur.

```cpp
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
