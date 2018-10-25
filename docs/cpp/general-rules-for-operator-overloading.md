---
title: İşleç aşırı yüklemesi genel kuralları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- operator overloading [C++], rules
ms.assetid: eb2b3754-35f7-4832-b1da-c502893dc0c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3a6eb1b97acfe2fa41511433de3990da8923de7d
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50059551"
---
# <a name="general-rules-for-operator-overloading"></a>İşleç Aşırı Yüklemesi Genel Kuralları

Aşağıdaki kuralları nasıl aşırı yüklenmiş işleçler sınırlamak uygulanır. Ancak, bunlar için geçerli değildir [yeni](../cpp/new-operator-cpp.md) ve [Sil](../cpp/delete-operator-cpp.md) işleçler, ayrı ayrı ele alınmaktadır.

- Yeni işleçleri gibi tanımlanamaz **.**.

- Anlamı yerleşik veri türlerine uygulandığında işleçleri yeniden tanımlanamaz.

- Aşırı yüklenmiş işleçler, ya da statik olmayan sınıf üyesi işlevi veya genel bir işlev olmalıdır. Özel veya korumalı sınıf üyelerine erişimi gerektiren bir genel işlev, söz konusu sınıfın arkadaş bildirilmelidir. Genel bir işlev sınıfı veya numaralandırılmış tür olan veya bir sınıf başvurusu veya listelenmiş türü en az bir bağımsız değişken almalıdır. Örneğin:

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

   Yukarıdaki kod örneğinde daha az bildirir-işleci bir üye işlev; olarak Ancak, toplama işleçleri öğesine friend erişimi olan genel işlevleri bildirilir. Birden fazla uygulama için belirli bir işleç sağlanabileceğini unutmayın. Önceki Toplama işleci söz konusu olduğunda iki uygulamaları commutativity kolaylaştırmak için sağlanır. Eklediğiniz yalnızca büyük olasılıkla bu işleçleri olan bir `Point` için bir `Point`, **int** için bir `Point`ve benzeri uygulanabilir.

- Gruplandırma işleçleri, öncelik uyma ve işlenenleri sayısı ile yerleşik türleri tipik kullanımları tarafından dikte. Bu nedenle, bir kavramı hızlı bir yolu yoktur "2 ve 3 türünde bir nesne eklemek `Point`," eklenecek 2 bekleniyor *x* koordinat ve 3 eklenecek *y* koordine edin.

- Birli işleçler üye işlevleri bildirilen bağımsız değişken almaz; Genel işlevleri bildirilen, bunlar bir bağımsız değişken alın.

- İkili işleçler üye işlevleri bildirilen bir bağımsız değişkenini alabilir; Genel işlevleri bildirilen, bunlar iki bağımsız değişken almaz.

- Bir işleç bir birli veya ikili işleç olarak kullanılıp kullanılamayacağını (__&__, __*__, __+__, ve __-__), ayrı ayrı her kullanım aşırı yükleyebilirler.

- Aşırı yüklenmiş işleçler, varsayılan bağımsız değişkenlere sahip olamaz.

- Tüm aşırı dışında atama işleçleri (**işleç =**) türetilmiş sınıflar tarafından devralınır.

- Her zaman için nesnenin sınıf türünün üye işlev aşırı yüklenmiş işleçler için ilk bağımsız değişken olduğundan, işleç (işleç bildirilen veya bu sınıftan türetilmiş bir sınıf sınıf) çağrılır. Hiçbir dönüştürme için ilk bağımsız değişken sağlanır.

Herhangi bir işleci anlamı tümüyle değiştirilebilir unutmayın. Address-of anlamını içeren (**&**), atama (**=**) ve işleç çağrısı işleçleri. Ayrıca, İşleç aşırı yüklemesi kullanarak temel yerleşik türler için dayanan kimlikleri değiştirilebilir. Örneğin, aşağıdaki dört ifade değerlendirildiğinde tamamen genellikle eşdeğerdir:

```cpp
var = var + 1;
var += 1;
var++;
++var;
```

Bu kimliği üzerinde aşırı yükleme işleçleri olan sınıf türleri için dayanan olamaz. Ayrıca, bazı temel türler için bu işleçlerin kullanımda örtük gereksinimleri için aşırı yüklenmiş işleçler esnek. Örneğin, toplama/atama işlecini **+=**, sol işlenen bir l-; temel türlerine uygulandığında bir değer olmasını gerektirir işleci aşırı yüklendiğinde bu tür bir gereksinim değildir.

> [!NOTE]
> Tutarlılık sağlamak için yerleşik türler modelini tanımlama işleçler aşırı yüklendiğinde izlemek idealdir. Aşırı yüklenmiş bir işleç semantiği anlamını diğer bağlamlarda önemli ölçüde farklılık, daha faydalı daha kafa karıştırıcı olabilir.

## <a name="see-also"></a>Ayrıca bkz.

[İşleç Aşırı Yüklemesi](../cpp/operator-overloading.md)