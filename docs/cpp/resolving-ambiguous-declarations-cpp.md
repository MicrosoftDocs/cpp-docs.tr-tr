---
title: "Belirsiz bildirimler (C++) çözme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
ms.assetid: 3d773ee7-bbea-47de-80c2-cb0a9d4ec0b9
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d9e62987a0007c01499cf4e4477d643fff9f65c3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="resolving-ambiguous-declarations-c"></a>Çözümleme belirsiz bildirimler (C++)
Bir türden diğerine açık dönüştürmeler gerçekleştirmek için istenen tür adını belirterek atamalar kullanmanız gerekir. Bazı tür atamaları, sözdizimi belirsizliğine neden olur. Aşağıdaki işlev stili tür ataması belirsizdir:  
  
```  
char *aName( String( s ) );  
```  
  
 İşlevi bildiriminde ya da işlevi tarzı başlatıcı olarak dönüştürme nesne bildirimiyle olup belirsiz: türü döndüren bir işlev bildirebilirsiniz **char \***  türünde bir bağımsız değişken alan `String` , veya nesne bildirebilirsiniz `aName` ve değeriyle başlatma `s` yazmak için cast `String`.  
  
 Bir bildirim geçerli işlev bildirimi olarak kabul edilebilirse, bu şekilde ele alınır. Yalnızca bir işlev bildirimi olamazsa, yani bu durum sözdizimi olarak göre yanlışsa, işlev stili tür araması olup olmadığını belirlemek için bir deyim incelenir. Bu nedenle, derleyici deyimi bir işlevin bildirimi olarak değerlendirir ve `s` tanımlayıcısının etrafındaki parantezleri yoksayar. Öte yandan  
  
```  
char *aName( (String)s );  
```  
  
 and  
  
```  
char *aName = String( s );  
```  
  
 açıkça nesneleri ve kullanıcı tanımlı bir dönüştürme türünden bildirimlerini olan `String` yazmak için **char \***  başlatılması gerçekleştirmek için çağrılan `aName`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 