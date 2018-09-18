---
title: Derleyici Hatası C2652 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2652
dev_langs:
- C++
helpviewer_keywords:
- C2652
ms.assetid: 6e3d1a90-a989-4088-8afd-dc82f6a2d66f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 37b7b259b8eb42692641883c8d69578542cce06e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46076625"
---
# <a name="compiler-error-c2652"></a>Derleyici Hatası C2652

'identifier': Geçersiz kopya Oluşturucusu: ilk parametre bir 'identifier' olmalıdır

Kopya Oluşturucu ilk parametre bir sınıf, yapı veya birleşim kendisi için tanımlanan aynı türde sahiptir. İlk parametre türü ancak türün kendisine bir başvuru olabilir.

Aşağıdaki örnek, C2651 oluşturur:

```
// C2652.cpp
// compile with: /c
class A {
   A( A );   // C2652 takes an A
};
class B {
   B( B& );   // OK, reference to B
};
```