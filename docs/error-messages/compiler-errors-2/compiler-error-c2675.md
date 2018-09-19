---
title: Derleyici Hatası C2675 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2675
dev_langs:
- C++
helpviewer_keywords:
- C2675
ms.assetid: 4b92a12b-bff8-4dd5-a109-620065fc146c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1772f6e88516e7c8c1498f84d180ab6c4e0e05ab
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46102415"
---
# <a name="compiler-error-c2675"></a>Derleyici Hatası C2675

birli 'operator': 'type' bu işleci veya tanımlamıyor kabul edilebilir bir türe dönüştürme için önceden tanımlanmış işleç

C2675 birli işleç kullanılarak zaman da meydana gelebilir ve türü önceden tanımlanmış işleç için operatör ya da kabul edilebilir bir türe dönüştürmeyi tanımlamıyor. İşlecini kullanmak için belirtilen tür için aşırı veya tanımlar işlecin tanımlandığı bir türe dönüştürmeyi gerekir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2675 oluşturur.

```
// C2675.cpp
struct C {
   C(){}
} c;

struct D {
   D(){}
   void operator-(){}
} d;

int main() {
   -c;   // C2675
   -d;   // OK
}
```