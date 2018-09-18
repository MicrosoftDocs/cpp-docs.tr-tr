---
title: Derleyici Hatası C2884 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2884
dev_langs:
- C++
helpviewer_keywords:
- C2884
ms.assetid: 8b4d43e3-3fb5-4360-86c8-de59d8736d4f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9d9266162d4608e39982cce1e94751e427bc5e47
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054720"
---
# <a name="compiler-error-c2884"></a>Derleyici Hatası C2884

'name': yerel'function 'işlevini kullanarak bildirimiyle çakışıyor tarafından tanıtılan

Birden çok kez bir fonksiyon tanımlayın denedi. Yerel bir tanımını ilk tanımıdır. Bir ad ile ikincisi ise bir `using` bildirimi.

Aşağıdaki örnek, C2884 oluşturur:

```
// C2884.cpp
namespace A {
   void z(int);
}

void f() {
   void z(int);
   using A::z;   // C2884 z is already defined
}
```