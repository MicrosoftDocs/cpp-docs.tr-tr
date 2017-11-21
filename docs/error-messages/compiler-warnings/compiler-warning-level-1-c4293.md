---
title: "Derleyici Uyarısı (düzey 1) C4293 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4293
dev_langs: C++
helpviewer_keywords: C4293
ms.assetid: babecd96-eb51-41a5-9835-462c7a46dbad
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 357ff16726bb4ab38e6b8d9d3e2708bcf9e44579
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4293"></a>Derleyici Uyarısı (düzey 1) C4293
'işleci': kaydırma sayısı negatif ya da çok büyük, undefined davranışı  
  
 Bir kaydırma sayısı negatif veya çok büyük ise, sonuçta elde edilen görüntü davranışını tanımlanmamıştır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4293 oluşturur:  
  
```  
// C4293.cpp  
// compile with: /c /W1  
unsigned __int64 combine (unsigned lo, unsigned hi) {  
  
   return (hi << 32) | lo;   // C4293  
  
   // try the following line instead  
   // return ( (unsigned __int64)hi << 32) | lo;  
}  
```