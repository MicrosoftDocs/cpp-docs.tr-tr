---
title: Derleyici Hatası C2633 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2633
dev_langs:
- C++
helpviewer_keywords:
- C2633
ms.assetid: a7aceb65-4255-42d6-a8fb-e3cb6c4d2270
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2750cad468158ec5f8eddc967392ea68c1029119
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46108572"
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