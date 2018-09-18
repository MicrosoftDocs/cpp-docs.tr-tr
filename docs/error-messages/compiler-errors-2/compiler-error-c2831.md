---
title: Derleyici Hatası C2831 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2831
dev_langs:
- C++
helpviewer_keywords:
- C2831
ms.assetid: c8c04288-0889-4265-a077-17f94cbcdcc9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a534fd379e8ec250f185370d7388171dc9ef3508
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46047596"
---
# <a name="compiler-error-c2831"></a>Derleyici Hatası C2831

'operator işleci' varsayılan parametrelere sahip olamaz

Varsayılan parametreleri yalnızca üç işleçleri olabilir:

- [new](../../cpp/new-operator-cpp.md)

- Atama =

- Sol parantez)

Aşağıdaki örnek, C2831 oluşturur:

```
// C2831.cpp
// compile with: /c
#define BINOP <=
class A {
public:
   int i;
   int operator BINOP(int x = 1) {   // C2831
   // try the following line instead
   // int operator BINOP(int x) {
      return i+x;
   }
};
```