---
title: Derleyici Uyarısı (düzey 1) C4624
ms.date: 11/04/2016
f1_keywords:
- C4624
helpviewer_keywords:
- C4624
ms.assetid: 14f61769-d92e-482b-9515-debd87b30a66
ms.openlocfilehash: 8ef871f31d5d1d31e6d1d26d46b6f7f99c8fba86
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051444"
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