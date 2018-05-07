---
title: Derleyici Hatası C2422 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2422
dev_langs:
- C++
helpviewer_keywords:
- C2422
ms.assetid: ef0ec302-4028-4778-b134-0b8cea4bcad9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 89a808e4b324b11c88be38ae7d8815bee4e232cd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2422"></a>Derleyici Hatası C2422
'işleneni' ın geçersiz kesim geçersiz kılma  
  
 Satır içi derleme kodu yanlış bir işlenen üzerinde bir kesim geçersiz kılma işleci (iki nokta üst üste) kullanır.  Olası nedenler şunlardır:  
  
-   İşleç önceki kaydı bir segment kayıt değil.  
  
-   İşleç önceki kayıt işleneni yalnızca segment kayıttaki değil.  
  
-   Kesim geçersiz kılma işleci indirection işleci (köşeli ayraç) içinde görüntülenir.  
  
-   Kesim geçersiz kılma operatöründen ifadesi, bir anlık işlenen ya da bir bellek işleneni değil.  
  
 Aşağıdaki örnek C2422 oluşturur:  
  
```  
// C2422.cpp  
// processor: x86  
int main() {  
   _asm {  
      mov AX, [BX:ES]   // C2422  
      mov AX, ES   // OK  
   }  
}  
```