---
title: "Derleyici Hatası C2562 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2562
dev_langs: C++
helpviewer_keywords: C2562
ms.assetid: 2c41e511-9952-4b98-9976-6b1523613e1b
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f6bf1d7d9be8468ed0ccf65abea135992a50ac11
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2562"></a>Derleyici Hatası C2562
'tanımlayıcısı': 'void' işlevi bir değer döndürme  
  
 İşlev olarak bildirilmiş `void` ancak bir değer döndürür.  
  
 Bu hata yanlış işlev prototipi tarafından neden olabilir.  
  
 İşlevi bildiriminde dönüş türü belirtirseniz, bu hata düzeltilebilir.  
  
 Aşağıdaki örnek C2562 oluşturur:  
  
```  
// C2562.cpp  
// compile with: /c  
void testfunc() {  
   int i;  
   return i;   // C2562 delete the return to resolve  
}  
```