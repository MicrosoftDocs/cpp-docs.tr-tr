---
title: Derleyici Hatası C2386 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2386
dev_langs:
- C++
helpviewer_keywords:
- C2386
ms.assetid: aaaa1284-34a0-4da2-8547-9fcbb559dae0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c799ec18eb062bbefcc91a8b1ef8364d9b2cdc03
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46043683"
---
# <a name="compiler-error-c2386"></a>Derleyici Hatası C2386

'symbol': Bu ada sahip bir simge geçerli kapsamda zaten var.

Ad alanı diğer adı oluşturmak denedik ancak önceden seçtiğiniz adı yok.

Aşağıdaki örnek, C2386 oluşturur:

```
// C2386.cpp
namespace A {
   int k;
}

int i;
namespace i = A;   // C2386, i already exists
```