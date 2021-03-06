---
description: 'Daha fazla bilgi edinin: geçici nesneler'
title: Geçici Nesneler
ms.date: 11/04/2016
helpviewer_keywords:
- temporary objects
- objects [C++], temporary
ms.assetid: 4c8cec02-391e-4225-9bc6-06d150201412
ms.openlocfilehash: d827568013b3684c2126887d390ecbf223c46da5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97164751"
---
# <a name="temporary-objects"></a>Geçici Nesneler

Bazı durumlarda, derleyicinin geçici nesneler oluşturması gerekir. Bu geçici nesneler aşağıdaki nedenlerde oluşturulabilir:

- **`const`** Başlatılmış olan başvurunun temel alınan türünden farklı bir tür başlatıcısıyla başvuru başlatmak için.

- Kullanıcı tanımlı bir tür döndüren bir işlevin dönüş değerini depolamak için. Bu geçici öğeler, yalnızca programınız nesnenin dönüş türünü kopyalamıyorsa oluşturulur. Örneğin:

    ```cpp
    UDT Func1();    //  Declare a function that returns a user-defined
                    //   type.

    ...

    Func1();        //  Call Func1, but discard return value.
                    //  A temporary object is created to store the return
                    //   value.
    ```

   Dönüş değeri başka bir nesneye kopyalanmadığından geçici bir nesne oluşturulur. Geçici öğelerin oluşturulduğu diğer bir sık karşılaşılan durum da aşırı yüklenmiş işleç işlevlerinin çağrılması gereken ifade değerlendirmesidir. Bu aşırı yüklenmiş işleç işlevleri, genellikle başka bir nesneye kopyalanmayan kullanıcı tanımlı bir tür döndürür.

   `ComplexResult = Complex1 + Complex2 + Complex3` ifadesini göz önünde bulundurun. `Complex1 + Complex2` ifadesi değerlendirilir ve sonuç geçici bir nesnede depolanır. Ardından, geçici ifade  `+ Complex3` değerlendirilir ve sonuç öğesine kopyalanır `ComplexResult` (atama işlecinin aşırı yüklü olmadığı varsayılarak).

- Bir atamanın sonucunu kullanıcı tanımlı türe depolamak için. Belirli bir türden nesne kullanıcı tanımlı bir türe açıkça dönüştürüldüğünde, yeni nesne geçici bir nesne olarak oluşturulur.

Geçici nesneler, oluşturulma ve yok edilme noktalarına göre tanımlanan bir ömre sahiptir. Birden fazla geçici nesne oluşturan bir ifade, bunları sonuçta oluşturuldukları sıranın tersiyle yok eder. Yok etme işleminin gerçekleştiği noktalar aşağıdaki tabloda gösterilmektedir.

### <a name="destruction-points-for-temporary-objects"></a>Geçici Nesneler için Yok Etme Noktaları

|Geçici Öğenin Oluşturulma Nedeni|Yok Etme Noktası|
|------------------------------|-----------------------|
|İfade değerlendirmesinin sonucu|İfade değerlendirmesinin sonucu olarak oluşturulan tüm geçiciler, ifade deyiminin sonunda (noktalı virgül) veya,,,, **`for`** **`if`** **`while`** **`do`** ve **`switch`** deyimleri için denetim ifadelerinin sonunda yok edilir.|
|**`const`** Başvuruları başlatma|Bir başlatıcı başlatılan başvuruyla aynı türden bir l değeri değilse, temel alınan nesne türünün geçici öğesi oluşturulur ve başlatma ifadesiyle başlatılır. Bu geçici nesne, bağlı olduğu başvuru nesnesi yok edildikten hemen sonra yok edilir.|
