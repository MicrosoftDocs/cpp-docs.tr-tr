---
title: Birden Çok Taban Sınıfı
ms.date: 11/19/2018
helpviewer_keywords:
- base classes [C++], multiple
- derived classes [C++], multiple bases
- multiple inheritance, class declaration
- multiple base classes [C++]
ms.assetid: a30c69fe-401c-4a87-96a0-e0da70c7c740
ms.openlocfilehash: 7cac70da5dd7093ce3e9c1cf3d2350d780c6b391
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81353729"
---
# <a name="multiple-base-classes"></a>Birden Çok Taban Sınıfı

Bir sınıf birden fazla taban sınıftan türetilebilir. Birden çok devralma modelinde (sınıfların birden fazla taban sınıftan türetildiği durumlarda), taban sınıflar *taban liste* dilbilgisi öğesi kullanılarak belirtilir. Örneğin, sınıf bildirimi `CollectionOfBook`, türetilmiş `Collection` ve `Book`, belirtilebilir:

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

Temel sınıfların belirtildiği sıra, yapıcıların ve yıkıcıların çağrıldığı bazı durumlar dışında önemli değildir. Bu gibi durumlarda, temel sınıfların belirtildiği sıra aşağıdakileri etkiler:

- Kurucu tarafından başlatmanın gerçekleştiği sıra. Kodunuz `Collection` parçadan önce `Book` başharfe başlatı edilecek kısma `CollectionOfBook` dayanıyorsa, belirtim sırası önemlidir. Başlatma, sınıfların *taban listesinde*belirtildiği sırada gerçekleşir.

- Yok edicilerin temizlenmesi için çağrıldığı sıra. Yine, sınıfın belirli bir "parçası" diğer parçası yok edilirken bulunması gerekiyorsa, sıra önemlidir. *Yıkıcılar, taban listesinde*belirtilen sınıfların ters sırasına göre çağrılır.

    > [!NOTE]
    >  Temel sınıfların belirtimi sırası sınıfın bellek düzenini etkileyebilir. Bellekte temel üyelerin sırasına göre herhangi bir programlama kararları yapmayın.

*Temel listeyi*belirtirken, aynı sınıf adını birden çok kez belirtemezsiniz. Ancak, bir sınıfın türemiş bir sınıfa birden fazla kez dolaylı bir taban olması mümkündür.

## <a name="virtual-base-classes"></a>Sanal temel sınıflar

Bir sınıf türetilmiş bir sınıfın bir kereden fazla dolaylı temel sınıfı olabileceği için C++ bu temel sınıfların çalışma biçimini iyileştiren bir yöntem sağlar. Sanal temel sınıflar, alandan kazanmak ve birden fazla devralma kullanan sınıf hiyerarşilerinde belirsizliklerden kaçınmak için bir yol sunar.

Sanal olmayan her nesne, temel sınıfta tanımlanmış veri üyelerinin bir kopyasını içerir. Bu çoğaltma alanı boşa harcar ve bunlara eriştiğinizde temel sınıf üyelerinin hangi kopyasını istediğinizi belirtmenizi gerektirir.

Temel sınıf sanal bir temel olarak belirtildiğinde, veri üyeleri çoğaltılmadan bir kereden fazla dolaylı temel olarak görev alabilir. Veri üyelerinin tek bir kopyası, onu sanal temel olarak kullanan tüm temel sınıflar tarafından paylaşılır.

Sanal taban sınıf bildirirken, **sanal** anahtar kelime türemiş sınıfların temel listelerinde görünür.

Sınıf hiyerarşisini, sanal bir öğle yemeği çizgi grafiğini gösteren aşağıdaki şekilde görebilirsiniz.

![Simüle öğle yemeği hattının grafiği](../cpp/media/vc38xp1.gif "Simüle öğle yemeği hattının grafiği") <br/>
Simüle öğle yemeği satırı grafiği

Şekilde, `Queue` hem `CashierQueue` hem de `LunchQueue` için temel sınıftır. Ancak, iki sınıf da `LunchCashierQueue` oluşturacak şekilde birleştirildiğinde, aşağıdaki sorun ortaya çıkar: yeni sınıf biri `Queue` öğesinden, diğeri `CashierQueue` öğesinden alınan `LunchQueue` türünde iki alt nesne içerir. Aşağıdaki şekilde, kavramsal bellek düzeni (gerçek bellek düzeni iyileştirilebilir) gösterilmektedir.

![Benzetimli öğle&#45;satır nesnesi](../cpp/media/vc38xp2.gif "Benzetimli öğle&#45;satır nesnesi") <br/>
Benzetimli öğle yemeği satırı nesnesi

`Queue` nesnesinde iki `LunchCashierQueue` alt nesnesi olduğuna dikkat edin. Aşağıdaki kod, `Queue` öğesinin sanal bir temel sınıf olduğunu bildirir:

```cpp
// deriv_VirtualBaseClasses.cpp
// compile with: /LD
class Queue {};
class CashierQueue : virtual public Queue {};
class LunchQueue : virtual public Queue {};
class LunchCashierQueue : public LunchQueue, public CashierQueue {};
```

**Sanal** anahtar kelime, alt nesnenin `Queue` yalnızca bir kopyasının eklenmesini sağlar (aşağıdaki şekile bakın).

![Simüle öğle yemeği&#45;satır nesnesi, sanal temel sınıflar](../cpp/media/vc38xp3.gif "Simüle öğle yemeği&#45;satır nesnesi, sanal temel sınıflar") <br/>
Sanal temel sınıfları ile simüle öğle yemeği satırı nesnesi

Bir sınıfta, belirli bir türden sanal bileşen ve sanal olmayan bileşen olabilir. Bu, aşağıdaki şekilde gösterilen koşullarda ortaya çıkar.

![Sınıfın sanal ve&#45;sanal bileşenleri](../cpp/media/vc38xp4.gif "Sınıfın sanal ve&#45;sanal bileşenleri") <br/>
Aynı sınıfın sanal ve sanal olmayan bileşenleri

Şekilde, `CashierQueue` ve `LunchQueue` sanal temel sınıf olarak `Queue` kullanmaktadır. Ancak `TakeoutQueue`, sanal temel sınıf olarak değil, temel sınıf olarak `Queue` belirtir. Bu nedenle, `LunchTakeoutCashierQueue``Queue` türünden iki alt nesneye sahiptir: biri `LunchCashierQueue` içeren devralma yolundan, diğeri ise `TakeoutQueue` içeren yoldan alınmıştır. Bu, aşağıdaki şekilde gösterilmiştir:

![Nesne düzeninde sanal &&#45;sanal devralma](../cpp/media/vc38xp5.gif "Nesne düzeninde sanal &&#45;sanal devralma") <br/>
Sanal ve sanal olmayan devralma ile nesne düzeni

> [!NOTE]
> Sanal devralma, sanal olmayan devralmayla karşılaştırıldığında önemli boyut avantajları sağlar. Ancak, ek işlem yükü ortaya çıkarabilir.

Türetilmiş bir sınıf sanal bir temel sınıftan devraldığı sanal bir işlemi geçersiz kılırsa ve türetilmiş temel sınıfın oluşturucusu veya yıkıcısı sanal temel sınıfa yönelik bir işaretçiyi kullanarak bu işlevi çağırırsa, derleyici sanal temellere sahip sınıflara ek gizli "vtordisk" alanları sunabilir. `/vd0` Derleyici seçeneği gizli vtordisp yapıcı/yıkıcı yer değiştirme üyesinin eklenmesini bastırır. `/vd1` Derleyici seçeneği, varsayılan, gerekli oldukları yerde bunları sağlar. Yalnızca tüm sınıf oluşturucularının ve yıkıcılarının sanal olarak sanal işlevleri çağırdığından eminseniz vtordisps'i kapatın.

`/vd` Derleyici seçeneği tüm derleme modüllerini etkiler. Alanları `vtordisp` sınıf bazında bastırmak ve `vtordisp` sonra yeniden etkinleştirmek için pragma'yı kullanın:

```cpp
#pragma vtordisp( off )
class GetReal : virtual public { ... };
\#pragma vtordisp( on )
```

## <a name="name-ambiguities"></a>İsim belirsizlikleri

Birden çok devralma, adların birden fazla yol boyunca devralınması olasılığını tanıtır. Bu yollar daki sınıf üyesi adlar benzersiz olmak zorunda değildir. Bu ad çakışmaları "belirsizlikler" olarak adlandırılır.

Bir sınıf üyesine başvuran herhangi bir ifade kesin bir başvuru yapmalıdır. Aşağıdaki örnek, belirsizliklerin nasıl geliştiğini gösterir:

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

Önceki sınıf bildirimleri göz önüne alındığında, aşağıdaki gibi kod `b` belirsizdir, `b` `A` çünkü `B`giriş veya in:'e atıfta bulunulup bulunulmadığı belirsizdir:

```cpp
C *pc = new C;

pc->b();
```

Önceki örneği göz önünde bulundurun. Ad `a` hem sınıfın hem de `A` sınıfın `B`bir üyesi olduğundan, derleyici çağrılacak işlevi `a` belirleyen ayırt edemez. Birden fazla işlev, nesne, tür veya sayısallaştırıcıya atıfta bulunabiliyorsa, bir üyeye erişim belirsizdir.

Derleyici, bu sırada testler gerçekleştirerek belirsizlikleri algılar:

1. Ada erişim belirsizse (azönce açıklandığı gibi), bir hata iletisi oluşturulur.

1. Aşırı yüklenen işlevler kesinse, bunlar çözülür.

1. Ada erişim üye erişim iznini ihlal ederse, bir hata iletisi oluşturulur. (Daha fazla bilgi için [Üye-Erişim Denetimi'ne](../cpp/member-access-control-cpp.md)bakın.)

Bir ifade devralma yoluyla bir belirsizlik oluşturduğunda, söz konusu adı sınıf adı ile niteleyerek el ile çözebilirsiniz. Önceki örneğin belirsizlik olmadan düzgün bir şekilde derlemesi için aşağıdakiler gibi kodu kullanın:

```cpp
C *pc = new C;

pc->B::a();
```

> [!NOTE]
> Beyan `C` edildiğinde, `C`'' nin kapsamına `B` başvurulduğunda hatalara neden olabilir. Ancak, `C`''nin kapsamında nitelenmemiş bir `B` başvuru yapılına kadar hata verilmez.

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

İşaretçilerden veya başvurulardan sınıf türlerine yapılan açık ve örtülü dönüşümler belirsizliklere neden olabilir. Sonraki şekil, İşaretçilerin Temel Sınıflara Belirsiz Dönüşümü aşağıdakileri gösterir:

- Türünde `D`bir nesnenin bildirimi .

- İşleç**&**() adresini o nesneye uygulamanın etkisi. İşleticinin adresinin her zaman nesnenin temel adresini sağladığını unutmayın.

- İşleç adresi kullanılarak elde edilen işaretçiyi taban sınıf türüne `A`açıkça dönüştürmenin etkisi. Nesnenin adresini türe `A*` zorlamanın derleyiciye her zaman hangi tür `A` alt nesnesini seçilebilecek kadar bilgi sağlamadığını unutmayın; bu durumda, iki alt nesne vardır.

![İşaretçilerin temel sınıflara belirsiz dönüşümü](../cpp/media/vc38xt1.gif "İşaretçilerin temel sınıflara belirsiz dönüşümü") <br/>
İşaretçilerin temel sınıflara belirsiz dönüşümü

Türe `A*` dönüştürme `A`(işaretçi) belirsizdir, çünkü türün `A` hangi alt nesnesinin doğru olduğunu ayırt etmenin bir yolu yoktur. Hangi alt nesneyi kullanmak istediğinizi aşağıdaki gibi açıkça belirterek belirsizliği önleyebileceğinizi unutmayın:

```cpp
(A *)(B *)&d       // Use B subobject.
(A *)(C *)&d       // Use C subobject.
```

### <a name="ambiguities-and-virtual-base-classes"></a>Belirsizlikler ve sanal taban sınıfları

Sanal temel sınıflar kullanılırsa, işlevler, nesneler, türler ve numaralandırıcılara birden çok devralma yolu üzerinde erişilebilir. Temel sınıfın yalnızca tek bir örneği olduğundan, bu adlara erişirken belirsizlik olmaz.

Aşağıdaki şekilde, nesnelerin sanal ve sanal olmayan devralma ile nasıl oluşturulduğu gösterilmektedir.

![Sanal türetme ve sanal&#45;olmayan sanal türetme](../cpp/media/vc38xr1.gif "Sanal türetme ve sanal&#45;olmayan sanal türetme") <br/>
Sanal vs sanal olmayan türetme

Şekilde, sanal olmayan temel sınıflar yoluyla `A` sınıfının her hangi bir üyesine erişmek belirsizliğe neden olur; derleyicide, `B` ile ilişkili alt nesnenin mi yoksa `C` ile ilişkili alt nesnenin mi kullanılacağını açıklayan herhangi bir bilgi yoktur. Ancak, bir sanal temel sınıf olarak `A` belirtildiğinde, hangi alt nesneye erişildiği sorun olmaz.

## <a name="see-also"></a>Ayrıca bkz.

[Devralma](../cpp/inheritance-cpp.md)
