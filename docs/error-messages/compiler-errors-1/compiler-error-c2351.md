---
title: Derleyici Hatası C2351
ms.date: 11/04/2016
f1_keywords:
- C2351
helpviewer_keywords:
- C2351
ms.assetid: 5439ccf6-66f6-4859-964c-c73f5eddfc1b
ms.openlocfilehash: 2d93902ee0008a54da1b2ecf165e0a829362511f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50665497"
---
# <a name="compiler-error-c2351"></a>Derleyici Hatası C2351

artık kullanılmayan C++ oluşturucusu başlatma sözdizimi

Bir oluşturucu için bir stil yeni başlatma listede yalnızca temel sınıf olsa bile her doğrudan temel sınıfı açıkça adlandırmalısınız.

Aşağıdaki örnek, C2351 oluşturur:

```
// C2351.cpp
// compile with: /c
class B {
public:
   B() : () {}   // C2351
   B() {}   // OK
};
```