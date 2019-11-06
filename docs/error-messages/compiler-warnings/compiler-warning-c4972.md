---
title: Derleyici Uyarısı C4972
ms.date: 11/04/2016
f1_keywords:
- C4972
helpviewer_keywords:
- C4972
ms.assetid: d18e8e65-b2ef-4d75-a207-fbd0c17c9060
ms.openlocfilehash: 785d845c3dce556c4d3182ddec07a42a666154f0
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626333"
---
# <a name="compiler-warning-c4972"></a>Derleyici Uyarısı C4972

Bir unbox işleminin sonucunu doğrudan değiştirmek veya sonucu lvalue olarak davranmak doğrulanamaz

Bir tanıtıcının bir değer türü olarak, kutudan çıkarma olarak da bilinmesinin ve daha sonra atanması doğrulanabilir olmadığından, bu bir işleyicinin başvurusunu oluşturma.

Daha fazla bilgi için bkz. [paketleme](../../extensions/boxing-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C4972 oluşturur.

```cpp
// C4972.cpp
// compile with: /clr:safe
using namespace System;
ref struct R {
   int ^ p;   // a value type
};

int main() {
   R ^ r = gcnew R;
   *(r->p) = 10;   // C4972

   // OK
   r->p = 10;
   Console::WriteLine( r->p );
   Console::WriteLine( *(r->p) );
}
```