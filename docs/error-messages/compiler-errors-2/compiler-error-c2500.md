---
title: Derleyici Hatası C2500
ms.date: 11/04/2016
f1_keywords:
- C2500
helpviewer_keywords:
- C2500
ms.assetid: 6bff8161-dc9a-48ca-91f1-fd2eefdbbc93
ms.openlocfilehash: a5753fc99efcdb1064a21981c62faaba84d44189
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50468373"
---
# <a name="compiler-error-c2500"></a>Derleyici Hatası C2500

'ıdentifier1': 'identifier2' olduğunu zaten bir doğrudan taban sınıfı

Bir sınıf veya yapı birden çok kez temel sınıflar listesinde görünür.

Bir doğrudan temel temel listesinde belirtilen biridir. Dolaylı bir temel listesinde sınıflarından birinin temel sınıftır.

Bir sınıf doğrudan temel sınıf olarak birden fazla kez belirtilemez. Bir sınıf kereden fazla dolaylı temel sınıf olarak kullanılabilir.

Aşağıdaki örnek, C2500 oluşturur:

```
// C2500.cpp
// compile with: /c
class A {};
class B : public A, public A {};    // C2500

// OK
class C : public A {};
class D : public A {};
class E : public C, public D {};
```