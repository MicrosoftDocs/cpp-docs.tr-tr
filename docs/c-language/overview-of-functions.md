---
title: İşlevlere Genel Bakış
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C++]
- control flow, function calls
ms.assetid: b6f4637f-02b9-49d8-8601-1f886bd2cfb9
ms.openlocfilehash: 1c54dcdeec1bad1ffbd335d411e39c77be0ad961
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56150330"
---
# <a name="overview-of-functions"></a>İşlevlere Genel Bakış

İşlevler bir tanım olmalıdır ve işlevi çağrılmadan önce bildirimi görünüyorsa bir tanımı bildirimi olarak hizmet verebilen olsa da bir bildirim olması gerekir. İşlev tanımı işlev gövdesini içerir — işlev çağrıldığında yürütülen kod.

Bir işlev bildirimi, adı, dönüş türü ve özniteliklerini programda başka yerde tanımlanmış bir işlev oluşturur. Bir işlev bildiriminin, işlev çağrısı gelmelidir. Çalışma zamanı işlevleri için bildirimleri içeren üst bilgi dosyaları, kodunuzun çalışma zamanı işlevi çağrısı önce dahil edilmemesinin nedeni budur. Bildirim türleri ve parametre sayısı hakkında bilgi varsa, bildirimi bir prototip olur. Bkz: [işlev prototipleri](../c-language/function-prototypes.md) daha fazla bilgi için.

Derleyici, sonraki çağrılarda işlevin parametrelerle işlev bağımsız değişkenlerinin türlerine karşılaştırın ve bağımsız değişken türlerinin parametre gerektiğinde türlerine dönüştürmek için prototip kullanır.

Bir işlev çağrısı yürütme denetimi için çağrılan işlev çağıran işlevden geçirir. Bağımsız değişken varsa, çağrılan işlev için değere göre geçirilir. Yürütülmesini bir `return` deyimi içinde çağrılan işlev çağıran işleve denetimi ve büyük olasılıkla bir değer döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[İşlevler](../c-language/functions-c.md)
