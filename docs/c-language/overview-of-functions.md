---
description: 'Hakkında daha fazla bilgi edinin: IŞLEVLERE genel bakış'
title: İşlevlere Genel Bakış
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C++]
- control flow, function calls
ms.assetid: b6f4637f-02b9-49d8-8601-1f886bd2cfb9
ms.openlocfilehash: b68591d9300cb1a2f63c37c78f4cc03406e9d68f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97243152"
---
# <a name="overview-of-functions"></a>İşlevlere Genel Bakış

İşlevler bir tanıma sahip olmalıdır ve bildirimi olmalıdır, ancak bildirim işlev çağrılmadan önce görüntülenirse bir tanım bildirim olarak görev yapabilir. İşlev tanımı, işlev gövdesini içerir — işlev çağrıldığında yürütülen kod.

Bir işlev bildirimi, programda başka bir yerde tanımlanmış bir işlevin adını, dönüş türünü ve özniteliklerini belirler. İşlev bildirimi, işleve yapılan çağrıdan önce gelmelidir. Bu, çalışma zamanı işlevlerine yönelik bildirimleri içeren üst bilgi dosyalarının, bir çalışma zamanı işlevine çağrıdan önce kodunuza dahil edilmeleridir. Bildirimin tür ve parametre sayısı hakkında bilgi varsa, bildirim bir prototipi olur. Daha fazla bilgi için bkz. [Işlev prototipleri](../c-language/function-prototypes.md) .

Derleyici, sonraki çağrılarındaki bağımsız değişkenlerin türlerini işlevin parametreleriyle ve bağımsız değişkenlerin türlerini gerektiğinde parametre türlerine dönüştürmek için prototipi kullanır.

Bir işlev çağrısı, yürütme denetimini çağıran işlevden çağrılan işleve geçirir. Varsa bağımsız değişkenler değeri tarafından çağrılan işleve geçirilir. **`return`** Çağrılan işlev içindeki bir deyimin yürütülmesi denetim ve muhtemelen çağıran işleve bir değer döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[İşlevler](../c-language/functions-c.md)
