---
title: "Derleyici Hatası C2034 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2034
dev_langs: C++
helpviewer_keywords: C2034
ms.assetid: 953d70fa-bde9-4ce6-a55d-741e7bc63ff4
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: df3d2310a5f066fdb937900abe545c16f5526508
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2034"></a>Derleyici Hatası C2034
'tanımlayıcısı': bit sayısını için çok küçük bit alanının türü  
  
 Bit alanı bildiriminde bit sayısını temel türü boyutunu aşıyor.  
  
 Aşağıdaki örnek C2034 oluşturur:  
  
```  
// C2034.cpp  
struct A {  
   char test : 9;   // C2034, char has 8 bits  
};  
```  
  
 Olası çözüm:  
  
```  
// C2034b.cpp  
// compile with: /c  
struct A {  
   char test : 8;  
};  
```