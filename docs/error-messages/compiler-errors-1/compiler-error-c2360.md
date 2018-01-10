---
title: "Derleyici Hatası C2360 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2360
dev_langs: C++
helpviewer_keywords: C2360
ms.assetid: 51bfd2ee-8108-4777-aa93-148b9cebfa83
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4c8bde56d32000ca51b07afbeb09438327b66120
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2360"></a>Derleyici Hatası C2360
'tanımlayıcısının' başlatma 'case' etiketle atlandı  
  
 Başlatılması `identifier` içinde atlandı bir `switch` deyimi. Bir blok bildirimi arasına sürece bir başlatıcı bildirimiyle geçmiş atlama olamaz. (Bir blokta bildirilir sürece kapsamında sonuna kadar değişkenidir `switch` deyimi.)  
  
 Aşağıdaki örnek C2360 oluşturur:  
  
```  
// C2360.cpp  
int main() {  
   int x = 0;  
   switch ( x ) {  
   case 0 :  
      int i = 1;  
      { int j = 1; }  
   case 1 :   // C2360  
      int k = 1;  
   }  
}  
```  
  
 Olası çözüm:  
  
```  
// C2360b.cpp  
int main() {  
   int x = 0;  
   switch ( x ) {  
   case 0 :  
      { int j = 1; int i = 1;}  
   case 1 :  
      int k = 1;  
   }  
}  
```