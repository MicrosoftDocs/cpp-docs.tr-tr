---
title: Derleyici hatası C3069
ms.date: 11/04/2016
f1_keywords:
- C3069
helpviewer_keywords:
- C3069
ms.assetid: ca94291b-2bb4-4e3f-9acf-534234b83513
ms.openlocfilehash: 230d2569ea314bde2ea9ef0c4fc58d1a9743807f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74749522"
---
# <a name="compiler-error-c3069"></a>Derleyici hatası C3069

' operator ': numaralandırma türü için kullanılamaz

CLR Numaralandırmalar için bir işleç desteklenmez.  Daha fazla bilgi için bkz. [nasıl yapılır:/CLI içinde C++numaralandırmalar tanımlama ve kullanma](../../dotnet/how-to-define-and-consume-enums-in-cpp-cli.md).

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
