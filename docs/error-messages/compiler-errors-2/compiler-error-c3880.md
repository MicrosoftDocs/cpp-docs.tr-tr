---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3880'
title: Derleyici hatası C3880
ms.date: 11/04/2016
f1_keywords:
- C3880
helpviewer_keywords:
- C3880
ms.assetid: b0e05d1e-32d0-4034-9246-f37d23573ea9
ms.openlocfilehash: c2d279cd50716f647fbbdf51f9f9c39863d4e2d2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97274599"
---
# <a name="compiler-error-c3880"></a>Derleyici hatası C3880

' var ': sabit değerli bir veri üyesi olamaz

[Sabit](../../extensions/literal-cpp-component-extensions.md) bir özniteliğin türü, aşağıdaki türlerden biri olan veya için derleme zamanı dönüştürülebilir olmalıdır:

- integral türü

- string

- integral veya temel alınan türden sabit listesi

Aşağıdaki örnek C3880 oluşturur:

```cpp
// C3880.cpp
// compile with: /clr /c
ref struct Y1 {
   literal System::Decimal staticConst1 = 10;   // C3880
   literal int staticConst2 = 10;   // OK
};
```
