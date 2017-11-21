---
title: "İçin işaretçi türlerine ve türlerinden dönüşümler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- pointers, converting
- conversions, pointer
- type casts, involving pointers
- void pointers
ms.assetid: 3facc56f-06d3-4570-b1a2-7d4927b83086
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1751c19ba222bbdf9dfc30a290201289db1af850
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="conversions-to-and-from-pointer-types"></a>İşaretçi Türlerine ve Türlerinden Dönüşümler
Bir değer türünün işaretçisi, farklı türden bir işaretçiye dönüştürülebilir. Ancak sonuç, depolanan farklı türlerin hizalama gereksinimleri ve boyutları nedeniyle tanımlanmamış olabilir. Bir nesnenin işaretçisi, türü daha az katı veya eşit derecede katı olan depolama hizalaması gerektiren bir nesnenin işaretçisine dönüştürülebilir ve değiştirilmeden geri alınabilir.  
  
 `void` işaretçisi, herhangi bir türden işaretçiye veya işaretçiden kısıtlama veya bilgi kaybı olmadan dönüştürülebilir. Sonuç yeniden orijinal türüne dönüştürülürse, orijinal işaretçi kurtarılır.  
  
 Bir işaretçi aynı türden, ancak farklı veya ek niteleyicileri olan başka bir işaretçiye dönüştürülürse, yeni işaretçi yeni niteleyici tarafından uygulanan kısıtlamalar dışında eskisiyle aynı olur.  
  
 İşaretçi değeri, integral değerine de dönüştürülebilir. Dönüştürme yolu, aşağıdaki kurallara göre işaretçinin boyutuna ve integral türünün boyutuna bağlıdır:  
  
-   İşaretçinin boyutu integral türünün boyutundan büyük veya buna eşitse, işaretçi dönüştürme işleminde işaretsiz bir değer gibi görev alır, ancak bu değer gibi kayan bir değere dönüştürülemez.  
  
-   İşaretçi integral türünden küçükse, işaretçi önce integral türüyle aynı boyuttan bir işaretçiye, ardından integral türüne dönüştürülür.  
  
 Bunun tersi olarak, aşağıdaki kurallara göre bir integral türü işaretçi türüne dönüştürülebilir:  
  
-   İntegral türü işaretçi türüyle aynı boyuttaysa, dönüştürme işlemi integral değerinin bir işaretçi (işaretsiz tamsayı) olarak değerlendirilmesine neden olur.  
  
-   İşaretçi türünün boyutundan tam sayı yazı tipi boyutu farklıysa, tam sayı türü ilk işaretçi boyutunu tablolarda verilen dönüştürme yollar kullanılarak dönüştürülür [dönüştürme imzalı tam sayı türlerinden](../c-language/conversions-from-signed-integral-types.md) ve [ İmzasız tam sayı türleri dönüştürme](../c-language/conversions-from-unsigned-integral-types.md). Daha sonra bir işaretçi değeri olarak kabul edilir.  
  
 Bir tam sayı sabit ifadeyle değer 0 veya böyle bir ifade türü için cast **void \***  göre cast türü atama veya herhangi bir türde bir işaretçi karşılaştırma dönüştürülebilir. Bu, aynı türden başka bir null işaretçisine eşit olan bir null işaretçisi oluşturur, ancak bu null işaretçisi bir işlevin veya nesnenin herhangi bir işaretçisine eşit değildir. 0 sabiti dışındaki tamsayılar işaretçi türüne dönüştürülebilir, ancak sonuç taşınabilir değildir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Atama dönüşümleri](../c-language/assignment-conversions.md)