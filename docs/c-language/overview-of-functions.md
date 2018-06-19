---
title: İşlevlerine genel bakış | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- functions [C++]
- control flow, function calls
ms.assetid: b6f4637f-02b9-49d8-8601-1f886bd2cfb9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eb5d7dbdfb5206a29e217a5de73ee492be6c28ab
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32385812"
---
# <a name="overview-of-functions"></a>İşlevlere Genel Bakış
İşlevler bir tanım olmalıdır ve işlevi çağrılmadan önce bildirimi görünürse bir tanımı bildirimi olarak hizmet verebilir rağmen bir bildirimi sahip olmalıdır. İşlev gövdesi işlev tanımı içerir — işlevi çağrıldığında yürütülen kodu.  
  
 Bir işlev bildirimi adını, dönüş türü ve başka bir programda tanımlı bir işlevin öznitelikleri oluşturur. Bir işlev bildirimi işlevi çağrısında gelmelidir. Çalışma zamanı işlevleri için bildirimleri içeren üst bilgi dosyaları, kodunuzun çalışma zamanı işlevi çağrısı önce yer alan nedeni budur. Bildirim parametre sayısı ve türleri hakkında bilgi varsa, bir prototip bildirimidir. Bkz: [işlev prototipleri](../c-language/function-prototypes.md) daha fazla bilgi için.  
  
 Derleyici prototip işlev parametreleri işleviyle yapılan sonraki çağrılar değişkenlerinde türlerini karşılaştırmasına ve bağımsız değişkenlerden tür parametrelerinin gerektiğinde türlerine dönüştürmek için kullanır.  
  
 Bir işlev çağrısı yürütme denetimi çağrılan işlev çağırma işlevinden geçirir. Bağımsız değişkenler varsa, değeri tarafından çağrılan işlev geçirilir. Yürütme işlemi bir `return` çağrılan işlev deyiminde, arama işlevi için denetimi ve büyük olasılıkla bir değer döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlevler](../c-language/functions-c.md)