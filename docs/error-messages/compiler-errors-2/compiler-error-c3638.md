---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3638'
title: Derleyici hatası C3638
ms.date: 11/04/2016
f1_keywords:
- C3638
helpviewer_keywords:
- C3638
ms.assetid: 8d8bc5ca-75aa-480e-b6b6-3178fab51b1d
ms.openlocfilehash: 1d1cc59cd8065a5b0e661292b717ba885c6febeb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239200"
---
# <a name="compiler-error-c3638"></a>Derleyici hatası C3638

' operator ': Standart kutulama ve kutudan çıkarma dönüştürme işleçleri yeniden tanımlanamaz

Derleyici örtük kutulamayı desteklemek için her yönetilen sınıf için bir dönüştürme işleci tanımlar. Bu işleç yeniden tanımlanamaz.

Daha fazla bilgi için bkz. [örtük paketleme](../../extensions/boxing-cpp-component-extensions.md).

Aşağıdaki örnek C3638 oluşturur:

```cpp
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
