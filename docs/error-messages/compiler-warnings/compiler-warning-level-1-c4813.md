---
title: Derleyici Uyarısı (düzey 1) C4813
ms.date: 11/04/2016
f1_keywords:
- C4813
helpviewer_keywords:
- C4813
ms.assetid: c30bf877-ab04-4fe4-897e-8162092426f0
ms.openlocfilehash: c6aaf3cc8e17cd1be1d9c964c03bb18b3bb0ff77
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410335"
---
# <a name="compiler-warning-level-1-c4813"></a>Derleyici Uyarısı (düzey 1) C4813

'function': bir arkadaş işlev yerel bir sınıfın önceden bildirilmiş olmalıdır

Bir iç sınıf, bir arkadaş işlev dış sınıfında bildirilmedi.

Aşağıdaki örnek, C4813 oluşturur:

```
// C4813.cpp
// compile with: /W1 /LD
void MyClass()
{
   // void func();
   class InnerClass
   {
      friend void func();   // C4813 uncomment declaration above
   };
}
```