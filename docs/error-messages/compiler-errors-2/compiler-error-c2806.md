---
title: Derleyici hatası C2806
ms.date: 11/04/2016
f1_keywords:
- C2806
helpviewer_keywords:
- C2806
ms.assetid: 7c9ff1f4-1590-4c47-991d-b1075a173b48
ms.openlocfilehash: be991d26cb822221051316f3557b23a2b82e732d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760627"
---
# <a name="compiler-error-c2806"></a>Derleyici hatası C2806

' işleç işleci ' çok fazla biçimsel parametreye sahip

Aşırı yüklenmiş bir işlecin çok fazla parametresi vardır.

Aşağıdaki örnek C2806 oluşturur:

```cpp
// C2806.cpp
// compile with: /c
class X {
public:
   X operator++ ( int, int );   // C2806 more than 1 parameter
   X operator++ ( int );   // OK
} ;
```
