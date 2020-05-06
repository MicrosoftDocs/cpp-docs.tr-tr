---
title: İşlevlere Genel Bakış
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C++]
- control flow, function calls
ms.assetid: b6f4637f-02b9-49d8-8601-1f886bd2cfb9
ms.openlocfilehash: 1c54dcdeec1bad1ffbd335d411e39c77be0ad961
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62232292"
---
# <a name="overview-of-functions"></a>İşlevlere Genel Bakış

İşlevler bir tanıma sahip olmalıdır ve bildirimi olmalıdır, ancak bildirim işlev çağrılmadan önce görüntülenirse bir tanım bildirim olarak görev yapabilir. İşlev tanımı, işlev gövdesini içerir — işlev çağrıldığında yürütülen kod.

Bir işlev bildirimi, programda başka bir yerde tanımlanmış bir işlevin adını, dönüş türünü ve özniteliklerini belirler. İşlev bildirimi, işleve yapılan çağrıdan önce gelmelidir. Bu, çalışma zamanı işlevlerine yönelik bildirimleri içeren üst bilgi dosyalarının, bir çalışma zamanı işlevine çağrıdan önce kodunuza dahil edilmeleridir. Bildirimin tür ve parametre sayısı hakkında bilgi varsa, bildirim bir prototipi olur. Daha fazla bilgi için bkz. [Işlev prototipleri](../c-language/function-prototypes.md) .

Derleyici, sonraki çağrılarındaki bağımsız değişkenlerin türlerini işlevin parametreleriyle ve bağımsız değişkenlerin türlerini gerektiğinde parametre türlerine dönüştürmek için prototipi kullanır.

Bir işlev çağrısı, yürütme denetimini çağıran işlevden çağrılan işleve geçirir. Varsa bağımsız değişkenler değeri tarafından çağrılan işleve geçirilir. Çağrılan işlev içindeki `return` bir deyimin yürütülmesi denetim ve muhtemelen çağıran işleve bir değer döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[İşlevler](../c-language/functions-c.md)
