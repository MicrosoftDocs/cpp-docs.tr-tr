---
title: Birden çok taban sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- base classes [C++], multiple
- derived classes [C++], multiple bases
- multiple inheritance, class declaration
- multiple base classes [C++]
ms.assetid: a30c69fe-401c-4a87-96a0-e0da70c7c740
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1b0dd2da0da84b6705fc1fdef2858cd45f181910
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46113948"
---
# <a name="multiple-base-classes"></a>Birden Çok Taban Sınıfı

Birden fazla temel sınıftan türetilmiş bir sınıf. (Burada sınıflar türetilen birden fazla temel sınıftan) bir birden çok devralma modeli temel sınıflar kullanılarak belirtilen *temel-liste* dilbilgisi öğesi. Örneğin, sınıf bildirimi `CollectionOfBook`, türetilmiş `Collection` ve `Book`, belirtilebilir:

```cpp
// deriv_MultipleBaseClasses.cpp
// compile with: /LD
class Collection {
};
class Book {};
class CollectionOfBook : public Book, public Collection {
    // New members
};
```

Temel sınıflar belirtildiği sırayı burada oluşturucular ve Yıkıcılar çağrılmadan belirli durumlarda dışındaki önemli değil. Bu durumlarda, temel sınıflar belirtildiği sırayı aşağıdakiler etkiler:

- Oluşturucu gerçekleştiğinde tarafından hangi başlatma sırası. Kodunuzu dayanıyorsa `Book` kısmı `CollectionOfBook` önce başlatılması için `Collection` bölümü belirtimi sırası önemlidir. Başlatma sınıfları, belirtilen sırada gerçekleşir *temel-liste*.

- Temizleme yok edicinin çağrılmadığına sırası. Yine, belirli bir sınıfın "bölümüne" diğer bölümü yok ediliyorken mevcut olması gerekir, bu sıra önemlidir. Belirtilen sınıfların ters sırada yok ediciler çağrılır *temel-liste*.

    > [!NOTE]
    >  Temel sınıfların belirtimi sırası sınıfının bellek düzeni etkileyebilir. Bellekte temel üye bazında tabanlı bir programlama kararlar vermeyin.

Belirtirken *temel-liste*, aynı sınıf adı birden çok kez belirtilemez. Ancak, bir sınıf birden çok kez dolaylı bir temel türetilmiş bir sınıf olması mümkündür.

## <a name="virtual-base-classes"></a>Sanal temel sınıflar

Bir sınıf türetilmiş bir sınıfın bir kereden fazla dolaylı temel sınıfı olabileceği için C++ bu temel sınıfların çalışma biçimini iyileştiren bir yöntem sağlar. Sanal temel sınıflar, alandan kazanmak ve birden fazla devralma kullanan sınıf hiyerarşilerinde belirsizliklerden kaçınmak için bir yol sunar.

Sanal olmayan her nesne, temel sınıfta tanımlanmış veri üyelerinin bir kopyasını içerir. Bu çoğaltma alanı boşa harcar ve bunlara eriştiğinizde temel sınıf üyelerinin hangi kopyasını istediğinizi belirtmenizi gerektirir.

Temel sınıf sanal bir temel olarak belirtildiğinde, veri üyeleri çoğaltılmadan bir kereden fazla dolaylı temel olarak görev alabilir. Veri üyelerinin tek bir kopyası, onu sanal temel olarak kullanan tüm temel sınıflar tarafından paylaşılır.

Sanal bir temel sınıf bildirilirken **sanal** anahtar sözcüğü türetilmiş sınıfların temel listelerinde görünür.

Sınıf hiyerarşisini, sanal bir öğle yemeği çizgi grafiğini gösteren aşağıdaki şekilde görebilirsiniz.

![Sanal öğle yemeği çizgi grafiği](../cpp/media/vc38xp1.gif "vc38XP1") sanal öğle yemeği çizgi grafiği

Şekilde, `Queue` hem `CashierQueue` hem de `LunchQueue` için temel sınıftır. Ancak, iki sınıf da `LunchCashierQueue` oluşturacak şekilde birleştirildiğinde, aşağıdaki sorun ortaya çıkar: yeni sınıf biri `Queue` öğesinden, diğeri `CashierQueue` öğesinden alınan `LunchQueue` türünde iki alt nesne içerir. Aşağıdaki şekilde, kavramsal bellek düzeni (gerçek bellek düzeni iyileştirilebilir) gösterilmektedir.

![Sanal öğle yemeği&#45;çizgi grafiği nesnesi](../cpp/media/vc38xp2.gif "vc38XP2") sanal öğle yemeği çizgi grafiği nesnesi

`Queue` nesnesinde iki `LunchCashierQueue` alt nesnesi olduğuna dikkat edin. Aşağıdaki kod, `Queue` öğesinin sanal bir temel sınıf olduğunu bildirir:

```cpp
// deriv_VirtualBaseClasses.cpp
// compile with: /LD
class Queue {};
class CashierQueue : virtual public Queue {};
class LunchQueue : virtual public Queue {};
class LunchCashierQueue : public LunchQueue, public CashierQueue {};
```

**Sanal** anahtar sözcüğü, yalnızca bir alt nesneye kopyasını sağlar `Queue` dahildir (Aşağıdaki şekle bakın).

![Sanal öğle yemeği&#45;çizgi grafiği nesnesi, sanal temel sınıflar](../cpp/media/vc38xp3.gif "vc38XP3") sanal temel sınıflarla sanal öğle yemeği çizgi grafiği nesnesi

Bir sınıfta, belirli bir türden sanal bileşen ve sanal olmayan bileşen olabilir. Bu, aşağıdaki şekilde gösterilen koşullarda ortaya çıkar.

![Bir sınıfın sanal ve sanal olmayan bileşenleri](../cpp/media/vc38xp4.gif "vc38XP4") sanal ve sanal olmayan bileşenleri aynı sınıfın

Şekilde, `CashierQueue` ve `LunchQueue` sanal temel sınıf olarak `Queue` kullanmaktadır. Ancak `TakeoutQueue`, sanal temel sınıf olarak değil, temel sınıf olarak `Queue` belirtir. Bu nedenle, `LunchTakeoutCashierQueue``Queue` türünden iki alt nesneye sahiptir: biri `LunchCashierQueue` içeren devralma yolundan, diğeri ise `TakeoutQueue` içeren yoldan alınmıştır. Bu, aşağıdaki şekilde gösterilmiştir:

![Nesne düzeni sanal ve sanal olmayan devralma](../cpp/media/vc38xp5.gif "vc38XP5") sanal ve sanal olmayan devralma ile nesne düzeni

> [!NOTE]
>  Sanal devralma, sanal olmayan devralmayla karşılaştırıldığında önemli boyut avantajları sağlar. Ancak, ek işlem yükü ortaya çıkarabilir.

Türetilmiş bir sınıf sanal bir temel sınıftan devraldığı sanal bir işlemi geçersiz kılırsa ve türetilmiş temel sınıfın oluşturucusu veya yıkıcısı sanal temel sınıfa yönelik bir işaretçiyi kullanarak bu işlevi çağırırsa, derleyici sanal temellere sahip sınıflara ek gizli "vtordisk" alanları sunabilir. `/vd0` Derleyici seçeneği, gizli vtordisp Oluşturucu/yıkıcı yer değiştirme üyesinin eklenmesini engeller. `/vd1` Derleyici seçeneği, varsayılan olarak, bunları gerekli nerede sağlar. Yalnızca tüm sınıf oluşturucularının ve yıkıcılarının sanal olarak sanal işlevleri çağırdığından eminseniz vtordisps'i kapatın.

`/vd` Derleyici seçeneği, tüm derleme modülünü etkiler. Kullanım `vtordisp` engellemek ve ardından yeniden etkinleştirmek için pragma `vtordisp` alanlarını sınıf sınıf olarak:

```cpp
#pragma vtordisp( off )
class GetReal : virtual public { ... };
\#pragma vtordisp( on )
```

## <a name="name-ambiguities"></a>Ad belirsizlikleri

Birden çok devralma birden fazla yol boyunca devralınacak adları için olasılık sunar. Sınıf üyesi adları bu yolları boyunca mutlaka özgü değildir. Bu ad çakışmalarını "belirsizlikleri." olarak adlandırılır

Bir sınıf üyesine başvuran herhangi bir ifade, belirsiz bir başvuru yapmanız gerekir. Aşağıdaki örnek nasıl belirsizlikleri geliştirme gösterir:

```cpp
// deriv_NameAmbiguities.cpp
// compile with: /LD
// Declare two base classes, A and B.
class A {
public:
    unsigned a;
    unsigned b();
};

class B {
public:
    unsigned a();  // Note that class A also has a member "a"
    int b();       //  and a member "b".
    char c;
};

// Define class C as derived from A and B.
class C : public A, public B {};
```

Belirsiz olduğundan aşağıdaki belirsiz olduğu gibi önceki sınıf bildirimleri verildiğinde, kod olup olmadığını `b` başvurduğu `b` içinde `A` veya `B`:

```cpp
C *pc = new C;

pc->b();
```

Yukarıdaki örnekte göz önünde bulundurun. Çünkü adı `a` iki sınıf üyesi `A` ve sınıf `B`, derleyicinin hangi ayrım `a` çağrılacak işlev belirler. Birden fazla işlev, nesne, türü veya numaralandırıcı başvuruda bulunuyorsa, üye erişimi belirsiz.

Derleyici, bu sırada testleri gerçekleştirerek belirsizlikleri algılar:

1. Adına erişim (yalnızca açıklandığı gibi) belirsiz ise, bir hata iletisi oluşturulur.

1. Bunlar, aşırı yüklenmiş işlevler belirsiz ise çözümlenir.

1. Üye erişim izni adına erişim ihlal edilirse, bir hata iletisi oluşturulur. (Daha fazla bilgi için [üye erişim denetimi](../cpp/member-access-control-cpp.md).)

Bir ifade bir belirsizlik devralma yoluyla vermediğinde adıyla söz konusu sınıfın adını nitelendirme tarafından el ile çözebilirsiniz. Önceki örnekte hiçbir belirsizlikleri ile düzgün şekilde derleme yapmak için kodu gibi kullanın:

```cpp
C *pc = new C;

pc->B::a();
```

> [!NOTE]
>  Zaman `C` bildirildiğinde, hatalara neden olanağına sahip olduğunda `B` kapsamı içinde başvurulan `C`. Hata, Bununla birlikte, nitelenmemiş bir başvuru kadar verilen `B` gerçekten gerçekleştirilir `C`kullanıcının kapsam.

### <a name="dominance"></a>Baskınlık

Devralma grafiğiyle birden fazla ada (işlev, nesne veya numaralandırma) ulaşılabilir. Bu gibi durumlar, sanal olmayan temel sınıflarla belirsiz olarak kabul edilir. Adlardan biri diğerinden "baskın olmadığı" sürece sanal temel sınıflarla da belirsiz olurlar.

Bir ad, iki sınıfta da tanımlanırsa ve bir sınıf diğerinden türetilirse diğer addan baskın olur. Baskın ad türetilmiş sınıftaki addır; bu ad aşağıdaki örnekte gösterildiği gibi bir belirsizliğin ortaya çıkabileceği durumlarda kullanılır:

```cpp
// deriv_Dominance.cpp
// compile with: /LD
class A {
public:
    int a;
};

class B : public virtual A {
public:
    int a();
};

class C : public virtual A {};

class D : public B, public C {
public:
    D() { a(); } // Not ambiguous. B::a() dominates A::a.
};
```

### <a name="ambiguous-conversions"></a>Belirsiz dönüşümler

Açık ve örtük dönüştürmelerine işaretçileri veya başvuruları sınıf türleri için belirsizliğe neden olabilir. Sonraki şekilde, temel sınıflar, belirsiz dönüştürme işaretçileri aşağıda gösterilmiştir:

- Bir nesne türü bildirimini `D`.

- Address-of işlecini etkisi (**&**), bu nesneye. Address-of işleci nesnenin temel adresi her zaman kaynakları unutmayın.

- Açıkça temel sınıf türüne address-of işleci kullanılarak elde edilen işaretçi dönüştürme etkisini `A`. Coercing türüne nesnenin adresini Not `A*` her zaman derleyici yetecek kadar bilgi türü için hangi alt nesneye sağlamaz `A` seçmek için; bu durumda, iki alt nesne yok.

![Temel sınıflar için işaretçiler belirsiz dönüştürme](../cpp/media/vc38xt1.gif "vc38XT1") temel sınıflar, belirsiz dönüştürme işaretçileri

Türüne dönüştürme `A*` (işaretçiye `A`) türünde hangi alt nesneye ayrım mümkün değildir çünkü belirsiz `A` doğru olduğundan. Not: şu şekilde kullanmak için ortalama hangi alt nesneye açıkça belirterek belirsizlik kaçınabilirsiniz

```cpp
(A *)(B *)&d       // Use B subobject.
(A *)(C *)&d       // Use C subobject.
```

### <a name="ambiguities-and-virtual-base-classes"></a>Belirsizlikler ve sanal tabanlı sınıflar

Sanal temel sınıflar kullanılırsa, işlevler, nesneler, türler ve numaralandırıcılara birden çok devralma yolu üzerinde erişilebilir. Temel sınıfın yalnızca tek bir örneği olduğundan, bu adlara erişirken belirsizlik olmaz.

Aşağıdaki şekilde, nesnelerin sanal ve sanal olmayan devralma ile nasıl oluşturulduğu gösterilmektedir.

![Sanal türetme ve sanal olmayan türetme](../cpp/media/vc38xr1.gif "vc38XR1") sanal vs. Sanal olmayan türetme

Şekilde, sanal olmayan temel sınıflar yoluyla `A` sınıfının her hangi bir üyesine erişmek belirsizliğe neden olur; derleyicide, `B` ile ilişkili alt nesnenin mi yoksa `C` ile ilişkili alt nesnenin mi kullanılacağını açıklayan herhangi bir bilgi yoktur. Ancak, bir sanal temel sınıf olarak `A` belirtildiğinde, hangi alt nesneye erişildiği sorun olmaz.

## <a name="see-also"></a>Ayrıca bkz.

[Devralma](../cpp/inheritance-cpp.md)