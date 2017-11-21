---
title: "Derleyici Hatası C2882 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2882
dev_langs: C++
helpviewer_keywords: C2882
ms.assetid: 617018ee-5a0d-4b8d-9612-77e8ae52679b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: acbe0158dd0514df066b37ffcc7544602ce3f5ca
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2882"></a>Derleyici Hatası C2882
'name': ifade ad alanı tanımlayıcıda geçersiz kullanımı  
  
 Bir ifadede bir ad alanı adını kullanmak çalışıldı.  
  
 Aşağıdaki örnek C2882 oluşturur:  
  
```  
// C2882.cpp  
// compile with: /c  
namespace A {  
   int k;  
}  
  
int i = A;   // C2882, can't assign A to i  
```