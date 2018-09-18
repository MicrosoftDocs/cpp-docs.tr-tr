---
title: Derleyici Hatası C2474 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2474
dev_langs:
- C++
helpviewer_keywords:
- C2474
ms.assetid: 64e6c61e-6e77-480e-bcf0-b30a2fc482ac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bd33c74a0f5fe179b0dfdd5754d15f24bf0026ff
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46092576"
---
# <a name="compiler-error-c2474"></a>Derleyici Hatası C2474

'anahtar sözcüğü': bir hemen yanında noktalı virgül eksik olabilir anahtar sözcük ya da tanımlayıcı.

Derleyici, noktalı virgül bekleniyordu ve amacınızla belirleyemedi. Bu hatayı gidermek için noktalı virgül ekleyin.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2474 oluşturur.

```
// C2474.cpp
// compile with: /clr /c

ref class A {
   ref class B {}
   property int i;   // C2474 error
};

// OK
ref class B {
   ref class D {};
   property int i;
};

ref class E {
   ref class F {} property;
   int i;
};
```