---
title: "Derleyici Hatası C2246 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2246
dev_langs: C++
helpviewer_keywords: C2246
ms.assetid: 4f3e4f83-21f3-4256-af96-43e0bb060311
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ce194e9f08655e0acc7d1dab53f2a2392cceb4f4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2246"></a>Derleyici Hatası C2246
'tanımlayıcısı': yerel olarak tanımlanmış sınıfında geçersiz statik veri üyesi  
  
 Sınıf, yapı veya yerel kapsamlı UNION üyesi bildirilmiş `static`.  
  
 Aşağıdaki örnek C2246 oluşturur:  
  
```  
// C2246.cpp  
// compile with: /c  
void func( void ) {  
   class A { static int i; };   // C2246  i is local to func  
   static int j;   // OK  
};  
```