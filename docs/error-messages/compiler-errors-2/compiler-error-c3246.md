---
title: Derleyici Hatası C3246
ms.date: 11/04/2016
f1_keywords:
- C3246
helpviewer_keywords:
- C3246
ms.assetid: ad85224a-e540-479b-a5eb-a3bc3964c30b
ms.openlocfilehash: 9e24fc28f84bfacb7478d700047c4eb1363247de
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50451278"
---
# <a name="compiler-error-c3246"></a>Derleyici Hatası C3246

'class': 'türünden' olarak bildirilmiş olsa devralınamıyor çünkü 'sealed' olarak

Olarak işaretlenmiş bir sınıf [korumalı](../../windows/sealed-cpp-component-extensions.md) herhangi diğer sınıflar için taban sınıf olamaz.

Aşağıdaki örnek, C3246 oluşturur:

```
// C3246_2.cpp
// compile with: /clr /LD
ref class X sealed {};

ref class Y : public X {}; // C3246
```
