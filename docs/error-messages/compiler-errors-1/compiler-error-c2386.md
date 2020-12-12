---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2386'
title: Derleyici hatası C2386
ms.date: 11/04/2016
f1_keywords:
- C2386
helpviewer_keywords:
- C2386
ms.assetid: aaaa1284-34a0-4da2-8547-9fcbb559dae0
ms.openlocfilehash: 65dca1cf052cab1292f6f594a316536a5097a032
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204101"
---
# <a name="compiler-error-c2386"></a>Derleyici hatası C2386

' symbol ': geçerli kapsamda bu ada sahip bir simge zaten var

Bir ad alanı diğer adı oluşturmaya çalıştınız, ancak seçtiğiniz ad zaten var.

Aşağıdaki örnek C2386 oluşturur:

```cpp
// C2386.cpp
namespace A {
   int k;
}

int i;
namespace i = A;   // C2386, i already exists
```
