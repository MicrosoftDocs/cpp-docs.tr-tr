---
title: "Derleyici Hatası C2032 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2032
dev_langs: C++
helpviewer_keywords: C2032
ms.assetid: 625d7c83-70b6-42c2-a558-81fbc0026324
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 87703c289dc522f62c29fd2110e969fd44abf645
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2032"></a>Derleyici Hatası C2032
'tanımlayıcısı': işlevi struct/union 'structorunion' üyesi olamaz  
  
 Yapı veya birlik C++ ancak C. izin üye işlevi vardır Hatayı gidermek için C++ programı olarak derleyin veya üye işlevi kaldırın.  
  
 Aşağıdaki örnek C2032 oluşturur:  
  
```  
// C2032.c  
struct z {  
   int i;  
   void func();   // C2032  
};  
```  
  
 Olası çözüm:  
  
```  
// C2032b.c  
// compile with: /c  
struct z {  
   int i;  
};  
```