---
description: 'Hakkında daha fazla bilgi edinin: hash_set Sınıfı'
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
ms.openlocfilehash: 36bcb0e1f35fd8012ad1398a481bdae17b6d1424
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324102"
---
# <a name="hash_set-class"></a>hash_set Sınıfı

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Kapsayıcı sınıfı hash_set, C++ standart kitaplığının bir uzantısıdır ve içerdiği öğelerin değerlerinin benzersiz olduğu ve anahtar değerler olarak kullanıldığı bir koleksiyondaki verilerin depolanması ve hızlı bir şekilde alınması için kullanılır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Key,
    class Traits=hash_compare<Key, less<Key>>,
    class Allocator=allocator<Key>>
class hash_set
```

### <a name="parameters"></a>Parametreler

*Anahtar*\
Hash_set depolanacak öğe veri türü.

*Lerdir*\
İki işlev nesnesi içeren tür, bir ikili koşul olan sınıf karşılaştırmasına sahip iki öğe değerini, öğelerin birli bir koşul eşleme anahtar değerleri olan bir karma işlevi ve türün işaretsiz tamsayılar olan bir karma işlevini tespit etmek için sıralama anahtarları olarak karşılaştırabilmeyebilir `size_t` . Bu bağımsız değişken isteğe bağlıdır ve `hash_compare<Key, less<Key> >` varsayılan değerdir.

*Öğe*\
Hash_set, bellek ayırma ve ayırmayı kaldırma hakkındaki ayrıntıları kapsülleyen saklı ayırıcı nesnesini temsil eden tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değerdir `allocator<Key>` .

## <a name="remarks"></a>Açıklamalar

Hash_set:

- İlişkili bir anahtar değerine dayalı öğe değerlerinin verimli alınmasını destekleyen bir değişken boyutu kapsayıcı olan ilişkilendirilebilir bir kapsayıcı. Dahası, basit bir ilişkilendirilebilir kapsayıcıdır, çünkü öğelerinin değerleri kendi anahtar değerleridir.

- Çift yönlüdür, çünkü öğelerine erişmek için çift yönlü bir yineleyici sağlar.

- Karma değeri, öğelerinin anahtar değerlerine uygulanan bir karma işlevin değerine bağlı olarak demet halinde gruplandığından karma hale getirilir.

- Benzersizdir, çünkü öğelerinin her birinde benzersiz bir anahtar olması gerekir. Hash_set Ayrıca basit ilişkilendirilebilir bir kapsayıcı olduğundan, öğeleri de benzersizdir.

- Bir sınıf şablonu, sağladığı işlevsellik geneldir ve bu nedenle öğe veya anahtar olarak içerilen belirli veri türünden bağımsızdır. Öğeler ve anahtarlar için kullanılacak veri türleri, karşılaştırma işlevi ve ayırıcı ile birlikte bir sınıf şablonunda parametreler olarak belirtilir.

Sıralama üzerinden karmalamanın başlıca avantajı daha fazla verimlilik; başarılı bir karma değer ekleme, silme işlemleri gerçekleştirir ve sabit ortalama süre içinde, sıralama teknikleri için kapsayıcıdaki öğelerin sayısının logaritmasına kıyasla bir zaman orantılı olarak bulur. Bir kümedeki bir öğenin değeri doğrudan değiştirilemez. Bunun yerine, eski değerleri silmeniz ve yeni değerlere sahip öğeler eklemeniz gerekir.

Kapsayıcı türünün seçimi genelde uygulamanın gerektirdiği arama ve ekleme türüne dayalı olmalıdır. Karma olarak ilişkilendirilebilir kapsayıcılar, arama, ekleme ve kaldırma işlemleri için iyileştirilmiştir. Bu işlemleri açıkça destekleyen üye işlevleri, iyi tasarlanmış bir karma işlevi ile kullanıldığında etkili olur ve bunları ortalama Sabitte olan ve kapsayıcıdaki öğelerin sayısına bağımlı olmayan bir zaman içinde gerçekleştiriyor. İyi tasarlanmış bir karma işlevi, karma değerler için Tekdüzen bir dağıtım üretir ve ayrı anahtar değerleri aynı karma değere eşlendiğinde bir çarpışmanın oluşmasına neden olan çakışmaların sayısını en aza indirir. En kötü durumda, mümkün olan en kötü karma işlevi olan işlem sayısı, dizideki öğelerin sayısıyla orantılıdır (doğrusal saat).

Değerleri, anahtar ile ilişkilendirirken, uygulama tarafından karşılandıkları durumlarda seçeneğin ilişkilendirilebilir kapsayıcısı olmalıdır. hash_set Hash_set öğeleri benzersizdir ve kendi sıralama anahtarları olarak görev yapar. Bu tür bir yapı modeli, sözcüklerin yalnızca bir defa geçebildiği sıralı bir sözcükler listesindedir. Sözcüklerin birden çok örneğine izin veriliyorsa, hash_multiset uygun kapsayıcı yapısı olur. Değerlerin benzersiz anahtar sözcükler listesine eklenmesi gerekiyorsa, bu verileri içeren bir hash_map uygun bir yapı olacaktır. Bunun yerine anahtarlar benzersiz değilse, bir hash_multimap tercih edilen kapsayıcı olur.

Hash_set, value_compare türünde depolanan bir karma nesne çağırarak denetlediği diziyi sıralar `Traits` . [](#value_compare) Bu saklı nesneye [key_comp](#key_comp)üye işlevi çağırarak erişilebilir. Böyle bir işlev nesnesi, *hash_compare<anahtarı, daha az \<Key> >* olan bir nesne ile aynı şekilde davranmalıdır. Özellikle, Key türündeki tüm değerler için `key` , Call nitelik (), `key` size_t türündeki değerlerin bir dağılımını verir.

Genelde, bu sıralamayı oluşturmak için öğelerin yalnızca küçüktür biçiminde karşılaştırılabilir olması gerekir; böylece, herhangi iki öğe belirtildiğinde, eşit oldukları (yani birinin diğerinden daha küçük olmadığı anlamında) veya birinin diğerinden küçük olduğu belirlenebilir. Bu, denk olmayan öğeler arasında bir sıralamaya neden olur. Daha teknik bir not üzerinde, karşılaştırma işlevi standart matematiksel anlamda katı bir zayıf sıralama sevk eden ikili bir koşuldur. Bir ikili koşul *f*( *x*, *y*) iki bağımsız değişken nesnesi olan x ve y ve true ya da false dönüş değerine sahip bir işlev nesnesidir. İkili koşul geri dönüşsüz, antisimetrik ve geçişli ve denklik geçişli ise, hash_set uygulanan bir sıralama katı zayıf bir sıradır, burada iki nesne *x* ve *y* , her ikisi de *f*( *x*, *y*) ve *f*( *y*, *x*) false olduğunda denk olarak tanımlanır. Anahtarlar arasındaki eşitliğinin daha güçlü koşulu bu denkliğin yerini alırsa, sıralama (içindeki tüm öğelerin birbirine göre sıralanması anlamında) toplam haline gelir ve eşleşen anahtarlar birbirinden ayırt edilemez olacaktır.

Denetlenen dizideki öğelerin gerçek sırası, karma işleve, sıralama işlevine ve kapsayıcı nesnesinde depolanan karma tablonun geçerli boyutuna bağlıdır. Karma tablonun geçerli boyutunu belirleyemez, bu nedenle denetimli dizideki öğelerin sırasını genel olarak tahmin edemezsiniz. Öğelerin eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; öğelerin kaldırılması yalnızca özellikle kaldırılan öğeleri gösteren yineleyicileri geçersiz kılar.

Hash_set Sınıfı tarafından verilen yineleyici çift yönlü bir yineleyicidir, ancak [Insert](#insert) ve [hash_set](#hash_set) sınıf üyesi işlevleri, şablon parametresi olarak daha zayıf bir giriş yineleyicisini alan, işlevsellik gereksinimleri çift yönlü yineleyicilerin sınıfına göre garantiden daha düşük olan sürümlere sahiptir. Farklı yineleyici kavramları, işlevselliklerindeki iyileştirmelere göre ilgili bir aile biçimlendirir. Her yineleyici kavramının kendi gereksinimler kümesi vardır ve bunlarla çalışan algoritmaların kendi varsayımlarını yineleyici türü tarafından sağlanan gereksinimlerle sınırlaması gerekir. Bir giriş yineleyicinin bazı nesnelere başvurusunun kaldırılacağı ve dizideki sonraki yineleyiciye artırılabileceği varsayılabilir. Bu en düşük işlevsellik kümesidir, ancak `first` `last` sınıf üye işlevleri bağlamında yineleyicilerin bir aralığı hakkında anlamlı bir şekilde konuşabilmek için yeterlidir.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[hash_set](#hash_set)|`hash_set`Boş olan veya bir kısmının tümünün veya bir kısmının kopyası olan oluşturur `hash_set` .|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[allocator_type](#allocator_type)|Nesnenin sınıfını temsil eden bir tür `allocator` `hash_set` .|
|[const_iterator](#const_iterator)|İçindeki bir öğeyi okuyabilen çift yönlü bir yineleyici sağlayan bir tür **`const`** `hash_set` .|
|[const_pointer](#const_pointer)|İçindeki bir öğeye işaretçi sağlayan bir tür **`const`** `hash_set` .|
|[const_reference](#const_reference)|**`const`** `hash_set` İşlem okumak ve gerçekleştirmek için içinde depolanan bir öğeye başvuru sağlayan bir tür **`const`** .|
|[const_reverse_iterator](#const_reverse_iterator)|İçindeki herhangi bir öğeyi okuyabilen çift yönlü bir yineleyici sağlayan bir tür **`const`** `hash_set` .|
|[difference_type](#difference_type)|Yineleyiciler tarafından gösterilen öğeler arasındaki bir aralıktaki öğelerinin sayısını temsil etmek için kullanılabilen işaretli bir tamsayı türü `hash_set` .|
|[iden](#iterator)|İçindeki herhangi bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleyici sağlayan bir tür `hash_set` .|
|[key_compare](#key_compare)|İçindeki iki öğenin göreli sırasını belirleyebilmek için iki sıralama anahtarını karşılaştırabilen bir işlev nesnesi sağlayan bir tür `hash_set` .|
|[key_type](#key_type)|Bir nesne olarak bir öğesi olarak depolanan bir nesneyi `hash_set` sıralama anahtarı olarak kapasitesinde tanımlayan bir tür.|
|[pointer](#pointer)|İçindeki bir öğeye işaretçi sağlayan bir tür `hash_set` .|
|[başvurunun](#reference)|İçinde depolanan bir öğeye başvuru sağlayan bir tür `hash_set` .|
|[reverse_iterator](#reverse_iterator)|Ters çevrilen bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleyici sağlayan bir tür `hash_set` .|
|[size_type](#size_type)|İçindeki öğe sayısını temsil eden işaretsiz bir tamsayı türü `hash_set` .|
|[value_compare](#value_compare)|İki işlev nesnesi sağlayan bir tür, bir ' ın iki öğe değerini, `hash_set` göreli sırasını ve öğeleri karmalarını sağlayan birli bir koşulu tespit etmek üzere karşılaştırabilen bir sınıf karşılaştırması ikili koşulu.|
|[value_type](#value_type)|Değeri olarak kapasitesinin bir öğesi olarak depolanan bir nesneyi açıklayan tür `hash_set` .|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[başladı](#begin)|İçindeki ilk öğeyi ele alan bir yineleyici döndürür `hash_set` .|
|[cbegin](#cbegin)|İçindeki ilk öğeyi adresleyen bir const yineleyici döndürür `hash_set` .|
|[cend](#cend)|İçindeki son öğeden sonraki konumu ele alan bir const yineleyici döndürür `hash_set` .|
|[lediğiniz](#clear)|Tüm öğelerini siler `hash_set` .|
|[biriktirme](#count)|Bir `hash_set` anahtarı parametre belirtilen anahtarla eşleşen bir öğe sayısını döndürür.|
|[crbegin](#crbegin)|Ters çevrilen ilk öğeyi adresleyen bir const yineleyici döndürür `hash_set` .|
|[crend](#crend)|Ters çevrilen son öğeden sonraki konumu ele alan bir const yineleyici döndürür `hash_set` .|
|[Emplace](#emplace)|İçinde oluşturulan bir öğesi ekler `hash_set` .|
|[emplace_hint](#emplace_hint)|Bir yerleştirme ipucuyla birlikte, içine oluşturulmuş bir öğe ekler `hash_set` .|
|[empty](#empty)|`hash_set`Boşsa, sınar.|
|[erer](#end)|İçindeki son öğeden sonra gelen konumu ele alan bir yineleyici döndürür `hash_set` .|
|[equal_range](#equal_range)|`hash_set`Belirtilen anahtardan daha büyük bir anahtarla ve anahtarından bir anahtarla `hash_set` eşit veya ondan daha büyük olan bir anahtarla ilk öğesine kadar yineleyicilerin bir çiftini döndürür.|
|[silme](#erase)|Belirtilen konumlardan bir öğeyi veya öğe aralığını kaldırır `hash_set` veya belirtilen bir anahtarla eşleşen öğeleri kaldırır.|
|[bilgi](#find)|İçindeki bir öğenin `hash_set` belirtilen anahtara denk eşdeğeri olan konumunu ele alan bir yineleyici döndürür.|
|[get_allocator](#get_allocator)|`allocator`Oluşturmak için kullanılan nesnenin bir kopyasını döndürür `hash_set` .|
|[ekleyin](#insert)|İçine bir öğe veya öğe aralığı ekler `hash_set` .|
|[key_comp](#key_comp)|İçindeki anahtarları sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır `hash_set` .|
|[lower_bound](#lower_bound)|Bir yineleyiciyi, `hash_set` belirtilen anahtardan daha büyük veya ona eşit olan bir anahtarla birlikte içindeki ilk öğeye döndürür.|
|[max_size](#max_size)|Maksimum uzunluğunu döndürür `hash_set` .|
|[rbegin](#rbegin)|Ters çevrilen ilk öğeyi adresleyen bir yineleyici döndürür `hash_set` .|
|[rend](#rend)|Ters çevrilen son öğeden sonraki konumu ele alan bir yineleyici döndürür `hash_set` .|
|[boyutla](#size)|İçindeki öğelerin sayısını döndürür `hash_set` .|
|[Kur](#swap)|İki öğenin öğelerini değiş tokuş eder `hash_set` .|
|[upper_bound](#upper_bound)|Bir yineleyiciyi `hash_set` belirtilen anahtardan daha büyük veya ona eşit olan bir anahtarla ilk öğesine döndürür.|
|[value_comp](#value_comp)|Karma nitelikleri nesnesinin bir kopyasını alır ve içindeki öğe anahtar değerlerini sıralamak için kullanılır `hash_set` .|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[hash_set:: operator =](#op_eq)|Öğesinin öğelerini `hash_set` başka bir kopyasıyla değiştirir `hash_set` .|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<hash_set>

**Ad alanı:** stdext

## <a name="hash_setallocator_type"></a><a name="allocator_type"></a> hash_set:: allocator_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Hash_set nesnesinin ayırıcı sınıfını temsil eden bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::allocator_type allocator_type;
```

### <a name="remarks"></a>Açıklamalar

`allocator_type` , şablon parametre *ayırıcısı* için bir eş anlamlı.

*Ayırıcı* hakkında daha fazla bilgi Için [hash_set Sınıfı](../standard-library/hash-set-class.md) konusunun açıklamalar bölümüne bakın.

### <a name="example"></a>Örnek

Tarafından kullanılan bir örnek için bkz. [get_allocator](#get_allocator) örneği `allocator_type` .

## <a name="hash_setbegin"></a><a name="begin"></a> hash_set:: Begin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Hash_set ilk öğeyi ele alan bir yineleyici döndürür.

```cpp
const_iterator begin() const;

iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

Hash_set ilk öğeyi adresleyen çift yönlü yineleyici veya konum boş bir hash_set başarılı oluyor.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri `begin` öğesine atanırsa `const_iterator` , hash_set nesnesindeki öğeler değiştirilemez. Dönüş değeri `begin` bir öğesine atanırsa `iterator` , hash_set nesnesindeki öğeler değiştirilebilir.

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

## <a name="hash_setcbegin"></a><a name="cbegin"></a> hash_set:: cbegin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Hash_set ilk öğeyi ele alan bir const yineleyici döndürür.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

[Hash_set](../standard-library/hash-set-class.md) ilk öğeyi adresleyen bir const çift yönlü yineleyici veya bir boş olan konum `hash_set` .

### <a name="remarks"></a>Açıklamalar

Dönüş değeri ile `cbegin` `hash_set` nesnedeki öğeler değiştirilemez.

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

## <a name="hash_setcend"></a><a name="cend"></a> hash_set:: cend

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Hash_set son öğeden sonraki konumu ele alan bir const yineleyici döndürür.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir [hash_set](../standard-library/hash-set-class.md)son öğeden sonraki konumu ele alan bir const çift yönlü Yineleyici. `hash_set`Boşsa, `hash_set::cend == hash_set::begin` .

### <a name="remarks"></a>Açıklamalar

`cend` , bir yineleyicinin sonuna kadar ulaşılmadığını test etmek için kullanılır `hash_set` . Tarafından döndürülen değer `cend` başvurulmamalıdır.

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

## <a name="hash_setclear"></a><a name="clear"></a> hash_set:: Clear

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Hash_set tüm öğelerini siler.

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

## <a name="hash_setconst_iterator"></a><a name="const_iterator"></a> hash_set:: const_iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Hash_set bir öğeyi okuyabilen çift yönlü bir yineleyici sağlayan bir tür **`const`** .

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_iterator const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_iterator` , bir öğenin değerini değiştirmek için kullanılamaz.

### <a name="example"></a>Örnek

Tarafından kullanılan bir [örnek için bkz](#begin) `const_iterator` . örnek.

## <a name="hash_setconst_pointer"></a><a name="const_pointer"></a> hash_set:: const_pointer

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Hash_set bir öğeye işaretçi sağlayan bir tür **`const`** .

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_pointer const_pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_pointer` , bir öğenin değerini değiştirmek için kullanılamaz.

Çoğu durumda, bir hash_set nesnesindeki öğelere erişmek için bir [const_iterator](#const_iterator) kullanılmalıdır **`const`** .

## <a name="hash_setconst_reference"></a><a name="const_reference"></a> hash_set:: const_reference

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

**`const`** İşlemleri okumak ve gerçekleştirmek için bir hash_set depolanan öğeye başvuru sağlayan bir tür **`const`** .

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

## <a name="hash_setconst_reverse_iterator"></a><a name="const_reverse_iterator"></a> hash_set:: const_reverse_iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Hash_set herhangi bir öğeyi okuyabilen çift yönlü bir yineleyici sağlayan bir tür **`const`** .

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_reverse_iterator const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür, `const_reverse_iterator` bir öğenin değerini değiştiremez ve hash_set ters bir şekilde yinelemek için kullanılır.

### <a name="example"></a>Örnek

Uygulamasının nasıl bildirilemeyeceğini ve kullanılacağı hakkında bir örnek için bkz. [rend](#rend) örneği `const_reverse_iterator`

## <a name="hash_setcount"></a><a name="count"></a> hash_set:: Count

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Anahtarı parametre tarafından belirtilen anahtarla eşleşen bir hash_set öğe sayısını döndürür.

```cpp
size_type count(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*anahtar*\
Hash_set eşleştirilecek öğelerin anahtarı.

### <a name="return-value"></a>Dönüş Değeri

hash_set sıralama anahtarı parametre anahtarıyla eşleşen bir öğe içeriyorsa 1.

hash_set eşleşen bir anahtara sahip bir öğe içermiyorsa 0.

### <a name="remarks"></a>Açıklamalar

Üye işlevi aşağıdaki aralıktaki öğelerin sayısını döndürür:

\[ lower_bound (*anahtar*), upper_bound (*anahtar*)).

### <a name="example"></a>Örnek

Aşağıdaki örnek hash_set:: Count üye işlevinin kullanımını gösterir.

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

## <a name="hash_setcrbegin"></a><a name="crbegin"></a> hash_set:: crbegin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Ters çevrilen hash_set ilk öğeyi adresleyen bir const yineleyici döndürür.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir [hash_set](../standard-library/hash-set-class.md) ilk öğeyi ele almak veya geri çevrilmede son öğenin ne olduğunu ele almak için bir const ters çift yönlü Yineleyici `hash_set` .

### <a name="remarks"></a>Açıklamalar

`crbegin` ters çevrilmiş bir hash_set ile birlikte kullanılır [hash_set:: Begin](#begin) bir hash_set ile kullanılır.

Dönüş değeri ile `crbegin` `hash_set` nesne değiştirilemez.

`crbegin` , geriye doğru yinelemek için kullanılabilir `hash_set` .

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

## <a name="hash_setcrend"></a><a name="crend"></a> hash_set:: crend

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Ters çevrilen hash_set son öğeden sonraki konumu ele alan bir const yineleyici döndürür.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir [hash_set](../standard-library/hash-set-class.md) (geri çevrilme içindeki ilk öğeden önce gelen konum) izleyen konumu ele alan bir sabit ters çift yönlü Yineleyici `hash_set` .

### <a name="remarks"></a>Açıklamalar

`crend` , bir ters ile birlikte kullanıldığında `hash_set` [hash_set:: End](#end) ile birlikte kullanılır `hash_set` .

Dönüş değeri ile `crend` `hash_set` nesne değiştirilemez.

`crend` , geriye doğru bir yineleyicinin sonuna ulaşılıp ulaşılmadığını test etmek için kullanılabilir `hash_set` .

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

## <a name="hash_setdifference_type"></a><a name="difference_type"></a> hash_set::d ifference_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Yineleyiciler tarafından gösterilen öğeler arasındaki bir aralıktaki hash_set öğelerinin sayısını temsil etmek için kullanılabilen işaretli bir tamsayı türü.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

`difference_type`Kapsayıcının yineleyiciler aracılığıyla çıkartılacak veya artırılarak döndürülen türdür. , `difference_type` Genellikle yineleyiciler arasındaki [,) aralıktaki öğelerin sayısını temsil etmek için kullanılır ve öğesi tarafından işaret edilen öğe `first` `last` `first` `last` `first` ve dahil `last` olmak üzere öğe aralığı ile işaret eder.

`difference_type`Küme gibi tersine çevrilebilir kapsayıcılar tarafından desteklenen çift yönlü yineleyicilerin sınıfını içeren bir giriş yineleyicisinin gereksinimlerini karşılayan tüm yineleyiciler için kullanılabilir olsa da, yineleyiciler arasında çıkarma, yalnızca bir rastgele erişim kapsayıcısı tarafından sağlanan vektör veya deque gibi rasgele erişim yineleyiciler tarafından desteklenir.

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

## <a name="hash_setemplace"></a><a name="emplace"></a> hash_set:: emplace

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Bir hash_set içinde oluşturulmuş bir öğe ekler.

```cpp
template <class ValTy>
pair <iterator, bool>
emplace(
    ValTy&& val);
```

### <a name="parameters"></a>Parametreler

*Acil*\
Zaten bu öğeyi veya daha genel bir öğeyi içermiyorsa, bu öğe için [hash_set](../standard-library/hash-set-class.md) eklenecek öğenin değeri, `hash_set` anahtarı equivalently sıralı bir öğe.

### <a name="return-value"></a>Dönüş Değeri

`emplace`Üye işlevi, **`bool`** bir ekleme işlemi ise bileşeni döndüren bir çift döndürür **`true`** ve **`false`** `hash_set` zaten anahtarı sıralamada denk bir değere sahip olan bir öğe içeriyorsa ve yineleyici bileşeni, yeni bir öğenin eklendiği veya öğenin zaten bulunduğu yerdeki bir adresi döndürüyor.

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

## <a name="hash_setemplace_hint"></a><a name="emplace_hint"></a> hash_set:: emplace_hint

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Bir hash_set içinde oluşturulmuş bir öğe ekler.

```cpp
template <class ValTy>
iterator emplace(
    const_iterator _Where,
    ValTy&& val);
```

### <a name="parameters"></a>Parametreler

*Acil*\
Zaten bu öğeyi veya daha genel bir öğeyi içermiyorsa, bu öğe için [hash_set](../standard-library/hash-set-class.md) eklenecek öğenin değeri, `hash_set` anahtarı equivalently sıralı bir öğe.

*_Where*\
Doğru ekleme noktasını aramaya başlamak için yer. (Ekleme noktası *_Where* hemen sonrasında, ekleme, logaritmik bir süre yerine, sabit zamanlı olarak ortaya çıkabilir.)

### <a name="return-value"></a>Dönüş Değeri

[Hash_set:: emplace](#emplace) üye işlevi, yeni öğenin içine eklendiği konuma `hash_set` veya eşdeğer sıralamaya sahip olan öğenin bulunduğu konuma işaret eden bir yineleyici döndürür.

### <a name="remarks"></a>Açıklamalar

Ekleme noktası *_Where* hemen ardından, ekleme noktası, logaritmik bir süre yerine, sabit zamanlı olarak meydana gelebilir.

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

## <a name="hash_setempty"></a><a name="empty"></a> hash_set:: boş

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Hash_set boş ise sınar.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** hash_set boşsa; **`false`** hash_set boş değilse.

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

## <a name="hash_setend"></a><a name="end"></a> hash_set:: End

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Hash_set son öğeden sonraki konumu ele alan bir yineleyici döndürür.

```cpp
const_iterator end() const;

iterator end();
```

### <a name="return-value"></a>Dönüş Değeri

Bir hash_set son öğeden sonraki konumu ele alan çift yönlü bir yineleyici. Hash_set boşsa, hash_set:: End = = hash_set:: BEGIN.

### <a name="remarks"></a>Açıklamalar

`end` , bir yineleyicinin hash_set sonuna kadar ulaşılıp ulaşmadığını test etmek için kullanılır. Tarafından döndürülen değer `end` başvurulmamalıdır.

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

## <a name="hash_setequal_range"></a><a name="equal_range"></a> hash_set:: equal_range

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Belirtilen bir anahtara ve anahtardan daha büyük bir anahtarla karma kümesindeki ilk öğeye eşit olan bir anahtarla bir karma kümesindeki ilk öğeye sırasıyla yineleyiciler çiftini döndürür.

```cpp
pair <const_iterator, const_iterator> equal_range (const Key& key) const;

pair <iterator, iterator> equal_range (const Key& key);
```

### <a name="parameters"></a>Parametreler

*anahtar*\
Aranan hash_set öğenin sıralama anahtarıyla Karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

İlk anahtarın [lower_bound](../standard-library/set-class.md#lower_bound) ve ikincisi anahtarın [upper_bound](../standard-library/set-class.md#upper_bound) olduğu yineleyiciler çifti.

Üye işlevi tarafından döndürülen bir çiftin PR 'nin ilk Yineleyici öğesine erişmek için kullanın `pr` . **ilk** olarak, alt sınır Yineleyici için başvuru yapmak üzere \* ( `pr` . **ilk**). Üye işlevi tarafından döndürülen bir çiftin ikinci Yineleyici öğesine erişmek için `pr` kullanın `pr` . **ikincisi** ve üst sınır yineleyicisini başvuru yapmak için \* ( `pr` . **ikinci**).

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

## <a name="hash_seterase"></a><a name="erase"></a> hash_set:: Erase

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Belirtilen konumlardan bir hash_set öğeyi veya öğe aralığını kaldırır veya belirtilen bir anahtarla eşleşen öğeleri kaldırır.

```cpp
iterator erase(iterator _Where);

iterator erase(iterator first, iterator last);

size_type erase(const key_type& key);
```

### <a name="parameters"></a>Parametreler

*_Where*\
Hash_set kaldırılacak öğenin konumu.

*adı*\
Hash_set kaldırılan ilk öğenin konumu.

*soyadına*\
Hash_set kaldırılan son öğenin hemen ötesinde konumlandır.

*anahtar*\
Hash_set kaldırılacak öğelerin anahtarı.

### <a name="return-value"></a>Dönüş Değeri

İlk iki üye işlevi için, kaldırılan öğelerin dışında kalan ilk öğeyi veya böyle bir öğe yoksa hash_set sonuna işaretçiyi atayan çift yönlü bir yineleyici. Üçüncü üye işlevi için, hash_set kaldırılan öğelerin sayısı.

### <a name="remarks"></a>Açıklamalar

Üye işlevleri hiçbir şekilde özel durum oluşturmaz.

### <a name="example"></a>Örnek

Aşağıdaki örnek hash_set:: Erase üye işlevinin kullanımını gösterir.

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

## <a name="hash_setfind"></a><a name="find"></a> hash_set:: Find

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Belirtilen anahtara eşdeğer bir anahtara sahip bir hash_set öğenin konumunu ele alan bir yineleyici döndürür.

```cpp
iterator find(const Key& key);

const_iterator find(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*anahtar*\
Aranan hash_set öğenin sıralama anahtarıyla eşleştirilecek bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Bir `iterator` veya `const_iterator` anahtarı için eşleşme bulunmazsa hash_set son öğeden sonra gelen konumu ele alan veya belirtilen bir anahtara denk gelen bir öğe.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, sıralama anahtarı, `equivalent` daha az karşılaştırılır ilişkisini temel alan bir sıralamayı karşılayan bir ikili koşulda bağımsız değişken anahtarına olan hash_set bir öğeyi ele alan bir yineleyici döndürür.

Dönüş değeri `find` bir öğesine atanırsa `const_iterator` , hash_set nesnesi değiştirilemez. Dönüş değeri `find` bir öğesine atanırsa `iterator` , hash_set nesnesi değiştirilebilir.

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

## <a name="hash_setget_allocator"></a><a name="get_allocator"></a> hash_set:: get_allocator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Hash_set oluşturmak için kullanılan ayırıcı nesnesinin bir kopyasını döndürür.

```cpp
Allocator get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şablon parametre *ayırıcısı* olan belleği yönetmek için hash_set tarafından kullanılan ayırıcı.

*Ayırıcı* hakkında daha fazla bilgi Için [hash_set Sınıfı](../standard-library/hash-set-class.md) konusunun açıklamalar bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

Hash_set Sınıfı için ayrıcılar, sınıfın depolamayı nasıl yönettiğini belirtir. C++ standart kitaplığı kapsayıcı sınıflarıyla birlikte sağlanan varsayılan ayrıcılar çoğu programlama ihtiyacı için yeterlidir. Kendi ayırıcı sınıfınızı yazmak ve kullanmak, gelişmiş bir C++ konudur.

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

## <a name="hash_sethash_set"></a><a name="hash_set"></a> hash_set:: hash_set

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

`hash_set`Boş olan veya bir kısmının tümünün veya bir kısmının kopyası olan oluşturur `hash_set` .

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

*Eşkenar*\
Varsayılan olarak, bu nesne için kullanılacak depolama ayırıcı sınıfı `hash_set` `Allocator` .

*İnin*\
`const Traits`' Deki öğeleri sıralamak için kullanılan tür karşılaştırma işlevi, `hash_set` Varsayılan olarak `hash_compare` .

*Right*\
`hash_set`Oluşturulan öğesinin `hash_set` bir kopyalama olduğu yer.

*Adı*\
Kopyalanacak öğe aralığındaki ilk öğenin konumu.

*Soyadına*\
Kopyalanacak öğe aralığının ötesinde ilk öğenin konumu.

### <a name="remarks"></a>Açıklamalar

Tüm oluşturucular, `hash_set` ve daha sonra [hash_set:: get_allocator](#get_allocator)çağırarak döndürülebilecek bellek depolamayı yöneten bir tür ayırıcı nesnesi depolar. Ayırıcı parametresi, genellikle sınıf bildirimlerinde atlanır ve alternatif ayırıcıları değiştirmek için kullanılan ön işleme makrolarıyla sonuçlanır.

Tüm oluşturucular hash_sets başlatır.

Tüm oluşturucular `Traits` , `hash_set` ve daha sonra [hash_set:: key_comp](#key_comp)çağırarak döndürülebilecek anahtarlar arasında bir sıra oluşturmak için kullanılan türünde bir işlev nesnesi depolar. Hakkında daha fazla bilgi için `Traits` [hash_set Sınıfı](../standard-library/hash-set-class.md) konusuna bakın.

İlk Oluşturucu boş bir başlangıç oluşturur `hash_set` İkincisi, `Comp` öğelerin sırasını oluşturmak için kullanılacak karşılaştırma işlevinin türünü () belirtir ve üçüncüsü açıkça kullanılacak ayırıcı türünü ( `Al` ) belirtir. Anahtar sözcük, **`explicit`** bazı otomatik tür dönüştürme türlerini bastırır.

Dördüncü ve beşinci oluşturucular öğesinin bir kopyasını belirtir `hash_set` `Right` .

Son altıncı, yedinci ve sekizinci oluşturucular öğeler için bir initializer_list kullanır.

Son oluşturucular, ' `First` ın [,) aralığını, `Last` `hash_set` sınıf nitelikleri ve ayırıcı 'un karşılaştırma işlevinin türünü belirtirken açıkça bir şekilde kopyalar.

Sekizinci Oluşturucu öğesini taşımaktır `hash_set` `Right` .

Bir kapsayıcıdaki öğelerin gerçek sıralaması, `hash_set` karma işleve, sıralama işlevine ve karma tablonun geçerli boyutuna bağlıdır ve genellikle sıralama işlevi tarafından belirlendiği şekilde, ayarlanan kapsayıcıda tahmin edilebilir.

## <a name="hash_setinsert"></a><a name="insert"></a> hash_set:: INSERT

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

İçine bir öğe veya öğe aralığı ekler `hash_set` .

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

*Acil*\
`hash_set` `hash_set` Zaten bu öğeyi veya daha genel olarak, anahtarı equivalently sıralı bir öğe içermiyorsa, içine eklenecek öğenin değeri.

*Olmadığı*\
Doğru ekleme noktasını aramaya başlamak için yer. (Ekleme noktası hemen ardından, ekleme noktası, Logaritmik süre yerine, sabit zamanlı olarak bir araya gelebilir `_Where` .)

*Adı*\
Bir öğesinden kopyalanacak ilk öğenin konumu `hash_set` .

*Soyadına*\
' Dan kopyalanacak son öğenin hemen ötesinde konum `hash_set` .

*IList*\
Öğelerin kopyalanacağı initializer_list.

### <a name="return-value"></a>Dönüş Değeri

İlk `insert` üye işlevi, **`bool`** bir ekleme işlemi ise bileşeni döndüren bir çift döndürür **`true`** ve **`false`** `hash_set` zaten anahtarı sıralamada denk bir değere sahip olan bir öğe içeriyorsa ve yineleyici bileşeni, yeni bir öğenin eklendiği veya öğenin zaten bulunduğu konumda yer alan adresi döndürüyor.

Bu üye işlevi tarafından döndürülen bir çiftin Yineleyici bileşenine erişmek için `pr` `pr.first` ve kullanarak başvuru yapın, öğesini kullanın `*(pr.first)` . **`bool`** `pr` Bu üye işlevi tarafından döndürülen bir çiftin bileşenine erişmek için, kullanın ve öğesini kullanın `pr.second` `*(pr.second)` .

İkinci `insert` üye işlevi, yeni öğenin içine eklendiği konuma işaret eden bir yineleyici döndürür `hash_set` .

### <a name="remarks"></a>Açıklamalar

Üçüncü üye işlevi, öğeleri bir initializer_list ekler.

Üçüncü üye işlevi, öğe değerlerinin dizisini, `hash_set` `First` belirtilen bir [,) aralığında bir yineleyici tarafından bahsedilen her öğeye karşılık gelen öğesine ekler `Last` `hash_set` .

## <a name="hash_setiterator"></a><a name="iterator"></a> hash_set:: Yineleyici

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Bir hash_set herhangi bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleyici sağlayan bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::iterator iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir türü `iterator` , bir öğenin değerini değiştirmek için kullanılabilir.

### <a name="example"></a>Örnek

Bildirme ve kullanma hakkında bir [örnek için bkz](#begin) . örnek `iterator` .

## <a name="hash_setkey_comp"></a><a name="key_comp"></a> hash_set:: key_comp

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Bir hash_set öğe anahtar değerlerini karma ve sıralama için kullanılan karma nitelikleri nesnesinin bir kopyasını alır.

```cpp
key_compare key_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Hash_set, şablon parametresi *nitelikleri* olan öğelerini sıralamak için kullandığı işlev nesnesini döndürür.

*Nitelikler* hakkında daha fazla bilgi Için [hash_set Sınıfı](../standard-library/hash-set-class.md) konusuna bakın.

### <a name="remarks"></a>Açıklamalar

Saklı nesne, üye işlevini tanımlar:

`bool operator( const Key& _xVal, const Key& _yVal );`

Bu, **`true`** `_xVal` önceki ve sıralama düzeninde eşit değilse döndürür `_yVal` .

Hem [key_compare](#key_compare) hem de [value_compare](#value_compare) şablon parametresi *nitelikleri* için eş anlamlı olduğunu unutmayın. Her iki tür de hash_set ve hash_multiset sınıfları için sağlanır ve bunlar birbirinden farklı oldukları hash_map ve hash_multimap sınıflarıyla uyumluluk içindir.

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

## <a name="hash_setkey_compare"></a><a name="key_compare"></a> hash_set:: key_compare

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Hash_set iki öğenin göreli sırasını belirleyebilmek için iki sıralama anahtarını karşılaştıran bir işlev nesnesi sağlayan bir tür.

```cpp
typedef Traits key_compare;
```

### <a name="remarks"></a>Açıklamalar

`key_compare` , şablon parametresi *nitelikleri* için bir eş anlamlı.

*Nitelikler* hakkında daha fazla bilgi Için [hash_set Sınıfı](../standard-library/hash-set-class.md) konusuna bakın.

Hem hem de `key_compare` [value_compare](#value_compare) şablon parametresi *nitelikleri* için eş anlamlı olduğunu unutmayın. Her iki tür de, farklı oldukları, eşleme ve multimap sınıfları ile uyumluluk için, aynı oldukları küme ve çoklu küme sınıfları için sağlanır.

### <a name="example"></a>Örnek

Bildirme ve kullanma hakkında bir örnek için bkz. [key_comp](#key_comp) örneği `key_compare` .

## <a name="hash_setkey_type"></a><a name="key_type"></a> hash_set:: key_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Hash_set öğesi olarak depolanan bir nesneyi sıralama anahtarı olarak kapasitesinde tanımlayan bir tür.

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Açıklamalar

`key_type` , şablon parametre *anahtarı* için bir eş anlamlı.

*Anahtar* hakkında daha fazla bilgi Için [hash_set Sınıfı](../standard-library/hash-set-class.md) konusunun açıklamalar bölümüne bakın.

Hem hem de `key_type` [value_type](#value_type) şablon parametresi *anahtarı* için eş anlamlı olduğunu unutmayın. Her iki tür de hash_set ve hash_multiset sınıfları için sağlanır ve bunlar birbirinden farklı oldukları hash_map ve hash_multimap sınıflarıyla uyumluluk içindir.

### <a name="example"></a>Örnek

Bildirme ve kullanma hakkında bir örnek için bkz. [value_type](#value_type) örneği `key_type` .

## <a name="hash_setlower_bound"></a><a name="lower_bound"></a> hash_set:: lower_bound

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Bir yineleyiciyi belirtilen anahtardan daha büyük veya ona eşit bir anahtarla bir hash_set ilk öğeye döndürür.

```cpp
const_iterator lower_bound(const Key& key) const;

iterator lower_bound(const Key& key);
```

### <a name="parameters"></a>Parametreler

*anahtar*\
Aranan hash_set öğenin sıralama anahtarıyla Karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Bir `iterator` veya `const_iterator` bağımsız değişken anahtarından büyük veya ona eşit olan veya anahtar için eşleşme bulunmazsa hash_set son öğeden sonraki konumu ele alan bir hash_set öğenin konumunu ele alan bir veya.

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

## <a name="hash_setmax_size"></a><a name="max_size"></a> hash_set:: max_size

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Hash_set maksimum uzunluğunu döndürür.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Hash_set olabilecek en uzun uzunluk.

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

## <a name="hash_setoperator"></a><a name="op_eq"></a> hash_set:: operator =

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Hash_set öğelerini başka bir hash_set kopyasıyla değiştirir.

```cpp
hash_set& operator=(const hash_set& right);

hash_set& operator=(hash_set&& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
İçine kopyalandığı [hash_set](../standard-library/hash-set-class.md) `hash_set` .

### <a name="remarks"></a>Açıklamalar

İçindeki varolan öğeleri sildikten sonra `hash_set` , ' `operator=` nin içeriğini kopyalar ya da içine *taşısa* `hash_set` .

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

## <a name="hash_setpointer"></a><a name="pointer"></a> hash_set::p oınter

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Hash_set bir öğeye işaretçi sağlayan bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir türü `pointer` , bir öğenin değerini değiştirmek için kullanılabilir.

Çoğu durumda, bir [yineleyici](#iterator) hash_set nesnesindeki öğelere erişmek için kullanılmalıdır.

## <a name="hash_setrbegin"></a><a name="rbegin"></a> hash_set:: rbegin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Ters çevrilen hash_set ilk öğeyi adresleyen bir yineleyici döndürür.

```cpp
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir hash_set ilk öğeyi ele almak veya geri alınamaz hash_set son öğe olduğunu ele almak için ters çift yönlü Yineleyici.

### <a name="remarks"></a>Açıklamalar

`rbegin` , [Başlangıç](#begin) olarak bir hash_set ile birlikte kullanılan bir ters hash_set ile kullanılır.

Öğesinin dönüş değeri `rbegin` öğesine atanmışsa `const_reverse_iterator` , hash_set nesnesi değiştirilemez. Dönüş değeri `rbegin` bir öğesine atanırsa `reverse_iterator` , hash_set nesnesi değiştirilebilir.

`rbegin` , bir hash_set geriye doğru yinelemek için kullanılabilir.

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

## <a name="hash_setreference"></a><a name="reference"></a> hash_set:: Reference

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Hash_set depolanan bir öğeye başvuru sağlayan bir tür.

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

## <a name="hash_setrend"></a><a name="rend"></a> hash_set:: rend

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Ters çevrilen hash_set son öğeden sonraki konumu ele alan bir yineleyici döndürür.

```cpp
const_reverse_iterator rend() const;

reverse_iterator rend();
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir hash_set en son öğeden sonra gelen konumu ele alan ters çift yönlü yineleyici (geri alınamaz hash_set ilk öğeden önce gelen konum).

### <a name="remarks"></a>Açıklamalar

`rend` , [End](#end) bir hash_set ile kullanıldığı gibi ters bir hash_set kullanılır.

Öğesinin dönüş değeri `rend` öğesine atanmışsa `const_reverse_iterator` , hash_set nesnesi değiştirilemez. Dönüş değeri `rend` bir öğesine atanırsa `reverse_iterator` , hash_set nesnesi değiştirilebilir. Tarafından döndürülen değer `rend` başvurulmamalıdır.

`rend` ters bir yineleyicinin hash_set sonuna kadar ulaştığı konusunda test etmek için kullanılabilir.

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

## <a name="hash_setreverse_iterator"></a><a name="reverse_iterator"></a> hash_set:: reverse_iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Ters çevrilen bir hash_set bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleyici sağlayan bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::reverse_iterator reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `reverse_iterator` , ters içinde hash_set yinelemek için kullanılır.

### <a name="example"></a>Örnek

Bildirme ve kullanma hakkında bir örnek için bkz. [rbegin](#rbegin) örneği `reverse_iterator` .

## <a name="hash_setsize"></a><a name="size"></a> hash_set:: size

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Hash_set öğe sayısını döndürür.

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

## <a name="hash_setsize_type"></a><a name="size_type"></a> hash_set:: size_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Bir hash_set öğe sayısını temsil eden işaretsiz bir tamsayı türü.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::size_type size_type;
```

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

Nasıl bildirilemeyeceğini ve kullanılacağına ilişkin bir örnek için [Boyut](#size) örneğine bakın `size_type`

## <a name="hash_setswap"></a><a name="swap"></a> hash_set:: swap

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

İki hash_sets öğelerini değiş tokuş eder.

```cpp
void swap(hash_set& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Bağımsız değişkeni, hedef hash_set birlikte takas edilecek öğeleri sağlayan hash_set.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, öğeleri takas edilmekte olan iki hash_sets öğeleri belirten başvuruları, işaretçileri veya yineleyicileri geçersiz kılar.

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

## <a name="hash_setupper_bound"></a><a name="upper_bound"></a> hash_set:: upper_bound

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Bir yineleyiciyi belirtilen anahtardan daha büyük bir anahtarla bir hash_set ilk öğeye döndürür.

```cpp
const_iterator upper_bound(const Key& key) const;

iterator upper_bound(const Key& key);
```

### <a name="parameters"></a>Parametreler

*anahtar*\
Aranan hash_set öğenin sıralama anahtarıyla Karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Bir `iterator` veya `const_iterator` bağımsız değişken anahtarına eşit veya daha büyük bir anahtara sahip bir hash_set öğenin konumunu ele alan veya anahtar için eşleşme bulunmazsa hash_set son öğeden sonraki konumu ele alan bir öğe.

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

## <a name="hash_setvalue_comp"></a><a name="value_comp"></a> hash_set:: value_comp

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Bir hash_set öğe değerlerini sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır.

```cpp
value_compare value_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Hash_set, şablon parametresi *karşılaştırma* olan öğelerini sıralamak için kullandığı işlev nesnesini döndürür.

*Karşılaştırma* hakkında daha fazla bilgi Için [hash_set Sınıfı](../standard-library/hash-set-class.md) konusunun açıklamalar bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

Saklı nesne, üye işlevini tanımlar:

`bool operator( const Key& _xVal, const Key& _yVal );`

Bu, **`true`** `_xVal` önceki ve sıralama düzeninde eşit değilse döndürür `_yVal` .

Hem [value_compare](../standard-library/set-class.md#value_compare) hem de [Key_compare](../standard-library/set-class.md#key_compare) şablon parametresi *karşılaştırması* için eş anlamlı olduğunu unutmayın. Her iki tür de hash_set ve hash_multiset sınıfları için sağlanır ve bunlar birbirinden farklı oldukları hash_map ve hash_multimap sınıflarıyla uyumluluk içindir.

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

## <a name="hash_setvalue_compare"></a><a name="value_compare"></a> hash_set:: value_compare

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

İki işlev nesnesi sağlayan bir tür, bir hash_set iki öğe değerini karşılaştırabilir ve öğelerin karma oluşturan birli bir koşulu tespit edebilir.

```cpp
typedef key_compare value_compare;
```

### <a name="remarks"></a>Açıklamalar

`value_compare` , şablon parametresi *nitelikleri* için bir eş anlamlı.

*Nitelikler* hakkında daha fazla bilgi Için [hash_set Sınıfı](../standard-library/hash-set-class.md) konusuna bakın.

Hem [key_compare](#key_compare) hem de `value_compare` şablon parametresi *nitelikleri* için eş anlamlıların olduğunu unutmayın. Her iki tür de hash_set ve hash_multiset sınıfları için sağlanır ve bunlar birbirinden farklı oldukları hash_map ve hash_multimap sınıflarıyla uyumluluk içindir.

### <a name="example"></a>Örnek

Bildirme ve kullanma hakkında bir örnek için bkz. [value_comp](#value_comp) örneği `value_compare` .

## <a name="hash_setvalue_type"></a><a name="value_type"></a> hash_set:: value_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

Bir değeri bir değer olarak kapasitesinin hash_set bir öğesi olarak tanımlayan bir tür.

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

[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ standart kitaplığı başvurusu](../standard-library/cpp-standard-library-reference.md)
