---
title: "Derleyici Hatası C2180 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2180
dev_langs: C++
helpviewer_keywords: C2180
ms.assetid: ea71b39e-b977-48a7-b7bd-af68ef5e263b
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 181309cca171c872a7c3767729a755d6e73bd288
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2180"></a>Derleyici Hatası C2180
türü 'type' sahip ifade denetleme  
  
 Denetleme ifadesinde bir `if`, `while`, `for`, veya `do` açıklamadır için bir ifade `void`. Bu sorunu gidermek için denetleme ifade üreten değiştirin bir `bool` veya dönüştürülebilir bir türü `bool`.  
  
 Aşağıdaki örnek C2180 oluşturur:  
  
```  
// C2180.c  
  
int main() {  
   while ((void)1)   // C2180  
      return 1;  
   while (1)         // OK  
      return 0;  
}  
```