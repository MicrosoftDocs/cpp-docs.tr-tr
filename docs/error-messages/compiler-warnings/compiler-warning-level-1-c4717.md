---
title: Derleyici Uyarısı (düzey 1) C4717
ms.date: 11/04/2016
f1_keywords:
- C4717
helpviewer_keywords:
- C4717
ms.assetid: 5ef3c6c7-8599-4714-a973-0f5b69cdab3c
ms.openlocfilehash: 40897e54601793431671bc14f855db43e905c656
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175294"
---
# <a name="compiler-warning-level-1-c4717"></a>Derleyici Uyarısı (düzey 1) C4717

' function ': tüm denetim yollarında özyinelemeli, işlev çalışma zamanı yığını taşmasına neden olacak

Bir işlev aracılığıyla her yol, işleve bir çağrı içerir. İşlevin kendisini yinelemeli olarak çağırmadan çıkmaması mümkün olmadığından, işlev hiçbir şekilde çıkmayacaktır.

Aşağıdaki örnek C4717 oluşturur:

```cpp
// C4717.cpp
// compile with: /W1 /c
// C4717 expected
int func(int x) {
   if (x > 1)
      return func(x - 1); // recursive call
   else {
      int y = func(0) + 1; // recursive call
      return y;
   }
}

int main(){
   func(1);
}
```
