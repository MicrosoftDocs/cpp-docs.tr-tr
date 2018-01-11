---
title: "Derleyici Hatası C2798 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2798
dev_langs: C++
helpviewer_keywords: C2798
ms.assetid: fb0cd861-b228-4f81-8090-e28344a727e0
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4336577d3f2d1174dadb370db6001e982e9035f9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2798"></a>Derleyici Hatası C2798
'super::member' belirsiz  
  
 Birden çok devralınan yapıları başvurulan sahip üyeyi içeren [Süper](../../cpp/super.md). Hatayı düzeltin ya da:  
  
-   B1 veya B2 D. devralma listesinden kaldırılıyor  
  
-   Veri üyesi B1 veya B2 adının değiştirilmesi.  
  
 Aşağıdaki örnek C2798 oluşturur:  
  
```  
// C2798.cpp  
struct B1 {  
   int i;  
};  
  
struct B2 {  
   int i;  
};  
  
struct D : B1, B2 {  
   void g() {  
      __super::i = 4; // C2798  
   }  
};  
```