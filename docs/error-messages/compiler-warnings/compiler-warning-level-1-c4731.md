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
ms.openlocfilehash: 31bdf972ef3791760469251dc4d0bf19627bded2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33283887"
---
# <a name="compiler-warning-level-1-c4731"></a>Derleyici Uyarısı (düzey 1) C4731
'işaretçi': çerçeve işaretçisi Kaydet 'Kaydet', satır içi derleme kodu tarafından değiştirilmiş  
  
 Çerçeve işaretçisi kaydı değiştirildi. Kaydet ve satır içi derleme blok veya çerçeve değişkeniniz (yerel veya değiştirilen kayıt bağlı olarak parametre) kaydı geri ya da kodunuzu düzgün çalışmayabilir.  
  
 Aşağıdaki örnek C4731 oluşturur:  
  
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
  
 EBP (FPO devre dışı bırakılmış) çerçeve işaretçisi olan ve değiştirilmekte olan. Zaman `p` sonraki başvurulan, göreli başvuru `EBP`. Ancak `EBP` program düzgün şekilde çalışmaz ve hatta arıza, kodun üzerine yazıldığını.