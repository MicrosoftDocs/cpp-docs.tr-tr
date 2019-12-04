---
title: Derleyici hatası C3891
ms.date: 11/04/2016
f1_keywords:
- C3891
helpviewer_keywords:
- C3891
ms.assetid: 6e1a9458-97f5-4580-bc0f-aa97a1bfd20d
ms.openlocfilehash: 4b5ef8b837033a149455c040f748f479aa3f424d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74736405"
---
# <a name="compiler-error-c3891"></a>Derleyici hatası C3891

' var ': sabit değerli bir veri üyesi bir l-değeri olarak kullanılamaz

[Sabit](../../extensions/literal-cpp-component-extensions.md) bir değişken const ve değeri bildirimde başlatıldıktan sonra değiştirilemez.

Aşağıdaki örnek C3891 oluşturur:

```cpp
// C3891.cpp
// compile with: /clr
ref struct Y1 {
   literal int staticConst = 9;
};

int main() {
   Y1::staticConst = 0;   // C3891
}
```
