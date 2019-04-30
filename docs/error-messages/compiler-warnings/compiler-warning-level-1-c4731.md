---
title: Derleyici Uyarısı (düzey 1) C4731
ms.date: 11/04/2016
f1_keywords:
- C4731
helpviewer_keywords:
- C4731
ms.assetid: 5658c24c-3e6f-4505-835b-1fb92d47cab0
ms.openlocfilehash: af091d1d35fff955afcc5af3da48b80416e79f36
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385439"
---
# <a name="compiler-warning-level-1-c4731"></a>Derleyici Uyarısı (düzey 1) C4731

'işaretçisi': çerçeve işaretçisi kaydı satır içi derleme kodu tarafından değiştirilen 'register'

Çerçeve işaretçisi kaydı değiştirildi. Kaydedin ve kaydı, satır içi bütünleştirilmiş kod bloğu veya çerçeve değişkeni (yerel veya parametre, değişiklik kaydı bağlı olarak) geri yükleme veya kodunuzun düzgün çalışmayabilir.

Aşağıdaki örnek, C4731 oluşturur:

```
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

EBP (FPO izin verilmiyor) çerçeve işaretçidir ve değiştirilmekte olan. Zaman `p` sonraki başvurulan, göreli başvuru `EBP`. Ancak `EBP` kodla yazıldığı program düzgün çalışmaz ve hatta hata.