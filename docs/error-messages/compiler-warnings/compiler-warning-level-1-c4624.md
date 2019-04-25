---
title: Derleyici Uyarısı (düzey 1) C4624
ms.date: 11/04/2016
f1_keywords:
- C4624
helpviewer_keywords:
- C4624
ms.assetid: 14f61769-d92e-482b-9515-debd87b30a66
ms.openlocfilehash: b1a7d715057f4c6d8ada104ad07f6ad0b9c52fb2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62221399"
---
# <a name="compiler-warning-level-1-c4624"></a>Derleyici Uyarısı (düzey 1) C4624

'derived class': yıkıcı örtük bir şekilde bir temel sınıf yok edicisini erişilemez veya silinmiş olduğundan silindi olarak tanımlandı

Bir yok edici erişilebilir veya silinmiş bir temel sınıfta değil ve bir türetilmiş sınıf için oluşturulmadı. Yığında bu türde bir nesne oluşturmak için her türlü girişim, bir derleyici hatasına neden olur.

Aşağıdaki örnek, C4624 oluşturur ve bu sorunun nasıl gösterir:

```
// C4624.cpp
// compile with: /W1 /c
class B {
// Uncomment the following line to fix.
// public:
   ~B();
};

class D : public B {};   // C4624 B's destructor not public
```