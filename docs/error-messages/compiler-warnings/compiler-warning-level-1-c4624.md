---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4624'
title: Derleyici Uyarısı (düzey 1) C4624
ms.date: 11/04/2016
f1_keywords:
- C4624
helpviewer_keywords:
- C4624
ms.assetid: 14f61769-d92e-482b-9515-debd87b30a66
ms.openlocfilehash: d5869742b548c4a54efe08e686571123fc570517
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281463"
---
# <a name="compiler-warning-level-1-c4624"></a>Derleyici Uyarısı (düzey 1) C4624

' derived class ': bir taban sınıf yıkıcısı erişilemediğinden veya silindiğinden yıkıcı örtük olarak silindi olarak tanımlandı

Bir yıkıcı bir temel sınıfta erişilebilir veya silinmemiş ve bu nedenle türetilmiş bir sınıf için üretilmedi. Yığında bu türde bir nesne oluşturma girişimi bir derleyici hatasına neden olur.

Aşağıdaki örnek C4624 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C4624.cpp
// compile with: /W1 /c
class B {
// Uncomment the following line to fix.
// public:
   ~B();
};

class D : public B {};   // C4624 B's destructor not public
```
