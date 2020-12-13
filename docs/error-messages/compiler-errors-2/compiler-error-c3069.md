---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3069'
title: Derleyici hatası C3069
ms.date: 11/04/2016
f1_keywords:
- C3069
helpviewer_keywords:
- C3069
ms.assetid: ca94291b-2bb4-4e3f-9acf-534234b83513
ms.openlocfilehash: cc56ded4f14e137b9f5bf28681fb319a650f363a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341145"
---
# <a name="compiler-error-c3069"></a>Derleyici hatası C3069

' operator ': numaralandırma türü için kullanılamaz

CLR Numaralandırmalar için bir işleç desteklenmez.  Daha fazla bilgi için bkz. [nasıl yapılır: C++/CLI üzerinde numaralandırmaları tanımlama ve kullanma](../../dotnet/how-to-define-and-consume-enums-in-cpp-cli.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3069 oluşturur:

```cpp
// C3069.cpp
// compile with: /clr
enum struct E { e1 };
enum F { f1 };

int main() {
   E e = E::e1;
   bool tf;
   tf = !e;   // C3069

   // supported for native enums
   F f = f1;
   tf = !f;
}
```
