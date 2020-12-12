---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3891'
title: Derleyici hatası C3891
ms.date: 11/04/2016
f1_keywords:
- C3891
helpviewer_keywords:
- C3891
ms.assetid: 6e1a9458-97f5-4580-bc0f-aa97a1bfd20d
ms.openlocfilehash: df853f3ed0a163b48e75d54561d00298edd215b3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144306"
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
