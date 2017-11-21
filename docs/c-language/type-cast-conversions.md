---
title: "Tür atama dönüşümleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- data type conversion [C++], type-cast conversions
- conversions [C++], type-cast
- type casts
- explicit type conversions
- type casts [C++], about type-cast conversion
- type-cast conversions [C++]
ms.assetid: 57ab5902-f12f-4326-a2f6-6282f1d4025a
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d3426d6ff06a5d07dd64889e6a5d89da543cfe68
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="type-cast-conversions"></a>Tür Atama Dönüştürmeleri
Tür atamaları açıkça türlerine dönüştürmek için kullanabilirsiniz.  
  
 **Sözdizimi**  
  
 *Cast ifadesi*:  
 *Tek terimli ifadesi*  
  
 **(***türü adı***)***cast ifadesi*   
  
 *tür adı*:  
 *belirleyici niteleyici listesinde Özet-bildirimcisi* iptal et  
  
 *Türü adı* bir tür ve *cast ifadesi* bu türe dönüştürülüp bir değerdir. Bir cast türünü sahip bir ifade l-değeri değil. *Cast ifadesi* türünde bir değişken için atanmış gibi sorgulamanıza dönüştürülür *türü adı*. Dönüştürme kurallarını atamaların (özetlenen [atama dönüşümleri](../c-language/assignment-conversions.md)) atamalar da türü için geçerlidir. Aşağıdaki tabloda verilen tüm tür atanabilecek türleri gösterilmektedir.  
  
### <a name="legal-type-casts"></a>Yasal tür atamaları  
  
|Hedef türleri|Olası kaynakları|  
|-----------------------|-----------------------|  
|Tam sayı türleri|Tüm tamsayı türü veya kayan nokta yazın veya bir nesne işaretçisi|  
|Kayan nokta|Herhangi bir aritmetik türü|  
|Bir nesne için bir işaretçi veya (**void \*** )|Herhangi bir tamsayı türü (**void \*** ), bir nesne için bir işaretçi ya da bir işlev işaretçisi|  
|işlev işaretçisi|Herhangi bir tam sayı türü, bir nesne için bir işaretçi veya bir işlev işaretçisi|  
|Yapısı, UNION veya dizi|Yok.|  
|Void türü|Herhangi bir türü|  
  
 Herhangi bir tanımlayıcı için çevirebilirsiniz `void` türü. Türü belirtilen ancak, bir tür atama ifadesi değilse `void`, tanımlayıcı olması için türü olamaz cast sonra bir `void` ifade. Bir ifadeyi dönüştürmek `void`, ancak türü bir ifadenin `void` başka bir türüne yayınlanamıyor. Örneğin, bir işlev ile `void` dönüş türü, kendi dönüş başka bir türe sahip olamaz.  
  
 Unutmayın bir **void \***  ifade türü işaretçi sahip `void`, türünde değil `void`. Bir nesne için cast varsa `void` türü, elde edilen ifadesi herhangi öğesine atanamaz. Hiçbir atama bir cast türünü nesnesine böylece benzer şekilde, bir tür atama nesnesi bir kabul edilebilir l-değeri değil.  
  
 **Microsoft özel**  
  
 Tanımlayıcı boyutunu değişmeyen sürece bir cast türünü bir l-değeri ifade olabilir. L-değeri ifadeleri hakkında daha fazla bilgi için bkz: [L-değeri ve r değeri ifadeleri](../c-language/l-value-and-r-value-expressions.md).  
  
 **SON Microsoft özel**  
  
 Türü için bir ifade dönüştürebilirsiniz `void` bir cast ile ancak elde edilen ifadesi yalnızca bir değer gerekli olduğu kullanılabilir. Bir nesne işaretçisi dönüştürülüp **void \***  ve özgün türü geri için özgün değeri döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tür dönüştürmeleri](../c-language/type-conversions-c.md)