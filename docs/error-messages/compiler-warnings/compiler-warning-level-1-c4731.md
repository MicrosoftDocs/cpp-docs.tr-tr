---
title: Derleyici Uyarısı (düzey 1) C4731
ms.date: 11/04/2016
f1_keywords:
- C4731
helpviewer_keywords:
- C4731
ms.assetid: 5658c24c-3e6f-4505-835b-1fb92d47cab0
ms.openlocfilehash: 72483b734a1463b7b211c49ef21a01536ffa0ea1
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80185730"
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
