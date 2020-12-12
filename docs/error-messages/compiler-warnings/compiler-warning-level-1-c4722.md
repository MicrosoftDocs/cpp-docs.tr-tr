---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4722'
title: Derleyici Uyarısı (düzey 1) C4722
ms.date: 11/04/2016
f1_keywords:
- C4722
helpviewer_keywords:
- C4722
ms.assetid: d8660710-f67b-4f59-a5fd-59259475529e
ms.openlocfilehash: b147eb63592235f4246c9826419aca77357df31a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328108"
---
# <a name="compiler-warning-level-1-c4722"></a>Derleyici Uyarısı (düzey 1) C4722

' function ': yıkıcı hiçbir şekilde döndürmez, olası bellek sızıntısı

Denetim akışı bir yıkıcıda sonlandırılır. İş parçacığı veya tüm program sonlandırılır ve ayrılan kaynaklar yayımlanmayabilir.  Ayrıca, özel durum işleme sırasında yığın geri sarma için bir yıkıcı çağrılacaktır, yürütülebilir dosyanın davranışı tanımsızdır.

Çözümlemek için, yok edicinin dönüşmesine neden olan işlev çağrısını kaldırın.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4722 oluşturur:

```cpp
// C4722.cpp
// compile with: /O1 /W1 /c
#include <stdlib.h>
class C {
public:
   C();
   ~C() { exit(1); };   // C4722
};

extern void func (C*);

void Test(){
   C x;
   func(&x);
   // control will not leave Test because destructor will exit
}
```
