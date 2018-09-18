---
title: Derleyici Hatası C2473 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2473
dev_langs:
- C++
helpviewer_keywords:
- C2473
ms.assetid: 6bb7dbf5-b198-490f-860e-fd64d0c2a284
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0eeecedd3ad2cee551b6003912d9b7af32883588
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46026081"
---
# <a name="compiler-error-c2473"></a>Derleyici Hatası C2473

'identifier': işlev tanımı gibi görünüyor, ancak hiçbir parametre listesi yoktur.

Derleyici, parametre listesi olmayan bir işlev göründüğüne algıladı.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2473 oluşturur.

```
// C2473.cpp
// compile with: /clr /c
class A {
   int i {}   // C2473
};

class B {
   int i() {}   // OK
};
```