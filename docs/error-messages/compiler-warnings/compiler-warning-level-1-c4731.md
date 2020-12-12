---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4731'
title: Derleyici Uyarısı (düzey 1) C4731
ms.date: 11/04/2016
f1_keywords:
- C4731
helpviewer_keywords:
- C4731
ms.assetid: 5658c24c-3e6f-4505-835b-1fb92d47cab0
ms.openlocfilehash: d2041936d7d3c4b7189f57d57ffb1c9f226ea933
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228657"
---
# <a name="compiler-warning-level-1-c4731"></a>Derleyici Uyarısı (düzey 1) C4731

' Pointer ': çerçeve işaretçisi yazmaç ' Register ' satır içi derleme kodu tarafından değiştirildi

Çerçeve işaretçisi kaydı değiştirildi. Kaydı satır içi derleme blobundan veya çerçeve değişkenine (yerel veya parametreye, kaydın değiştirilmesine bağlı olarak) kaydetmeniz ve geri yüklemeniz gerekir, aksi durumda kodunuz düzgün çalışmayabilir.

Aşağıdaki örnek C4731 oluşturur:

```cpp
// C4731.cpp
// compile with: /W1 /LD
// processor: x86
// C4731 expected
void bad(int p) {
   __asm
   {
      mov ebp, 1
   }

   if (p == 1)
   {
      // ...
   }
}
```

EBP çerçeve işaretçisine (mı izin verilmiyor) ve değiştirilmektedir. `p`Daha sonra başvurulduğunda, öğesine göre başvurulur `EBP` . Ancak `EBP` kod tarafından üzerine yazıldı, bu nedenle program düzgün çalışmayacaktır ve hatta hataya neden olur.
