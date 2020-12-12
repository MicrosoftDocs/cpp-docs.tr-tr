---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2626'
title: Derleyici hatası C2626
ms.date: 11/04/2016
f1_keywords:
- C2626
helpviewer_keywords:
- C2626
ms.assetid: 4c283ad0-251b-4571-bc18-468b9836746f
ms.openlocfilehash: 1a89d63d18fd029daa98ce1d248da24296ee2d4f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123557"
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
