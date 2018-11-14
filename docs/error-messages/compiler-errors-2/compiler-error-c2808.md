---
title: Derleyici Hatası C2808
ms.date: 11/04/2016
f1_keywords:
- C2808
helpviewer_keywords:
- C2808
ms.assetid: 3d745102-d3b3-4735-a7d2-ad42d5bf3cfa
ms.openlocfilehash: 84135288255c806e644e153a4d8f678fc13d2787
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51522148"
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