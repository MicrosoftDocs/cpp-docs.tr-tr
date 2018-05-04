---
title: Belirsiz bildirimler (C++) çözme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 3d773ee7-bbea-47de-80c2-cb0a9d4ec0b9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 530111ee439a991201debab876d485a36b7f5ac5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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
 