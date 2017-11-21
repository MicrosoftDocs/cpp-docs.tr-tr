---
title: "İşlevlerine genel bakış | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- functions [C++]
- control flow, function calls
ms.assetid: b6f4637f-02b9-49d8-8601-1f886bd2cfb9
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9abb23be750a4c707b7a2d73ee2650bf3b786731
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="overview-of-functions"></a>İşlevlere Genel Bakış
İşlevler bir tanım olmalıdır ve işlevi çağrılmadan önce bildirimi görünürse bir tanımı bildirimi olarak hizmet verebilir rağmen bir bildirimi sahip olmalıdır. İşlev gövdesi işlev tanımı içerir — işlevi çağrıldığında yürütülen kodu.  
  
 Bir işlev bildirimi adını, dönüş türü ve başka bir programda tanımlı bir işlevin öznitelikleri oluşturur. Bir işlev bildirimi işlevi çağrısında gelmelidir. Çalışma zamanı işlevleri için bildirimleri içeren üst bilgi dosyaları, kodunuzun çalışma zamanı işlevi çağrısı önce yer alan nedeni budur. Bildirim parametre sayısı ve türleri hakkında bilgi varsa, bir prototip bildirimidir. Bkz: [işlev prototipleri](../c-language/function-prototypes.md) daha fazla bilgi için.  
  
 Derleyici prototip işlev parametreleri işleviyle yapılan sonraki çağrılar değişkenlerinde türlerini karşılaştırmasına ve bağımsız değişkenlerden tür parametrelerinin gerektiğinde türlerine dönüştürmek için kullanır.  
  
 Bir işlev çağrısı yürütme denetimi çağrılan işlev çağırma işlevinden geçirir. Bağımsız değişkenler varsa, değeri tarafından çağrılan işlev geçirilir. Yürütme işlemi bir `return` çağrılan işlev deyiminde, arama işlevi için denetimi ve büyük olasılıkla bir değer döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlevler](../c-language/functions-c.md)