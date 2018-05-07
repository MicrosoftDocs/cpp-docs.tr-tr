---
title: Derleyici Hatası C2460 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2460
dev_langs:
- C++
helpviewer_keywords:
- C2460
ms.assetid: d969fca9-3ac5-4e4e-88fc-df05510e2093
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b4220be654f93ecd79d196efc14657ca7346411f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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