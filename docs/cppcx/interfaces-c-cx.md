---
title: Arabirimler (C++/CX)
ms.date: 01/22/2017
ms.assetid: 11034314-d54a-426d-923b-5ab7a6b9f8ce
ms.openlocfilehash: df010468d5e90fe61ac2cf57c754ac5ed01b1c0f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230993"
---
# <a name="interfaces-ccx"></a>Arabirimler (C++/CX)

Başvuru sınıfı en fazla bir somut taban sınıftan devralınabilir olsa da, herhangi bir sayıda arabirim sınıfı uygulayabilir. Bir arabirim sınıfı (veya arabirim yapısı), birden çok arabirim sınıfı alabilir (veya gerektirebilir), üye işlevlerini aşırı yükleyebilir ve tür parametrelerine sahip olabilir.

## <a name="characteristics"></a>Özellikler

Bir arabirim şu özelliklere sahiptir:

- Bir arabirim sınıfı (veya yapısı) bir ad alanı içinde bildirilmelidir ve Public veya Private erişilebilirliği olabilir. Meta verilere yalnızca ortak arabirimler dağıtılır.

- Bir arabirimin üyeleri özellikler, Yöntemler ve olaylar içerebilir.

- Tüm arabirim üyeleri örtük olarak genel ve sanal.

- Alanlara ve statik üyelere izin verilmez.

- Özellikler, yöntem parametreleri veya dönüş değerleri olarak kullanılan türler yalnızca Windows Çalışma Zamanı türleri olabilir; Bu, temel türleri ve enum sınıfı türlerini içerir.

## <a name="declaration-and-usage"></a>Bildirim ve kullanım

Aşağıdaki örnek, bir arabirimin nasıl bildirilemeyeceğini gösterir. Bir arabirimin sınıf veya yapı türü olarak bildirilebilecek olduğuna dikkat edin.

[!code-cpp[cx_interfaces#01](../cppcx/codesnippet/CPP/interfacestest/class1.h#01)]

Bir arabirim uygulamak için bir başvuru sınıfı veya başvuru yapısı, sanal yöntemleri ve özellikleri bildirir ve uygular. Arabirim ve uygulama başvurusu sınıfı, bu örnekte gösterildiği gibi aynı yöntem parametresi adlarını kullanmalıdır:

[!code-cpp[cx_interfaces#02](../cppcx/codesnippet/CPP/interfacestest/class1.h#02)]

## <a name="interface-inheritance-hierarchies"></a>Arabirim devralma hiyerarşileri

Bir arabirim, bir veya daha fazla arabirimden devralınabilir. Ancak başvuru sınıfının ya da yapısının aksine, bir arabirim devralınan arabirim üyelerini bildirmez. B arabirimi A arabiriminden devralırsa ve C başvuru sınıfı B 'den devralırsa C, hem A hem de B 'yi uygulamalıdır. Bu, sonraki örnekte gösterilmiştir.

[!code-cpp[cx_interfaces#03](../cppcx/codesnippet/CPP/interfacestest/class1.h#03)]

## <a name="implementing-interface-properties-and-events"></a>Arabirim özelliklerini ve olayları uygulama

Önceki örnekte gösterildiği gibi, arabirim özelliklerini uygulamak için önemsiz sanal özellikleri kullanabilirsiniz. Ayrıca, uygulama sınıfında özel alıcılar ve ayarlayıcılar sağlayabilirsiniz.  Hem alıcı hem de ayarlayıcı, bir arabirim özelliğinde ortak olmalıdır.

[!code-cpp[cx_interfaces#04](../cppcx/codesnippet/CPP/interfacestest/class1.h#04)]

Bir arabirim yalnızca bir Al veya Ayarla özelliği bildirirse, uygulama sınıfı açıkça bir alıcı veya ayarlayıcı sağlamalıdır.

[!code-cpp[cx_interfaces#05](../cppcx/codesnippet/CPP/interfacestest/class1.h#05)]

Uygulama sınıfındaki olaylar için özel ekleme ve kaldırma yöntemleri de uygulayabilirsiniz.

## <a name="explicit-interface-implementation"></a>Açık arabirim uygulama

Bir başvuru sınıfı birden çok arabirim uygularsa ve bu arabirimlerde, adları ve imzaları derleyiciye özdeş olan yöntemler varsa, bir sınıf yönteminin uyguladığı arabirim yöntemini açıkça belirtmek için aşağıdaki sözdizimini kullanabilirsiniz.

[!code-cpp[cx_interfaces#06](../cppcx/codesnippet/CPP/interfacestest/class1.h#06)]

## <a name="generic-interfaces"></a>Genel arabirimler

C++/CX ' te, **`generic`** anahtar sözcüğü Windows çalışma zamanı parametreli bir türü temsil etmek için kullanılır. Parametreli bir tür meta verilerde yayınlanır ve tür parametrelerini destekleyen herhangi bir dilde yazılmış kod tarafından tüketilebilir. Windows Çalışma Zamanı bazı genel arabirimleri tanımlar — Örneğin, [Windows:: Foundation:: Collections:: IVector \<T> ](/uwp/api/windows.foundation.collections.ivector-1)—, ancak C++/cx'de ortak Kullanıcı tanımlı genel arabirimlerin oluşturulmasını desteklemez. Bununla birlikte, özel genel arabirimler de oluşturabilirsiniz.

Genel bir arabirim yazmak için Windows Çalışma Zamanı türlerinin nasıl kullanılabileceği aşağıda verilmiştir:

- Bir bileşende genel kullanıcı tanımlı **`interface class`** , Windows meta veri dosyasına yayılmayacak, bu nedenle genel erişilebilirliği olamaz ve diğer. winmd dosyalarındaki istemci kodu bunu uygulayamaz. Aynı bileşendeki ortak olmayan başvuru sınıfları tarafından uygulanabilir. Ortak bir başvuru sınıfı özel üye olarak genel bir arabirim türüne sahip olabilir.

   Aşağıdaki kod parçacığı, genel olarak nasıl bildirilemeyeceğini **`interface class`** ve sonra özel bir başvuru sınıfında nasıl uygulanacağını gösterir ve başvuru sınıfını ortak bir başvuru sınıfında özel üye olarak kullanır.

   [!code-cpp[cx_interfaces#07](../cppcx/codesnippet/CPP/interfacestest/class1.h#07)]

- Genel bir arabirim, erişilebilirliği, üyeleri *, ilişkileri,* temel sınıfları ve benzerlerini yöneten standart arabirim kurallarını izlemelidir.

- Genel arabirim, veya öncesinde olan bir veya daha fazla genel tür parametresi alabilir **`typename`** **`class`** . Tür olmayan parametreler desteklenmez.

- Tür parametresi herhangi bir Windows Çalışma Zamanı türü olabilir. Diğer bir deyişle, tür parametresi bir başvuru türü, bir değer türü, bir arabirim sınıfı, bir temsilci, temel tür veya genel enum sınıfı olabilir.

- *Kapalı bir genel arabirim* , genel arabirimden devralan ve tüm tür parametreleri için somut tür bağımsız değişkenlerini belirten bir arabirimdir. Genel olmayan özel bir arabirimin kullanılabilmesi için herhangi bir yerde kullanılabilir.

- *Açık genel arabirim* , hiçbir somut tür sağlanmadığından bir veya daha fazla tür parametresine sahip bir arabirimdir. Başka bir genel arabirimin tür bağımsız değişkeni olarak da dahil olmak üzere, bir türün kullanılabileceği her yerde kullanılabilir.

- Tek tek Yöntemler değil, yalnızca bir arabirimin tamamını parametreleştirebilirsiniz.

- Tür parametreleri kısıtlanamaz.

- Kapalı bir genel arabirimde örtük olarak oluşturulmuş bir UUID vardır. Kullanıcı UUID 'yi belirtemez.

- Arabiriminde, geçerli arabirime yönelik herhangi bir başvuru — bir yöntem parametresi, dönüş değeri veya özellik —, geçerli örnek oluşturma için başvurulacak varsayılır. Örneğin, *imytf* , * \<T> imıntf*anlamına gelir.

- Bir yöntem parametresinin türü bir tür parametresi olduğunda, bu parametrenin veya değişkenin bildirimi herhangi bir işaretçi, yerel başvuru veya tanıtıcı bildirimci olmadan tür parametresinin adını kullanır. Diğer bir deyişle, hiçbir şekilde "T ^" yazmayın.

- Şablonlu ref sınıfları Private olmalıdır. Bunlar genel arabirimler uygulayabilir ve şablon parametresi *t* parametresini *genel bağımsız değişkenine*geçirebilir. Şablonlu bir başvuru sınıfının her örneklenmesi bir başvuru sınıfıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Tür sistemi](../cppcx/type-system-c-cx.md)<br/>
[C++/CX dil başvurusu](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Ad alanı başvurusu](../cppcx/namespaces-reference-c-cx.md)
