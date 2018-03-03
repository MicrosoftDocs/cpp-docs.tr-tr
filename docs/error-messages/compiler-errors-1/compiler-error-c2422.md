---
title: "Derleyici Hatası C2422 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2422
dev_langs:
- C++
helpviewer_keywords:
- C2422
ms.assetid: ef0ec302-4028-4778-b134-0b8cea4bcad9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 852a495406a8baf147fc53262f8fe856fce726b5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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