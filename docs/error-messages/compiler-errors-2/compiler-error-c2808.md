---
title: Derleyici Hatası C2808
ms.date: 11/04/2016
f1_keywords:
- C2808
helpviewer_keywords:
- C2808
ms.assetid: 3d745102-d3b3-4735-a7d2-ad42d5bf3cfa
ms.openlocfilehash: 7b40a81748748a7566a8c1e6add84121f8925895
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50572025"
---
# <a name="compiler-error-c2808"></a>Derleyici Hatası C2808

birli 'operator işleci' çok fazla sayıda biçimsel parametre içeriyor

Birli işleç nonvoid parametre listesi vardır.

Aşağıdaki örnek, C2808 oluşturur:

```
// C2808.cpp
// compile with: /c
class X {
public:
   X operator! ( X );   // C2808 nonvoid parameter list
   X operator! ( void );   // OK
};

```