---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2882'
title: Derleyici hatası C2882
ms.date: 11/04/2016
f1_keywords:
- C2882
helpviewer_keywords:
- C2882
ms.assetid: 617018ee-5a0d-4b8d-9612-77e8ae52679b
ms.openlocfilehash: b060fbc741bc768c2f27625c25345f5e8ed1a484
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332362"
---
# <a name="compiler-error-c2882"></a>Derleyici hatası C2882

' name ': ifadede geçersiz ad alanı tanımlayıcısının kullanımı

Bir ifadede bir ad alanının adını kullanmayı denediniz.

Aşağıdaki örnek C2882 oluşturur:

```cpp
// C2882.cpp
// compile with: /c
namespace A {
   int k;
}

int i = A;   // C2882, can't assign A to i
```
