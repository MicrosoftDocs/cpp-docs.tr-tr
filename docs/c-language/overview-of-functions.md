---
title: İşlevlere genel bakış | Microsoft Docs
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
ms.openlocfilehash: b03357ed094684bb561eff9b790c090a1ebb0712
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46033634"
---
# <a name="overview-of-functions"></a>İşlevlere Genel Bakış

İşlevler bir tanım olmalıdır ve işlevi çağrılmadan önce bildirimi görünüyorsa bir tanımı bildirimi olarak hizmet verebilen olsa da bir bildirim olması gerekir. İşlev tanımı işlev gövdesini içerir — işlev çağrıldığında yürütülen kod.

Bir işlev bildirimi, adı, dönüş türü ve özniteliklerini programda başka yerde tanımlanmış bir işlev oluşturur. Bir işlev bildiriminin, işlev çağrısı gelmelidir. Çalışma zamanı işlevleri için bildirimleri içeren üst bilgi dosyaları, kodunuzun çalışma zamanı işlevi çağrısı önce dahil edilmemesinin nedeni budur. Bildirim türleri ve parametre sayısı hakkında bilgi varsa, bildirimi bir prototip olur. Bkz: [işlev prototipleri](../c-language/function-prototypes.md) daha fazla bilgi için.

Derleyici, sonraki çağrılarda işlevin parametrelerle işlev bağımsız değişkenlerinin türlerine karşılaştırın ve bağımsız değişken türlerinin parametre gerektiğinde türlerine dönüştürmek için prototip kullanır.

Bir işlev çağrısı yürütme denetimi için çağrılan işlev çağıran işlevden geçirir. Bağımsız değişken varsa, çağrılan işlev için değere göre geçirilir. Yürütülmesini bir `return` deyimi içinde çağrılan işlev çağıran işleve denetimi ve büyük olasılıkla bir değer döndürür.

## <a name="see-also"></a>Ayrıca Bkz.

[İşlevler](../c-language/functions-c.md)