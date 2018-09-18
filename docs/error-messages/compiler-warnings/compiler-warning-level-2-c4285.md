---
title: Derleyici Uyarısı (Düzey 2) C4285 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4285
dev_langs:
- C++
helpviewer_keywords:
- C4285
ms.assetid: fa14de1f-fc19-4eec-8bea-81003636e12f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 27ad828e25f647bddcc8a9ebe9662e2ba61f48d6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46040706"
---
# <a name="compiler-warning-level-2-c4285"></a>Derleyici Uyarısı (Düzey 2) C4285

'-> identifier::operator için' dönüş türü içtakı gösterimi kullanılırsa özyinelemelidir

Belirtilen **-> () işleci** işlev dönüş türü olamaz, tanımlanan veya kendisi için tanımlanmış olduğu tür başvurusu.

Aşağıdaki örnek, C4285 oluşturur:

```
// C4285.cpp
// compile with: /W2
class C
{
public:
    C operator->();   // C4285
   // C& operator->();  C4285, also
};

int main()
{
}
```