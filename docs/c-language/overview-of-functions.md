---
title: İşlevlere Genel Bakış
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C++]
- control flow, function calls
ms.assetid: b6f4637f-02b9-49d8-8601-1f886bd2cfb9
ms.openlocfilehash: 3b2f2cfe5cd769b3cdaef002a970ad21c48162ac
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50557371"
---
# <a name="overview-of-functions"></a>İşlevlere Genel Bakış

İşlevler bir tanım olmalıdır ve işlevi çağrılmadan önce bildirimi görünüyorsa bir tanımı bildirimi olarak hizmet verebilen olsa da bir bildirim olması gerekir. İşlev tanımı işlev gövdesini içerir — işlev çağrıldığında yürütülen kod.

Bir işlev bildirimi, adı, dönüş türü ve özniteliklerini programda başka yerde tanımlanmış bir işlev oluşturur. Bir işlev bildiriminin, işlev çağrısı gelmelidir. Çalışma zamanı işlevleri için bildirimleri içeren üst bilgi dosyaları, kodunuzun çalışma zamanı işlevi çağrısı önce dahil edilmemesinin nedeni budur. Bildirim türleri ve parametre sayısı hakkında bilgi varsa, bildirimi bir prototip olur. Bkz: [işlev prototipleri](../c-language/function-prototypes.md) daha fazla bilgi için.

Derleyici, sonraki çağrılarda işlevin parametrelerle işlev bağımsız değişkenlerinin türlerine karşılaştırın ve bağımsız değişken türlerinin parametre gerektiğinde türlerine dönüştürmek için prototip kullanır.

Bir işlev çağrısı yürütme denetimi için çağrılan işlev çağıran işlevden geçirir. Bağımsız değişken varsa, çağrılan işlev için değere göre geçirilir. Yürütülmesini bir `return` deyimi içinde çağrılan işlev çağıran işleve denetimi ve büyük olasılıkla bir değer döndürür.

## <a name="see-also"></a>Ayrıca Bkz.

[İşlevler](../c-language/functions-c.md)