---
title: Derleyici Uyarısı (Düzey 3) C4102 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4102
dev_langs:
- C++
helpviewer_keywords:
- C4102
ms.assetid: 349f308a-daf3-48c6-bd53-6c38b73f8880
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 451fb810da68eb6915203cf087e75371837d16ef
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46082657"
---
# <a name="compiler-warning-level-3-c4102"></a>Derleyici Uyarısı (Düzey 3) C4102

'etiketi': Etiket başvurusu kaldırıldı

Etiket tanımlandı ancak nikdy neodkazovalo. Derleyici, etiket yok sayar.

Aşağıdaki örnek, C4102 oluşturur:

```
// C4102.cpp
// compile with: /W3
int main() {
   int a;

   test:   // C4102, remove the unreferenced label to resolve

   a = 1;
}
```