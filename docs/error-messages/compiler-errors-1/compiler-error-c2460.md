---
title: "Derleyici Hatası C2460 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2460
dev_langs: C++
helpviewer_keywords: C2460
ms.assetid: d969fca9-3ac5-4e4e-88fc-df05510e2093
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 00e4015a0dae5054973ba72bb0e4f89c7443ae03
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2460"></a>Derleyici Hatası C2460
'identifier1': 'hangi tanımlanıyorsa kullanır identifier2',  
  
 Bir sınıf veya yapı (`identifier2`) kendisinin üyesi bildirilen (`identifier1`). Sınıfları ve yapıları özyinelemeli tanımları izin verilmiyor.  
  
 Aşağıdaki örnek C2460 oluşturur:  
  
```  
// C2460.cpp  
class C {  
   C aC;    // C2460  
};  
```  
  
 Bunun yerine, bir işaretçi başvuru sınıfında kullanın.  
  
```  
// C2460.cpp  
class C {  
   C * aC;    // OK  
};  
```