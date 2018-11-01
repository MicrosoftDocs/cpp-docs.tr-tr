---
title: Derleyici Hatası C2007
ms.date: 11/04/2016
f1_keywords:
- C2007
helpviewer_keywords:
- C2007
ms.assetid: ecd09d99-5036-408b-9e46-bc15488f049e
ms.openlocfilehash: f3c7b1a18dda9b2f9af7e346c2a1ed2f0303bb61
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50434690"
---
# <a name="compiler-error-c2007"></a>Derleyici Hatası C2007

\#söz dizimi tanımlayın

Hiçbir tanımlayıcı sonra görünen bir `#define`. Hatayı gidermek için bir tanımlayıcı kullanın.

Aşağıdaki örnek, C2007 oluşturur:

```
// C2007.cpp
#define   // C2007
```

Olası çözüm:

```
// C2007b.cpp
// compile with: /c
#define true 1
```