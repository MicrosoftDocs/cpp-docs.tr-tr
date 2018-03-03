---
title: "Birden çok taban sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- base classes [C++], multiple
- derived classes [C++], multiple bases
- multiple inheritance, class declaration
- multiple base classes [C++]
ms.assetid: a30c69fe-401c-4a87-96a0-e0da70c7c740
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b765fabe8b83169353650286d05d02301dcb4807
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="multiple-base-classes"></a>Birden Çok Taban Sınıfı
Bölümünde açıklandığı gibi [birden çok devralma](http://msdn.microsoft.com/en-us/3b74185e-2beb-4e29-8684-441e51d2a2ca), bir sınıfın birden fazla temel sınıfından türetilmiş olmalıdır. (Burada türetilmiş sınıfları birden fazla temel sınıfından) birden çok devralmayı modelinde, temel sınıfları kullanılarak belirtilir *ana listesi* dilbilgisi öğesi. Örneğin, sınıf bildirimi `CollectionOfBook`, türetilmiş `Collection` ve `Book`, belirtilebilir:  
  
```  
// deriv_MultipleBaseClasses.cpp  
// compile with: /LD  
class Collection {  
};  
class Book {};  
class CollectionOfBook : public Book, public Collection {  
    // New members  
};  
```  
  
 Temel sınıflar belirtilen sırada Kurucular ve Yıkıcılar burada çağrılan belirli durumlarda dışındaki önemli değildir. Bu durumlarda, temel sınıflar belirtilen sırada aşağıdakiler etkiler:  
  
-   Hangi başlatma Oluşturucusu gerçekleşmesi tarafından sırayla. Kodunuzu kullanır, `Book` kısmı `CollectionOfBook` önce başlatılması için `Collection` belirtimi sırasını bölümüdür önemli. Başlatma sınıfları belirtilen sırada kurulur *ana listesi*.  
  
-   Temizleme Yıkıcılar çağrılan sırası. Yeniden, belirli bir sınıfın "bölümünü" diğer bölümü bozulduğunda mevcut olması gerekir, sıra önemlidir. Yıkıcılar adında ters sırada belirtilen sınıfların *ana listesi*.  
  
    > [!NOTE]
    >  Temel sınıflar belirtimi sırasını sınıfı bellek düzenini etkileyebilir. Temel üyeler bellekte terabayt temel programlama karar yapmayın.  
  
 Belirtirken *ana listesi*, aynı sınıf adı birden çok kez belirtilemez. Ancak, bir sınıf türetilmiş bir sınıf dolaylı bir tabanına birden çok kez olması mümkündür.  
  
## <a name="virtual-base-classes"></a>Sanal temel sınıflar  
 Bir sınıf türetilmiş bir sınıfın bir kereden fazla dolaylı temel sınıfı olabileceği için C++ bu temel sınıfların çalışma biçimini iyileştiren bir yöntem sağlar. Sanal temel sınıflar, alandan kazanmak ve birden fazla devralma kullanan sınıf hiyerarşilerinde belirsizliklerden kaçınmak için bir yol sunar.  
  
 Sanal olmayan her nesne, temel sınıfta tanımlanmış veri üyelerinin bir kopyasını içerir. Bu çoğaltma alanı boşa harcar ve bunlara eriştiğinizde temel sınıf üyelerinin hangi kopyasını istediğinizi belirtmenizi gerektirir.  
  
 Temel sınıf sanal bir temel olarak belirtildiğinde, veri üyeleri çoğaltılmadan bir kereden fazla dolaylı temel olarak görev alabilir. Veri üyelerinin tek bir kopyası, onu sanal temel olarak kullanan tüm temel sınıflar tarafından paylaşılır.  
  
 Sanal bir temel sınıf bildirirken **sanal** anahtar sözcüğü türetilmiş sınıflar temel listelerinde görünür.  
  
 Sınıf hiyerarşisini, sanal bir öğle yemeği çizgi grafiğini gösteren aşağıdaki şekilde görebilirsiniz.  
  
 ![Benzetimli Yemeği Çizgi grafiği](../cpp/media/vc38xp1.gif "vc38XP1")  
Sanal Öğle Yemeği Çizgi Grafiği  
  
 Şekilde, `Queue` hem `CashierQueue` hem de `LunchQueue` için temel sınıftır. Ancak, iki sınıf da `LunchCashierQueue` oluşturacak şekilde birleştirildiğinde, aşağıdaki sorun ortaya çıkar: yeni sınıf biri `Queue` öğesinden, diğeri `CashierQueue` öğesinden alınan `LunchQueue` türünde iki alt nesne içerir. Aşağıdaki şekilde, kavramsal bellek düzeni (gerçek bellek düzeni iyileştirilebilir) gösterilmektedir.  
  
 ![Benzetimli Yemeği &#45; çizgi nesnesi](../cpp/media/vc38xp2.gif "vc38XP2")  
Sanal Öğle Yemeği Çizgi Grafiği Nesnesi  
  
 `Queue` nesnesinde iki `LunchCashierQueue` alt nesnesi olduğuna dikkat edin. Aşağıdaki kod, `Queue` öğesinin sanal bir temel sınıf olduğunu bildirir:  
  
```  
// deriv_VirtualBaseClasses.cpp  
// compile with: /LD  
class Queue {};  
class CashierQueue : virtual public Queue {};  
class LunchQueue : virtual public Queue {};  
class LunchCashierQueue : public LunchQueue, public CashierQueue {};  
```  
  
 `virtual` anahtar sözcüğü, `Queue` alt nesnesinin yalnızca bir kopyasının dahil edilmesini sağlar (bkz. aşağıdaki şekil).  
  
 ![Benzetimli Yemeği &#45; çizgi nesnesi, sanal taban sınıflar](../cpp/media/vc38xp3.gif "vc38XP3")  
Sanal Temel Sınıflarla Sanal Öğle Yemeği Çizgi Grafiği Nesnesi  
  
 Bir sınıfta, belirli bir türden sanal bileşen ve sanal olmayan bileşen olabilir. Bu, aşağıdaki şekilde gösterilen koşullarda ortaya çıkar.  
  
 ![Bir sınıf sanal ve sanal olmayan bileşenlerinin](../cpp/media/vc38xp4.gif "vc38XP4")  
Aynı Sınıfın Sanal ve Sanal Olmayan Bileşenleri  
  
 Şekilde, `CashierQueue` ve `LunchQueue` sanal temel sınıf olarak `Queue` kullanmaktadır. Ancak `TakeoutQueue`, sanal temel sınıf olarak değil, temel sınıf olarak `Queue` belirtir. Bu nedenle, `LunchTakeoutCashierQueue``Queue` türünden iki alt nesneye sahiptir: biri `LunchCashierQueue` içeren devralma yolundan, diğeri ise `TakeoutQueue` içeren yoldan alınmıştır. Bu, aşağıdaki şekilde gösterilmiştir:  
  
 ![Nesne düzeni'nde sanal olan ve olmayan Devralmanın](../cpp/media/vc38xp5.gif "vc38XP5")  
Sanal ve Sanal Olmayan Devralma ile Nesne Düzeni  
  
> [!NOTE]
>  Sanal devralma, sanal olmayan devralmayla karşılaştırıldığında önemli boyut avantajları sağlar. Ancak, ek işlem yükü ortaya çıkarabilir.  
  
 Türetilmiş bir sınıf sanal bir temel sınıftan devraldığı sanal bir işlemi geçersiz kılırsa ve türetilmiş temel sınıfın oluşturucusu veya yıkıcısı sanal temel sınıfa yönelik bir işaretçiyi kullanarak bu işlevi çağırırsa, derleyici sanal temellere sahip sınıflara ek gizli "vtordisk" alanları sunabilir. /vd0 derleyici seçeneği, gizli vtordisp oluşturucu/yıkıcı yer değiştirme üyesinin eklenmesini engeller. Varsayılan olan /vd1 derleyici seçeneği, gerekli olduğunda bunları etkinleştirir. Yalnızca tüm sınıf oluşturucularının ve yıkıcılarının sanal olarak sanal işlevleri çağırdığından eminseniz vtordisps'i kapatın.  
  
 /vd derleyici seçeneği, tüm derleme modülünü etkiler. Kullanım **vtordisp** pragma bastırmak ve sınıfı tarafından sınıfı temelinde vtordisp alanları yeniden etkinleştirmek için:  
  
```  
#pragma vtordisp( off )  
class GetReal : virtual public { ... };  
#pragma vtordisp( on )  
```  
  
## <a name="name-ambiguities"></a>Ad belirsizlikleri  
 Birden çok devralma olasılığı birden fazla yol boyunca devralınan adları için tanıtır. Bu yollar boyunca sınıf üyesi adlarının benzersiz olması gerekmeyen. Bu ad çakışmalarını "belirsizlikleri." olarak adlandırılır  
  
 Sınıf üyesine başvuruyor herhangi bir ifade anlaşılır bir başvuru yapmanız gerekir. Aşağıdaki örnek, nasıl belirsizlikleri geliştirmek gösterir:  
  
```  
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
  
 Belirsiz olduğundan aşağıdaki belirsiz gibi önceki sınıf bildirimleri verildiğinde, kod olup olmadığını `b` başvurduğu `b` içinde `A` veya `B`:  
  
```  
C *pc = new C;  
  
pc->b();  
```  
  
 Önceki örneği göz önünde bulundurun. Çünkü adı `a` iki sınıf üyesi `A` ve sınıf `B`, derleyici, keşfedilir `a` çağrılacak işlev belirler. Üye erişimi olan birden fazla işlevi, nesne, türü veya numaralandırıcı başvurduğundan belirsiz.  
  
 Derleyici, bu sırada testleri gerçekleştirerek belirsizlikleri algılar:  
  
1.  Adı (yalnızca açıklandığı gibi) belirsiz ise, bir hata iletisi oluşturulur.  
  
2.  Aşırı yüklenen işlevler anlaşılır olması durumunda, bunlar çözümlenir.
  
3.  Üye erişimi izni adına erişimi ihlal edilirse, bir hata iletisi oluşturulur. (Daha fazla bilgi için bkz: [üye erişim denetimi](../cpp/member-access-control-cpp.md).)  
  
 Bir ifadenin bir belirsizlik devralma yoluyla vermediğinde adıyla söz konusu sınıf adını niteleme tarafından el ile çözebilirsiniz. Önceki örnekte düzgün hiçbir belirsizlikleri ile derleme yapmak için kod gibi kullanın:  
  
```  
C *pc = new C;  
  
pc->B::a();  
```  
  
> [!NOTE]
>  Zaman `C` bildirilmiş hatalara neden olanağına sahip olduğunda `B` kapsamında başvurulan `C`. Hata, ancak, nitelenmemiş referansı kadar verilmez `B` gerçekten yapılır `C`kullanıcının kapsam.  
  
### <a name="dominance"></a>Baskınlık  
 Devralma grafiğiyle birden fazla ada (işlev, nesne veya numaralandırma) ulaşılabilir. Bu gibi durumlar, sanal olmayan temel sınıflarla belirsiz olarak kabul edilir. Adlardan biri diğerinden "baskın olmadığı" sürece sanal temel sınıflarla da belirsiz olurlar.  
  
 Bir ad, iki sınıfta da tanımlanırsa ve bir sınıf diğerinden türetilirse diğer addan baskın olur. Baskın ad türetilmiş sınıftaki addır; bu ad aşağıdaki örnekte gösterildiği gibi bir belirsizliğin ortaya çıkabileceği durumlarda kullanılır:  
  
```  
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
 Açık ve kapalı dönüşümleri işaretçileri veya sınıf türleri başvurular belirsizliğe neden olabilir. Sonraki şekilde, temel sınıf olarak belirsiz dönüştürme işaretçileri aşağıda gösterilmiştir:  
  
-   Bir nesne türü bildirimi `D`.  
  
-   Address-of işleci uygulama etkisini (**&**), bu nesneye. Address-of işleci her zaman nesnenin temel adres sağlayan unutmayın.  
  
-   Address-of işleci temel sınıf türü kullanılarak edinilen işaretçi açıkça dönüştürme etkisini `A`. Bu nesne türü için adres coercing Not `A*` her zaman derleyici yeterli bilgileri türü ile hangi alt nesne sağlamaz `A` seçmek için; bu durumda, iki alt nesnelerinin mevcut.  
  
 ![Temel sınıflar için işaretçileri belirsiz dönüştürülmesi](../cpp/media/vc38xt1.gif "vc38XT1")  
Belirsiz işaretçileri dönüştürmeye temel sınıflar  
  
 Türüne dönüştürme `A*` (işaretçi `A`) hangi alt nesne türü keşfedilir şekilde olduğundan belirsiz `A` doğru olduğundan. Belirsizliği açıkça şu şekilde kullanmak için ortalama hangi alt nesne belirterek önleyebilirsiniz dikkat edin:  
  
```  
(A *)(B *)&d       // Use B subobject.  
(A *)(C *)&d       // Use C subobject.  
```  
  
### <a name="ambiguities-and-virtual-base-classes"></a>Belirsizlikler ve sanal tabanlı sınıflar  
 Sanal temel sınıflar kullanılırsa, işlevler, nesneler, türler ve numaralandırıcılara birden çok devralma yolu üzerinde erişilebilir. Temel sınıfın yalnızca tek bir örneği olduğundan, bu adlara erişirken belirsizlik olmaz.  
  
 Aşağıdaki şekilde, nesnelerin sanal ve sanal olmayan devralma ile nasıl oluşturulduğu gösterilmektedir.  
  
 ![Sanal türetme ve olmayan türetme](../cpp/media/vc38xr1.gif "vc38XR1")  
Sanal vs. Olmayan türetme  
  
 Şekilde, sanal olmayan temel sınıflar yoluyla `A` sınıfının her hangi bir üyesine erişmek belirsizliğe neden olur; derleyicide, `B` ile ilişkili alt nesnenin mi yoksa `C` ile ilişkili alt nesnenin mi kullanılacağını açıklayan herhangi bir bilgi yoktur. Ancak, bir sanal temel sınıf olarak `A` belirtildiğinde, hangi alt nesneye erişildiği sorun olmaz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Devralma](../cpp/inheritance-cpp.md)