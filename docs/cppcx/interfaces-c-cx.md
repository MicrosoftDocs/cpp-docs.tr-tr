---
title: Arabirimler (C++/CX)
ms.date: 01/22/2017
ms.assetid: 11034314-d54a-426d-923b-5ab7a6b9f8ce
ms.openlocfilehash: b904f041e34bcf5fda78fed11aaad4998ba5208a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366033"
---
# <a name="interfaces-ccx"></a>Arabirimler (C++/CX)

Bir ref sınıfı en fazla bir somut taban sınıftan devralabilir, ancak herhangi bir sayıda arabirim sınıfı uygulayabilir. Bir arabirim sınıfı (veya arabirim struct) kendisi birden çok arabirim sınıfları devralabilir (veya gerektirir), üye işlevlerini aşırı yükleyebilir ve tür parametreleri olabilir.

## <a name="characteristics"></a>Özellikler

Arabirim şu özelliklere sahiptir:

- Bir arabirim sınıfı (veya yapı) bir ad alanı içinde bildirilmelidir ve ortak veya özel erişilebilirlik olabilir. Meta verilere yalnızca ortak arabirimler yayılır.

- Arabirimin üyeleri özellikleri, yöntemleri ve olayları içerebilir.

- Tüm arayüz üyeleri örtülü olarak herkese açık ve sanaldır.

- Alanlara ve statik üyelere izin verilmez.

- Özellik, yöntem parametreleri veya iade değerleri olarak kullanılan türler yalnızca Windows Runtime türleri olabilir; bu temel türleri ve enum sınıf türlerini içerir.

## <a name="declaration-and-usage"></a>Beyan ve kullanım

Aşağıdaki örnek, arabirimin nasıl bildirilen gösteriş olduğunu gösterir. Arabirimin sınıf veya yapı türü olarak bildirilene dikkat edin.

[!code-cpp[cx_interfaces#01](../cppcx/codesnippet/CPP/interfacestest/class1.h#01)]

Bir arabirim uygulamak için, bir ref sınıfı veya ref struct bildirir ve sanal yöntemler ve özellikleri uygular. Arabirim ve uygulayıcı ref sınıfı, bu örnekte gösterildiği gibi aynı yöntem parametre adlarını kullanmalıdır:

[!code-cpp[cx_interfaces#02](../cppcx/codesnippet/CPP/interfacestest/class1.h#02)]

## <a name="interface-inheritance-hierarchies"></a>Arabirim devralma hiyerarşileri

Bir arabirim bir veya daha fazla arabirimden devralınabilir. Ancak bir ref sınıfı nın veya yapının aksine, bir arabirim devralınan arabirim üyelerini bildirmez. B arabirimi A arabiriminden, ref sınıfı C ise B'den devralıyorsa, C hem A hem de B'yi uygulamalıdır. Bu sonraki örnekte gösterilir.

[!code-cpp[cx_interfaces#03](../cppcx/codesnippet/CPP/interfacestest/class1.h#03)]

## <a name="implementing-interface-properties-and-events"></a>Arabirim özelliklerini ve olaylarını uygulama

Önceki örnekte gösterildiği gibi, arabirim özelliklerini uygulamak için önemsiz sanal özellikleri kullanabilirsiniz. Uygulama sınıfında özel getters ve ayarlayıcılar da sağlayabilirsiniz.  Hem verici hem de ayarlayıcı bir arabirim özelliğinde herkese açık olmalıdır.

[!code-cpp[cx_interfaces#04](../cppcx/codesnippet/CPP/interfacestest/class1.h#04)]

Arabirim yalnızca alırım veya yalnızca ayar özelliğini bildirirse, uygulama sınıfı açıkça bir getter veya ayarlayıcı sağlamalıdır.

[!code-cpp[cx_interfaces#05](../cppcx/codesnippet/CPP/interfacestest/class1.h#05)]

Uygulama sınıfındaki olaylar için özel ekleme ve kaldırma yöntemleri de uygulayabilirsiniz.

## <a name="explicit-interface-implementation"></a>Açık arayüz uygulaması

Bir ref sınıfı birden çok arabirim uygularve bu arabirimler, adları ve imzaları derleyiciyle aynı yöntemleri varsa, sınıf yönteminin uyguladığı arabirim yöntemini açıkça belirtmek için aşağıdaki sözdizimini kullanabilirsiniz.

[!code-cpp[cx_interfaces#06](../cppcx/codesnippet/CPP/interfacestest/class1.h#06)]

## <a name="generic-interfaces"></a>Genel arabirimler

C++/CX'te `generic` anahtar kelime, Windows Runtime parametreli türünü temsil etmek için kullanılır. Parametreli bir tür meta verilere yayılır ve tür parametrelerini destekleyen herhangi bir dilde yazılmış kod tarafından tüketilebilir. Windows Runtime bazı genel arabirimleri tanımlar (örneğin, [Windows:Foundation::Collections::IVector\<T>](/uwp/api/Windows.Foundation.Collections.IVector_T_)— ancak C++/CX'te ortak kullanıcı tanımlı genel arabirimlerin oluşturulmasını desteklemez. Ancak, özel genel arabirimler oluşturabilirsiniz.

Genel bir arabirim yazarken Windows Runtime türleri şu şekilde kullanılabilir:

- Bir bileşende `interface class` tanımlanan genel bir kullanıcının Windows meta veri dosyasına aktarılmasına izin verilmez; bu nedenle, ortak erişilebilirlik olamaz ve diğer .winmd dosyalarındaki istemci kodu bunu uygulayamaz. Aynı bileşendeki kamu ref sınıfları tarafından uygulanabilir. Genel bir ref sınıfı, özel bir üye olarak genel bir arabirim türüne sahip olabilir.

   Aşağıdaki kod snippet nasıl bir `interface class` genel beyan ve daha sonra özel bir ref sınıfında uygulamak ve bir kamu ref sınıfında özel bir üye olarak ref sınıfı kullanmak gösterir.

   [!code-cpp[cx_interfaces#07](../cppcx/codesnippet/CPP/interfacestest/class1.h#07)]

- Genel bir arabirim, erişilebilirliği, üyeleri yöneten, ilişkiler, temel sınıflar ve benzeri *kuralları* yöneten standart arabirim kurallarına uymalıdır.

- Genel bir arabirim, öncesindeki bir veya daha `typename` `class`fazla genel tür parametresini alabilir veya . Tür dışı parametreler desteklenmez.

- Bir tür parametresi herhangi bir Windows Runtime türü olabilir. Diğer bir süre, tür parametresi bir başvuru türü, değer türü, arabirim sınıfı, bir temsilci, temel bir tür veya ortak enum sınıfı olabilir.

- *Kapalı genel arabirim,* genel bir arabirimden devralan ve tüm tür parametreleri için somut tür bağımsız değişkenleri belirten bir arabirimdir. Genel olmayan bir özel arabirim kullanılabilir her yerde kullanılabilir.

- *Açık genel arabirim,* henüz somut bir tür sağlanamadan bir veya daha fazla tür parametresine sahip bir arabirimdir. Başka bir genel arabirimin tür bağımsız değişkeni olarak da dahil olmak üzere, bir türün kullanılabileceğinin her yerde kullanılabilir.

- Tek tek yöntemleri değil, yalnızca tüm arabirimi parametreleştirebilirsiniz.

- Tür parametreleri kısıtlanamaz.

- Kapalı genel arabirimde örtülü olarak oluşturulan uUID vardır. Kullanıcı UUID'yi belirtemez.

- Arabirimde, yöntem parametresi, iade değeri veya özellik te geçerli arabirime yapılan herhangi bir başvurunun geçerli anlık anlama atıfta bulunduğu varsayılır. Örneğin, *IMyIntf* *iMyIntf\<T>* anlamına gelir.

- Yöntem parametresi türü bir tür parametresi olduğunda, bu parametre veya değişkenin bildirimi, herhangi bir işaretçi, yerel başvuru veya işleme bildirimatörü olmadan tür parametresinin adını kullanır. Başka bir deyişle, asla "T^" yazmıyorsun.

- Şablonlanmış ref sınıfları özel olmalıdır. Genel arabirimleri uygulayabilirler ve şablon parametresi *T'yi* genel bağımsız değişken *T'ye*geçirebilirler. Şablonlanmış bir ref sınıfının her anlık kendisi bir ref sınıfıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Tür Sistemi](../cppcx/type-system-c-cx.md)<br/>
[C++/CX Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Ad Alanları Başvurusu](../cppcx/namespaces-reference-c-cx.md)
