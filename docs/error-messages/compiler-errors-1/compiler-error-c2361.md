---
title: "Derleyici Hatası C2361 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2361
dev_langs: C++
helpviewer_keywords: C2361
ms.assetid: efbdaeb9-891c-4f7d-97da-89088a8413f3
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3e80c1a1ebcd56b4125ef9aa43e904d9093fc8a9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2361"></a>Derleyici Hatası C2361
'tanımlayıcısının' başlatma 'default' etiketle atlandı  
  
 Başlatılması `identifier` içinde atlandı bir `switch` deyimi. Bir blok bildirimi arasına sürece bir başlatıcı bildirimiyle geçmiş atlama olamaz. (Bir blokta bildirilir sürece kapsamında sonuna kadar değişkenidir `switch` deyimi.)  
  
 Aşağıdaki örnek C2361 oluşturur:  
  
```  
// C2361.cpp  
void func( void ) {  
   int x;  
   switch (x) {  
   case 0 :  
      int i = 1;  
      { int j = 1; }  
   default :   // C2361 error  
      int k = 1;  
   }  
}  
```  
  
 Olası çözüm:  
  
```  
// C2361b.cpp  
// compile with: /c  
void func( void ) {  
   int x = 0;  
   switch (x) {  
   case 0 :  
      { int j = 1; int i = 1;}  
   default :  
      int k = 1;  
   }  
}  
```