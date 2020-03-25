---
title: Birden Çok Taban Sınıfı
ms.date: 11/19/2018
helpviewer_keywords:
- base classes [C++], multiple
- derived classes [C++], multiple bases
- multiple inheritance, class declaration
- multiple base classes [C++]
ms.assetid: a30c69fe-401c-4a87-96a0-e0da70c7c740
ms.openlocfilehash: b8bc411b1b8d0b459fe58a39cf351d59d09b2d0e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179542"
---
# <a name="multiple-base-classes"></a>Birden Çok Taban Sınıfı

Bir sınıf birden fazla taban sınıftan türetilebilir. Birden çok devralma modelinde (sınıfların birden fazla taban sınıftan türetildiğinden), temel sınıflar *temel liste* dilbilgisi öğesi kullanılarak belirtilir. Örneğin, `Collection` ve `Book`türetilen `CollectionOfBook`yönelik sınıf bildirimi belirtilebilir:

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

- Oluşturucunun başlatılma sırası gerçekleşir. Kodunuz `Collection` bölümden önce başlatılacak `CollectionOfBook` `Book` bölümünü kullanıyorsa, belirtim sırası önemli olur. Başlatma, sınıfların *taban listede*belirtilene göre gerçekleşir.

- Yok edicilerin temizlemek için çağrıldığı sıra. Daha sonra, başka bir bölüm yok edildiğinde sınıfın belirli bir "bölümü" mevcut olması gerekiyorsa, sıralama önemlidir. Yok ediciler, *taban listesinde*belirtilen sınıfların ters sırasıyla çağrılır.

    > [!NOTE]
    >  Temel sınıfların belirtim sırası, sınıfının bellek düzenini etkileyebilir. Bellekteki temel üyelerin sırasına göre programlama kararları vermeyin.

*Taban listesini*belirtirken, aynı sınıf adını birden çok kez belirtemezsiniz. Ancak, bir sınıfın türetilmiş bir sınıf için bir kereden fazla dolaylı temel olması mümkündür.

## <a name="virtual-base-classes"></a>Sanal temel sınıflar

Bir sınıf türetilmiş bir sınıfın bir kereden fazla dolaylı temel sınıfı olabileceği için C++ bu temel sınıfların çalışma biçimini iyileştiren bir yöntem sağlar. Sanal temel sınıflar, alandan kazanmak ve birden fazla devralma kullanan sınıf hiyerarşilerinde belirsizliklerden kaçınmak için bir yol sunar.

Sanal olmayan her nesne, temel sınıfta tanımlanmış veri üyelerinin bir kopyasını içerir. Bu çoğaltma alanı boşa harcar ve bunlara eriştiğinizde temel sınıf üyelerinin hangi kopyasını istediğinizi belirtmenizi gerektirir.

Temel sınıf sanal bir temel olarak belirtildiğinde, veri üyeleri çoğaltılmadan bir kereden fazla dolaylı temel olarak görev alabilir. Veri üyelerinin tek bir kopyası, onu sanal temel olarak kullanan tüm temel sınıflar tarafından paylaşılır.

Bir sanal temel sınıf bildirirken, türetilmiş sınıfların temel listelerinde **sanal** anahtar sözcüğü görünür.

Sınıf hiyerarşisini, sanal bir öğle yemeği çizgi grafiğini gösteren aşağıdaki şekilde görebilirsiniz.

![Sanal Öğle yemeği çizgi grafiği](../cpp/media/vc38xp1.gif "Sanal Öğle yemeği çizgi grafiği") <br/>
Sanal Öğle yemeği çizgi grafiği

Şekilde, `Queue` hem `CashierQueue` hem de `LunchQueue` için temel sınıftır. Ancak, iki sınıf da `LunchCashierQueue` oluşturacak şekilde birleştirildiğinde, aşağıdaki sorun ortaya çıkar: yeni sınıf biri `Queue` öğesinden, diğeri `CashierQueue` öğesinden alınan `LunchQueue` türünde iki alt nesne içerir. Aşağıdaki şekilde, kavramsal bellek düzeni (gerçek bellek düzeni iyileştirilebilir) gösterilmektedir.

![Sanal Öğle&#45;yemeği çizgi nesnesi](../cpp/media/vc38xp2.gif "Sanal Öğle&#45;yemeği çizgi nesnesi") <br/>
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

**Sanal** anahtar sözcüğü, alt nesne `Queue` yalnızca bir kopyasının dahil edilmesini sağlar (aşağıdaki şekle bakın).

![Sanal bir&#45;öğle yemeği çizgi nesnesi, sanal taban sınıflar](../cpp/media/vc38xp3.gif "Sanal bir&#45;öğle yemeği çizgi nesnesi, sanal taban sınıflar") <br/>
Sanal temel sınıflarla Sanal Öğle Yemeği satırı nesnesi

Bir sınıfta, belirli bir türden sanal bileşen ve sanal olmayan bileşen olabilir. Bu, aşağıdaki şekilde gösterilen koşullarda ortaya çıkar.

![Bir sınıfın sanal&#45;ve sanal olmayan bileşenleri](../cpp/media/vc38xp4.gif "Bir sınıfın sanal&#45;ve sanal olmayan bileşenleri") <br/>
Aynı sınıfın sanal ve sanal olmayan bileşenleri

Şekilde, `CashierQueue` ve `LunchQueue` sanal temel sınıf olarak `Queue` kullanmaktadır. Ancak `TakeoutQueue`, sanal temel sınıf olarak değil, temel sınıf olarak `Queue` belirtir. Bu nedenle, `LunchTakeoutCashierQueue``Queue` türünden iki alt nesneye sahiptir: biri `LunchCashierQueue` içeren devralma yolundan, diğeri ise `TakeoutQueue` içeren yoldan alınmıştır. Bu, aşağıdaki şekilde gösterilmiştir:

![Nesne düzeninde sanal&#45;& devralınmayan sanal devralma](../cpp/media/vc38xp5.gif "Nesne düzeninde sanal&#45;& devralınmayan sanal devralma") <br/>
Sanal ve sanal olmayan devralma ile nesne düzeni

> [!NOTE]
>  Sanal devralma, sanal olmayan devralmayla karşılaştırıldığında önemli boyut avantajları sağlar. Ancak, ek işlem yükü ortaya çıkarabilir.

Türetilmiş bir sınıf sanal bir temel sınıftan devraldığı sanal bir işlemi geçersiz kılırsa ve türetilmiş temel sınıfın oluşturucusu veya yıkıcısı sanal temel sınıfa yönelik bir işaretçiyi kullanarak bu işlevi çağırırsa, derleyici sanal temellere sahip sınıflara ek gizli "vtordisk" alanları sunabilir. `/vd0` derleyici seçeneği, gizli vtordisp Oluşturucusu/yıkıcısı yer değiştirme üyesinin eklenmesini engeller. `/vd1` derleyici seçeneği, varsayılan olarak, gerekli oldukları yerde etkinleştirilir. Yalnızca tüm sınıf oluşturucularının ve yıkıcılarının sanal olarak sanal işlevleri çağırdığından eminseniz vtordisps'i kapatın.

`/vd` derleyici seçeneği tüm derleme modülünü etkiler. Sınıf temelinde `vtordisp` alanlarını gizlemek ve sonra yeniden etkinleştirmek için `vtordisp` pragma kullanın:

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

Önceki sınıf bildirimleri söz konusu olduğunda, aşağıdaki gibi bir kod belirsiz olduğundan `b`, `A` veya `B`içinde `b` başvuruda bulunduğundan net değildir.

```cpp
C *pc = new C;

pc->b();
```

Yukarıdaki örneği göz önünde bulundurun. `a` adı hem sınıf `A` hem de sınıf `B`bir üyesi olduğundan, derleyici, işlevi hangi `a` atayan olduğunu ayırt edemez. Birden fazla işleve, nesneye, türe veya Numaralandırıcıya başvurabileceği bir üyeye erişim belirsiz olur.

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
>  `C` bildirildiği zaman, `B` `C`kapsamında başvuruluyorsa hatalara neden olma olasılığı vardır. Ancak, `C`kapsamında `B` nitelenmemiş bir başvuru yapılana kadar hiçbir hata verilmez.

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

- `D`türünde bir nesnenin bildirimi.

- Bu nesneye adres işlecinin ( **&** ) uygulanması etkisi. Address-of işlecinin, her zaman nesnenin temel adresini sağladığı unutulmamalıdır.

- ' In Address-of işleci kullanılarak alınan işaretçiyi açıkça dönüştürmenin etkisi `A`. Zorlama türüne `A*` nesnenin adresinin, her zaman derleyicinin seçilecek `A` türündeki alt nesne için yeterli bilgi sağlamayacağını unutmayın; Bu durumda, iki alt nesne vardır.

![Taban sınıflara işaretçiler belirsiz şekilde dönüştürülemedi](../cpp/media/vc38xt1.gif "Taban sınıflara işaretçiler belirsiz şekilde dönüştürülemedi") <br/>
Taban sınıflara işaretçiler belirsiz şekilde dönüştürülemedi

`A*` türüne dönüştürme (`A`işaretçisi), türü `A` hangi alt nesne türünün doğru olduğunu ayırt etmenin bir yolu olmadığından belirsizdir. Hangi alt nesne kullanmak istediğinizi açıkça belirterek belirsizliğin önleneceğini aşağıdaki gibi unutmayın:

```cpp
(A *)(B *)&d       // Use B subobject.
(A *)(C *)&d       // Use C subobject.
```

### <a name="ambiguities-and-virtual-base-classes"></a>Belirsizlikleri ve sanal taban sınıflar

Sanal temel sınıflar kullanılırsa, işlevler, nesneler, türler ve numaralandırıcılara birden çok devralma yolu üzerinde erişilebilir. Temel sınıfın yalnızca tek bir örneği olduğundan, bu adlara erişirken belirsizlik olmaz.

Aşağıdaki şekilde, nesnelerin sanal ve sanal olmayan devralma ile nasıl oluşturulduğu gösterilmektedir.

![Sanal türetme ve sanal&#45;olmayan türetme](../cpp/media/vc38xr1.gif "Sanal türetme ve sanal&#45;olmayan türetme") <br/>
Sanal ve sanal olmayan türetme

Şekilde, sanal olmayan temel sınıflar yoluyla `A` sınıfının her hangi bir üyesine erişmek belirsizliğe neden olur; derleyicide, `B` ile ilişkili alt nesnenin mi yoksa `C` ile ilişkili alt nesnenin mi kullanılacağını açıklayan herhangi bir bilgi yoktur. Ancak, bir sanal temel sınıf olarak `A` belirtildiğinde, hangi alt nesneye erişildiği sorun olmaz.

## <a name="see-also"></a>Ayrıca bkz.

[Devralma](../cpp/inheritance-cpp.md)
