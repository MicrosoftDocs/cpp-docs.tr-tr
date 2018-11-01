---
title: Devralma (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- derived classes [C++]
- derived classes [C++], about derived classes
- classes [C++], derived
ms.assetid: 3534ca19-d9ed-4a40-be1b-b921ad0e6956
ms.openlocfilehash: 0180a2f7b41e3169bc9e25d8b598dbe2b84be088
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50508048"
---
# <a name="inheritance--c"></a>Devralma (C++)

Bu bölümde, genişletilebilir programlar oluşturmak için türetilmiş sınıfların nasıl kullanılacağı açıklanmaktadır.

## <a name="overview"></a>Genel Bakış

Yeni sınıflar "devralma" adı verilen bir mekanizma kullanılarak varolan sınıflardan türetilebilir türetilmiş (bakın bölümünden itibaren başlayarak bilgileri [tek devralma](../cpp/single-inheritance.md)). Türetme için kullanılan sınıflara belirli bir türetilmiş sınıfın "temel sınıflar" denir. Türetilmiş bir sınıf aşağıdaki sözdizimini kullanarak bildirilmiştir:

```cpp
class Derived : [virtual] [access-specifier] Base
{
   // member list
};
class Derived : [virtual] [access-specifier] Base1,
   [virtual] [access-specifier] Base2, . . .
{
   // member list
};
```

Sınıfın etiketinden (ad) sonra, temel özellikler listesinin ardından bir "iki nokta üst üste" işareti görünür.  Bu şekilde adlandırılmış temel sınıflar önceden bildirilmiş olmalıdır.  Temel belirtimler, anahtar sözcükleri biri olan bir erişim belirticisi içerebilir **genel**, **korumalı** veya **özel**.  Bu erişim belirticileri temel sınıf adından önce görünür ve yalnızca o temel sınıfa uygulanır.  Bu tanımlayıcılar türetilmiş sınıfın temel sınıf üyelerini kullanma iznini denetler.  Bkz: [üye erişim denetimi](../cpp/member-access-control-cpp.md) temel sınıf üyelerine için erişim hakkında bilgi için.  Erişim belirticisi atlanırsa, söz konusu temele erişim değerlendirilir **özel**.  Temel belirtimler, anahtar sözcüğünü içerebilir **sanal** sanal devralmayı belirtmek için.  Bu anahtar sözcük erişim belirticisinden (varsa) önce veya sonra görünebilir.  Sanal devralma kullanılıyorsa, temel sınıf sanal bir temel sınıf olarak kabul edilir.

Virgülle ayırarak birden çok temel sınıf belirtilebilir.  Tek bir temel sınıf belirtilmişse, devralma modeli alır [tek devralma](../cpp/single-inheritance.md). Birden fazla temel sınıf belirtilmişse, devralma modeli denir [birden çok devralma](../cpp/multiple-base-classes.md).

Aşağıdaki konular bulunur:

- [Tek devralma](../cpp/single-inheritance.md)

- [Birden çok taban sınıfı](../cpp/multiple-base-classes.md)

- [Sanal işlevler](../cpp/virtual-functions.md)

- [Açık geçersiz kılmalar](../cpp/explicit-overrides-cpp.md)

- [Soyut sınıflar](../cpp/abstract-classes-cpp.md)

- [Kapsam kuralları özeti](../cpp/summary-of-scope-rules.md)

[__Super](../cpp/super.md) ve [__interface](../cpp/interface.md) anahtar sözcükleri Bu bölümde belgelenmiştir.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)