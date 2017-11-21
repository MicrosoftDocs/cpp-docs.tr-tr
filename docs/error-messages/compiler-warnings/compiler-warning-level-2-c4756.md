---
title: "Derleyici Uyarısı (Düzey 2) C4756 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4756
dev_langs: C++
helpviewer_keywords: C4756
ms.assetid: 5a16df83-6b82-4619-83bd-319af4ef1d1d
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ead332970500afbc69e21a5ed5d6507dec571244
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-2-c4756"></a>Derleyici Uyarısı (Düzey 2) C4756
içinde sabit aritmetik taşma  
  
 Derleyici derleme sırasında sabit aritmetik yaparken bir özel durum oluşturdu.  
  
 Aşağıdaki örnek C4756 oluşturur:  
  
```  
// C4756.cpp  
// compile with: /W2 /Od  
int main()  
{  
   float f = 1e100+1e100;   // C4756  
}  
```