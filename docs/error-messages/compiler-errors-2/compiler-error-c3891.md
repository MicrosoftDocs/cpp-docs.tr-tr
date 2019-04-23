---
title: Derleyici Hatası C3891
ms.date: 11/04/2016
f1_keywords:
- C3891
helpviewer_keywords:
- C3891
ms.assetid: 6e1a9458-97f5-4580-bc0f-aa97a1bfd20d
ms.openlocfilehash: 74b8802a165ab3265cc0f1c6a0b33b31d3db401d
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59779173"
---
# <a name="compiler-error-c3891"></a>Derleyici Hatası C3891

'var': sabit değerli veri üyesi lvalue kullanılamaz

A [değişmez değer](../../extensions/literal-cpp-component-extensions.md) değişkendir const ve değeri bildiriminde başlatıldıktan sonra değiştirilemez.

Aşağıdaki örnek, C3891 oluşturur:

```
// C3891.cpp
// compile with: /clr
ref struct Y1 {
   literal int staticConst = 9;
};

int main() {
   Y1::staticConst = 0;   // C3891
}
```