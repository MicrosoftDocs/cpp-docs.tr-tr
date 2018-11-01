---
title: Derleyici Uyarısı (düzey 4) C4434
ms.date: 11/04/2016
f1_keywords:
- C4434
helpviewer_keywords:
- C4434
ms.assetid: 24b8785e-353a-4c37-8bed-ed61001a871d
ms.openlocfilehash: 6a7d760a7d192c7e0a7bd5e16f77efe1a4099c31
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50591271"
---
# <a name="compiler-warning-level-4-c4434"></a>Derleyici Uyarısı (düzey 4) C4434

bir sınıf oluşturucusu özel erişilebilirliği olmalıdır; özel erişim olarak değiştiriliyor

C4434, derleyici bir statik Oluşturucu erişilebilirliğini değiştiğini gösterir. Bunlar yalnızca ortak dil çalışma zamanı tarafından çağrılacak yöneliktir gibi statik oluşturucular özel erişilebilirliği olmalıdır. Daha fazla bilgi için [statik oluşturucular](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Static_constructors).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4434 oluşturur.

```
// C4434.cpp
// compile with: /W4 /c /clr
public ref struct R {
   static R(){}   // C4434
};
```