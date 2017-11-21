---
title: "İşlev gövdesi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- functions [C], syntax
- variables, function syntax
- function definitions, function body
- function body
ms.assetid: f7e74822-fac8-4dc8-8f3a-2b1611da4640
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a30ad1b016e0ab4814e0ac6f6f4627cdf265f59b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="function-body"></a>İşlev Gövdesi
"İşlev gövdesi" işlevi ne yapacağını belirtin deyimleri içeren bileşik bir ifadedir.  
  
## <a name="syntax"></a>Sözdizimi  
 *işlev tanımı*:  
 *bildirim tanımlayıcıları* kabul*özniteliği seq* kabul*bildirimcisi bildirimi listesi* kabul*bileşik deyim*  
  
 /\**özniteliği seq* Microsoft Specific * /  
  
 *Bileşik deyim*: /\* işlev gövdesi\*/  
 **{***bildirimi listesi* kabul*deyimi listesi* kabul**}**   
  
 İşlev gövdesi içinde "yerel değişkenler," bildirilen değişkenleri **otomatik** depolama sınıfı aksi belirtilmediği sürece. İşlevi çağrıldığında, depolama için yerel değişkenleri oluşturulur ve yerel başlatmaları gerçekleştirilir. Yürütme denetimi geçirir ilk ifadesine *bileşik deyim* ve kadar devam eder bir `return` deyimi yürütüldüğünde veya işlev gövdesi sonu ile karşılaşıldı. Denetim ardından işlevi çağrıldı noktasına döndürür.  
  
 A `return` bir ifade içeren deyimi gerekir yürütülebilir işlevi bir değer döndürülmesini istiyorsanız. Öyle değilse bir işlevin dönüş değeri tanımlanmamış `return` deyimi yürütüldüğünde veya `return` deyimi bir ifade içermiyor.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C işlev tanımları](../c-language/c-function-definitions.md)