---
title: "İşlev gövdesi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- functions [C], syntax
- variables, function syntax
- function definitions, function body
- function body
ms.assetid: f7e74822-fac8-4dc8-8f3a-2b1611da4640
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a0c85ecf0752ff34bf5b61e42309360f2bc4d448
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [C İşlev Tanımları](../c-language/c-function-definitions.md)