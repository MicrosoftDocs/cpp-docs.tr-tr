---
title: Derleyici Hatası C3638
ms.date: 11/04/2016
f1_keywords:
- C3638
helpviewer_keywords:
- C3638
ms.assetid: 8d8bc5ca-75aa-480e-b6b6-3178fab51b1d
ms.openlocfilehash: 33bb248faf946c39543de4a14a44e2ebbda49880
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58775237"
---
# <a name="compiler-error-c3638"></a>Derleyici Hatası C3638

'operator': standart kutulama ve kutudan çıkarma dönüştürme işleçleri yeniden tanımlanamaz

Derleyici örtük olarak kutulama desteklemek için her bir yönetilen sınıf için dönüştürme işleci tanımlar. Bu işleci tanımlanamaz.

Daha fazla bilgi için [örtük kutulama](../../extensions/boxing-cpp-component-extensions.md).

Aşağıdaki örnek, C3638 oluşturur:

```
// C3638.cpp
// compile with: /clr
value struct V {
   V(){}
   static operator V^(V);   // C3638
};

int main() {
   V myV;
   V ^ pmyV = myV;   // operator supports implicit boxing
}
```