---
title: Derleyici Hatası C2633
ms.date: 11/04/2016
f1_keywords:
- C2633
helpviewer_keywords:
- C2633
ms.assetid: a7aceb65-4255-42d6-a8fb-e3cb6c4d2270
ms.openlocfilehash: 746f01706c7c0ec09a64c5faee748f9582ac9a14
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50662572"
---
# <a name="compiler-error-c2633"></a>Derleyici Hatası C2633

'identifier': 'inline' oluşturucular için tek geçerli depolama sınıfıdır

Bir oluşturucu, satır içi dışındaki bir depolama sınıfı olarak bildirilir.

Aşağıdaki örnek, C2633 oluşturur:

```
// C2633.cpp
// compile with: /c
class C {
   extern C();   // C2633, not inline
   inline C();   // OK
};
```