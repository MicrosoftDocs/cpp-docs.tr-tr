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
ms.workload: cplusplus
ms.openlocfilehash: 093400e5d98b0b5e0336c2f640ed0937bdb157b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="overview-of-functions"></a>İşlevlere Genel Bakış
İşlevler bir tanım olmalıdır ve işlevi çağrılmadan önce bildirimi görünürse bir tanımı bildirimi olarak hizmet verebilir rağmen bir bildirimi sahip olmalıdır. İşlev gövdesi işlev tanımı içerir — işlevi çağrıldığında yürütülen kodu.  
  
 Bir işlev bildirimi adını, dönüş türü ve başka bir programda tanımlı bir işlevin öznitelikleri oluşturur. Bir işlev bildirimi işlevi çağrısında gelmelidir. Çalışma zamanı işlevleri için bildirimleri içeren üst bilgi dosyaları, kodunuzun çalışma zamanı işlevi çağrısı önce yer alan nedeni budur. Bildirim parametre sayısı ve türleri hakkında bilgi varsa, bir prototip bildirimidir. Bkz: [işlev prototipleri](../c-language/function-prototypes.md) daha fazla bilgi için.  
  
 Derleyici prototip işlev parametreleri işleviyle yapılan sonraki çağrılar değişkenlerinde türlerini karşılaştırmasına ve bağımsız değişkenlerden tür parametrelerinin gerektiğinde türlerine dönüştürmek için kullanır.  
  
 Bir işlev çağrısı yürütme denetimi çağrılan işlev çağırma işlevinden geçirir. Bağımsız değişkenler varsa, değeri tarafından çağrılan işlev geçirilir. Yürütme işlemi bir `return` çağrılan işlev deyiminde, arama işlevi için denetimi ve büyük olasılıkla bir değer döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlevler](../c-language/functions-c.md)