---
title: Birden Çok Taban Sınıfı
ms.date: 11/19/2018
helpviewer_keywords:
- base classes [C++], multiple
- derived classes [C++], multiple bases
- multiple inheritance, class declaration
- multiple base classes [C++]
ms.assetid: a30c69fe-401c-4a87-96a0-e0da70c7c740
ms.openlocfilehash: 0e663f33213a5fd57f2adbdcc53233c6af29954e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227380"
---
# <a name="multiple-base-classes"></a>Birden Çok Taban Sınıfı

Bir sınıf birden fazla taban sınıftan türetilebilir. Birden çok devralma modelinde (sınıfların birden fazla taban sınıftan türetildiğinden), temel sınıflar *temel liste* dilbilgisi öğesi kullanılarak belirtilir. Örneğin, `CollectionOfBook` ve ' den türetilen için sınıf bildirimi `Collection` `Book` belirtilebilir:

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

Temel sınıfların belirtilme sırası, oluşturucuların ve yıkıcıların çağrıldığı belirli durumlar haricinde önemli değildir. Bu durumlarda, temel sınıfların belirtilme sırası aşağıdakileri etkiler:

- Oluşturucunun başlatılma sırası gerçekleşir. Kodunuz `Book` `CollectionOfBook` bölümden önce başlatılacak olan bölümünü kullanıyorsa `Collection` Belirtim sırası önemlidir. Başlatma, sınıfların *taban listede*belirtilene göre gerçekleşir.

- Yok edicilerin temizlemek için çağrıldığı sıra. Daha sonra, başka bir bölüm yok edildiğinde sınıfın belirli bir "bölümü" mevcut olması gerekiyorsa, sıralama önemlidir. Yok ediciler, *taban listesinde*belirtilen sınıfların ters sırasıyla çağrılır.

    > [!NOTE]
    >  Temel sınıfların belirtim sırası, sınıfının bellek düzenini etkileyebilir. Bellekteki temel üyelerin sırasına göre programlama kararları vermeyin.

*Taban listesini*belirtirken, aynı sınıf adını birden çok kez belirtemezsiniz. Ancak, bir sınıfın türetilmiş bir sınıf için bir kereden fazla dolaylı temel olması mümkündür.

## <a name="virtual-base-classes"></a>Sanal temel sınıflar

Bir sınıf türetilmiş bir sınıfın bir kereden fazla dolaylı temel sınıfı olabileceği için C++ bu temel sınıfların çalışma biçimini iyileştiren bir yöntem sağlar. Sanal temel sınıflar, alandan kazanmak ve birden fazla devralma kullanan sınıf hiyerarşilerinde belirsizliklerden kaçınmak için bir yol sunar.

Sanal olmayan her nesne, temel sınıfta tanımlanmış veri üyelerinin bir kopyasını içerir. Bu çoğaltma alanı boşa harcar ve bunlara eriştiğinizde temel sınıf üyelerinin hangi kopyasını istediğinizi belirtmenizi gerektirir.

Temel sınıf sanal bir temel olarak belirtildiğinde, veri üyeleri çoğaltılmadan bir kereden fazla dolaylı temel olarak görev alabilir. Veri üyelerinin tek bir kopyası, onu sanal temel olarak kullanan tüm temel sınıflar tarafından paylaşılır.

Bir sanal temel sınıf bildirirken, **`virtual`** anahtar sözcük türetilmiş sınıfların temel listelerinde görünür.

Sınıf hiyerarşisini, sanal bir öğle yemeği çizgi grafiğini gösteren aşağıdaki şekilde görebilirsiniz.

![Sanal Öğle yemeği çizgi grafiği](../cpp/media/vc38xp1.gif "Sanal Öğle yemeği çizgi grafiği") <br/>
Sanal Öğle yemeği çizgi grafiği

Şekilde, `Queue` hem `CashierQueue` hem de `LunchQueue` için temel sınıftır. Ancak, iki sınıf da `LunchCashierQueue` oluşturacak şekilde birleştirildiğinde, aşağıdaki sorun ortaya çıkar: yeni sınıf biri `Queue` öğesinden, diğeri `CashierQueue` öğesinden alınan `LunchQueue` türünde iki alt nesne içerir. Aşağıdaki şekilde, kavramsal bellek düzeni (gerçek bellek düzeni iyileştirilebilir) gösterilmektedir.

![Sanal Öğle Yemeği&#45;satırı nesnesi](../cpp/media/vc38xp2.gif "Sanal Öğle Yemeği&#45;satırı nesnesi") <br/>
Sanal Öğle Yemeği satırı nesnesi

`Queue` nesnesinde iki `LunchCashierQueue` alt nesnesi olduğuna dikkat edin. Aşağıdaki kod, `Queue` öğesinin sanal bir temel sınıf olduğunu bildirir:

```cpp
// deriv_VirtualBaseClasses.cpp
// compile with: /LD
class Queue {};
class CashierQueue : virtual public Queue {};
class LunchQueue : virtual public Queue {};
class LunchCashierQueue : public LunchQueue, public CashierQueue {};
```

**`virtual`** Anahtar sözcüğü, alt nesne öğesinin yalnızca bir kopyasının dahil edilmesini sağlar `Queue` (aşağıdaki şekle bakın).

![Simülasyonu&#45;satırı nesnesi, sanal taban sınıflar](../cpp/media/vc38xp3.gif "Simülasyonu&#45;satırı nesnesi, sanal taban sınıflar") <br/>
Sanal temel sınıflarla Sanal Öğle Yemeği satırı nesnesi

Bir sınıfta, belirli bir türden sanal bileşen ve sanal olmayan bileşen olabilir. Bu, aşağıdaki şekilde gösterilen koşullarda ortaya çıkar.

![Bir sınıfın sanal ve&#45;olmayan sanal bileşenleri](../cpp/media/vc38xp4.gif "Bir sınıfın sanal ve&#45;olmayan sanal bileşenleri") <br/>
Aynı sınıfın sanal ve sanal olmayan bileşenleri

Şekilde, `CashierQueue` ve `LunchQueue` sanal temel sınıf olarak `Queue` kullanmaktadır. Ancak `TakeoutQueue`, sanal temel sınıf olarak değil, temel sınıf olarak `Queue` belirtir. Bu nedenle, `LunchTakeoutCashierQueue``Queue` türünden iki alt nesneye sahiptir: biri `LunchCashierQueue` içeren devralma yolundan, diğeri ise `TakeoutQueue` içeren yoldan alınmıştır. Bu, aşağıdaki şekilde gösterilmiştir:

![Nesne düzeninde sanal &&#45;sanal devralma](../cpp/media/vc38xp5.gif "Nesne düzeninde sanal &&#45;sanal devralma") <br/>
Sanal ve sanal olmayan devralma ile nesne düzeni

> [!NOTE]
> Sanal devralma, sanal olmayan devralmayla karşılaştırıldığında önemli boyut avantajları sağlar. Ancak, ek işlem yükü ortaya çıkarabilir.

Türetilmiş bir sınıf sanal bir temel sınıftan devraldığı sanal bir işlemi geçersiz kılırsa ve türetilmiş temel sınıfın oluşturucusu veya yıkıcısı sanal temel sınıfa yönelik bir işaretçiyi kullanarak bu işlevi çağırırsa, derleyici sanal temellere sahip sınıflara ek gizli "vtordisk" alanları sunabilir. `/vd0`Derleyici seçeneği, gizli vtordisp Oluşturucusu/yıkıcısı yer değiştirme üyesinin eklenmesini engeller. `/vd1`Varsayılan olarak, derleyici seçeneği gerektiği yerde etkinleştirilir. Yalnızca tüm sınıf oluşturucularının ve yıkıcılarının sanal olarak sanal işlevleri çağırdığından eminseniz vtordisps'i kapatın.

`/vd`Derleyici seçeneği tüm derleme modülünü etkiler. Bir sınıf `vtordisp` temelinde alanları gizlemek ve sonra yeniden etkinleştirmek için pragma 'ı kullanın `vtordisp` :

```cpp
#pragma vtordisp( off )
class GetReal : virtual public { ... };
\#pragma vtordisp( on )
```

## <a name="name-ambiguities"></a>Ad belirsizlikleri

Birden çok devralma, adların birden fazla yoldan devralınmasını sağlar. Bu yolların üzerindeki sınıf üye adları benzersiz değildir. Bu ad çakışmaları "belirsizlikleri" olarak adlandırılır.

Bir sınıf üyesine başvuran herhangi bir ifade, belirsiz bir başvuru olmalıdır. Aşağıdaki örnek, belirsizlikleri 'in nasıl geliştirileceği gösterilmektedir:

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

Önceki sınıf bildirimleri söz konusu olduğunda, aşağıdaki gibi bir kod, `b` `b` içinde veya içinde öğesine başvuruda bulunup bulunmadığı için belirsiz olduğu için belirsizdir `A` `B` :

```cpp
C *pc = new C;

pc->b();
```

Yukarıdaki örneği göz önünde bulundurun. Ad `a` hem sınıfın hem de sınıfının bir üyesi olduğundan `A` `B` , derleyici, `a` çağrılan işlevi atayan şekilde ayırt edemez. Birden fazla işleve, nesneye, türe veya Numaralandırıcıya başvurabileceği bir üyeye erişim belirsiz olur.

Derleyici, testleri şu sırayla gerçekleştirerek belirsizlikleri algılar:

1. Ada erişim belirsiz ise (yalnızca açıklandığı gibi), bir hata iletisi oluşturulur.

1. Aşırı yüklenmiş işlevler belirsiz ise çözümlenirler.

1. Ada erişim üye erişim iznini ihlal ederse, bir hata iletisi oluşturulur. (Daha fazla bilgi için bkz. [üye-Access Control](../cpp/member-access-control-cpp.md).)

Bir ifade devralma aracılığıyla bir belirsizlik üretirse, söz konusu adı sınıf adıyla niteleyerek el ile çözebilirsiniz. Önceki örneği belirsizlikleri olmadan doğru şekilde derlemek için, şu gibi bir kod kullanın:

```cpp
C *pc = new C;

pc->B::a();
```

> [!NOTE]
> Ne zaman `C` bildirildiğinde, `B` kapsamında başvuruluyorsa hatalara neden olma olasılığı vardır `C` . Bununla birlikte, tanımlanmamış bir başvuruya `B` gerçekten kapsam içinde getirilene kadar bir hata verilmez `C` .

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

### <a name="ambiguous-conversions"></a>Belirsiz dönüştürmeler

İşaretçilerden ya da sınıf türlerine yapılan açık ve örtük dönüştürmeler belirsizlikleri neden olabilir. Bir sonraki şekil, taban sınıflara Işaretçilerin belirsiz dönüştürmesi, aşağıdakileri gösterir:

- Türünde bir nesnenin bildirimi `D` .

- Bu nesneye adres işleci () uygulamanın etkisi **&** . Address-of işlecinin, her zaman nesnenin temel adresini sağladığı unutulmamalıdır.

- İşaretçiyi, Address-of işleci kullanılarak alınan işaretçiyi, temel sınıf türüne açıkça dönüştürmenin etkisi `A` . Zorlama türündeki nesnenin adresi `A*` her zaman derleyicinin seçilecek türdeki alt nesne ile ilgili yeterli bilgi sağlamayacağını unutmayın `A` ; Bu durumda iki alt nesne vardır.

![Taban sınıflara işaretçiler belirsiz şekilde dönüştürülemedi](../cpp/media/vc38xt1.gif "Taban sınıflara işaretçiler belirsiz şekilde dönüştürülemedi") <br/>
Taban sınıflara işaretçiler belirsiz şekilde dönüştürülemedi

Türe dönüştürme `A*` (işaretçi `A` ) belirsiz, çünkü türü hangi alt nesne doğru bir şekilde ayırt etmenin bir yolu yoktur `A` . Hangi alt nesne kullanmak istediğinizi açıkça belirterek belirsizliğin önleneceğini aşağıdaki gibi unutmayın:

```cpp
(A *)(B *)&d       // Use B subobject.
(A *)(C *)&d       // Use C subobject.
```

### <a name="ambiguities-and-virtual-base-classes"></a>Belirsizlikleri ve sanal taban sınıflar

Sanal temel sınıflar kullanılırsa, işlevler, nesneler, türler ve numaralandırıcılara birden çok devralma yolu üzerinde erişilebilir. Temel sınıfın yalnızca tek bir örneği olduğundan, bu adlara erişirken belirsizlik olmaz.

Aşağıdaki şekilde, nesnelerin sanal ve sanal olmayan devralma ile nasıl oluşturulduğu gösterilmektedir.

![Sanal türetme ve&#45;sanal türetme](../cpp/media/vc38xr1.gif "Sanal türetme ve&#45;sanal türetme") <br/>
Sanal ve sanal olmayan türetme

Şekilde, sanal olmayan temel sınıflar yoluyla `A` sınıfının her hangi bir üyesine erişmek belirsizliğe neden olur; derleyicide, `B` ile ilişkili alt nesnenin mi yoksa `C` ile ilişkili alt nesnenin mi kullanılacağını açıklayan herhangi bir bilgi yoktur. Ancak, bir sanal temel sınıf olarak `A` belirtildiğinde, hangi alt nesneye erişildiği sorun olmaz.

## <a name="see-also"></a>Ayrıca bkz.

[Devralma](../cpp/inheritance-cpp.md)
