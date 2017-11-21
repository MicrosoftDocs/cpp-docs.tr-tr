---
title: "Derleyici Hatası C2675 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2675
dev_langs: C++
helpviewer_keywords: C2675
ms.assetid: 4b92a12b-bff8-4dd5-a109-620065fc146c
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c9c5815e7c57eb2469599a26c2cbc5202018f27e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2675"></a>Derleyici Hatası C2675
birli 'işleci': 'type' değil tanımlamak bu işleci veya kabul edilebilir bir tür dönüşümünü önceden tanımlanmış işleci  
  
 C2675 de birli işleç kullanılarak ortaya çıkabilir ve türü için önceden tanımlanmış işleci işleci veya kabul edilebilir bir tür dönüşümünü tanımlamıyor. İşleç kullanmak için belirtilen tür için aşırı yükleme veya işleci tanımlandığı bir türe dönüştürme tanımlayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2675 oluşturur.  
  
```  
// C2675.cpp  
struct C {   
   C(){}  
} c;  
  
struct D {   
   D(){}  
   void operator-(){}  
} d;  
  
int main() {  
   -c;   // C2675  
   -d;   // OK  
}  
```