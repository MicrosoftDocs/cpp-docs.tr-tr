---
title: Derleyici Uyarısı (düzey 1) C4731 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4731
dev_langs:
- C++
helpviewer_keywords:
- C4731
ms.assetid: 5658c24c-3e6f-4505-835b-1fb92d47cab0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 75117b34e63694cfa6aeec97abf178ff8e61a7da
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46086492"
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