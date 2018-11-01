---
title: Derleyici Hatası C2991
ms.date: 11/04/2016
f1_keywords:
- C2991
helpviewer_keywords:
- C2991
ms.assetid: a87e4404-26e8-4927-b3ee-5d02b3b8bee1
ms.openlocfilehash: bb7d709f757b6da10c8b17d5b30e2c2b86edd85e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50646179"
---
# <a name="compiler-error-c2991"></a>Derleyici Hatası C2991

'parameter' tür parametresinin yeniden tanımlanması

İki genel veya şablon tanımları arasında türü çakışma oluştu `parameter`. Birden çok genel veya şablon parametreleri tanımlanırken, eşdeğer türlerle kullanmanız gerekir.

Aşağıdaki örnek, C2991 oluşturur:

```
// C2991.cpp
// compile with: /c
template<class T, class T> struct TC {};   // C2991
// try the following line instead
// template<class T, class T2> struct TC {};
```

C2991, genel türler kullanırken da meydana gelebilir:

```
// C2991b.cpp
// compile with: /clr /c
generic<class T,class T> ref struct GC {};   // C2991
// try the following line instead
// generic<class T,class T2> ref struct GC {};
```