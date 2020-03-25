---
title: Devralma (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- derived classes [C++]
- derived classes [C++], about derived classes
- classes [C++], derived
ms.assetid: 3534ca19-d9ed-4a40-be1b-b921ad0e6956
ms.openlocfilehash: 214900f8f36de0fa90ffcd6ca75f3a4e6e2c0777
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178268"
---
# <a name="inheritance--c"></a>Devralma (C++)

Bu bölümde, genişletilebilir programlar oluşturmak için türetilmiş sınıfların nasıl kullanılacağı açıklanmaktadır.

## <a name="overview"></a>Genel Bakış

Yeni sınıflar, "devralma" adlı bir mekanizma kullanılarak varolan sınıflardan türetilebilir ( [tek devralmayla](../cpp/single-inheritance.md)başlayan bilgilere bakın). Türetme için kullanılan sınıflara belirli bir türetilmiş sınıfın "temel sınıflar" denir. Türetilmiş bir sınıf aşağıdaki sözdizimini kullanarak bildirilmiştir:

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

Sınıfın etiketinden (ad) sonra, temel özellikler listesinin ardından bir "iki nokta üst üste" işareti görünür.  Bu şekilde adlandırılmış temel sınıflar önceden bildirilmiş olmalıdır.  Temel belirtimler, **genel**, **korumalı** veya **özel**anahtar sözcüklerinden biri olan bir erişim belirticisi içerebilir.  Bu erişim belirticileri temel sınıf adından önce görünür ve yalnızca o temel sınıfa uygulanır.  Bu tanımlayıcılar türetilmiş sınıfın temel sınıf üyelerini kullanma iznini denetler.  Temel sınıf üyelerine erişim hakkında bilgi için bkz. [member-Access Control](../cpp/member-access-control-cpp.md) .  Erişim belirticisi atlanırsa, bu temele erişim **özel**olarak değerlendirilir.  Temel belirtimlerde sanal devralmayı göstermek için **sanal** anahtar sözcük yer alabilir.  Bu anahtar sözcük erişim belirticisinden (varsa) önce veya sonra görünebilir.  Sanal devralma kullanılıyorsa, temel sınıf sanal bir temel sınıf olarak kabul edilir.

Virgülle ayırarak birden çok temel sınıf belirtilebilir.  Tek bir temel sınıf belirtilirse, devralma modeli [tek devralma](../cpp/single-inheritance.md)olur. Birden fazla temel sınıf belirtilirse, devralma modeline [birden fazla devralma](../cpp/multiple-base-classes.md)denir.

Aşağıdaki konular dahil edilmiştir:

- [Tek devralma](../cpp/single-inheritance.md)

- [Birden çok temel sınıf](../cpp/multiple-base-classes.md)

- [Sanal işlevler](../cpp/virtual-functions.md)

- [Açık geçersiz kılmalar](../cpp/explicit-overrides-cpp.md)

- [Soyut sınıflar](../cpp/abstract-classes-cpp.md)

- [Kapsam kurallarının Özeti](../cpp/summary-of-scope-rules.md)

[__Super](../cpp/super.md) ve [__interface](../cpp/interface.md) anahtar sözcükleri bu bölümde belgelenmiştir.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)
