---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2749'
title: Derleyici hatası C2749
ms.date: 11/04/2016
f1_keywords:
- C2749
helpviewer_keywords:
- C2749
ms.assetid: a81aef36-cdca-4d78-89d5-b72eff2500b2
ms.openlocfilehash: 582bc035411c8ee77684f89ca841260a4391340a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97122895"
---
# <a name="compiler-error-c2749"></a>Derleyici hatası C2749

' Type ': yalnızca/clr: Safe ile yönetilen bir sınıfa tanıtıcı throw veya catch yapılabilir

**/Clr: Safe** kullanılırken yalnızca bir başvuru türü oluşturabilir veya yakalayabilirsiniz.

Daha fazla bilgi için bkz. [/clr (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C2749 oluşturur:

```cpp
// C2749.cpp
// compile with: /clr:safe
ref struct MyStruct {
public:
   int i;
};

int main() {
   MyStruct ^x = gcnew MyStruct;

   // Delete the following 4 lines to resolve.
   try {
      throw (1);   // C2749
   }
   catch(int){}

   // OK
   try {
      throw (x);
   }
   catch(MyStruct ^){}
}
```
