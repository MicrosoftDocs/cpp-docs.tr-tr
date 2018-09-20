---
title: Değer türü anlamları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interior_ptr keyword [C++]
- virtual functions, value types
- inheritance, value types
- pinning pointers
- pin_ptr keyword [C++]
- __pin keyword
ms.assetid: 7f065589-ad25-4850-baf1-985142e35e52
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 72dc6a613616d13e9ff92e8af0c39c63dfe63162
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46413802"
---
# <a name="value-type-semantics"></a>Değer Türü Anlamları

Değer türü anlamları, C++ için Visual C++ için Yönetilen Uzantılar'dan değişti.

C++ belirtimi için Yönetilen Uzantılar kullanılan kurallı basit değer türü şu şekildedir:

```
__value struct V { int i; };
__gc struct R { V vr; };
```

Yönetilen Uzantılar'biz (forms 2 ve 3 aynı anlamsal olarak nerede) bir değer türü dört söz dizimsel çeşitleri olabilir:

```
V v = { 0 };       // Form (1)
V *pv = 0;         // Form (2) an implicit form of (3)
V __gc *pvgc = 0;  // Form (3)
__box V* pvbx = 0; // Form (4) must be local
```

## <a name="invoking-inherited-virtual-methods"></a>Devralınan sanal yöntemleri çağırma

`Form (1)` kurallı değer nesnedir ve bunu makul de, birisi gibi devralınan sanal bir yöntem çağırmak çalıştığında dışında anlaşılır `ToString()`. Örneğin:

```
v.ToString(); // error!
```

İçinde kılınmayan çünkü bu yöntemi çağırmak için `V`, derleyicinin temel sınıf sanal bir ilişkili tabloya erişimi olmalıdır. Değer türleri olmayan ilişkili işaretçiyi kendi sanal tablosuna (vptr) durum depolama birimi olduğundan bu gerektiren `v` kutulanmış. Yönetilen Uzantılar dil tasarımını örtük kutulama desteklenmez ancak olarak Programcı tarafından açıkça belirtilmelidir

```
__box( v )->ToString(); // Managed Extensions: note the arrow
```

Bu tasarım arkasındaki birincil neden pedagojik: temel mekanizma Filiz 'değer türünde bir örnek maliyeti' anlayacaksınız böylece programcıya görünür olması gerekir. Olan `V` örneğini içeren `ToString`, kutulama gerekli olmaz.

Nesne, ancak temel maliyeti kutulamanın kendi, açıkça kutulama sözcük karmaşıklığı yeni sözdiziminde kaldırılır:

```
v.ToString(); // new syntax
```

Ancak, büyük olasılıkla Sınıf Tasarımcısı, açık bir örneği sağlanmamış maliyetine yanıltıcı `ToString` yöntemi içinde `V`. Örtük kutulama belgelemeyi nedeni genellikle yalnızca bir sınıf Tasarımcısı olsa da kullanıcılar değiştirme özgürlüğü sahip kim hiçbiri, sınırsız sayıda yoktur `V` açık kutulamayı ortadan kaldırmak için.

Geçersiz kılma örneği sağlayan gerekip gerekmediğini belirlemek üzere ölçüt `ToString` kullanımları konumunu ve sıklığı sınıf arasında bir değer olmalıdır. Nadiren çağrılırsa, da Elbette tanımında küçük avantajı yoktur. Uygulamanın yüksek performanslı olmayan alanlarda çağrılırsa, benzer şekilde, bunu ekleyerek başarımına uygulamanın genel performansını için ekler. Alternatif olarak, bir paketlenmiş değere izleme işleyicisi tutabilirsiniz ve o tanıtıcının çağrılar kutulama gerektirmez.

## <a name="there-is-no-longer-a-value-class-default-constructor"></a>Artık bir değer sınıf varsayılan oluşturucusuna yoktur

Başka bir değer türü ile arasındaki yönetilen uzantıları ve yeni sözdiziminin bir varsayılan oluşturucu desteğinin kaldırılması farktır. Durumlar, ilişkili bir varsayılan oluşturucu çağırmadan değer türünün bir örneği CLR oluşturabilirsiniz yürütme sırasında olduğundan budur. Diğer bir deyişle, değer türünde bir varsayılan oluşturucu desteklemek için Yönetilen Uzantılar altında'girişimi pratikte garanti edilmez. Garanti göz önünde bulundurulduğunda, bunun yerine tamamen bırakma desteği olan, uygulamada belirleyici olması daha iyi olmasını düşünmüştür.

Bu, başlangıçta göründüğü bozuk değil. Her nesne bir değer türü otomatik olarak sıfırlanmasını olmasıdır (diğer bir deyişle, her tür için varsayılan değeri başlatılır). Sonuç olarak, yerel bir örnek üyesi hiçbir zaman tanımsızdır. Bu bağlamda Önemsiz varsayılan bir oluşturucu tanımlama yeteneği kaybı gerçekten kaybı hiç - değil ve hatta CLR tarafından gerçekleştirildiğinde daha verimli olur.

Yönetilen Uzantılar'ın bir kullanıcı, Önemsiz olmayan varsayılan bir oluşturucu tanımladığında sorunudur. Bu, hiçbir eşleme yeni sözdizimine sahiptir. Kod Oluşturucu içinde kullanıcı tarafından açıkça çağrılması gereken adlandırılmış başlatma yönteme girmeyi geçirilmesi gerekir.

Aksi takdirde bir değer türü nesne yeni söz diziminde bildirimi değiştirilmez. Bu olumsuz tarafı, değer türleri aşağıdaki nedenlerden dolayı yerel türleri sarmalama için kabul edilebilir olmadığını şöyledir:

- Bir değer türü içinde yok edici için desteği yoktur. Diğer bir deyişle, bir dizi eylemi nesnenin kullanım ömrü sonu tarafından tetiklenen otomatik hale getirmek için hiçbir yolu yoktur.

- Bir yerel sınıf, ardından yerel yığında ayrılan bir işaretçi olarak yalnızca yönetilen bir tür içinde bulunabilir.

Bir değer türü yerine bir başvuru türü bir çift yığın ayırmasını engellemek için küçük bir yerel sınıfı sarmalama istiyoruz: yerel tür tutmak için yerel yığın ve CLR yığınındaki yönetilen sarmalayıcı tutacak. Değer türünde bir yerel sınıfı sarmalama yönetilen yığını engellemenize olanak sağlar, ancak yerel yığın bellek geri kazanma işlemini otomatik hale getirmek için bir yol sağlar. Yalnızca lisans yönetilen türü, Önemsiz olmayan yerel sınıfları sarmalamak içinden başvuru türleridir.

## <a name="interior-pointers"></a>İç işaretçiler

`Form (2)` ve `Form (3)` bu dünya sonraki (diğer bir deyişle, yönetilen veya yerel her şey) neredeyse her şeyi yukarıdaki karşılayabilirsiniz. Bu nedenle, örneğin, aşağıdakilerin tümü Yönetilen Uzantılar'izin verilir:

```
__value struct V { int i; };
__gc struct R { V vr; };

V v = { 0 };  // Form (1)
V *pv = 0;  // Form (2)
V __gc *pvgc = 0;  // Form (3)
__box V* pvbx = 0;  // Form (4)

R* r;

pv = &v;            // address a value type on the stack
pv = __nogc new V;  // address a value type on native heap
pv = pvgc;          // we are not sure what this addresses
pv = pvbx;          // address a boxed value type on managed heap
pv = &r->vr;        // an interior pointer to value type within a
                    //    reference type on the managed heap
```

Bu nedenle, bir `V*` yerel bir blok içinde bir konuma ele (ve bu nedenle sarkan), yerel içinde genel kapsamda (örneğin, adresleri nesne zaten silinmiş olması durumunda), CLR yığınına yığın (ve istiyorsanız, bu nedenle izlenir binmesi çöp toplama sırasında) ve iç (iç işaretçiye çağrılırken Bu ayrıca saydam bir şekilde izlenir) CLR yığında başvuru nesnesi.

Yönetilen Uzantılar'yerel yönlerini ayırmak için bir yolu yoktur bir `V*`; diğer bir deyişle, kendi (dahil), bunu bir nesne veya alt nesneye yönetilen yığındaki adresleme olasılığını işleme kabul edilir.

Yeni sözdiziminde, bir değer türü işaretçisi iki türe ayrılır: `V*`, CLR olmayan Kaçağı konumlarına ve işaretçiye sınırlı olduğu `interior_ptr<V>`, sağlar, ancak bir adresi ve yönetilen yığında gerektirmez.

```
// may not address within managed heap
V *pv = 0;

// may or may not address within managed heap
interior_ptr<V> pvgc = nullptr;
```

`Form (2)` ve `Form (3)` Yönetilen Uzantılar ' eşlenir `interior_ptr<V>`. `Form (4)` İzleme işleyicisidir. Bu yönetilen yığında Kutulu tüm nesne ele alır. Yeni sözdiziminde çevrilmiş bir `V^`,

```
V^ pvbx = nullptr; // __box V* pvbx = 0;
```

Aşağıdaki bildirimleri Yönetilen Uzantılar tüm yeni sözdiziminde iç işaretçiler eşleyin. (Değer türleri içinde oldukları `System` ad.)

```
Int32 *pi;   // => interior_ptr<Int32> pi;
Boolean *pb; // => interior_ptr<Boolean> pb;
E *pe;       // => interior_ptr<E> pe; // Enumeration
```

Diğer türlere olarak hizmet rağmen yerleşik türler yönetilen türler dikkate alınmaz `System` ad alanı. Bu nedenle şu eşlemeler arasında yönetilen uzantıları ve yeni sözdiziminin doğru tutun:

```
int * pi;     // => int* pi;
int __gc * pi2; // => interior_ptr<int> pi2;
```

Çevirirken bir `V*` var olan programınızı en koruyucu strateji etmektir her zaman bir `interior_ptr<V>`. Yönetilen Uzantılar'altında nasıl değerlendirilme budur. Yeni sözdiziminde, programcı belirterek yönetilmeyen yığın adresleri için bir değer türü kısıtlama seçeneği vardır. `V*` iç işaretçiye yerine. Programınızı çevirirken, geçişli kapatma tüm kullanımlarını yapın ve yönetilen yığında hiçbir atanan adresi olduğundan emin olarak bırakarak `V*` bir sakınca yoktur.

## <a name="pinning-pointers"></a>İşaretçileri sabitleme

Çöp toplayıcı, isteğe bağlı olarak farklı konumlara yığın içinde CLR yığında genellikle bir sıkıştırma aşaması sırasında bulunan nesneleri taşıyabilir. Bu taşıma izleme tanıtıcıları, izleme başvuruları ve iç işaretçiler, bu varlıkları şeffaf bir şekilde güncelleştirmek için bir sorun değildir. Kullanıcının çalışma zamanı ortamı dışında CLR yığındaki bir nesne adresi geçtiyse Bu taşıma ancak bir sorun olur. Bu durumda, çalışma zamanı hatasına neden olabilecek geçici nesne hareketini ' dir. Taşınan biz gerekir yerel olarak sabitleme bunları konumlarına kapsam dışında kullanımları için bunlardan gibi muaf nesnelere.

Yönetilen Uzantılar bir *sabitleme işaretçisi* bir işaretçi bildirimi ile uygun tarafından bildirilen `__pin` anahtar sözcüğü. Yönetilen Uzantılar'belirtiminden biraz değiştirilmiş bir örnek aşağıda verilmiştir:

```
__gc struct H { int j; };

int main()
{
   H * h = new H;
   int __pin * k = & h -> j;

   // ...
};
```

Yeni dil tasarımında, iç işaretçiye benzer bir sözdizimi ile bir sabitleme işaretçisi bildirilir.

```
ref struct H
{
public:
   int j;
};

int main()
{
   H^ h = gcnew H;
   pin_ptr<int> k = &h->j;

   // ...
}
```

Yeni sözdiziminde bir sabitleme işaretçisi, iç işaretçiye özel bir durumdur. Bir sabitleme işaretçisi özgün kısıtlamalar kalır. Örneğin, bir parametre olarak kullanılamaz veya dönüş türü bir yöntemin; yalnızca yerel bir nesne üzerinde bildirilebilir. Birkaç ek kısıtlamalar, ancak yeni sözdiziminde eklendi.

Varsayılan değer, bir sabitleme işaretçisi `nullptr`değil `0`. A `pin_ptr<>` başlatılmamış veya atanan `0`. Tüm atamalarını `0` mevcut kod içinde değiştirilmesi gerekecektir `nullptr`.

Yönetilen Uzantılar altında bir sabitleme işaretçisi Yönetilen Uzantılar'belirtiminden alınan aşağıdaki örnekte olduğu gibi tüm bir nesneye yönelik izin verilir:

```
__gc class G {
public:
   void incr(int* pi) { pi += 1; }
};
__gc struct H { int j; };
void f( G * g ) {
   H __pin * pH = new H;
   g->incr(& pH -> j);
};
```

Yeni sözdiziminde, tüm nesne sabitlenmesi döndürdüğü `new` ifadesi desteklenmiyor. Bunun yerine, iç üyenin adresi sabitlenmiş gerekir. Örneğin,

```
ref class G {
public:
   void incr(int* pi) { *pi += 1; }
};
ref struct H { int j; };
void f( G^ g ) {
   H ^ph = gcnew H;
   Console::WriteLine(ph->j);
   pin_ptr<int> pj = &ph->j;
   g->incr(  pj );
   Console::WriteLine(ph->j);
}
```

## <a name="see-also"></a>Ayrıca Bkz.

[Değer Türleri ve Davranışları (C++/CLI)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)<br/>
[Sınıflar ve Yapılar](../windows/classes-and-structs-cpp-component-extensions.md)<br/>
[interior_ptr (C++/CLI)](../windows/interior-ptr-cpp-cli.md)<br/>
[pin_ptr (C++/CLI)](../windows/pin-ptr-cpp-cli.md)