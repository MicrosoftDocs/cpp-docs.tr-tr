---
title: İşleç Aşırı Yüklemesi Genel Kuralları
ms.date: 11/04/2016
helpviewer_keywords:
- operator overloading [C++], rules
ms.assetid: eb2b3754-35f7-4832-b1da-c502893dc0c7
ms.openlocfilehash: da0bf04435118c819fc29efd3082d8d312e43006
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213404"
---
# <a name="general-rules-for-operator-overloading"></a>İşleç Aşırı Yüklemesi Genel Kuralları

Aşağıdaki kurallar, aşırı yüklenmiş işleçlerin nasıl uygulandığını kısıtlar. Ancak, bunlar ayrı olarak ele alınan [New](../cpp/new-operator-cpp.md) ve [Delete](../cpp/delete-operator-cpp.md) işleçleri için de geçerlidir.

- Gibi yeni işleçler tanımlayamazsınız **.**..

- Yerleşik veri türlerine uygulandığında işleçlerin anlamını yeniden tanımlayamazsınız.

- Aşırı yüklenmiş işleçler, statik olmayan bir sınıf üyesi işlevi ya da genel bir işlev olmalıdır. Özel veya korumalı sınıf üyelerine erişmesi gereken genel bir işlev, bu sınıfın bir arkadaşınız olarak bildirilmelidir. Genel bir işlev, sınıf veya numaralandırılmış tür olan veya bir sınıfa veya numaralandırılmış türe başvuru olan en az bir bağımsız değişken almalıdır. Örnek:

    ```cpp
    // rules_for_operator_overloading.cpp
    class Point
    {
    public:
        Point operator<( Point & );  // Declare a member operator
                                     //  overload.
        // Declare addition operators.
        friend Point operator+( Point&, int );
        friend Point operator+( int, Point& );
    };

    int main()
    {
    }
    ```

   Yukarıdaki kod örneği, bir üye işlevi olarak küçüktür işlecini bildirir; Ancak, ekleme işleçleri arkadaş erişimi olan genel işlevler olarak bildirilmiştir. Belirli bir operatör için birden fazla uygulamanın sağlandığını unutmayın. Önceki ekleme operatörü söz konusu olduğunda, commutativity 'yi kolaylaştırmak için iki uygulama sağlanır. Bu, bir,, `Point` ve gibi bir öğesine ekleyen operatörlerin `Point` **`int`** `Point` uygulanmasından kaynaklanıyor olabilir.

- İşleçler, yerleşik türlerle tipik kullanımları tarafından dikte edilen değer, gruplama ve işlenenlerin sayısına uyar. Bu nedenle, "2 ve 3. Ekle" kavramının "tür bir nesneye" eklenmesi `Point` , " *x* koordinatına 2 eklenerek ve *y* koordinamına eklenmek üzere 3 ' ün bir yolu yoktur.

- Üye işlevleri olarak belirtilen Birli İşleçler bağımsız değişken almaz; genel işlevler olarak bildirilirse, bir bağımsız değişken alırlar.

- Üye işlevleri olarak belirtilen ikili işleçler bir bağımsız değişken alır; genel işlevler olarak bildirilirse, iki bağımsız değişken alırlar.

- Bir işleç birli veya ikili işleç ( __&__ , __*__ , __+__ ve) olarak kullanılıyorsa __-__ , her bir kullanımı ayrı olarak aşırı yükleyebilirsiniz.

- Aşırı yüklenmiş işleçler varsayılan bağımsız değişkenlere sahip olamaz.

- Atama (**operator =**) hariç tüm aşırı yüklenmiş işleçler türetilmiş sınıflar tarafından devralınır.

- Üye işlevi aşırı yüklenmiş işleçleri için ilk bağımsız değişken, her zaman işlecinin çağrıldığı nesnenin sınıf türüdür (işlecin bildirildiği sınıf veya bu sınıftan türetilmiş bir sınıf). İlk bağımsız değişken için hiçbir dönüştürme sağlanmaz.

Operatörlerin herhangi birinin anlamı tamamen değişebileceğini unutmayın. Bu, ( **&** ), atama ( **=** ) ve işlev çağrısı işleçlerinin anlamını içerir. Ayrıca, yerleşik türler için güvenilede bir kimlik, işleç aşırı yüklemesi kullanılarak değiştirilebilir. Örneğin, aşağıdaki dört deyim genellikle tamamen değerlendirildikleri zaman eşdeğerdir:

```cpp
var = var + 1;
var += 1;
var++;
++var;
```

Bu kimlik, işleçleri aşırı yükleyen sınıf türleri için güvenilelemez. Üstelik, temel türler için bu işleçleri kullanan bazı gereksinimler, aşırı yüklenmiş işleçler için rahat bir şekilde indirgenir. Örneğin, toplama/atama işleci, **+=** sol işlenenin temel türlere uygulandığında l değeri olmasını gerektirir; operatör aşırı yüklendiğinde böyle bir gereksinim yoktur.

> [!NOTE]
> Tutarlılık açısından, aşırı yüklenmiş işleçleri tanımlarken yerleşik türlerin modelini izlemek genellikle en iyisidir. Aşırı yüklenmiş bir işlecin semantiği diğer bağlamlardaki anlamından önemli ölçüde farklıysa, faydalı olandan daha karmaşık olabilir.

## <a name="see-also"></a>Ayrıca bkz.

[İşleç aşırı yüklemesi](../cpp/operator-overloading.md)
