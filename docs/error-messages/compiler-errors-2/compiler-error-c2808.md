---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2808'
title: Derleyici hatası C2808
ms.date: 11/04/2016
f1_keywords:
- C2808
helpviewer_keywords:
- C2808
ms.assetid: 3d745102-d3b3-4735-a7d2-ad42d5bf3cfa
ms.openlocfilehash: bdc47ff480afa77c22784536c1ed6337358e3d87
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320580"
---
# <a name="compiler-error-c2808"></a>Derleyici hatası C2808

Birli ' işleç işleci ' çok fazla biçimsel parametreye sahip

Birli işlecin void olmayan bir parametre listesi vardır.

Aşağıdaki örnek C2808 oluşturur:

```cpp
// C2808.cpp
// compile with: /c
class X {
public:
   X operator! ( X );   // C2808 nonvoid parameter list
   X operator! ( void );   // OK
};
```
