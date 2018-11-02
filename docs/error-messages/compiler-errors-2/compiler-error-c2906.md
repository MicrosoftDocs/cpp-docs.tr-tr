---
title: Derleyici Hatası C2906
ms.date: 11/04/2016
f1_keywords:
- C2906
helpviewer_keywords:
- C2906
ms.assetid: 30f652f1-6af6-4a2f-a69e-a1a4876cc8c6
ms.openlocfilehash: 621b31cf362c1dcc740390cf9e405b7da3f05da8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50587778"
---
# <a name="compiler-error-c2906"></a>Derleyici Hatası C2906

'özelleştirmesi': açık özelleştirme 'şablon <>' gerektirir

Şablonlarının açık alt uzmanlaşması için yeni sözdizimini kullanmanız gerekir.

Aşağıdaki örnek, C2906 oluşturur:

```
// C2906.cpp
// compile with: /c
template<class T> class X{};   // primary template
class X<int> { }   // C2906
template<> class X<int> { };   // new syntax
```