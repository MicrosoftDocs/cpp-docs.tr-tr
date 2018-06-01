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
ms.openlocfilehash: 7e9cd1a0ba57b5a2f0d5afb2d02ff9c21b7e0b2c
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34705432"
---
# <a name="general-rules-for-operator-overloading"></a>İşleç Aşırı Yüklemesi Genel Kuralları
Aşağıdaki kuralları nasıl aşırı yüklenmiş işleçler sınırlamak uygulanır. Bununla birlikte, bunlar için uygulanmaz [yeni](../cpp/new-operator-cpp.md) ve [silmek](../cpp/delete-operator-cpp.md) ayrı olarak ele alınmıştır işleçler.  
  
-   Yeni işleçleri gibi tanımlayamazsınız **.**.  
  
-   Yerleşik veri türlerine uygulandığında işleçleri anlamını tanımlanamaz.  
  
-   Aşırı yüklenmiş işleçler ya da statik olmayan sınıf üye işlevi veya genel bir işlev olmalıdır. Özel veya korumalı sınıf üyelerine erişimi gerektiren bir genel işlevi, o sınıfın arkadaş bildirilmesi gerekir. Genel işlevi, sınıf veya numaralandırılmış türde olan veya bir sınıf için bir başvuru veya numaralandırılmış türü en az bir değişken almanız gerekir. Örneğin:  
  
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
  
     Yukarıdaki kod örneğinde küçüktür bildirir-operatör olarak bir üye işlevi;'den Ancak, ek işleçleri friend erişimi genel işlevler bildirilir. Birden fazla uygulama için belirli bir işleç sağlanabilir unutmayın. Önceki Toplama işleci söz konusu olduğunda, iki uygulamaları commutativity kolaylaştırmak için sağlanır. Eklediğiniz yalnızca büyük olasılıkla bu işleçleri olan bir `Point` için bir `Point`, `int` için bir `Point`ve benzeri uygulanabilir.  
  
-   Gruplandırma öncelik işleçleri uymalı ve yerleşik türleri ile tipik kullanımları tarafından işlenen sayısı belirler. Bu nedenle, kavram hızlı bir yolu yoktur "2 ve 3 türünde bir nesne eklemek `Point`," eklenecek 2 bekleniyor *x* koordinat ve 3 eklenecek *y* koordinatı.  
  
-   Üye işlevleri bildirilen birli işleçleri bağımsız değişkenler almayan; genel işlevler bildirilen kullanırsanız, bunlar bir bağımsız değişken gerçekleştirin.  
  
-   İkili işleçler üye işlevleri bildirilen bir bağımsız değişken alın; genel işlevler bildirilen, bunlar iki bağımsız değişkenleri alır.  
  
-   Bir operatör bir birli ya da bir ikili işleç olarak kullanılıp kullanılamayacağını (**&**, **\***, **+**, ve **-**), her kullanım ayrı ayrı aşırı yüklenebilir.  
  
-   Aşırı yüklenmiş işleçler varsayılan bağımsız değişkenler sahip olamaz.  
  
-   Aşırı yüklenmiş tüm dışında atama işleçleri (`operator=`) türetilen sınıflar tarafından devralınır.  
  
-   Üye işlevini aşırı yüklenmiş işleçler için ilk bağımsız değişken nesne için sınıf tür her zaman olduğu işleci olan (işleci bildirilmiş veya bu sınıftan türetilen bir sınıfı sınıfı) çağrılır. Hiçbir dönüştürme ilk bağımsız değişkeni için sağlanır.  
  
 Herhangi bir işleci anlamını tamamen değiştirilebilir unutmayın. Adres, anlamını içeren (**&**), atama (**=**) ve işlev çağrısı işleçler. Ayrıca, üzerine yerleşik türleri için dayanıyordu kimlikleri İşleç aşırı yüklemesi kullanılarak değiştirilebilir. Örneğin, aşağıdaki dört ifadeyi tamamen değerlendirildiğinde genellikle eşdeğerdir:  
  
```  
var = var + 1;  
var += 1;  
var++;  
++var;  
```  
  
 Bu kimlik bağlı işleçleri aşırı sınıf türleri için dayanıyordu olamaz. Ayrıca, bazı temel türleri için bu işleci kullanın örtük gereksinimleri için aşırı yüklenmiş işleçler rahat. Örneğin, toplama/ataması işleci `+=`, sol işleneni bir l-temel türleri için; uygulandığında değer olmasını gerektirir işleci aşırı zaman böyle bir gereklilik değildir.  
  
> [!NOTE]
> Tutarlılık için tanımlama işleçleri aşırı zaman yerleşik türleri modelini izlemek idealdir. Aşırı yüklenmiş bir işleç semantiği anlamlarını diğer bağlamlarda önemli ölçüde farklıdır, daha kullanışlı daha kafa karıştırıcı olabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşleç Aşırı Yüklemesi](../cpp/operator-overloading.md)