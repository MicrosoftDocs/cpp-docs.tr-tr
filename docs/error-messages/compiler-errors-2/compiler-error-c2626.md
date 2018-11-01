---
title: Derleyici Hatası C2626
ms.date: 11/04/2016
f1_keywords:
- C2626
helpviewer_keywords:
- C2626
ms.assetid: 4c283ad0-251b-4571-bc18-468b9836746f
ms.openlocfilehash: 434858991c23345e2a6c174c8f323000d42b9b6b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50565191"
---
# <a name="compiler-error-c2626"></a>Derleyici Hatası C2626

'identifier': bir anonim bir yapı veya birleşim özel veya korumalı veri üyesine izin verilmez

Bir anonim bir yapı veya birleşim üyesi ortak erişimi olmalıdır.

Aşağıdaki örnek, C2626 oluşturur:

```
// C2626.cpp
int main() {
   union {
   protected:
      int j;     // C2626, j is protected
   private:
      int k;     // C2626, k is private
   };
}
```

Bu sorunu gidermek için herhangi bir özel veya korumalı etiket kaldırın:

```
// C2626b.cpp
int main() {
   union {
   public:
      int i;   // OK, i is public
   };
}
```