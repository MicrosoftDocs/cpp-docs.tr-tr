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
ms.openlocfilehash: bb0a411651cf7c7f614942563baee5f04075fdf3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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