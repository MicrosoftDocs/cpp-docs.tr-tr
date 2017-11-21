---
title: "Sayıların indirgenmesi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: demoting integers
ms.assetid: 51fb3654-60b0-4de7-80eb-bd910086c18a
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e09a81ca21f6e00777322178dcdf1c09ef22dd5b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="demotion-of-integers"></a>Tam Sayıların İndirgenmesi
**ANSI 3.2.1.2** daha kısa bir imzalı tamsayıya tamsayı dönüştürmenin sonucunu ya da değeri gösterilemezse işaretsiz tamsayıya eşit uzunlukta imzalı bir tamsayı olarak dönüştürmenin sonucunu  
  
 Zaman bir **uzun** tamsayı atandığında **kısa**, veya bir **kısa** için cast bir `char`, en az önemli bayt korunur.  
  
 Örneğin, bu satır  
  
```  
short x = (short)0x12345678L;  
```  
  
 0x5678 değerini `x`'e atar ve bu satır  
  
```  
char y = (char)0x1234;  
```  
  
 0x34 değerini `y`'ye atar.  
  
 İşaretli değişkenler işaretsiz değişkenlere ve işaretsiz değişkenler işaretli değişkenlere dönüştürüldüğünde, bit düzenleri aynı kalır. Örneğin, -2 atama (0xFE) 254 (Ayrıca 0xFE) imzasız bir değer verir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tamsayılara](../c-language/integers.md)