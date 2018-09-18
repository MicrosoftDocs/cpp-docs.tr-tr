---
title: Derleyici Hatası C3891 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3891
dev_langs:
- C++
helpviewer_keywords:
- C3891
ms.assetid: 6e1a9458-97f5-4580-bc0f-aa97a1bfd20d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c85e5fa5ed5e6f202750fef05ffc96e9a0c86bc1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46051704"
---
# <a name="compiler-error-c3891"></a>Derleyici Hatası C3891

'var': sabit değerli veri üyesi lvalue kullanılamaz

A [değişmez değer](../../windows/literal-cpp-component-extensions.md) değişkendir const ve değeri bildiriminde başlatıldıktan sonra değiştirilemez.

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