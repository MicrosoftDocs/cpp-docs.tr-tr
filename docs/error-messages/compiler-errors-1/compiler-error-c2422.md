---
title: "Derleyici Hatası C2422 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2422
dev_langs: C++
helpviewer_keywords: C2422
ms.assetid: ef0ec302-4028-4778-b134-0b8cea4bcad9
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 65412576c3c1a5e6b8205652d826d0eca6d222e6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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