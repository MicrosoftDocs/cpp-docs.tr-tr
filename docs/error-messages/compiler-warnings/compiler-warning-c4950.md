---
description: 'Hakkında daha fazla bilgi edinin: derleyici uyarısı C4950'
title: Derleyici Uyarısı C4950
ms.date: 11/04/2016
f1_keywords:
- C4950
helpviewer_keywords:
- C4950
ms.assetid: 50226a5c-c664-4d09-ac59-e9e874ca244f
ms.openlocfilehash: e1bb05501fcac6c836bfd4aa89f72807b625c292
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314886"
---
# <a name="compiler-warning-c4950"></a>Derleyici Uyarısı C4950

' type_or_member ': eski olarak işaretlendi

Bir üye veya tür, özniteliğiyle kullanılmıyor olarak işaretlendi <xref:System.ObsoleteAttribute> .

C4950 her zaman bir hata olarak verilir. [Uyarı](../../preprocessor/warning.md) pragma yönergesini veya [/WD](../../build/reference/compiler-option-warning-level.md) derleyici seçeneğini kullanarak bu uyarıyı kapatabilirsiniz.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4950 oluşturur:

```cpp
// C4950.cpp
// compile with: /clr
using namespace System;

// Any reference to Func3 should generate an error with message
[System::ObsoleteAttribute("Will be removed in next version", true)]
Int32 Func3(Int32 a, Int32 b) {
   return (a + b);
}

int main() {
   Int32 MyInt3 = ::Func3(2, 2);   // C4950
}
```
