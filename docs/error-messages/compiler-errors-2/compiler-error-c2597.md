---
title: "Derleyici Hatası C2597 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2597
dev_langs: C++
helpviewer_keywords: C2597
ms.assetid: 2e48127d-e3ff-4a40-8156-2863e45b1a38
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7530805c7b5ad1e16ec95ea69324f6717791a6f1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2597"></a>Derleyici Hatası C2597
Statik olmayan üye 'tanımlayıcısı' için geçersiz başvuru  
  
 Olası nedenler:  
  
1.  Statik olmayan üye statik üye işlevinde belirtilir. Statik olmayan üye erişmek için geçirin veya yerel bir sınıf örneği oluşturabilir ve üye erişimi işleci kullanmanız gerekir (`.` veya `->`).  
  
2.  Belirtilen tanımlayıcı bir sınıf, yapı veya birleşim üyesi değil. Tanımlayıcı yazım denetimi yapın.  
  
3.  Üye erişimi işleci dahil olmayan işlevine ifade eder.  
  
4.  Aşağıdaki örnek C2597 oluşturur ve düzeltmek gösterilmektedir:  
  
```  
// C2597.cpp  
// compile with: /c  
struct s1 {  
   static void func();  
   static void func2(s1&);  
   int i;  
};  
  
void s1::func() {  
   i = 1;    // C2597 - static function can't access non-static data member  
}  
  
// OK - fix by passing an instance of s1  
void s1::func2(s1& a) {  
   a.i = 1;  
}  
```