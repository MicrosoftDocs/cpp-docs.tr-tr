---
title: Derleyici Hatası C2571 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2571
dev_langs:
- C++
helpviewer_keywords:
- C2571
ms.assetid: c6522616-dee9-4d7d-9bf8-30a7e1deaadf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 30cc078251d0511da77e08690db275a788973ffb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46067941"
---
# <a name="compiler-error-c2571"></a>Derleyici Hatası C2571

'function': sanal işlevi, 'union' birleşimi içinde yer alamaz

UNION, bir sanal işlev ile bildirilir. Bir sınıf veya yapı içinde yalnızca bir sanal işlev bildirebilirsiniz.  Olası çözümler:

1. Bir sınıf veya yapı, birleşim değiştirin.

1. Sanal olmayan işlev olun.

Aşağıdaki örnek, C2571 oluşturur:

```
// C2571.cpp
// compile with: /c
union A {
   virtual void func1();   // C2571
   void func2();   // OK
};
```