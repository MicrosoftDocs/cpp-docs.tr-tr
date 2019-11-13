---
title: Derleyici Uyarısı (düzey 1) C4731
ms.date: 11/04/2016
f1_keywords:
- C4731
helpviewer_keywords:
- C4731
ms.assetid: 5658c24c-3e6f-4505-835b-1fb92d47cab0
ms.openlocfilehash: b2591756dfaa8887affbe4e470f1c98738b6b680
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052423"
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

EBP çerçeve işaretçisine (mı izin verilmiyor) ve değiştirilmektedir. `p` daha sonra başvuruluyorsa, `EBP`göreli olarak başvurulur. Ancak `EBP` kodla üzerine yazıldı, bu nedenle program düzgün çalışmayacaktır ve hatta hataya neden olur.