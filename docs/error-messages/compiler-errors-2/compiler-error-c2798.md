---
title: Derleyici Hatası C2798 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2798
dev_langs:
- C++
helpviewer_keywords:
- C2798
ms.assetid: fb0cd861-b228-4f81-8090-e28344a727e0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: de30a19a2a27cde991cfce0ca061ce6f5447f033
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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