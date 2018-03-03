---
title: "Derleyici Uyarısı (düzey 1) C4731 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4731
dev_langs:
- C++
helpviewer_keywords:
- C4731
ms.assetid: 5658c24c-3e6f-4505-835b-1fb92d47cab0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9d8c59a22166c3f4f44db3bea43e241a2199009d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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