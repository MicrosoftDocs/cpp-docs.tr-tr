---
title: hash_set Sınıfı
ms.date: 11/04/2016
f1_keywords:
- hash_set/stdext::hash_set
- hash_set/stdext::hash_set::allocator_type
- hash_set/stdext::hash_set::const_iterator
- hash_set/stdext::hash_set::const_pointer
- hash_set/stdext::hash_set::const_reference
- hash_set/stdext::hash_set::const_reverse_iterator
- hash_set/stdext::hash_set::difference_type
- hash_set/stdext::hash_set::iterator
- hash_set/stdext::hash_set::key_compare
- hash_set/stdext::hash_set::key_type
- hash_set/stdext::hash_set::pointer
- hash_set/stdext::hash_set::reference
- hash_set/stdext::hash_set::reverse_iterator
- hash_set/stdext::hash_set::size_type
- hash_set/stdext::hash_set::value_compare
- hash_set/stdext::hash_set::value_type
- hash_set/stdext::hash_set::begin
- hash_set/stdext::hash_set::cbegin
- hash_set/stdext::hash_set::cend
- hash_set/stdext::hash_set::clear
- hash_set/stdext::hash_set::count
- hash_set/stdext::hash_set::crbegin
- hash_set/stdext::hash_set::crend
- hash_set/stdext::hash_set::emplace
- hash_set/stdext::hash_set::emplace_hint
- hash_set/stdext::hash_set::empty
- hash_set/stdext::hash_set::end
- hash_set/stdext::hash_set::equal_range
- hash_set/stdext::hash_set::erase
- hash_set/stdext::hash_set::find
- hash_set/stdext::hash_set::get_allocator
- hash_set/stdext::hash_set::insert
- hash_set/stdext::hash_set::key_comp
- hash_set/stdext::hash_set::lower_bound
- hash_set/stdext::hash_set::max_size
- hash_set/stdext::hash_set::rbegin
- hash_set/stdext::hash_set::rend
- hash_set/stdext::hash_set::size
- hash_set/stdext::hash_set::swap
- hash_set/stdext::hash_set::upper_bound
- hash_set/stdext::hash_set::value_comp
helpviewer_keywords:
- stdext::hash_set
- stdext::hash_set::allocator_type
- stdext::hash_set::const_iterator
- stdext::hash_set::const_pointer
- stdext::hash_set::const_reference
- stdext::hash_set::const_reverse_iterator
- stdext::hash_set::difference_type
- stdext::hash_set::iterator
- stdext::hash_set::key_compare
- stdext::hash_set::key_type
- stdext::hash_set::pointer
- stdext::hash_set::reference
- stdext::hash_set::reverse_iterator
- stdext::hash_set::size_type
- stdext::hash_set::value_compare
- stdext::hash_set::value_type
- stdext::hash_set::begin
- stdext::hash_set::cbegin
- stdext::hash_set::cend
- stdext::hash_set::clear
- stdext::hash_set::count
- stdext::hash_set::crbegin
- stdext::hash_set::crend
- stdext::hash_set::emplace
- stdext::hash_set::emplace_hint
- stdext::hash_set::empty
- stdext::hash_set::end
- stdext::hash_set::equal_range
- stdext::hash_set::erase
- stdext::hash_set::find
- stdext::hash_set::get_allocator
- stdext::hash_set::insert
- stdext::hash_set::key_comp
- stdext::hash_set::lower_bound
- stdext::hash_set::max_size
- stdext::hash_set::rbegin
- stdext::hash_set::rend
- stdext::hash_set::size
- stdext::hash_set::swap
- stdext::hash_set::upper_bound
- stdext::hash_set::value_comp
ms.assetid: c765c06e-cbb6-48c2-93ca-d15468eb28d7
ms.openlocfilehash: becf038678f4abbe285e719e4d1cc1f3f12de982
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689543"
---
# <a name="hash_set-class"></a>hash_set Sınıfı

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Kapsayıcı sınıfı hash_set, C++ standart kitaplığın bir uzantısıdır ve içerdiği öğelerin değerlerinin benzersiz olduğu ve anahtar değerler olarak kullanıldığı bir koleksiyondaki verilerin depolanması ve hızlı bir şekilde alınması için kullanılır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Key,
    class Traits=hash_compare<Key, less<Key>>,
    class Allocator=allocator<Key>>
class hash_set
```

### <a name="parameters"></a>Parametreler

*Anahtar* \
Hash_set içinde depolanacak öğe veri türü.

*Nitelikler* \
İki işlev nesnesi içeren tür, bir ikili koşul olan sınıf karşılaştırmadan, kendi göreli sıralarını ve öğelerin birli koşul eşleme anahtarı değerleri işaretsiz olan bir karma işlevi `size_t` türünde tamsayılar. Bu bağımsız değişken isteğe bağlıdır ve `hash_compare<Key, less<Key> >` varsayılan değerdir.

*Ayırıcı* \
Belleğin hash_set's ayırması ve ayırmayı kaldırma hakkındaki ayrıntıları kapsülleyen saklı ayırıcı nesnesini temsil eden tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `allocator<Key>`.

## <a name="remarks"></a>Açıklamalar

Hash_set:

- İlişkili bir anahtar değerine dayalı öğe değerlerinin verimli alınmasını destekleyen bir değişken boyutu kapsayıcı olan ilişkilendirilebilir bir kapsayıcı. Dahası, basit bir ilişkilendirilebilir kapsayıcıdır, çünkü öğelerinin değerleri kendi anahtar değerleridir.

- Çift yönlüdür, çünkü öğelerine erişmek için çift yönlü bir yineleyici sağlar.

- Karma değeri, öğelerinin anahtar değerlerine uygulanan bir karma işlevin değerine bağlı olarak demet halinde gruplandığından karma hale getirilir.

- Benzersizdir, çünkü öğelerinin her birinde benzersiz bir anahtar olması gerekir. Hash_set Ayrıca basit ilişkilendirilebilir bir kapsayıcı olduğundan, öğeleri de benzersizdir.

- Bir sınıf şablonu, sağladığı işlevsellik geneldir ve bu nedenle öğe veya anahtar olarak içerilen belirli veri türünden bağımsızdır. Öğeler ve anahtarlar için kullanılacak veri türleri, karşılaştırma işlevi ve ayırıcı ile birlikte bir sınıf şablonunda parametreler olarak belirtilir.

Sıralama üzerinden karmalamanın başlıca avantajı daha fazla verimlilik; başarılı bir karma değer ekleme, silme işlemleri gerçekleştirir ve sabit ortalama süre içinde, sıralama teknikleri için kapsayıcıdaki öğelerin sayısının logaritmasına kıyasla bir zaman orantılı olarak bulur. Bir kümedeki bir öğenin değeri doğrudan değiştirilemez. Bunun yerine, eski değerleri silmeniz ve yeni değerlere sahip öğeler eklemeniz gerekir.

Kapsayıcı türünün seçimi genelde uygulamanın gerektirdiği arama ve ekleme türüne dayalı olmalıdır. Karma olarak ilişkilendirilebilir kapsayıcılar, arama, ekleme ve kaldırma işlemleri için iyileştirilmiştir. Bu işlemleri açıkça destekleyen üye işlevleri, iyi tasarlanmış bir karma işlevi ile kullanıldığında etkili olur ve bunları ortalama Sabitte olan ve kapsayıcıdaki öğelerin sayısına bağımlı olmayan bir zaman içinde gerçekleştiriyor. İyi tasarlanmış bir karma işlevi, karma değerler için Tekdüzen bir dağıtım üretir ve ayrı anahtar değerleri aynı karma değere eşlendiğinde bir çarpışmanın oluşmasına neden olan çakışmaların sayısını en aza indirir. En kötü durumda, mümkün olan en kötü karma işlevi olan işlem sayısı, dizideki öğelerin sayısıyla orantılıdır (doğrusal saat).

Değerleri, anahtar ile ilişkilendirirken, uygulama tarafından karşılanmadığı durumlarda hash_set 'in ilişkilendirilebilir kapsayıcısı olmalıdır. Bir hash_set öğeleri benzersizdir ve kendi sıralama anahtarları olarak görev yapar. Bu tür bir yapı modeli, sözcüklerin yalnızca bir defa geçebildiği sıralı bir sözcükler listesindedir. Sözcüklerin birden çok örneğine izin veriliyorsa, hash_multiset uygun kapsayıcı yapısı olur. Değerlerin benzersiz anahtar sözcükler listesine eklenmesi gerekiyorsa, hash_map bu verileri içeren uygun bir yapı olacaktır. Bunun yerine anahtarlar benzersiz değilse, hash_multimap kapsayıcı olur.

Hash_set, [value_compare](#value_compare)türünde bir depolanmış karma `Traits` nesnesi çağırarak denetlediği diziyi sıralar. Bu saklı nesneye [key_comp](#key_comp)üye işlevi çağırarak erişilebilir. Böyle bir işlev nesnesi, hash_compare < Key sınıfının bir nesnesiyle aynı davranmalıdır *> > daha az \<Key.* Özellikle, anahtar türü `key` tüm değerler için, Call nitelik (`key`), size_t türündeki değerlerin bir dağılımını verir.

Genelde, bu sıralamayı oluşturmak için öğelerin yalnızca küçüktür biçiminde karşılaştırılabilir olması gerekir; böylece, herhangi iki öğe belirtildiğinde, eşit oldukları (yani birinin diğerinden daha küçük olmadığı anlamında) veya birinin diğerinden küçük olduğu belirlenebilir. Bu, denk olmayan öğeler arasında bir sıralamaya neden olur. Daha teknik bir not üzerinde, karşılaştırma işlevi standart matematiksel anlamda katı bir zayıf sıralama sevk eden ikili bir koşuldur. Bir ikili koşul *f*( *x*, *y*) iki bağımsız değişken nesnesi olan x ve y ve true ya da false dönüş değerine sahip bir işlev nesnesidir. İkili koşul geri dönüşsüz, antisimetrik ve geçişli ve denklik geçişli ise, hash_set üzerine getirilen bir sıralama katı zayıf bir sıradır, burada iki nesne *x* ve *y* , her ikisi de *f*( *x* , *y*) ve *f*( *y*, *x*) false 'tur. Anahtarlar arasındaki eşitliğinin daha güçlü koşulu bu denkliğin yerini alırsa, sıralama (içindeki tüm öğelerin birbirine göre sıralanması anlamında) toplam haline gelir ve eşleşen anahtarlar birbirinden ayırt edilemez olacaktır.

Denetlenen dizideki öğelerin gerçek sırası, karma işleve, sıralama işlevine ve kapsayıcı nesnesinde depolanan karma tablonun geçerli boyutuna bağlıdır. Karma tablonun geçerli boyutunu belirleyemez, bu nedenle denetimli dizideki öğelerin sırasını genel olarak tahmin edemezsiniz. Öğelerin eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; öğelerin kaldırılması yalnızca özellikle kaldırılan öğeleri gösteren yineleyicileri geçersiz kılar.

Hash_set Sınıfı tarafından sunulan Yineleyici çift yönlü bir yineleyicidir, ancak [Insert](#insert) ve [hash_set](#hash_set) sınıf üyesi işlevleri, şablon parametresi olarak alan ve işlev gereksinimleri daha zayıf bir giriş yineleyicisi olan sürümlere sahiptir Çift yönlü yineleyicilerin sınıfının garantisi olan en az. Farklı yineleyici kavramları, işlevselliklerindeki iyileştirmelere göre ilgili bir aile biçimlendirir. Her yineleyici kavramının kendi gereksinimler kümesi vardır ve bunlarla çalışan algoritmaların kendi varsayımlarını yineleyici türü tarafından sağlanan gereksinimlerle sınırlaması gerekir. Bir giriş yineleyicinin bazı nesnelere başvurusunun kaldırılacağı ve dizideki sonraki yineleyiciye artırılabileceği varsayılabilir. Bu en düşük işlevsellik kümesidir, ancak sınıf üye işlevleri bağlamında yineleyicilerin bir aralığı [`first`, `last`) hakkında anlamlı bir şekilde konuşabilmek yeterlidir.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[hash_set](#hash_set)|Boş olan veya diğer bir `hash_set` tümünün veya bir kısmının kopyası olan bir `hash_set` oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[allocator_type](#allocator_type)|@No__t_1 nesnesi için `allocator` sınıfını temsil eden bir tür.|
|[const_iterator](#const_iterator)|@No__t_1 `const` bir öğeyi okuyabilen çift yönlü bir yineleyici sağlayan bir tür.|
|[const_pointer](#const_pointer)|@No__t_1 bir **const** öğesine işaretçi sağlayan bir tür.|
|[const_reference](#const_reference)|**Const** işlemlerini okumak ve gerçekleştirmek için bir `hash_set` depolanan **const** öğesine başvuru sağlayan bir tür.|
|[const_reverse_iterator](#const_reverse_iterator)|@No__t_1 herhangi bir **const** öğesini okuyabilen çift yönlü bir yineleyici sağlayan bir tür.|
|[difference_type](#difference_type)|Yineleyiciler tarafından gösterilen öğeler arasındaki bir aralıktaki `hash_set` öğelerinin sayısını temsil etmek için kullanılabilen işaretli bir tamsayı türü.|
|[iden](#iterator)|Bir `hash_set` herhangi bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleyici sağlayan bir tür.|
|[key_compare](#key_compare)|@No__t_0 iki öğenin göreli sırasını belirleyebilmek için iki sıralama anahtarını karşılaştıran bir işlev nesnesi sağlayan bir tür.|
|[key_type](#key_type)|@No__t_0 öğesi olarak depolanan bir nesneyi sıralama anahtarı olarak kapasitesinde tanımlayan bir tür.|
|[çağrısı](#pointer)|@No__t_0 bir öğeye işaretçi sağlayan bir tür.|
|[başvurunun](#reference)|@No__t_0 depolanan bir öğeye başvuru sağlayan bir tür.|
|[reverse_iterator](#reverse_iterator)|Ters çevrilen bir `hash_set` bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleyici sağlayan bir tür.|
|[size_type](#size_type)|Bir `hash_set` öğe sayısını temsil eden işaretsiz bir tamsayı türü.|
|[value_compare](#value_compare)|İki işlev nesnesi sağlayan bir tür, bir `hash_set` iki öğe değerini karşılaştırabilir ve öğelerin karma oluşturan birli bir koşulu tespit edebilir.|
|[value_type](#value_type)|Bir değeri bir değer olarak kapasitesinin `hash_set` bir öğesi olarak tanımlayan bir tür.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[başladı](#begin)|@No__t_0 ilk öğeyi ele alan bir yineleyici döndürür.|
|[cbegin](#cbegin)|@No__t_0 ilk öğeyi adresleyen bir const yineleyici döndürür.|
|[cend](#cend)|@No__t_0 son öğeden sonraki konumu ele alan bir const yineleyici döndürür.|
|[lediğiniz](#clear)|@No__t_0 tüm öğelerini siler.|
|[biriktirme](#count)|Anahtarı parametre tarafından belirtilen anahtarla eşleşen bir `hash_set` öğe sayısını döndürür.|
|[crbegin](#crbegin)|Ters çevrilen `hash_set` ilk öğeyi adresleyen bir const yineleyici döndürür.|
|[crend](#crend)|Ters çevrilen `hash_set` son öğeden sonraki konumu ele alan bir const yineleyici döndürür.|
|[Emplace](#emplace)|Bir `hash_set` içinde oluşturulmuş bir öğe ekler.|
|[emplace_hint](#emplace_hint)|Yerleştirme ipucuyla birlikte `hash_set` oluşturulan bir öğe ekler.|
|[olmamalıdır](#empty)|@No__t_0 boş ise sınar.|
|[erer](#end)|@No__t_0 son öğeden sonraki konumu ele alan bir yineleyici döndürür.|
|[equal_range](#equal_range)|Belirtilen anahtardan daha büyük bir anahtarla ve anahtardan daha büyük veya ona eşit olan bir anahtarla `hash_set` ilk öğe olan bir `hash_set` yineleyicilerin bir çiftini döndürür.|
|[silme](#erase)|Belirtilen konumlardan bir `hash_set` öğeyi veya öğe aralığını kaldırır veya belirtilen bir anahtarla eşleşen öğeleri kaldırır.|
|[bilgi](#find)|Belirtilen anahtara eşdeğer bir anahtara sahip bir `hash_set` öğenin konumunu ele alan bir yineleyici döndürür.|
|[get_allocator](#get_allocator)|@No__t_1 oluşturmak için kullanılan `allocator` nesnesinin bir kopyasını döndürür.|
|[ekleyin](#insert)|Bir `hash_set` öğe veya öğe aralığı ekler.|
|[key_comp](#key_comp)|@No__t_0 anahtarları sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır.|
|[lower_bound](#lower_bound)|Bir yineleyiciyi belirtilen anahtardan daha büyük veya ona eşit bir anahtarla bir `hash_set` ilk öğeye döndürür.|
|[max_size](#max_size)|@No__t_0 maksimum uzunluğunu döndürür.|
|[rbegin](#rbegin)|Ters çevrilen `hash_set` ilk öğeyi adresleyen bir yineleyici döndürür.|
|[rend](#rend)|Ters çevrilen `hash_set` son öğeden sonraki konumu ele alan bir yineleyici döndürür.|
|[boyutla](#size)|@No__t_0 öğe sayısını döndürür.|
|[Kur](#swap)|İki `hash_set`s öğelerini değiş tokuş eder.|
|[upper_bound](#upper_bound)|Bir yineleyiciyi belirtilen anahtardan daha büyük veya ona eşit olan bir anahtarla `hash_set` ilk öğeye döndürür.|
|[value_comp](#value_comp)|Bir `hash_set` öğe anahtar değerlerini karma ve sıralama için kullanılan karma nitelikleri nesnesinin bir kopyasını alır.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[hash_set:: operator =](#op_eq)|@No__t_0 öğelerini başka bir `hash_set` kopyasıyla değiştirir.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<hash_set >

**Ad alanı:** stdext

## <a name="allocator_type"></a>hash_set::allocator_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Hash_set nesnesinin ayırıcı sınıfını temsil eden bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::allocator_type allocator_type;
```

### <a name="remarks"></a>Açıklamalar

`allocator_type`, şablon parametre *ayırıcısı*için bir eş anlamlı.

*Ayırıcı*hakkında daha fazla bilgi Için [hash_set Class](../standard-library/hash-set-class.md) konusunun açıklamalar bölümüne bakın.

### <a name="example"></a>Örnek

@No__t_1 kullanan bir örnek için bkz. [get_allocator](#get_allocator) .

## <a name="begin"></a>hash_set:: Begin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Hash_set içindeki ilk öğeyi ele alan bir yineleyici döndürür.

```cpp
const_iterator begin() const;

iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

Hash_set içindeki ilk öğeyi ele alarak çift yönlü bir yineleyici veya bir boş hash_set başarılı bir.

### <a name="remarks"></a>Açıklamalar

@No__t_0 dönüş değeri bir `const_iterator` atanırsa, hash_set nesnesindeki öğeler değiştirilemez. @No__t_0 dönüş değeri bir `iterator` atanırsa, hash_set nesnesindeki öğeler değiştirilebilir.

### <a name="example"></a>Örnek

```cpp
// hash_set_begin.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;
   hash_set <int>::iterator hs1_Iter;
   hash_set <int>::const_iterator hs1_cIter;

   hs1.insert( 1 );
   hs1.insert( 2 );
   hs1.insert( 3 );

   hs1_Iter = hs1.begin( );
   cout << "The first element of hs1 is " << *hs1_Iter << endl;

   hs1_Iter = hs1.begin( );
   hs1.erase( hs1_Iter );

   // The following 2 lines would err because the iterator is const
   // hs1_cIter = hs1.begin( );
   // hs1.erase( hs1_cIter );

   hs1_cIter = hs1.begin( );
   cout << "The first element of hs1 is now " << *hs1_cIter << endl;
}
```

```Output
The first element of hs1 is 1
The first element of hs1 is now 2
```

## <a name="cbegin"></a>hash_set:: cbegin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Hash_set içindeki ilk öğeyi ele alan bir sabit yineleyici döndürür.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

[Hash_set](../standard-library/hash-set-class.md) içindeki ilk öğeyi ele alarak const çift yönlü yineleyicisi veya konumdaki boş bir `hash_set`.

### <a name="remarks"></a>Açıklamalar

@No__t_0 dönüş değeri ile `hash_set` nesnesindeki öğeler değiştirilemez.

### <a name="example"></a>Örnek

```cpp
// hash_set_cbegin.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;
   hash_set <int>::const_iterator hs1_cIter;

   hs1.insert( 1 );
   hs1.insert( 2 );
   hs1.insert( 3 );

   hs1_cIter = hs1.cbegin( );
   cout << "The first element of hs1 is " << *hs1_cIter << endl;
}
```

```Output
The first element of hs1 is 1
```

## <a name="cend"></a>hash_set:: cend

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Bir hash_set içindeki son öğeden sonraki konumu ele alan bir const yineleyici döndürür.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir [hash_set](../standard-library/hash-set-class.md)içindeki son öğeden sonra gelen konumu ele alan bir const çift yönlü Yineleyici. @No__t_0 boşsa, `hash_set::cend == hash_set::begin`.

### <a name="remarks"></a>Açıklamalar

`cend`, bir yineleyicinin `hash_set` sonuna ulaşılıp ulaşılmadığını test etmek için kullanılır. @No__t_0 tarafından döndürülen değer başvurulmamalıdır.

### <a name="example"></a>Örnek

```cpp
// hash_set_cend.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;
   hash_set <int> :: const_iterator hs1_cIter;

   hs1.insert( 1 );
   hs1.insert( 2 );
   hs1.insert( 3 );

   hs1_cIter = hs1.cend( );
   hs1_cIter--;
   cout << "The last element of hs1 is " << *hs1_cIter << endl;
}
```

```Output
The last element of hs1 is 3
```

## <a name="clear"></a>hash_set:: Clear

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Bir hash_set öğesinin tüm öğelerini siler.

```cpp
void clear();
```

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_set_clear.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;

   hs1.insert( 1 );
   hs1.insert( 2 );

   cout << "The size of the hash_set is initially " << hs1.size( )
        << "." << endl;

   hs1.clear( );
   cout << "The size of the hash_set after clearing is "
        << hs1.size( ) << "." << endl;
}
```

```Output
The size of the hash_set is initially 2.
The size of the hash_set after clearing is 0.
```

## <a name="const_iterator"></a>hash_set::const_iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Hash_set içinde bir **const** öğesini okuyabilen çift yönlü bir yineleyici sağlayan bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_iterator const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_iterator`, bir öğenin değerini değiştirmek için kullanılamaz.

### <a name="example"></a>Örnek

@No__t_1 kullanan bir örnek için [Begin](#begin) örneğine bakın.

## <a name="const_pointer"></a>hash_set::const_pointer

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Bir hash_set içinde **const** öğesine işaretçi sağlayan bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_pointer const_pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_pointer`, bir öğenin değerini değiştirmek için kullanılamaz.

Çoğu durumda, bir **const** hash_set nesnesindeki öğelere erişmek için bir [const_iterator](#const_iterator) kullanılmalıdır.

## <a name="const_reference"></a>hash_set::const_reference

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

**Const** işlemlerini okumak ve gerçekleştirmek için bir hash_set depolanan **const** öğesine başvuru sağlayan bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_reference const_reference;
```

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_set_const_ref.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;

   hs1.insert( 10 );
   hs1.insert( 20 );

   // Declare and initialize a const_reference &Ref1
   // to the 1st element
   const int &Ref1 = *hs1.begin( );

   cout << "The first element in the hash_set is "
        << Ref1 << "." << endl;

   // The following line would cause an error because the
   // const_reference cannot be used to modify the hash_set
   // Ref1 = Ref1 + 5;
}
```

```Output
The first element in the hash_set is 10.
```

## <a name="const_reverse_iterator"></a>hash_set::const_reverse_iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Hash_set içinde herhangi bir **const** öğesini okuyabilen çift yönlü bir yineleyici sağlayan bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_reverse_iterator const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_reverse_iterator`, bir öğenin değerini değiştiremiyor ve hash_set içinde ters yönde yinelemek için kullanılır.

### <a name="example"></a>Örnek

@No__t_1 bildirme ve kullanma hakkında bir örnek için bkz. [rend](#rend) örneği

## <a name="count"></a>hash_set:: Count

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Anahtarı parametre tarafından belirtilen anahtarla eşleşen bir hash_set içindeki öğe sayısını döndürür.

```cpp
size_type count(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*anahtar* \
Hash_set eşleştirilecek öğelerin anahtarı.

### <a name="return-value"></a>Dönüş Değeri

hash_set, sıralama anahtarı parametre anahtarıyla eşleşen bir öğe içeriyorsa 1.

hash_set, eşleşen bir anahtara sahip bir öğe içermiyorsa 0.

### <a name="remarks"></a>Açıklamalar

Üye işlevi aşağıdaki aralıktaki öğelerin sayısını döndürür:

\[ lower_bound (*anahtar*), upper_bound (*anahtar*)).

### <a name="example"></a>Örnek

Aşağıdaki örnek, hash_set:: Count üye işlevinin kullanımını gösterir.

```cpp
// hash_set_count.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
    using namespace std;
    using namespace stdext;
    hash_set<int> hs1;
    hash_set<int>::size_type i;

    hs1.insert(1);
    hs1.insert(1);

    // Keys must be unique in hash_set, so duplicates are ignored.
    i = hs1.count(1);
    cout << "The number of elements in hs1 with a sort key of 1 is: "
         << i << "." << endl;

    i = hs1.count(2);
    cout << "The number of elements in hs1 with a sort key of 2 is: "
         << i << "." << endl;
}
```

```Output
The number of elements in hs1 with a sort key of 1 is: 1.
The number of elements in hs1 with a sort key of 2 is: 0.
```

## <a name="crbegin"></a>hash_set:: crbegin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Ters çevrilen bir hash_set ilk öğeyi ele alarak bir const yineleyici döndürür.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir [hash_set](../standard-library/hash-set-class.md) içindeki ilk öğeyi ele almak veya geri çevrilmeyen `hash_set` son öğe olduğunu belirlemek için bir const ters çift yönlü Yineleyici.

### <a name="remarks"></a>Açıklamalar

`crbegin`, [hash_set:: Begin](#begin) bir hash_set ile birlikte kullanılan ters bir hash_set ile kullanılır.

@No__t_0 dönüş değeri ile `hash_set` nesnesi değiştirilemez.

`crbegin`, `hash_set` geriye doğru yinelemek için kullanılabilir.

### <a name="example"></a>Örnek

```cpp
// hash_set_crbegin.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;
   hash_set <int>::const_reverse_iterator hs1_crIter;

   hs1.insert( 10 );
   hs1.insert( 20 );
   hs1.insert( 30 );

   hs1_crIter = hs1.crbegin( );
   cout << "The first element in the reversed hash_set is "
        << *hs1_crIter << "." << endl;
}
```

```Output
The first element in the reversed hash_set is 30.
```

## <a name="crend"></a>hash_set:: crend

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Ters çevrilen bir hash_set son öğeden sonraki konumu ele alan bir const yineleyici döndürür.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir [hash_set](../standard-library/hash-set-class.md) (önünde olmayan `hash_set` ilk öğeden önce gelen konum) son öğeden sonra gelen konumu ele alan bir sabit ters çift yönlü Yineleyici.

### <a name="remarks"></a>Açıklamalar

`crend`, [hash_set:: End](#end) bir `hash_set` ile birlikte kullanılan ters bir `hash_set` ile kullanılır.

@No__t_0 dönüş değeri ile `hash_set` nesnesi değiştirilemez.

`crend`, geriye doğru bir yineleyicinin `hash_set` sonuna ulaşıp ulaşılmadığını test etmek için kullanılabilir.

### <a name="example"></a>Örnek

```cpp
// hash_set_crend.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;
   hash_set <int>::const_reverse_iterator hs1_crIter;

   hs1.insert( 10 );
   hs1.insert( 20 );
   hs1.insert( 30 );

   hs1_crIter = hs1.crend( );
   hs1_crIter--;
   cout << "The last element in the reversed hash_set is "
        << *hs1_crIter << "." << endl;
}
```

```Output
The last element in the reversed hash_set is 10.
```

## <a name="difference_type"></a>hash_set::d ifference_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Yineleyiciler tarafından gösterilen öğeler arasındaki bir aralıktaki bir hash_set öğelerinin sayısını temsil etmek için kullanılabilen işaretli bir tamsayı türü.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

@No__t_0 kapsayıcının yineleyiciler aracılığıyla çıkartılacak veya arttırılarak döndürülen türdür. @No__t_0 genellikle yineleyiciler `first` ve `last` arasındaki [`first`, `last`) aralıktaki öğelerin sayısını temsil etmek için kullanılır, `first` tarafından işaret edilen öğeyi ve öğe aralığını , ancak `last` tarafından işaret edilen öğe dahil değildir.

@No__t_0, bir giriş yineleyicisinin gereksinimlerini karşılayan tüm yineleyiciler için kullanılabilir olsa da, bu arada ters çevrilebilir kapsayıcılar tarafından desteklenen çift yönlü yineleyicilerin sınıfını içeren, yineleyiciler arasındaki çıkarma yalnızca vektör veya deque gibi rastgele erişim kapsayıcısı tarafından sunulan rastgele erişim yineleyiciler.

### <a name="example"></a>Örnek

```cpp
// hash_set_diff_type.cpp
// compile with: /EHsc
#include <iostream>
#include <hash_set>
#include <algorithm>

int main( )
{
   using namespace std;
   using namespace stdext;

   hash_set <int> hs1;
   hash_set <int>::iterator hs1_Iter, hs1_bIter, hs1_eIter;

   hs1.insert( 20 );
   hs1.insert( 10 );
   hs1.insert( 20 );   // Won't insert as hash_set elements are unique

   hs1_bIter = hs1.begin( );
   hs1_eIter = hs1.end( );

   hash_set <int>::difference_type   df_typ5, df_typ10, df_typ20;

   df_typ5 = count( hs1_bIter, hs1_eIter, 5 );
   df_typ10 = count( hs1_bIter, hs1_eIter, 10 );
   df_typ20 = count( hs1_bIter, hs1_eIter, 20 );

   // The keys, and hence the elements, of a hash_set are unique,
   // so there is at most one of a given value
   cout << "The number '5' occurs " << df_typ5
        << " times in hash_set hs1.\n";
   cout << "The number '10' occurs " << df_typ10
        << " times in hash_set hs1.\n";
   cout << "The number '20' occurs " << df_typ20
        << " times in hash_set hs1.\n";

   // Count the number of elements in a hash_set
   hash_set <int>::difference_type  df_count = 0;
   hs1_Iter = hs1.begin( );
   while ( hs1_Iter != hs1_eIter)
   {
      df_count++;
      hs1_Iter++;
   }

   cout << "The number of elements in the hash_set hs1 is: "
        << df_count << "." << endl;
}
```

```Output
The number '5' occurs 0 times in hash_set hs1.
The number '10' occurs 1 times in hash_set hs1.
The number '20' occurs 1 times in hash_set hs1.
The number of elements in the hash_set hs1 is: 2.
```

## <a name="emplace"></a>hash_set:: emplace

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Bir hash_set içinde oluşturulmuş bir öğe ekler.

```cpp
template <class ValTy>
pair <iterator, bool>
emplace(
    ValTy&& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Acil*|@No__t_1 zaten bu öğeyi veya daha genel olarak, anahtarı equivalently olan bir öğeyi içermediği müddetçe, [hash_set](../standard-library/hash-set-class.md) içine eklenecek bir öğe değeri.|

### <a name="return-value"></a>Dönüş Değeri

@No__t_0 member işlevi, bir ekleme işlemi varsa **bool** bileşeni **true** döndüren bir çift döndürür ve `hash_set` zaten anahtarı sıralamada denk bir değere sahip olan bir **öğe içeriyorsa ve** Yineleyici Bileşen, yeni bir öğenin eklendiği veya öğenin zaten bulunduğu yerdeki adresi döndürür.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_set_emplace.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>
#include <string>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set<string> hs3;
   string str1("a");

   hs3.emplace(move(str1));
   cout << "After the emplace insertion, hs3 contains "
      << *hs3.begin() << "." << endl;
}
```

```Output
After the emplace insertion, hs3 contains a.
```

## <a name="emplace_hint"></a>hash_set::emplace_hint

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Bir hash_set içinde oluşturulmuş bir öğe ekler.

```cpp
template <class ValTy>
iterator emplace(
    const_iterator _Where,
    ValTy&& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Acil*|@No__t_1 zaten bu öğeyi veya daha genel olarak, anahtarı equivalently olan bir öğeyi içermediği müddetçe, [hash_set](../standard-library/hash-set-class.md) içine eklenecek bir öğe değeri.|
|*_Konum*|Doğru ekleme noktasını aramaya başlamak için yer. (Ekleme noktası *_Nerede*olursa), ekleme noktası, Logaritmik süre yerine, sabit zamanlı olarak ortaya çıkabilir.|

### <a name="return-value"></a>Dönüş Değeri

[Hash_set:: emplace](#emplace) üye işlevi, yeni öğenin `hash_set` eklendiği konuma veya eşdeğer sıralamaya sahip olan öğenin bulunduğu konuma işaret eden bir yineleyici döndürür.

### <a name="remarks"></a>Açıklamalar

Ekleme noktası *_Nerede*olursa, ekleme noktası, logaritmik bir süre yerine, sabit zamanlı olarak bir araya gelebilir.

### <a name="example"></a>Örnek

```cpp
// hash_set_emplace_hint.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>
#include <string>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set<string> hs3;
   string str1("a");

   hs3.insert(hs3.begin(), move(str1));
   cout << "After the emplace insertion, hs3 contains "
      << *hs3.begin() << "." << endl;
}
```

```Output
After the emplace insertion, hs3 contains a.
```

## <a name="empty"></a>hash_set:: Empty

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Bir hash_set boş ise sınar.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

hash_set boşsa **doğru** ; hash_set boş değilse **false** .

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_set_empty.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1, hs2;
   hs1.insert ( 1 );

   if ( hs1.empty( ) )
      cout << "The hash_set hs1 is empty." << endl;
   else
      cout << "The hash_set hs1 is not empty." << endl;

   if ( hs2.empty( ) )
      cout << "The hash_set hs2 is empty." << endl;
   else
      cout << "The hash_set hs2 is not empty." << endl;
}
```

```Output
The hash_set hs1 is not empty.
The hash_set hs2 is empty.
```

## <a name="end"></a>hash_set:: End

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Bir hash_set içindeki son öğeden sonraki konumu ele alan bir yineleyici döndürür.

```cpp
const_iterator end() const;

iterator end();
```

### <a name="return-value"></a>Dönüş Değeri

Bir hash_set içindeki son öğeden sonraki konumu ele alan çift yönlü bir yineleyici. Hash_set boşsa, hash_set:: End = = hash_set:: BEGIN.

### <a name="remarks"></a>Açıklamalar

`end`, bir yineleyicinin hash_set sonuna ulaşıp ulaşılmadığını test etmek için kullanılır. @No__t_0 tarafından döndürülen değer başvurulmamalıdır.

### <a name="example"></a>Örnek

```cpp
// hash_set_end.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;
   hash_set <int> :: iterator hs1_Iter;
   hash_set <int> :: const_iterator hs1_cIter;

   hs1.insert( 1 );
   hs1.insert( 2 );
   hs1.insert( 3 );

   hs1_Iter = hs1.end( );
   hs1_Iter--;
   cout << "The last element of hs1 is " << *hs1_Iter << endl;

   hs1.erase( hs1_Iter );

   // The following 3 lines would err because the iterator is const:
   // hs1_cIter = hs1.end( );
   // hs1_cIter--;
   // hs1.erase( hs1_cIter );

   hs1_cIter = hs1.end( );
   hs1_cIter--;
   cout << "The last element of hs1 is now " << *hs1_cIter << endl;
}
```

```Output
The last element of hs1 is 3
The last element of hs1 is now 2
```

## <a name="equal_range"></a>hash_set::equal_range

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Belirtilen bir anahtara ve anahtardan daha büyük bir anahtarla karma kümesindeki ilk öğeye eşit olan bir anahtarla bir karma kümesindeki ilk öğeye sırasıyla yineleyiciler çiftini döndürür.

```cpp
pair <const_iterator, const_iterator> equal_range (const Key& key) const;

pair <iterator, iterator> equal_range (const Key& key);
```

### <a name="parameters"></a>Parametreler

*anahtar* \
Aranan hash_set öğesinden bir öğenin sıralama anahtarıyla Karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Birincisi, anahtarın [lower_bound](../standard-library/set-class.md#lower_bound) , ikincisi ise anahtarın [upper_bound](../standard-library/set-class.md#upper_bound) olduğu yineleyicilerin bir çiftinden biridir.

Üye işlevi tarafından döndürülen bir çiftin PR 'nin ilk Yineleyici öğesine erişmek için `pr` kullanın. **ilk**olarak, alt sınır yineleyicisini başvuru için \* (`pr` kullanın. **ilk**). Üye işlevi tarafından döndürülen bir çiftin ikinci Yineleyici `pr` erişmek için `pr` kullanın. **ikinci**olarak, üst sınır yineleyicisinin başvurusu için \* (`pr` kullanın. **ikinci**).

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_set_equal_range.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   typedef hash_set<int> IntHSet;
   IntHSet hs1;
   hash_set <int> :: const_iterator hs1_RcIter;

   hs1.insert( 10 );
   hs1.insert( 20 );
   hs1.insert( 30 );

   pair <IntHSet::const_iterator, IntHSet::const_iterator> p1, p2;
   p1 = hs1.equal_range( 20 );

   cout << "The upper bound of the element with "
        << "a key of 20 in the hash_set hs1 is: "
        << *(p1.second) << "." << endl;

   cout << "The lower bound of the element with "
        << "a key of 20 in the hash_set hs1 is: "
        << *(p1.first) << "." << endl;

   // Compare the upper_bound called directly
   hs1_RcIter = hs1.upper_bound( 20 );
   cout << "A direct call of upper_bound( 20 ) gives "
        << *hs1_RcIter << "," << endl
        << "matching the 2nd element of the pair"
        << " returned by equal_range( 20 )." << endl;

   p2 = hs1.equal_range( 40 );

   // If no match is found for the key,
   // both elements of the pair return end( )
   if ( ( p2.first == hs1.end( ) ) && ( p2.second == hs1.end( ) ) )
      cout << "The hash_set hs1 doesn't have an element "
           << "with a key greater than or equal to 40." << endl;
   else
      cout << "The element of hash_set hs1 with a key >= 40 is: "
           << *(p1.first) << "." << endl;
}
```

```Output
The upper bound of the element with a key of 20 in the hash_set hs1 is: 30.
The lower bound of the element with a key of 20 in the hash_set hs1 is: 20.
A direct call of upper_bound( 20 ) gives 30,
matching the 2nd element of the pair returned by equal_range( 20 ).
The hash_set hs1 doesn't have an element with a key greater than or equal to 40.
```

## <a name="erase"></a>hash_set:: Erase

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Belirtilen konumlardan bir hash_set içindeki öğe veya öğe aralığını kaldırır veya belirtilen bir anahtarla eşleşen öğeleri kaldırır.

```cpp
iterator erase(iterator _Where);

iterator erase(iterator first, iterator last);

size_type erase(const key_type& key);
```

### <a name="parameters"></a>Parametreler

*_@No__t_1*
Hash_set kaldırılacak öğenin konumu.

*ilk* \
Hash_set öğesinden kaldırılan ilk öğenin konumu.

*son* \
Hash_set öğesinden kaldırılan son öğenin hemen ötesinde konumlandır.

*anahtar* \
Hash_set kaldırılacak öğelerin anahtarı.

### <a name="return-value"></a>Dönüş Değeri

İlk iki üye işlevi için, kaldırılan öğelerin dışında kalan ilk öğeyi belirten çift yönlü bir yineleyici veya böyle bir öğe yoksa hash_set sonuna bir işaretçi. Üçüncü üye işlevi için, hash_set kaldırılmış olan öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Üye işlevleri hiçbir şekilde özel durum oluşturmaz.

### <a name="example"></a>Örnek

Aşağıdaki örnek, hash_set:: Erase üye işlevinin kullanımını gösterir.

```cpp
// hash_set_erase.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main()
{
    using namespace std;
    using namespace stdext;
    hash_set<int> hs1, hs2, hs3;
    hash_set<int>::iterator pIter, Iter1, Iter2;
    int i;
    hash_set<int>::size_type n;

    for (i = 1; i < 5; i++)
    {
        hs1.insert (i);
        hs2.insert (i * i);
        hs3.insert (i - 1);
    }

    // The 1st member function removes an element at a given position
    Iter1 = ++hs1.begin();
    hs1.erase(Iter1);

    cout << "After the 2nd element is deleted, the hash_set hs1 is:";
    for (pIter = hs1.begin(); pIter != hs1.end(); pIter++)
        cout << " " << *pIter;
    cout << "." << endl;

    // The 2nd member function removes elements
    // in the range [ first,  last)
    Iter1 = ++hs2.begin();
    Iter2 = --hs2.end();
    hs2.erase(Iter1, Iter2);

    cout << "After the middle two elements are deleted, "
         << "the hash_set hs2 is:";
    for (pIter = hs2.begin(); pIter != hs2.end(); pIter++)
        cout << " " << *pIter;
    cout << "." << endl;

    // The 3rd member function removes elements with a given  key
    n = hs3.erase(2);

    cout << "After the element with a key of 2 is deleted, "
         << "the hash_set hs3 is:";
    for (pIter = hs3.begin(); pIter != hs3.end(); pIter++)
        cout << " " << *pIter;
    cout << "." << endl;

    // The 3rd member function returns the number of elements removed
    cout << "The number of elements removed from hs3 is: "
         << n << "." << endl;

    // The dereferenced iterator can also be used to specify a key
    Iter1 = ++hs3.begin();
    hs3.erase(Iter1);

    cout << "After another element (unique for hash_set) with a key "
         << endl;
    cout  << "equal to that of the 2nd element is deleted, "
          << "the hash_set hs3 is:";
    for (pIter = hs3.begin(); pIter != hs3.end(); pIter++)
        cout << " " << *pIter;
    cout << "." << endl;
}
```

```Output
After the 2nd element is deleted, the hash_set hs1 is: 1 3 4.
After the middle two elements are deleted, the hash_set hs2 is: 16 4.
After the element with a key of 2 is deleted, the hash_set hs3 is: 0 1 3.
The number of elements removed from hs3 is: 1.
After another element (unique for hash_set) with a key
equal to that of the 2nd element is deleted, the hash_set hs3 is: 0 3.
```

## <a name="find"></a>hash_set:: Find

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Belirtilen anahtara denk bir anahtara sahip bir hash_set içindeki bir öğenin konumunu ele alan bir yineleyici döndürür.

```cpp
iterator find(const Key& key);

const_iterator find(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*anahtar* \
Aranan hash_set öğesinden bir öğenin sıralama anahtarıyla eşleştirilecek bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Anahtar için herhangi bir eşleşme bulunmazsa, belirtilen anahtara denk bir öğenin konumunu adresleyen veya hash_set içindeki son öğeden sonra gelen konumu ele alan bir `iterator` veya `const_iterator`.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, hash_set içindeki bir öğeyi adresleyen bir yineleyici döndürür. Bu sıralama anahtarı, daha az karşılaştırıtan bir ilişkiye göre bir sıralamayı karşılayan bir ikili koşuldaki bağımsız değişken anahtarına `equivalent`.

@No__t_0 dönüş değeri bir `const_iterator` atanırsa, hash_set nesnesi değiştirilemez. @No__t_0 dönüş değeri bir `iterator` atanırsa, hash_set nesnesi değiştirilebilir.

### <a name="example"></a>Örnek

```cpp
// hash_set_find.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;
   hash_set <int> :: const_iterator hs1_AcIter, hs1_RcIter;

   hs1.insert( 10 );
   hs1.insert( 20 );
   hs1.insert( 30 );

   hs1_RcIter = hs1.find( 20 );
   cout << "The element of hash_set hs1 with a key of 20 is: "
        << *hs1_RcIter << "." << endl;

   hs1_RcIter = hs1.find( 40 );

   // If no match is found for the key, end( ) is returned
   if ( hs1_RcIter == hs1.end( ) )
      cout << "The hash_set hs1 doesn't have an element "
           << "with a key of 40." << endl;
   else
      cout << "The element of hash_set hs1 with a key of 40 is: "
           << *hs1_RcIter << "." << endl;

   // The element at a specific location in the hash_set can be found
   // by using a dereferenced iterator addressing the location
   hs1_AcIter = hs1.end( );
   hs1_AcIter--;
   hs1_RcIter = hs1.find( *hs1_AcIter );
   cout << "The element of hs1 with a key matching "
        << "that of the last element is: "
        << *hs1_RcIter << "." << endl;
}
```

```Output
The element of hash_set hs1 with a key of 20 is: 20.
The hash_set hs1 doesn't have an element with a key of 40.
The element of hs1 with a key matching that of the last element is: 30.
```

## <a name="get_allocator"></a>hash_set::get_allocator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Hash_set oluşturmak için kullanılan ayırıcı nesnesinin bir kopyasını döndürür.

```cpp
Allocator get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şablon parametre *ayırıcısı*olan belleği yönetmek için hash_set tarafından kullanılan ayırıcı.

*Ayırıcı*hakkında daha fazla bilgi Için [hash_set Class](../standard-library/hash-set-class.md) konusunun açıklamalar bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

Hash_set Sınıfı için ayrıcılar, sınıfın depolamayı nasıl yönettiğini belirtir. C++ Standart kitaplık kapsayıcı sınıflarıyla sağlanan varsayılan ayrıcılar çoğu programlama ihtiyacı için yeterlidir. Kendi ayırıcı sınıfınızı yazmak ve kullanmak Gelişmiş C++ bir konudur.

### <a name="example"></a>Örnek

```cpp
// hash_set_get_allocator.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;

   // The following lines declare objects
   // that use the default allocator.
   hash_set <int, hash_compare <int, less<int> > > hs1;
   hash_set <int,  hash_compare <int, greater<int> > > hs2;
   hash_set <double, hash_compare <double,
      less<double> >, allocator<double> > hs3;

   hash_set <int, hash_compare <int,
      greater<int> > >::allocator_type hs2_Alloc;
   hash_set <double>::allocator_type hs3_Alloc;
   hs2_Alloc = hs2.get_allocator( );

   cout << "The number of integers that can be allocated"
        << endl << "before free memory is exhausted: "
        << hs1.max_size( ) << "." << endl;

   cout << "The number of doubles that can be allocated"
        << endl << "before free memory is exhausted: "
        << hs3.max_size( ) <<  "." << endl;

   // The following lines create a hash_set hs4
   // with the allocator of hash_set hs1.
   hash_set <int>::allocator_type hs4_Alloc;
   hash_set <int> hs4;
   hs4_Alloc = hs2.get_allocator( );

   // Two allocators are interchangeable if
   // storage allocated from each can be
   // deallocated by the other
   if( hs2_Alloc == hs4_Alloc )
   {
      cout << "The allocators are interchangeable."
           << endl;
   }
   else
   {
      cout << "The allocators are not interchangeable."
           << endl;
   }
}
```

## <a name="hash_set"></a>hash_set::hash_set

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Boş olan veya diğer bir `hash_set` tümünün veya bir kısmının kopyası olan bir `hash_set` oluşturur.

```cpp
hash_set();

explicit hash_set(
    const Traits& Comp);

hash_set(
    const Traits& Comp,
    const Allocator& Al);

hash_set(
    const hash_set<Key, Traits, Allocator>& Right);

hash_set(
    hash_set&& Right);

hash_set(
    initializer_list<Type> IList);

hash_set(
    initializer_list<Type> IList,
    const Compare& Comp);

hash_set(
    initializer_list<value_type> IList,
    const Compare& Comp,
    const Allocator& Al);

template <class InputIterator>
hash_set(
    InputIterator First,
    InputIterator Last);

template <class InputIterator>
hash_set(
    InputIterator First,
    InputIterator Last,
    const Traits& Comp);

template <class InputIterator>
hash_set(
    InputIterator First,
    InputIterator Last,
    const Traits& Comp,
    const Allocator& Al);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Eşkenar*|@No__t_1 varsayılan olarak bu `hash_set` nesnesi için kullanılacak depolama ayırıcı sınıfı.|
|*İnin*|@No__t_1 öğeleri sıralamak için kullanılan `const Traits` türü karşılaştırma işlevi, varsayılan olarak `hash_compare`.|
|*Right*|Oluşturulan `hash_set` bir kopya olduğu `hash_set`.|
|*Adı*|Kopyalanacak öğe aralığındaki ilk öğenin konumu.|
|*Soyadına*|Kopyalanacak öğe aralığının ötesinde ilk öğenin konumu.|

### <a name="remarks"></a>Açıklamalar

Tüm oluşturucular, `hash_set` bellek depolamayı yöneten ve daha sonra [hash_set:: get_allocator](#get_allocator)çağırarak döndürülebilecek bir tür ayırıcı nesnesi depolar. Ayırıcı parametresi, genellikle sınıf bildirimlerinde atlanır ve alternatif ayırıcıları değiştirmek için kullanılan ön işleme makrolarıyla sonuçlanır.

Tüm oluşturucular hash_sets başlatır.

Tüm oluşturucular, `hash_set` anahtarları arasında bir sıra oluşturmak için kullanılan ve daha sonra [hash_set:: key_comp](#key_comp)çağırarak döndürülebilecek `Traits` türünde bir işlev nesnesi depolar. @No__t_0 hakkında daha fazla bilgi için [hash_set Class](../standard-library/hash-set-class.md) konusuna bakın.

İlk Oluşturucu boş bir ilk `hash_set` oluşturur ve ikinci olarak, öğelerin sırasını oluşturmak için kullanılacak karşılaştırma işlevinin türünü (`Comp`) belirtir ve üçüncüsü açıkça kullanılacak ayırıcı türünü (`Al`) belirtir. @No__t_0 anahtar sözcük, bazı otomatik tür dönüştürme türlerini bastırır.

Dördüncü ve beşinci oluşturucular `hash_set` `Right` bir kopyasını belirtir.

Son altıncı, yedinci ve sekizinci oluşturucular öğeler için bir initializer_list kullanır.

Son oluşturucular, sınıf nitelikleri ve ayırıcısı 'nın karşılaştırma işlevinin türünü belirtirken, bir `hash_set` [`First`, `Last`) aralığını açıkça artırır.

Sekizinci Oluşturucu `hash_set` `Right` taşımaktır.

@No__t_0 kapsayıcısındaki öğelerin gerçek sıralaması, karma işleve, sıralama işlevine ve karma tablonun geçerli boyutuna bağlıdır ve genellikle sıralama işlevi tarafından belirlendiği şekilde, ayarlanan kapsayıcıda tahmin edilebilir. .

## <a name="insert"></a>hash_set:: insert

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Bir `hash_set` öğe veya öğe aralığı ekler.

```cpp
pair<iterator, bool> insert(
    const value_type& Val);

iterator insert(
    iterator Where,
    const value_type& Val);

void insert(
    initializer_list<value_type> IList)
template <class InputIterator>
void insert(
    InputIterator First,
    InputIterator Last);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Acil*|@No__t_1 zaten bu öğeyi veya daha genel bir öğeyi içermiyorsa, bu öğe `hash_set` eklenecek öğenin değeri.|
|*Olmadığı*|Doğru ekleme noktasını aramaya başlamak için yer. (Ekleme noktası `_Where` hemen sonrasında, ekleme, logaritmik bir süre yerine, sabit zamanlı olarak ortaya çıkabilir.)|
|*Adı*|@No__t_0 kopyalanacak ilk öğenin konumu.|
|*Soyadına*|@No__t_0 kopyalanacak son öğenin hemen ötesinde konum.|
|*IList*|Öğelerin kopyalanacağı initializer_list.|

### <a name="return-value"></a>Dönüş Değeri

İlk `insert` member işlevi, bir ekleme işlemi olursa **bool** bileşeni **true** döndüren bir çift döndürür ve `hash_set` zaten anahtarı sıralamada denk bir değere sahip olan bir **öğe içeriyorsa ve** Yineleyici Bileşen, yeni bir öğenin eklendiği veya öğenin zaten bulunduğu yerdeki adresi döndürür.

Bu üye işlevi tarafından döndürülen bir çift `pr` Yineleyici bileşenine erişmek için `pr.first` kullanın ve `*(pr.first)` kullanın. Bu üye işlevi tarafından döndürülen bir çift `pr` **bool** bileşenine erişmek için, `pr.second` kullanın ve başvuru yapmak için `*(pr.second)` kullanın.

İkinci `insert` member işlevi, yeni öğenin `hash_set` eklendiği konuma işaret eden bir yineleyici döndürür.

### <a name="remarks"></a>Açıklamalar

Üçüncü üye işlevi, öğeleri bir initializer_list içine ekler.

Üçüncü üye işlevi, belirtilen `hash_set` [`First`, `Last`) aralığında bir yineleyici tarafından bahsedilen her öğeye karşılık gelen bir `hash_set` öğe değerleri dizisini ekler.

## <a name="iterator"></a>hash_set:: Yineleyici

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Bir hash_set içinde herhangi bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleyici sağlayan bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::iterator iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `iterator`, bir öğenin değerini değiştirmek için kullanılabilir.

### <a name="example"></a>Örnek

@No__t_1 bildirme ve kullanma hakkında bir [örnek için bkz](#begin) . örnek.

## <a name="key_comp"></a>hash_set::key_comp

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Bir hash_set içindeki öğe anahtar değerlerini karma ve sıralama için kullanılan karma nitelikleri nesnesinin bir kopyasını alır.

```cpp
key_compare key_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir hash_set öğesinin, şablon parametresi *nitelikleri*olan öğelerini sıralamak için kullandığı işlev nesnesini döndürür.

*Nitelikler* hakkında daha fazla bilgi Için [hash_set Sınıfı](../standard-library/hash-set-class.md) konusuna bakın.

### <a name="remarks"></a>Açıklamalar

Saklı nesne, üye işlevini tanımlar:

`bool operator( const Key& _xVal, const Key& _yVal );`

`_xVal` önce varsa **true** , sıralama düzeninde `_yVal` eşit değildir.

Hem [key_compare](#key_compare) hem de [value_compare](#value_compare) şablon parametresi *nitelikleri*için eş anlamlı olduğunu unutmayın. Her iki tür de hash_set ve hash_multiset sınıfları için sağlanır ve bunlar birbirinden farklı oldukları hash_map ve hash_multimap sınıflarıyla uyumluluk içindir.

### <a name="example"></a>Örnek

```cpp
// hash_set_key_comp.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;

   hash_set <int, hash_compare < int, less<int> > >hs1;
   hash_set<int, hash_compare < int, less<int> > >::key_compare kc1
          = hs1.key_comp( ) ;
   bool result1 = kc1( 2, 3 ) ;
   if( result1 == true )
   {
      cout << "kc1( 2,3 ) returns value of true, "
           << "where kc1 is the function object of hs1."
           << endl;
   }
   else
   {
      cout << "kc1( 2,3 ) returns value of false "
           << "where kc1 is the function object of hs1."
        << endl;
   }

   hash_set <int, hash_compare < int, greater<int> > > hs2;
   hash_set<int, hash_compare < int, greater<int> > >::key_compare
         kc2 = hs2.key_comp( ) ;
   bool result2 = kc2( 2, 3 ) ;
   if(result2 == true)
   {
      cout << "kc2( 2,3 ) returns value of true, "
           << "where kc2 is the function object of hs2."
           << endl;
   }
   else
   {
      cout << "kc2( 2,3 ) returns value of false, "
           << "where kc2 is the function object of hs2."
           << endl;
   }
}
```

## <a name="key_compare"></a>hash_set::key_compare

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Hash_set içindeki iki öğenin göreli sırasını belirleyebilmek için iki sıralama anahtarını karşılaştırabilen bir işlev nesnesi sağlayan bir tür.

```cpp
typedef Traits key_compare;
```

### <a name="remarks"></a>Açıklamalar

`key_compare` şablon parametresi *nitelikleri*için bir eş anlamlı.

*Nitelikler* hakkında daha fazla bilgi Için [hash_set Sınıfı](../standard-library/hash-set-class.md) konusuna bakın.

Hem `key_compare` hem de [value_compare](#value_compare) şablon parametresi *nitelikleri*için eş anlamlı olduğunu unutmayın. Her iki tür de, farklı oldukları, eşleme ve multimap sınıfları ile uyumluluk için, aynı oldukları küme ve çoklu küme sınıfları için sağlanır.

### <a name="example"></a>Örnek

@No__t_1 bildirme ve kullanma hakkında bir örnek için bkz. [key_comp](#key_comp) .

## <a name="key_type"></a>hash_set::key_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Hash_set öğesi olarak depolanan bir nesneyi sıralama anahtarı olarak kapasitesinde tanımlayan bir tür.

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Açıklamalar

`key_type`, şablon parametre *anahtarı*için bir eş anlamlı.

*Anahtar*hakkında daha fazla bilgi Için [hash_set Class](../standard-library/hash-set-class.md) konusunun açıklamalar bölümüne bakın.

Hem `key_type` hem de [value_type](#value_type) şablon parametre *anahtarı*için eş anlamlı olduğunu unutmayın. Her iki tür de hash_set ve hash_multiset sınıfları için sağlanır ve bunlar birbirinden farklı oldukları hash_map ve hash_multimap sınıflarıyla uyumluluk içindir.

### <a name="example"></a>Örnek

@No__t_1 bildirme ve kullanma hakkında bir örnek için bkz. [value_type](#value_type) .

## <a name="lower_bound"></a>hash_set::lower_bound

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Bir yineleyiciyi belirtilen anahtardan daha büyük veya ona eşit bir anahtarla bir hash_set içindeki ilk öğeye döndürür.

```cpp
const_iterator lower_bound(const Key& key) const;

iterator lower_bound(const Key& key);
```

### <a name="parameters"></a>Parametreler

*anahtar* \
Aranan hash_set öğesinden bir öğenin sıralama anahtarıyla Karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişken anahtarına eşit veya ondan büyük olan veya anahtar için eşleşme bulunmazsa hash_set içindeki son öğeden sonraki konumu ele alan bir hash_set içindeki bir öğenin konumunu ele alan bir `iterator` veya `const_iterator`.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_set_lower_bound.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;
   hash_set <int> :: const_iterator hs1_AcIter, hs1_RcIter;

   hs1.insert( 10 );
   hs1.insert( 20 );
   hs1.insert( 30 );

   hs1_RcIter = hs1.lower_bound( 20 );
   cout << "The element of hash_set hs1 with a key of 20 is: "
        << *hs1_RcIter << "." << endl;

   hs1_RcIter = hs1.lower_bound( 40 );

   // If no match is found for the key, end( ) is returned
   if ( hs1_RcIter == hs1.end( ) )
      cout << "The hash_set hs1 doesn't have an element "
           << "with a key of 40." << endl;
   else
      cout << "The element of hash_set hs1 with a key of 40 is: "
           << *hs1_RcIter << "." << endl;

   // An element at a specific location in the hash_set can be found
   // by using a dereferenced iterator that addresses the location
   hs1_AcIter = hs1.end( );
   hs1_AcIter--;
   hs1_RcIter = hs1.lower_bound( *hs1_AcIter );
   cout << "The element of hs1 with a key matching "
        << "that of the last element is: "
        << *hs1_RcIter << "." << endl;
}
```

```Output
The element of hash_set hs1 with a key of 20 is: 20.
The hash_set hs1 doesn't have an element with a key of 40.
The element of hs1 with a key matching that of the last element is: 30.
```

## <a name="max_size"></a>hash_set::max_size

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Hash_set maksimum uzunluğunu döndürür.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Hash_set maksimum olası uzunluğu.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_set_max_size.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;
   hash_set <int>::size_type i;

   i = hs1.max_size( );
   cout << "The maximum possible length "
        << "of the hash_set is " << i << "." << endl;
}
```

## <a name="op_eq"></a>hash_set:: operator =

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Hash_set öğelerini başka bir hash_set kopyası ile değiştirir.

```cpp
hash_set& operator=(const hash_set& right);

hash_set& operator=(hash_set&& right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Right*|@No__t_1 Kopyalanmakta olan [hash_set](../standard-library/hash-set-class.md) .|

### <a name="remarks"></a>Açıklamalar

Bir `hash_set` var olan öğeleri sildikten sonra, `operator=` içeriğini kopyalar veya `hash_set` içine *taşısa* .

### <a name="example"></a>Örnek

```cpp
// hash_set_operator_as.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set<int> v1, v2, v3;
   hash_set<int>::iterator iter;

   v1.insert(10);

   cout << "v1 = " ;
   for (iter = v1.begin(); iter != v1.end(); iter++)
      cout << iter << " ";
   cout << endl;

   v2 = v1;
   cout << "v2 = ";
   for (iter = v2.begin(); iter != v2.end(); iter++)
      cout << iter << " ";
   cout << endl;

// move v1 into v2
   v2.clear();
   v2 = move(v1);
   cout << "v2 = ";
   for (iter = v2.begin(); iter != v2.end(); iter++)
      cout << iter << " ";
   cout << endl;
}
```

## <a name="pointer"></a>hash_set::p oınter

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Bir hash_set içinde bir öğe işaretçisi sağlayan bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `pointer`, bir öğenin değerini değiştirmek için kullanılabilir.

Çoğu durumda, bir [Yineleyici](#iterator) bir hash_set nesnesindeki öğelere erişmek için kullanılmalıdır.

## <a name="rbegin"></a>hash_set:: rbegin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Ters çevrilen bir hash_set ilk öğeyi adresleyen bir yineleyici döndürür.

```cpp
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir hash_set içindeki ilk öğeyi ele almak veya geri çevrilme hash_set son öğesinin ne olduğunu ele almak için ters yönlü bir yineleyici.

### <a name="remarks"></a>Açıklamalar

`rbegin`, [Başlangıç](#begin) olarak bir hash_set ile kullanıldığı için ters çevrilmiş bir hash_set ile kullanılır.

@No__t_0 dönüş değeri bir `const_reverse_iterator` atanırsa, hash_set nesnesi değiştirilemez. @No__t_0 dönüş değeri bir `reverse_iterator` atanırsa, hash_set nesnesi değiştirilebilir.

`rbegin`, bir hash_set geriye doğru yinelemek için kullanılabilir.

### <a name="example"></a>Örnek

```cpp
// hash_set_rbegin.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;
   hash_set <int>::iterator hs1_Iter;
   hash_set <int>::reverse_iterator hs1_rIter;

   hs1.insert( 10 );
   hs1.insert( 20 );
   hs1.insert( 30 );

   hs1_rIter = hs1.rbegin( );
   cout << "The first element in the reversed hash_set is "
        << *hs1_rIter << "." << endl;

   // begin can be used to start an iteration
   // through a hash_set in a forward order
   cout << "The hash_set is: ";
   for ( hs1_Iter = hs1.begin( ) ; hs1_Iter != hs1.end( );
         hs1_Iter++ )
      cout << *hs1_Iter << " ";
   cout << endl;

   // rbegin can be used to start an iteration
   // through a hash_set in a reverse order
   cout << "The reversed hash_set is: ";
   for ( hs1_rIter = hs1.rbegin( ) ; hs1_rIter != hs1.rend( );
         hs1_rIter++ )
      cout << *hs1_rIter << " ";
   cout << endl;

   // A hash_set element can be erased by dereferencing to its key
   hs1_rIter = hs1.rbegin( );
   hs1.erase ( *hs1_rIter );

   hs1_rIter = hs1.rbegin( );
   cout << "After the erasure, the first element "
        << "in the reversed hash_set is "<< *hs1_rIter << "."
        << endl;
}
```

```Output
The first element in the reversed hash_set is 30.
The hash_set is: 10 20 30
The reversed hash_set is: 30 20 10
After the erasure, the first element in the reversed hash_set is 20.
```

## <a name="reference"></a>hash_set:: Reference

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Bir hash_set içinde depolanan bir öğeye başvuru sağlayan bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::reference reference;
```

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_set_reference.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;

   hs1.insert( 10 );
   hs1.insert( 20 );

   // Declare and initialize a reference &Ref1 to the 1st element
   int &Ref1 = *hs1.begin( );

   cout << "The first element in the hash_set is "
        << Ref1 << "." << endl;

   // The value of the 1st element of the hash_set can be changed
   // by operating on its (non-const) reference
   Ref1 = Ref1 + 5;

   cout << "The first element in the hash_set is now "
        << *hs1.begin() << "." << endl;
}
```

```Output
The first element in the hash_set is 10.
The first element in the hash_set is now 15.
```

## <a name="rend"></a>hash_set:: rend

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Ters çevrilen bir hash_set son öğeden sonraki konumu ele alan bir yineleyici döndürür.

```cpp
const_reverse_iterator rend() const;

reverse_iterator rend();
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir hash_set içindeki son öğeden sonra gelen konumu ele alan bir ters çift yönlü yineleyici (geri çevrilme hash_set içindeki ilk öğeden önce gelen konum).

### <a name="remarks"></a>Açıklamalar

`rend`, [End](#end) bir hash_set ile kullanıldığı gibi, ters çevrilmiş bir hash_set ile kullanılır.

@No__t_0 dönüş değeri bir `const_reverse_iterator` atanırsa, hash_set nesnesi değiştirilemez. @No__t_0 dönüş değeri bir `reverse_iterator` atanırsa, hash_set nesnesi değiştirilebilir. @No__t_0 tarafından döndürülen değer başvurulmamalıdır.

`rend`, bir ters yineleyicinin hash_set sonuna ulaşıp ulaşılmadığını test etmek için kullanılabilir.

### <a name="example"></a>Örnek

```cpp
// hash_set_rend.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;
   hash_set <int>::iterator hs1_Iter;
   hash_set <int>::reverse_iterator hs1_rIter;
   hash_set <int>::const_reverse_iterator hs1_crIter;

   hs1.insert( 10 );
   hs1.insert( 20 );
   hs1.insert( 30 );

   hs1_rIter = hs1.rend( );
   hs1_rIter--;
   cout << "The last element in the reversed hash_set is "
        << *hs1_rIter << "." << endl;

   // end can be used to terminate an iteration
   // through a hash_set in a forward order
   cout << "The hash_set is: ";
   for ( hs1_Iter = hs1.begin( ) ; hs1_Iter != hs1.end( );
         hs1_Iter++ )
      cout << *hs1_Iter << " ";
   cout << "." << endl;

   // rend can be used to terminate an iteration
   // through a hash_set in a reverse order
   cout << "The reversed hash_set is: ";
   for ( hs1_rIter = hs1.rbegin( ) ; hs1_rIter != hs1.rend( );
         hs1_rIter++ )
      cout << *hs1_rIter << " ";
   cout << "." << endl;

   hs1_rIter = hs1.rend( );
   hs1_rIter--;
   hs1.erase ( *hs1_rIter );

   hs1_rIter = hs1.rend( );
   hs1_rIter--;
   cout << "After the erasure, the last element in the "
        << "reversed hash_set is " << *hs1_rIter << "."
        << endl;
}
```

```Output
The last element in the reversed hash_set is 10.
The hash_set is: 10 20 30 .
The reversed hash_set is: 30 20 10 .
After the erasure, the last element in the reversed hash_set is 20.
```

## <a name="reverse_iterator"></a>hash_set::reverse_iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Ters çevrilen bir hash_set bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleyici sağlayan bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::reverse_iterator reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `reverse_iterator`, ters hash_set üzerinden yinelemek için kullanılır.

### <a name="example"></a>Örnek

@No__t_1 bildirme ve kullanma hakkında bir örnek için bkz. [rbegin](#rbegin) örneği.

## <a name="size"></a>hash_set:: size

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Hash_set içindeki öğelerin sayısını döndürür.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Hash_set geçerli uzunluğu.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_set_size.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;
   hash_set <int> :: size_type i;

   hs1.insert( 1 );
   i = hs1.size( );
   cout << "The hash_set length is " << i << "." << endl;

   hs1.insert( 2 );
   i = hs1.size( );
   cout << "The hash_set length is now " << i << "." << endl;
}
```

```Output
The hash_set length is 1.
The hash_set length is now 2.
```

## <a name="size_type"></a>hash_set::size_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Bir hash_set içindeki öğe sayısını temsil eden işaretsiz bir tamsayı türü.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::size_type size_type;
```

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

Nasıl bildirilemeyeceğini ve kullanılacağına ilişkin bir örnek için [Boyut](#size) örneğine bakın `size_type`

## <a name="swap"></a>hash_set:: swap

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

İki hash_sets öğelerini değiş tokuş eder.

```cpp
void swap(hash_set& right);
```

### <a name="parameters"></a>Parametreler

*sağ* \
Hash_set bağımsız değişkeni, hedef hash_set ile takas edilecek öğeleri sağlar.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, öğeleri takas edilmekte olan iki hash_sets öğeleri belirten hiçbir başvuru, işaretçi veya yineleyiciyi geçersiz kılar.

### <a name="example"></a>Örnek

```cpp
// hash_set_swap.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1, hs2, hs3;
   hash_set <int>::iterator hs1_Iter;

   hs1.insert( 10 );
   hs1.insert( 20 );
   hs1.insert( 30 );
   hs2.insert( 100 );
   hs2.insert( 200 );
   hs3.insert( 300 );

   cout << "The original hash_set hs1 is:";
   for ( hs1_Iter = hs1.begin( ); hs1_Iter != hs1.end( );
         hs1_Iter++ )
         cout << " " << *hs1_Iter;
   cout   << "." << endl;

   // This is the member function version of swap
   hs1.swap( hs2 );

   cout << "After swapping with hs2, list hs1 is:";
   for ( hs1_Iter = hs1.begin( ); hs1_Iter != hs1.end( );
         hs1_Iter++ )
         cout << " " << *hs1_Iter;
   cout  << "." << endl;

   // This is the specialized template version of swap
   swap( hs1, hs3 );

   cout << "After swapping with hs3, list hs1 is:";
   for ( hs1_Iter = hs1.begin( ); hs1_Iter != hs1.end( );
         hs1_Iter++ )
         cout << " " << *hs1_Iter;
   cout   << "." << endl;
}
```

```Output
The original hash_set hs1 is: 10 20 30.
After swapping with hs2, list hs1 is: 200 100.
After swapping with hs3, list hs1 is: 300.
```

## <a name="upper_bound"></a>hash_set::upper_bound

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Bir yineleyiciyi belirtilen anahtardan daha büyük bir anahtarla bir hash_set içindeki ilk öğeye döndürür.

```cpp
const_iterator upper_bound(const Key& key) const;

iterator upper_bound(const Key& key);
```

### <a name="parameters"></a>Parametreler

*anahtar* \
Aranan hash_set öğesinden bir öğenin sıralama anahtarıyla Karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişken anahtarına eşit veya daha büyük bir anahtarla bir hash_set içindeki bir öğenin konumunu adresleyen veya anahtar için eşleşme bulunmazsa hash_set içindeki son öğeden sonra gelen konumu ele alan bir `iterator` veya `const_iterator`.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_set_upper_bound.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;
   hash_set <int> :: const_iterator hs1_AcIter, hs1_RcIter;

   hs1.insert( 10 );
   hs1.insert( 20 );
   hs1.insert( 30 );

   hs1_RcIter = hs1.upper_bound( 20 );
   cout << "The first element of hash_set hs1 with a key greater "
        << "than 20 is: " << *hs1_RcIter << "." << endl;

   hs1_RcIter = hs1.upper_bound( 30 );

   // If no match is found for the key, end( ) is returned
   if ( hs1_RcIter == hs1.end( ) )
      cout << "The hash_set hs1 doesn't have an element "
           << "with a key greater than 30." << endl;
   else
      cout << "The element of hash_set hs1 with a key > 40 is: "
           << *hs1_RcIter << "." << endl;

   // An element at a specific location in the hash_set can be found
   // by using a dereferenced iterator addressing the location
   hs1_AcIter = hs1.begin( );
   hs1_RcIter = hs1.upper_bound( *hs1_AcIter );
   cout << "The first element of hs1 with a key greater than "
        << endl << "that of the initial element of hs1 is: "
        << *hs1_RcIter << "." << endl;
}
```

```Output
The first element of hash_set hs1 with a key greater than 20 is: 30.
The hash_set hs1 doesn't have an element with a key greater than 30.
The first element of hs1 with a key greater than
that of the initial element of hs1 is: 20.
```

## <a name="value_comp"></a>hash_set::value_comp

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Bir hash_set içindeki öğe değerlerini sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır.

```cpp
value_compare value_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Hash_set 'in, şablon parametresi *karşılaştırma*olan öğelerini sıralamak için kullandığı işlev nesnesini döndürür.

*Karşılaştırma*hakkında daha fazla bilgi Için [hash_set Class](../standard-library/hash-set-class.md) konusunun açıklamalar bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

Saklı nesne, üye işlevini tanımlar:

`bool operator( const Key& _xVal, const Key& _yVal );`

`_xVal` önce varsa **true** , sıralama düzeninde `_yVal` eşit değildir.

Hem [value_compare](../standard-library/set-class.md#value_compare) hem de [Key_compare](../standard-library/set-class.md#key_compare) şablon parametre *karşılaştırması*için eş anlamlı olduğunu unutmayın. Her iki tür de hash_set ve hash_multiset sınıfları için sağlanır ve bunlar birbirinden farklı oldukları hash_map ve hash_multimap sınıflarıyla uyumluluk içindir.

### <a name="example"></a>Örnek

```cpp
// hash_set_value_comp.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;

   hash_set <int, hash_compare < int, less<int> > > hs1;
   hash_set <int, hash_compare < int, less<int> >  >::value_compare
      vc1 = hs1.value_comp( );
   bool result1 = vc1( 2, 3 );
   if( result1 == true )
   {
      cout << "vc1( 2,3 ) returns value of true, "
           << "where vc1 is the function object of hs1."
           << endl;
   }
   else
   {
      cout << "vc1( 2,3 ) returns value of false, "
           << "where vc1 is the function object of hs1."
           << endl;
   }

   hash_set <int, hash_compare < int, greater<int> > > hs2;
   hash_set<int, hash_compare < int, greater<int> > >::value_compare
      vc2 = hs2.value_comp( );
   bool result2 = vc2( 2, 3 );
   if( result2 == true )
   {
      cout << "vc2( 2,3 ) returns value of true, "
           << "where vc2 is the function object of hs2."
           << endl;
   }
   else
   {
      cout << "vc2( 2,3 ) returns value of false, "
           << "where vc2 is the function object of hs2."
           << endl;
   }
}
```

## <a name="value_compare"></a>hash_set::value_compare

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

İki işlev nesnesi sağlayan bir tür, bir hash_set öğesinin iki öğe değerini, göreli sıralarını ve öğeleri karmalarını sağlayan birli bir koşulu tespit edebilir.

```cpp
typedef key_compare value_compare;
```

### <a name="remarks"></a>Açıklamalar

`value_compare` şablon parametresi *nitelikleri*için bir eş anlamlı.

*Nitelikler* hakkında daha fazla bilgi Için [hash_set Sınıfı](../standard-library/hash-set-class.md) konusuna bakın.

Hem [key_compare](#key_compare) hem de `value_compare` şablon parametresi *nitelikleri*için eş anlamlı olduğunu unutmayın. Her iki tür de hash_set ve hash_multiset sınıfları için sağlanır ve bunlar birbirinden farklı oldukları hash_map ve hash_multimap sınıflarıyla uyumluluk içindir.

### <a name="example"></a>Örnek

@No__t_1 bildirme ve kullanma hakkında bir örnek için bkz. [value_comp](#value_comp) .

## <a name="value_type"></a>hash_set::value_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Bir hash_set öğesi olarak depolanan bir nesneyi bir değer olarak kapasitesinde tanımlayan bir tür.

```cpp
typedef Key value_type;
```

### <a name="example"></a>Örnek

```cpp
// hash_set_value_type.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;
   hash_set <int>::iterator hs1_Iter;

   hash_set <int> :: value_type hsvt_Int;   // Declare value_type
   hsvt_Int = 10;             // Initialize value_type

   hash_set <int> :: key_type hskt_Int;   // Declare key_type
   hskt_Int = 20;             // Initialize key_type

   hs1.insert( hsvt_Int );         // Insert value into hs1
   hs1.insert( hskt_Int );         // Insert key into hs1

   // A hash_set accepts key_types or value_types as elements
   cout << "The hash_set has elements:";
   for ( hs1_Iter = hs1.begin( ) ; hs1_Iter != hs1.end( ); hs1_Iter++)
      cout << " " << *hs1_Iter;
   cout << "." << endl;
}
```

```Output
The hash_set has elements: 10 20.
```

## <a name="see-also"></a>Ayrıca bkz.

[Standart kitaplıkta Iş parçacığı güvenliği \ C++ ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)
