---
title: Devralma  [C++]
ms.date: 11/04/2016
helpviewer_keywords:
- derived classes [C++]
- derived classes [C++], about derived classes
- classes [C++], derived
ms.assetid: 3534ca19-d9ed-4a40-be1b-b921ad0e6956
ms.openlocfilehash: ab8425a916eb96f6419c67a76fa401716ad84631
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87232267"
---
# <a name="inheritance--c"></a>Devralma  [C++]

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

Sınıfın etiketinden (ad) sonra, temel özellikler listesinin ardından bir "iki nokta üst üste" işareti görünür.  Bu şekilde adlandırılmış temel sınıflar önceden bildirilmiş olmalıdır.  Temel belirtimlerde, veya anahtar sözcüklerinden biri olan bir erişim belirticisi bulunabilir **`public`** **`protected`** **`private`** .  Bu erişim belirticileri temel sınıf adından önce görünür ve yalnızca o temel sınıfa uygulanır.  Bu tanımlayıcılar türetilmiş sınıfın temel sınıf üyelerini kullanma iznini denetler.  Temel sınıf üyelerine erişim hakkında bilgi için bkz. [member-Access Control](../cpp/member-access-control-cpp.md) .  Erişim belirticisi atlanırsa, bu temele erişim kabul edilir **`private`** .  Taban belirtimleri, **`virtual`** sanal devralmayı göstermek için anahtar sözcüğünü içerebilir.  Bu anahtar sözcük erişim belirticisinden (varsa) önce veya sonra görünebilir.  Sanal devralma kullanılıyorsa, temel sınıf sanal bir temel sınıf olarak kabul edilir.

Virgülle ayırarak birden çok temel sınıf belirtilebilir.  Tek bir temel sınıf belirtilirse, devralma modeli [tek devralma](../cpp/single-inheritance.md)olur. Birden fazla temel sınıf belirtilirse, devralma modeline [birden fazla devralma](../cpp/multiple-base-classes.md)denir.

Aşağıdaki konular dahil edilmiştir:

- [Tek devralma](../cpp/single-inheritance.md)

- [Birden çok taban sınıfı](../cpp/multiple-base-classes.md)

- [Sanal işlevler](../cpp/virtual-functions.md)

- [Açık geçersiz kılmalar](../cpp/explicit-overrides-cpp.md)

- [Soyut sınıflar](../cpp/abstract-classes-cpp.md)

- [Kapsam kuralları özeti](../cpp/summary-of-scope-rules.md)

[__Super](../cpp/super.md) ve [__interface](../cpp/interface.md) anahtar sözcükleri bu bölümde belgelenmiştir.

## <a name="see-also"></a>Ayrıca bkz.

[C++ dil başvurusu](../cpp/cpp-language-reference.md)
