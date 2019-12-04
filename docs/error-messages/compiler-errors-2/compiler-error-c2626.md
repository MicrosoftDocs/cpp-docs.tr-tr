---
title: Derleyici hatası C2626
ms.date: 11/04/2016
f1_keywords:
- C2626
helpviewer_keywords:
- C2626
ms.assetid: 4c283ad0-251b-4571-bc18-468b9836746f
ms.openlocfilehash: 339d48265bdc1f68ea4e18fadfde48fca956dd1f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754751"
---
# <a name="compiler-error-c2626"></a>Derleyici hatası C2626

' tanımlayıcı ': anonim bir yapıda veya birleşimde özel veya korumalı bir veri üyesine izin verilmez

Anonim yapının veya birleşimin bir üyesinin genel erişimi olmalıdır.

Aşağıdaki örnek C2626 oluşturur:

```cpp
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

Bu sorunu onarmak için, tüm özel veya korumalı etiketleri kaldırın:

```cpp
// C2626b.cpp
int main() {
   union {
   public:
      int i;   // OK, i is public
   };
}
```
