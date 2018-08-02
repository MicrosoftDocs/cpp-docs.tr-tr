---
title: Denetim taşıma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- control flow, branching
- control flow, transferring control
ms.assetid: aa51e7f2-060f-4106-b0fe-331f04357423
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e773a0188eb3450ab1a13a24fc556fa8e8c4f874
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39464275"
---
# <a name="transfers-of-control"></a>Denetim Taşıma
Kullanabilirsiniz **goto** deyimi veya bir **çalışması** etiketi bir **geçiş** deyimini bir başlatıcı dallar bir program belirtin. Başlatıcı içeren bildirimi blok tarafından alınmış bir blok içinde olmadığı sürece bu tür kod geçersiz atlama deyimi oluştuğu içinde.  
  
 Aşağıdaki örnek, bir döngüyü bildirir ve nesneleri başlatır gösterir `total`, `ch`, ve `i`. De mevcuttur bir hatalı **goto** aktaran bir başlatıcı son denetim ifadesi.  
  
```cpp 
// transfers_of_control.cpp  
// compile with: /W1  
// Read input until a nonnumeric character is entered.  
int main()  
{  
   char MyArray[5] = {'2','2','a','c'};  
   int i = 0;  
   while( 1 )  
   {  
      int total = 0;  
  
      char ch = MyArray[i++];  
  
      if ( ch >= '0' && ch <= '9' )  
      {  
         goto Label1;  
  
         int i = ch - '0';  
      Label1:  
         total += i;   // C4700: transfers past initialization of i.  
      } // i would be destroyed here if  goto error were not present  
   else  
      // Break statement transfers control out of loop,  
      //  destroying total and ch.  
      break;  
   }  
}  
```  
  
 Önceki örnekte **goto** deyimi son başlatma denetimi aktarım dener `i`. Ancak, varsa `i` bildirildi ancak başlatılmadı, aktarımı geçerli olacaktır.  
  
 Nesneleri `total` ve `ch`görevi gören bir blok içinde bildirilen *deyimi* , **sırada** deyimini kullanarak o blok çıkıldı zaman yok  **Kesme** deyimi.  