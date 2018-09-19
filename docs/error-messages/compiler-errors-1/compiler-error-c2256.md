---
title: Derleyici Hatası C2256 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2256
dev_langs:
- C++
helpviewer_keywords:
- C2256
ms.assetid: 171fa2bc-8c72-49cd-afe5-d723b7acd3c5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4d4b32021b5c0688cfe51601722006e9741bfa4c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46108345"
---
# <a name="compiler-error-c2256"></a>Derleyici Hatası C2256

'function' üzerinde friend belirticisinin geçersiz kullanımı

Bir yok Edicisi veya oluşturucusu olarak belirtilemez bir [arkadaş](../../cpp/friend-cpp.md).

Aşağıdaki örnek, C2256 oluşturur:

```
// C2256.cpp
// compile with: /c
class C {
public:
   friend ~C();   // C2256
   ~C();   // OK
};
```