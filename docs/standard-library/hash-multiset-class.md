---
title: hash_multiset Sınıfı
ms.date: 11/04/2016
f1_keywords:
- hash_set/stdext::hash_multiset
- hash_set/stdext::hash_multiset::allocator_type
- hash_set/stdext::hash_multiset::const_iterator
- hash_set/stdext::hash_multiset::const_pointer
- hash_set/stdext::hash_multiset::const_reference
- hash_set/stdext::hash_multiset::const_reverse_iterator
- hash_set/stdext::hash_multiset::difference_type
- hash_set/stdext::hash_multiset::iterator
- hash_set/stdext::hash_multiset::key_compare
- hash_set/stdext::hash_multiset::key_type
- hash_set/stdext::hash_multiset::pointer
- hash_set/stdext::hash_multiset::reference
- hash_set/stdext::hash_multiset::reverse_iterator
- hash_set/stdext::hash_multiset::size_type
- hash_set/stdext::hash_multiset::value_compare
- hash_set/stdext::hash_multiset::value_type
- hash_set/stdext::hash_multiset::begin
- hash_set/stdext::hash_multiset::cbegin
- hash_set/stdext::hash_multiset::cend
- hash_set/stdext::hash_multiset::clear
- hash_set/stdext::hash_multiset::count
- hash_set/stdext::hash_multiset::crbegin
- hash_set/stdext::hash_multiset::crend
- hash_set/stdext::hash_multiset::emplace
- hash_set/stdext::hash_multiset::emplace_hint
- hash_set/stdext::hash_multiset::empty
- hash_set/stdext::hash_multiset::end
- hash_set/stdext::hash_multiset::equal_range
- hash_set/stdext::hash_multiset::erase
- hash_set/stdext::hash_multiset::find
- hash_set/stdext::hash_multiset::get_allocator
- hash_set/stdext::hash_multiset::insert
- hash_set/stdext::hash_multiset::key_comp
- hash_set/stdext::hash_multiset::lower_bound
- hash_set/stdext::hash_multiset::max_size
- hash_set/stdext::hash_multiset::rbegin
- hash_set/stdext::hash_multiset::rend
- hash_set/stdext::hash_multiset::size
- hash_set/stdext::hash_multiset::swap
- hash_set/stdext::hash_multiset::upper_bound
- hash_set/stdext::hash_multiset::value_comp
helpviewer_keywords:
- stdext::hash_multiset
- stdext::hash_multiset::allocator_type
- stdext::hash_multiset::const_iterator
- stdext::hash_multiset::const_pointer
- stdext::hash_multiset::const_reference
- stdext::hash_multiset::const_reverse_iterator
- stdext::hash_multiset::difference_type
- stdext::hash_multiset::iterator
- stdext::hash_multiset::key_compare
- stdext::hash_multiset::key_type
- stdext::hash_multiset::pointer
- stdext::hash_multiset::reference
- stdext::hash_multiset::reverse_iterator
- stdext::hash_multiset::size_type
- stdext::hash_multiset::value_compare
- stdext::hash_multiset::value_type
- stdext::hash_multiset::begin
- stdext::hash_multiset::cbegin
- stdext::hash_multiset::cend
- stdext::hash_multiset::clear
- stdext::hash_multiset::count
- stdext::hash_multiset::crbegin
- stdext::hash_multiset::crend
- stdext::hash_multiset::emplace
- stdext::hash_multiset::emplace_hint
- stdext::hash_multiset::empty
- stdext::hash_multiset::end
- stdext::hash_multiset::equal_range
- stdext::hash_multiset::erase
- stdext::hash_multiset::find
- stdext::hash_multiset::get_allocator
- stdext::hash_multiset::insert
- stdext::hash_multiset::key_comp
- stdext::hash_multiset::lower_bound
- stdext::hash_multiset::max_size
- stdext::hash_multiset::rbegin
- stdext::hash_multiset::rend
- stdext::hash_multiset::size
- stdext::hash_multiset::swap
- stdext::hash_multiset::upper_bound
- stdext::hash_multiset::value_comp
ms.assetid: 0580397a-a76e-40ad-aea2-5c6f3a9d0a21
ms.openlocfilehash: d4722a9c535207b21098db4e33810340d99e6b6a
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88561446"
---
# <a name="hash_multiset-class"></a>hash_multiset Sınıfı

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfıdır](../standard-library/unordered-multiset-class.md).

Kapsayıcı sınıfı hash_multiset, C++ standart kitaplığı 'nın bir uzantısıdır ve içinde bulunan öğelerin değerlerinin anahtar değerler olarak çalıştığı ve benzersiz olması gerekmediği bir koleksiyondaki verilerin depolanması ve hızlı bir şekilde alınması için kullanılır.

## <a name="syntax"></a>Söz dizimi

```cpp
template <class Key, class Traits =hash_compare<Key, less <Key>>, class Allocator =allocator <Key>>
class hash_multiset
```

### <a name="parameters"></a>Parametreler

*Anahtar*\
Hash_multiset depolanacak öğe veri türü.

*Lerdir*\
İki işlev nesnesi içeren tür, bir ikili koşul olan sınıf karşılaştırmasına sahip iki öğe değerini, öğelerin birli bir koşul eşleme anahtar değerleri olan bir karma işlevi ve türün işaretsiz tamsayılar olan bir karma işlevini tespit etmek için sıralama anahtarları olarak karşılaştırabilmeyebilir `size_t` . Bu bağımsız değişken isteğe bağlıdır ve `hash_compare<Key, less<Key> >` varsayılan değerdir.

*Öğe*\
Hash_multiset, bellek ayırma ve ayırmayı kaldırma hakkındaki ayrıntıları kapsülleyen saklı ayırıcı nesnesini temsil eden tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değerdir `allocator<Key>` .

## <a name="remarks"></a>Açıklamalar

Hash_multiset:

- İlişkili bir anahtar değerine dayalı öğe değerlerinin verimli alınmasını destekleyen bir değişken boyutu kapsayıcı olan ilişkilendirilebilir bir kapsayıcı. Dahası, basit bir ilişkilendirilebilir kapsayıcıdır, çünkü öğelerinin değerleri kendi anahtar değerleridir.

- Çift yönlüdür, çünkü öğelerine erişmek için çift yönlü bir yineleyici sağlar.

- Karma değeri, öğelerinin anahtar değerlerine uygulanan bir karma işlevin değerine bağlı olarak demet halinde gruplandığından karma hale getirilir.

- Benzersizdir, çünkü öğelerinin her birinde benzersiz bir anahtar olması gerekir. Hash_multiset Ayrıca basit ilişkilendirilebilir bir kapsayıcı olduğundan, öğeleri de benzersizdir.

- Bir sınıf şablonu, sağladığı işlevsellik geneldir ve bu nedenle öğe veya anahtar olarak içerilen belirli veri türünden bağımsızdır. Öğeler ve anahtarlar için kullanılacak veri türleri, karşılaştırma işlevi ve ayırıcı ile birlikte bir sınıf şablonunda parametreler olarak belirtilir.

Sıralamaya kıyasla karmaların başlıca avantajı daha fazla verimlilik: başarılı bir karma değer ekleme, silme işlemleri gerçekleştirir ve sabit ortalama süre içinde, sıralama teknikleri için kapsayıcıdaki öğelerin sayısının logaritmasına göre orantılı bir süre ile karşılaştırılır. Bir kümedeki bir öğenin değeri doğrudan değiştirilemez. Bunun yerine, eski değerleri silmeniz ve yeni değerlere sahip öğeler eklemeniz gerekir.

Kapsayıcı türünün seçimi genelde uygulamanın gerektirdiği arama ve ekleme türüne dayalı olmalıdır. Karma olarak ilişkilendirilebilir kapsayıcılar, arama, ekleme ve kaldırma işlemleri için iyileştirilmiştir. Bu işlemleri açıkça destekleyen üye işlevleri, iyi tasarlanmış bir karma işlevi ile kullanıldığında etkili olur ve bunları ortalama Sabitte olan ve kapsayıcıdaki öğelerin sayısına bağımlı olmayan bir zaman içinde gerçekleştiriyor. İyi tasarlanmış bir karma işlevi, karma değerler için Tekdüzen bir dağıtım üretir ve ayrı anahtar değerleri aynı karma değere eşlendiğinde bir çarpışmanın oluşmasına neden olan çakışmaların sayısını en aza indirir. En kötü durumda, mümkün olan en kötü karma işlevi olan işlem sayısı, dizideki öğelerin sayısıyla orantılıdır (doğrusal saat).

Değerleri, anahtar ile ilişkilendirirken, uygulama tarafından bu koşulların ilişkilendirilmesi durumunda hash_multiset, seçeneğin ilişkilendirilebilir kapsayıcısı olmalıdır. Hash_multiset öğeleri birden çok olabilir ve kendi sıralama anahtarları olarak işlev gösterebilir. bu nedenle anahtarlar benzersiz değildir. Bu tür bir yapı modeli, sözcüklerin birden çok defa geçebildiği sıralı bir sözcükler listesindedir. Sözcüklerin birden çok örneğine izin verilmediğinden, uygun kapsayıcı yapısı hash_set. Benzersiz tanımlar benzersiz anahtar sözcükler listesine değer olarak iliştirilmişse, bu verileri içeren bir hash_map uygun bir yapı olacaktır. Bunun yerine tanımlar benzersiz değilse, bir hash_multimap tercih edilen kapsayıcı olur.

Hash_multiset, [value_compare](#value_compare)türünde depolanan bir karma nitelikleri nesnesini çağırarak denetlediği diziyi sıralar. Bu saklı nesneye [key_comp](#key_comp)üye işlevi çağırarak erişilebilir. Böyle bir işlev nesnesi, sınıfının bir nesnesi ile aynı şekilde davranmalıdır `hash_compare<Key, less<Key> >` . Özellikle, türündeki tüm değerler *anahtarı* için `Key` , çağrı, `Trait(Key)` türündeki değerlerin bir dağılımını verir `size_t` .

Genelde, bu sıralamayı oluşturmak için öğelerin yalnızca küçüktür biçiminde karşılaştırılabilir olması gerekir; böylece, herhangi iki öğe belirtildiğinde, eşit oldukları (yani birinin diğerinden daha küçük olmadığı anlamında) veya birinin diğerinden küçük olduğu belirlenebilir. Bu, denk olmayan öğeler arasında bir sıralamaya neden olur. Daha teknik bir not üzerinde, karşılaştırma işlevi standart matematiksel anlamda katı bir zayıf sıralama sevk eden ikili bir koşuldur. Bir ikili koşul *f*( *x*, *y*) iki bağımsız değişken nesnesi olan x ve y ve true ya da false dönüş değerine sahip bir işlev nesnesidir. İkili koşul geri dönüşsüz, antisimetrik ve geçişli ve denklik geçişli ise, hash_multiset uygulanan bir sıralama katı zayıf bir sıradır, burada iki nesne x ve y, her ikisi de *f*( *x*, *y*) ve *f*( *y*, *x*) false olduğunda denk olarak tanımlanır. Anahtarlar arasındaki eşitliğinin daha güçlü koşulu bu denkliğin yerini alırsa, sıralama (içindeki tüm öğelerin birbirine göre sıralanması anlamında) toplam haline gelir ve eşleşen anahtarlar birbirinden ayırt edilemez olacaktır.

Denetlenen dizideki öğelerin gerçek sırası, karma işleve, sıralama işlevine ve kapsayıcı nesnesinde depolanan karma tablonun geçerli boyutuna bağlıdır. Karma tablonun geçerli boyutunu belirleyemez, bu nedenle denetimli dizideki öğelerin sırasını genel olarak tahmin edemezsiniz. Öğelerin eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; öğelerin kaldırılması yalnızca özellikle kaldırılan öğeleri gösteren yineleyicileri geçersiz kılar.

Hash_multiset sınıfı tarafından verilen yineleyici çift yönlü bir yineleyicidir, ancak INSERT ve hash_multiset sınıf üyesi işlevleri, şablon parametresi olarak daha zayıf bir giriş yineleyicisini alan, işlevsellik gereksinimleri çift yönlü yineleyicilerin sınıfına göre garantiden daha düşük olan sürümlere sahiptir. Farklı yineleyici kavramları, işlevselliklerindeki iyileştirmelere göre ilgili bir aile biçimlendirir. Her Yineleyici kavramının kendi gereksinimleri hash_multiset vardır ve bunlarla çalışan algoritmaların kendi varsayımları, bu tür Yineleyici tarafından belirtilen gereksinimlere göre sınırlandırmalıdır. Bir giriş yineleyicinin bazı nesnelere başvurusunun kaldırılacağı ve dizideki sonraki yineleyiciye artırılabileceği varsayılabilir. Bu, işlevselliğin en az bir hash_multiset, ancak `first` `last` sınıf üye işlevleri bağlamında bir dizi yineleyiciler [,) hakkında anlamlı bir şekilde konuşabilmek için yeterlidir.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[hash_multiset](#hash_multiset)|`hash_multiset`Boş olan veya bir kısmının tümünün veya bir kısmının kopyası olan oluşturur `hash_multiset` .|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[allocator_type](#allocator_type)|Nesnenin sınıfını temsil eden bir tür `allocator` `hash_multiset` .|
|[const_iterator](#const_iterator)|İçindeki bir öğeyi okuyabilen çift yönlü bir yineleyici sağlayan bir tür **`const`** `hash_multiset` .|
|[const_pointer](#const_pointer)|İçindeki bir öğeye işaretçi sağlayan bir tür **`const`** `hash_multiset` .|
|[const_reference](#const_reference)|**`const`** `hash_multiset` İşlem okumak ve gerçekleştirmek için içinde depolanan bir öğeye başvuru sağlayan bir tür **`const`** .|
|[const_reverse_iterator](#const_reverse_iterator)|İçindeki herhangi bir öğeyi okuyabilen çift yönlü bir yineleyici sağlayan bir tür **`const`** `hash_multiset` .|
|[difference_type](#difference_type)|Aynı içindeki öğeleri ele alan iki yineleyiciler arasındaki farkı sağlayan işaretli bir tamsayı türü `hash_multiset` .|
|[iden](#iterator)|İçindeki herhangi bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleyici sağlayan bir tür `hash_multiset` .|
|[key_compare](#key_compare)|İçindeki iki öğenin göreli sırasını belirleyebilmek için iki sıralama anahtarını karşılaştırabilen bir işlev nesnesi sağlayan bir tür `hash_multiset` .|
|[key_type](#key_type)|Bir nesne olarak bir öğesi olarak depolanan bir nesneyi `hash_set` sıralama anahtarı olarak kapasitesinde tanımlayan bir tür.|
|[pointer](#pointer)|İçindeki bir öğeye işaretçi sağlayan bir tür `hash_multiset` .|
|[başvurunun](#reference)|İçinde depolanan bir öğeye başvuru sağlayan bir tür `hash_multiset` .|
|[reverse_iterator](#reverse_iterator)|Ters çevrilen bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleyici sağlayan bir tür `hash_multiset` .|
|[size_type](#size_type)|İçindeki öğe sayısını temsil eden işaretsiz bir tamsayı türü `hash_multiset` .|
|[value_compare](#value_compare)|İki işlev nesnesi sağlayan bir tür, bir ' ın iki öğe değerini, `hash_multiset` göreli sırasını ve öğeleri karmalarını sağlayan birli bir koşulu tespit etmek üzere karşılaştırabilen bir sınıf karşılaştırması ikili koşulu.|
|[value_type](#value_type)|Değeri olarak kapasitesinin bir öğesi olarak depolanan bir nesneyi açıklayan tür `hash_multiset` .|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[başladı](#begin)|İçindeki ilk öğeyi ele alan bir yineleyici döndürür `hash_multiset` .|
|[cbegin](#cbegin)|İçindeki ilk öğeyi adresleyen bir const yineleyici döndürür `hash_multiset` .|
|[cend](#cend)|İçindeki son öğeden sonraki konumu ele alan bir const yineleyici döndürür `hash_multiset` .|
|[lediğiniz](#clear)|Tüm öğelerini siler `hash_multiset` .|
|[biriktirme](#count)|Bir `hash_multiset` anahtarı parametre belirtilen anahtarla eşleşen öğe sayısını döndürür|
|[crbegin](#crbegin)|Ters çevrilen ilk öğeyi adresleyen bir const yineleyici döndürür `hash_multiset` .|
|[crend](#crend)|Ters çevrilen son öğeden sonraki konumu ele alan bir const yineleyici döndürür `hash_multiset` .|
|[Emplace](#emplace)|İçinde oluşturulan bir öğesi ekler `hash_multiset` .|
|[emplace_hint](#emplace_hint)|Bir yerleştirme ipucuyla birlikte, içine oluşturulmuş bir öğe ekler `hash_multiset` .|
|[empty](#empty)|`hash_multiset`Boşsa, sınar.|
|[erer](#end)|İçindeki son öğeden sonra gelen konumu ele alan bir yineleyici döndürür `hash_multiset` .|
|[equal_range](#equal_range)|`hash_multiset`Belirtilen anahtardan daha büyük bir anahtarla ve anahtarından bir anahtarla `hash_multiset` eşit veya ondan daha büyük olan bir anahtarla ilk öğesine kadar yineleyicilerin bir çiftini döndürür.|
|[silme](#erase)|Belirtilen konumlardan bir öğeyi veya öğe aralığını kaldırır `hash_multiset` veya belirtilen bir anahtarla eşleşen öğeleri kaldırır.|
|[find](#find)|İçindeki bir öğenin `hash_multiset` belirtilen anahtara denk eşdeğeri olan konumunu ele alan bir yineleyici döndürür.|
|[get_allocator](#get_allocator)|`allocator`Oluşturmak için kullanılan nesnenin bir kopyasını döndürür `hash_multiset` .|
|[ekleyin](#insert)|İçine bir öğe veya öğe aralığı ekler `hash_multiset` .|
|[key_comp](#key_compare)|İçindeki anahtarları sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır `hash_multiset` .|
|[lower_bound](#lower_bound)|Bir yineleyiciyi, `hash_multiset` belirtilen anahtardan daha büyük veya ona eşit olan bir anahtarla birlikte içindeki ilk öğeye döndürür.|
|[max_size](#max_size)|Maksimum uzunluğunu döndürür `hash_multiset` .|
|[rbegin](#rbegin)|Ters çevrilen ilk öğeyi adresleyen bir yineleyici döndürür `hash_multiset` .|
|[rend](#rend)|Ters çevrilen son öğeden sonraki konumu ele alan bir yineleyici döndürür `hash_multiset` .|
|[boyutla](#size)|İçindeki öğelerin sayısını döndürür `hash_multiset` .|
|[Kur](#swap)|İki öğenin öğelerini değiş tokuş eder `hash_multiset` .|
|[upper_bound](#upper_bound)|Bir yineleyiciyi `hash_multiset` belirtilen anahtardan daha büyük veya ona eşit olan bir anahtarla ilk öğesine döndürür.|
|[value_comp](#value_comp)|Karma nitelikleri nesnesinin bir kopyasını alır ve içindeki öğe anahtar değerlerini sıralamak için kullanılır `hash_multiset` .|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[hash_multiset:: operator =](#op_eq)|Hash_multiset öğelerini başka bir hash_multiset kopyasıyla değiştirir.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<hash_set>

**Ad alanı:** stdext

## <a name="hash_multisetallocator_type"></a><a name="allocator_type"></a> hash_multiset:: allocator_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfıdır](../standard-library/unordered-multiset-class.md).

Hash_multiset nesnesinin ayırıcı sınıfını temsil eden bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::allocator_type allocator_type;
```

### <a name="example"></a>Örnek

Şunu kullanarak bir örnek için [get_allocator](#get_allocator) örneğine bakın `allocator_type`

## <a name="hash_multisetbegin"></a><a name="begin"></a> hash_multiset:: Begin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfıdır](../standard-library/unordered-multiset-class.md).

Hash_multiset ilk öğeyi ele alan bir yineleyici döndürür.

```cpp
const_iterator begin() const;

iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

Hash_multiset ilk öğeyi adresleyen çift yönlü yineleyici veya konum boş bir hash_multiset başarılı oluyor.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri `begin` öğesine atanırsa `const_iterator` , hash_multiset nesnesindeki öğeler değiştirilemez. Dönüş değeri `begin` bir öğesine atanırsa `iterator` , hash_multiset nesnesindeki öğeler değiştirilebilir.

### <a name="example"></a>Örnek

```cpp
// hash_multiset_begin.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hms1;
   hash_multiset <int>::iterator hms1_Iter;
   hash_multiset <int>::const_iterator hms1_cIter;

   hms1.insert( 1 );
   hms1.insert( 2 );
   hms1.insert( 3 );

   hms1_Iter = hms1.begin( );
   cout << "The first element of hms1 is " << *hms1_Iter << endl;

   hms1_Iter = hms1.begin( );
   hms1.erase( hms1_Iter );

   // The following 2 lines would err because the iterator is const
   // hms1_cIter = hms1.begin( );
   // hms1.erase( hms1_cIter );

   hms1_cIter = hms1.begin( );
   cout << "The first element of hms1 is now " << *hms1_cIter << endl;
}
```

```Output
The first element of hms1 is 1
The first element of hms1 is now 2
```

## <a name="hash_multisetcbegin"></a><a name="cbegin"></a> hash_multiset:: cbegin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfıdır](../standard-library/unordered-multiset-class.md).

Hash_multiset ilk öğeyi ele alan bir const yineleyici döndürür.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

[Hash_multiset](../standard-library/hash-multiset-class.md) ilk öğeyi adresleyen bir const çift yönlü yineleyici veya bir boş olan konum `hash_multiset` .

### <a name="remarks"></a>Açıklamalar

Dönüş değeri ile `cbegin` `hash_multiset` nesnedeki öğeler değiştirilemez.

### <a name="example"></a>Örnek

```cpp
// hash_multiset_cbegin.cpp
// compile with: /EHsc
#include <hash_multiset>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hs1;
   hash_multiset <int>::const_iterator hs1_cIter;

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

## <a name="hash_multisetcend"></a><a name="cend"></a> hash_multiset:: cend

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfıdır](../standard-library/unordered-multiset-class.md).

Hash_multiset son öğeden sonraki konumu ele alan bir const yineleyici döndürür.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir [hash_multiset](../standard-library/hash-multiset-class.md)son öğeden sonraki konumu ele alan bir const çift yönlü Yineleyici. `hash_multiset`Boşsa, `hash_multiset::cend == hash_multiset::begin` .

### <a name="remarks"></a>Açıklamalar

`cend` , bir yineleyicinin sonuna kadar ulaşılmadığını test etmek için kullanılır `hash_multiset` . Tarafından döndürülen değer `cend` başvurulmamalıdır.

### <a name="example"></a>Örnek

```cpp
// hash_multiset_cend.cpp
// compile with: /EHsc
#include <hash_multiset>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hs1;
   hash_multiset <int> :: const_iterator hs1_cIter;

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

## <a name="hash_multisetclear"></a><a name="clear"></a> hash_multiset:: Clear

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfıdır](../standard-library/unordered-multiset-class.md).

Hash_multiset tüm öğelerini siler.

```cpp
void clear();
```

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_multiset_clear.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hms1;

   hms1.insert( 1 );
   hms1.insert( 2 );

   cout << "The size of the hash_multiset is initially " << hms1.size( )
        << "." << endl;

   hms1.clear( );
   cout << "The size of the hash_multiset after clearing is "
        << hms1.size( ) << "." << endl;
}
```

```Output
The size of the hash_multiset is initially 2.
The size of the hash_multiset after clearing is 0.
```

## <a name="hash_multisetconst_iterator"></a><a name="const_iterator"></a> hash_multiset:: const_iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfıdır](../standard-library/unordered-multiset-class.md).

Hash_multiset bir öğeyi okuyabilen çift yönlü bir yineleyici sağlayan bir tür **`const`** .

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_iterator const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_iterator` , bir öğenin değerini değiştirmek için kullanılamaz.

### <a name="example"></a>Örnek

Bir [örnek için bkz](#begin) . using örneği `const_iterator` .

## <a name="hash_multisetconst_pointer"></a><a name="const_pointer"></a> hash_multiset:: const_pointer

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfıdır](../standard-library/unordered-multiset-class.md).

Hash_multiset bir öğeye işaretçi sağlayan bir tür **`const`** .

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::const_pointer const_pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_pointer` , bir öğenin değerini değiştirmek için kullanılamaz.

Çoğu durumda, bir hash_multiset nesnesindeki öğelere erişmek için bir [const_iterator](#const_iterator) kullanılmalıdır **`const`** .

## <a name="hash_multisetconst_reference"></a><a name="const_reference"></a> hash_multiset:: const_reference

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfıdır](../standard-library/unordered-multiset-class.md).

**`const`** İşlemleri okumak ve gerçekleştirmek için bir hash_multiset depolanan öğeye başvuru sağlayan bir tür **`const`** .

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::const_reference const_reference;
```

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_multiset_const_reference.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hms1;

   hms1.insert( 10 );
   hms1.insert( 20 );

   // Declare and initialize a const_reference &Ref1
   // to the 1st element
   const int &Ref1 = *hms1.begin( );

   cout << "The first element in the hash_multiset is "
        << Ref1 << "." << endl;

   // The following line would cause an error because the
   // const_reference cannot be used to modify the hash_multiset
   // Ref1 = Ref1 + 5;
}
```

```Output
The first element in the hash_multiset is 10.
```

## <a name="hash_multisetconst_reverse_iterator"></a><a name="const_reverse_iterator"></a> hash_multiset:: const_reverse_iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfıdır](../standard-library/unordered-multiset-class.md).

Hash_multiset herhangi bir öğeyi okuyabilen çift yönlü bir yineleyici sağlayan bir tür **`const`** .

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_reverse_iterator const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür, `const_reverse_iterator` bir öğenin değerini değiştiremez ve hash_multiset ters bir şekilde yinelemek için kullanılır.

### <a name="example"></a>Örnek

' In nasıl bildirilemeyeceğini ve kullanılacağına ilişkin bir örnek için bkz. [rend](#rend) için örneğe bakın `const_reverse_iterator` .

## <a name="hash_multisetcount"></a><a name="count"></a> hash_multiset:: Count

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfıdır](../standard-library/unordered-multiset-class.md).

Anahtarı parametre tarafından belirtilen anahtarla eşleşen bir hash_multiset öğe sayısını döndürür.

```cpp
size_type count(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*anahtar*\
Hash_multiset eşleştirilecek öğelerin anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Parametre belirtilen anahtarla hash_multiset öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Üye işlevi aşağıdaki aralıktaki öğelerin sayısını döndürür:

\[ lower_bound (*anahtar*), upper_bound (*anahtar*)).

### <a name="example"></a>Örnek

Aşağıdaki örnek hash_multiset:: Count üye işlevinin kullanımını gösterir.

```cpp
// hash_multiset_count.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
    using namespace std;
    using namespace stdext;
    hash_multiset<int> hms1;
    hash_multiset<int>::size_type i;

    hms1.insert(1);
    hms1.insert(1);

    // Keys do not need to be unique in hash_multiset,
    // so duplicates may exist.
    i = hms1.count(1);
    cout << "The number of elements in hms1 with a sort key of 1 is: "
         << i << "." << endl;

    i = hms1.count(2);
    cout << "The number of elements in hms1 with a sort key of 2 is: "
         << i << "." << endl;
}
```

```Output
The number of elements in hms1 with a sort key of 1 is: 2.
The number of elements in hms1 with a sort key of 2 is: 0.
```

## <a name="hash_multisetcrbegin"></a><a name="crbegin"></a> hash_multiset:: crbegin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfıdır](../standard-library/unordered-multiset-class.md).

Ters çevrilen hash_multiset ilk öğeyi adresleyen bir const yineleyici döndürür.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir [hash_multiset](../standard-library/hash-multiset-class.md) ilk öğeyi ele almak veya geri çevrilmede son öğenin ne olduğunu ele almak için bir const ters çift yönlü Yineleyici `hash_multiset` .

### <a name="remarks"></a>Açıklamalar

`crbegin` , ile bir ters ile kullanılır `hash_multiset` [hash_multiset:: Begin](#begin) , ile kullanılır `hash_multiset` .

Dönüş değeri ile `crbegin` `hash_multiset` nesne değiştirilemez.

`crbegin` , geriye doğru yinelemek için kullanılabilir `hash_multiset` .

### <a name="example"></a>Örnek

```cpp
// hash_multiset_crbegin.cpp
// compile with: /EHsc
#include <hash_multiset>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hs1;
   hash_multiset <int>::const_reverse_iterator hs1_crIter;

   hs1.insert( 10 );
   hs1.insert( 20 );
   hs1.insert( 30 );

   hs1_crIter = hs1.crbegin( );
   cout << "The first element in the reversed hash_multiset is "
        << *hs1_crIter << "." << endl;
}
```

```Output
The first element in the reversed hash_multiset is 30.
```

## <a name="hash_multisetcrend"></a><a name="crend"></a> hash_multiset:: crend

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfıdır](../standard-library/unordered-multiset-class.md).

Ters çevrilen hash_multiset son öğeden sonraki konumu ele alan bir const yineleyici döndürür.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir [hash_multiset](../standard-library/hash-multiset-class.md) (geri çevrilme içindeki ilk öğeden önce gelen konum) izleyen konumu ele alan bir sabit ters çift yönlü Yineleyici `hash_multiset` .

### <a name="remarks"></a>Açıklamalar

`crend` , bir ters ile birlikte kullanıldığında `hash_multiset` [hash_multiset:: End](#end) ile birlikte kullanılır `hash_multiset` .

Dönüş değeri ile `crend` `hash_multiset` nesne değiştirilemez.

`crend` ters bir yineleyicinin hash_multiset sonuna kadar ulaştığı konusunda test etmek için kullanılabilir.

### <a name="example"></a>Örnek

```cpp
// hash_multiset_crend.cpp
// compile with: /EHsc
#include <hash_multiset>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hs1;
   hash_multiset <int>::const_reverse_iterator hs1_crIter;

   hs1.insert( 10 );
   hs1.insert( 20 );
   hs1.insert( 30 );

   hs1_crIter = hs1.crend( );
   hs1_crIter--;
   cout << "The last element in the reversed hash_multiset is "
        << *hs1_crIter << "." << endl;
}
```

```Output
The last element in the reversed hash_multiset is 10.
```

## <a name="hash_multisetdifference_type"></a><a name="difference_type"></a> hash_multiset::d ifference_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfıdır](../standard-library/unordered-multiset-class.md).

Aynı hash_multiset içindeki öğeleri ele alan iki yineleyiciler arasındaki farkı sağlayan işaretli bir tamsayı türü.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

`difference_type`Kapsayıcının yineleyiciler aracılığıyla çıkartılacak veya artırılarak döndürülen türdür. , `difference_type` Genellikle yineleyiciler arasındaki [,) aralıktaki öğelerin sayısını temsil etmek için kullanılır ve öğesi tarafından işaret edilen öğe `first` `last` `first` `last` `first` ve dahil `last` olmak üzere öğe aralığı ile işaret eder.

`difference_type`Bir giriş yineleyicisinin gereksinimlerini karşılayan tüm yineleyiciler için kullanılabilir olsa da, küme gibi tersine çevrilebilir kapsayıcılar tarafından desteklenen çift yönlü yineleyicilerin sınıfını içeren tüm yineleyiciler için kullanılabilir olduğuna unutmayın. Yineleyiciler arasında çıkarma yalnızca vektör veya deque gibi bir rastgele erişim kapsayıcısı tarafından sunulan rastgele erişim yineleyiciler tarafından desteklenir.

### <a name="example"></a>Örnek

```cpp
// hash_multiset_diff_type.cpp
// compile with: /EHsc
#include <iostream>
#include <hash_set>
#include <algorithm>

int main( )
{
   using namespace std;
   using namespace stdext;

   hash_multiset <int> hms1;
   hash_multiset <int>::iterator hms1_Iter, hms1_bIter, hms1_eIter;

   hms1.insert( 20 );
   hms1.insert( 10 );

   // hash_multiset elements need not be unique
   hms1.insert( 20 );

   hms1_bIter = hms1.begin( );
   hms1_eIter = hms1.end( );

   hash_multiset <int>::difference_type   df_typ5, df_typ10,
        df_typ20;

   df_typ5 = count( hms1_bIter, hms1_eIter, 5 );
   df_typ10 = count( hms1_bIter, hms1_eIter, 10 );
   df_typ20 = count( hms1_bIter, hms1_eIter, 20 );

   // The keys & hence the elements of a hash_multiset
   // need not be unique and may occur multiple times
   cout << "The number '5' occurs " << df_typ5
        << " times in hash_multiset hms1.\n";
   cout << "The number '10' occurs " << df_typ10
        << " times in hash_multiset hms1.\n";
   cout << "The number '20' occurs " << df_typ20
        << " times in hash_multiset hms1.\n";

   // Count the number of elements in a hash_multiset
   hash_multiset <int>::difference_type  df_count = 0;
   hms1_Iter = hms1.begin( );
   while ( hms1_Iter != hms1_eIter)
   {
      df_count++;
      hms1_Iter++;
   }

   cout << "The number of elements in the hash_multiset hms1 is "
        << df_count << "." << endl;
}
```

```Output
The number '5' occurs 0 times in hash_multiset hms1.
The number '10' occurs 1 times in hash_multiset hms1.
The number '20' occurs 2 times in hash_multiset hms1.
The number of elements in the hash_multiset hms1 is 3.
```

## <a name="hash_multisetemplace"></a><a name="emplace"></a> hash_multiset:: emplace

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfıdır](../standard-library/unordered-multiset-class.md).

Bir hash_multiset içinde oluşturulmuş bir öğe ekler.

```cpp
template <class ValTy>
iterator insert(ValTy&& val);
```

### <a name="parameters"></a>Parametreler

*Acil*\
Zaten bu öğeyi veya daha genel bir öğeyi içermiyorsa, bu öğe için [hash_multiset](../standard-library/hash-multiset-class.md) eklenecek öğenin değeri, `hash_multiset` anahtarı equivalently sıralı bir öğe.

### <a name="return-value"></a>Dönüş Değeri

`emplace`Üye işlevi, yeni öğenin eklendiği konuma işaret eden bir yineleyici döndürür.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_multiset_emplace.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>
#include <string>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset<string> hms3;
   string str1("a");

   hms3.emplace(move(str1));
   cout << "After the emplace insertion, hms3 contains "
      << *hms3.begin() << "." << endl;
}
```

```Output
After the emplace insertion, hms3 contains a.
```

## <a name="hash_multisetemplace_hint"></a><a name="emplace_hint"></a> hash_multiset:: emplace_hint

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfıdır](../standard-library/unordered-multiset-class.md).

Yerleştirme ipucuyla birlikte hash_multiset oluşturulan bir öğe ekler.

```cpp
template <class ValTy>
iterator insert(
    const_iterator where,
    ValTy&& val);
```

### <a name="parameters"></a>Parametreler

*Acil*\
Zaten bu öğeyi veya daha genel bir öğeyi içermiyorsa, bu öğe için [hash_multiset](../standard-library/hash-multiset-class.md) eklenecek öğenin değeri, `hash_multiset` anahtarı equivalently sıralı bir öğe.

*olmadığı*\
Doğru ekleme noktasını aramaya başlamak için yer. (Ekleme noktası *nerede*olursa, ekleme noktası, logaritmik bir süre yerine, sabit zamanlı olarak bir araya gelebilir.)

### <a name="return-value"></a>Dönüş Değeri

[Hash_multiset:: emplace](#emplace) üye işlevi, yeni öğenin içine eklendiği konuma işaret eden bir yineleyici döndürür `hash_multiset` .

### <a name="remarks"></a>Açıklamalar

Ekleme noktası *nerede*olursa, ekleme noktası, logaritmik bir süre yerine, sabit zamanlı olarak ortaya çıkabilir.

### <a name="example"></a>Örnek

```cpp
// hash_multiset_emplace_hint.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>
#include <string>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset<string> hms1;
   string str1("a");

   hms1.insert(hms1.begin(), move(str1));
   cout << "After the emplace insertion, hms1 contains "
      << *hms1.begin() << "." << endl;
}
```

```Output
After the emplace insertion, hms1 contains a.
```

## <a name="hash_multisetempty"></a><a name="empty"></a> hash_multiset:: boş

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfıdır](../standard-library/unordered-multiset-class.md).

Hash_multiset boş ise sınar.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** hash_multiset boşsa; **`false`** hash_multiset boş değilse.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_multiset_empty.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hms1, hms2;
   hms1.insert ( 1 );

   if ( hms1.empty( ) )
      cout << "The hash_multiset hms1 is empty." << endl;
   else
      cout << "The hash_multiset hms1 is not empty." << endl;

   if ( hms2.empty( ) )
      cout << "The hash_multiset hms2 is empty." << endl;
   else
      cout << "The hash_multiset hms2 is not empty." << endl;
}
```

```Output
The hash_multiset hms1 is not empty.
The hash_multiset hms2 is empty.
```

## <a name="hash_multisetend"></a><a name="end"></a> hash_multiset:: End

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfıdır](../standard-library/unordered-multiset-class.md).

Hash_multiset son öğeden sonraki konumu ele alan bir yineleyici döndürür.

```cpp
const_iterator end() const;

iterator end();
```

### <a name="return-value"></a>Dönüş Değeri

Bir hash_multiset son öğeden sonraki konumu ele alan çift yönlü bir yineleyici. Hash_multiset boşsa, hash_multiset:: End = = hash_multiset:: BEGIN.

### <a name="remarks"></a>Açıklamalar

`end` , bir yineleyicinin hash_multiset sonuna kadar ulaşılıp ulaşmadığını test etmek için kullanılır. Tarafından döndürülen değer `end` başvurulmamalıdır.

### <a name="example"></a>Örnek

```cpp
// hash_multiset_end.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hms1;
   hash_multiset <int> :: iterator hms1_Iter;
   hash_multiset <int> :: const_iterator hms1_cIter;

   hms1.insert( 1 );
   hms1.insert( 2 );
   hms1.insert( 3 );

   hms1_Iter = hms1.end( );
   hms1_Iter--;
   cout << "The last element of hms1 is " << *hms1_Iter << endl;

   hms1.erase( hms1_Iter );

   // The following 3 lines would err because the iterator is const
   // hms1_cIter = hms1.end( );
   // hms1_cIter--;
   // hms1.erase( hms1_cIter );

   hms1_cIter = hms1.end( );
   hms1_cIter--;
   cout << "The last element of hms1 is now " << *hms1_cIter << endl;
}
```

```Output
The last element of hms1 is 3
The last element of hms1 is now 2
```

## <a name="hash_multisetequal_range"></a><a name="equal_range"></a> hash_multiset:: equal_range

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfıdır](../standard-library/unordered-multiset-class.md).

Belirtilen anahtardan daha büyük bir anahtarla ve anahtardan daha büyük veya ona eşit olan bir anahtarla hash_multiset ilk öğe olan bir hash_multiset yineleyicilerin bir çiftini döndürür.

```cpp
pair <const_iterator, const_iterator> equal_range (const Key& key) const;

pair <iterator, iterator> equal_range (const Key& key);
```

### <a name="parameters"></a>Parametreler

*anahtar*\
Aranan hash_multiset öğenin sıralama anahtarıyla Karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

İlk anahtarın [lower_bound](#lower_bound) ve ikincisi anahtarın [upper_bound](#upper_bound) olduğu yineleyiciler çifti.

Üye işlevi tarafından döndürülen bir çiftin ilk Yineleyici öğesine erişmek için `pr` kullanın `pr` . **ilk** olarak, alt sınır Yineleyici için başvuru yapmak üzere \* ( `pr` . **ilk**). Üye işlevi tarafından döndürülen bir çiftin ikinci Yineleyici öğesine erişmek için `pr` kullanın `pr` . **ikincisi** ve üst sınır yineleyicisini başvuru yapmak için \* ( `pr` . **ikinci**).

### <a name="example"></a>Örnek

```cpp
// hash_multiset_equal_range.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   typedef hash_multiset<int> IntHSet;
   IntHSet hms1;
   hash_multiset <int> :: const_iterator hms1_RcIter;

   hms1.insert( 10 );
   hms1.insert( 20 );
   hms1.insert( 30 );

   pair <IntHSet::const_iterator, IntHSet::const_iterator> p1, p2;
   p1 = hms1.equal_range( 20 );

   cout << "The upper bound of the element with "
        << "a key of 20\nin the hash_multiset hms1 is: "
        << *(p1.second) << "." << endl;

   cout << "The lower bound of the element with "
        << "a key of 20\nin the hash_multiset hms1 is: "
        << *(p1.first) << "." << endl;

   // Compare the upper_bound called directly
   hms1_RcIter = hms1.upper_bound( 20 );
   cout << "A direct call of upper_bound( 20 ) gives "
        << *hms1_RcIter << "," << endl
        << "matching the 2nd element of the pair"
        << " returned by equal_range( 20 )." << endl;

   p2 = hms1.equal_range( 40 );

   // If no match is found for the key,
   // both elements of the pair return end( )
   if ( ( p2.first == hms1.end( ) )
      && ( p2.second == hms1.end( ) ) )
      cout << "The hash_multiset hms1 doesn't have an element "
           << "with a key less than 40." << endl;
   else
      cout << "The element of hash_multiset hms1"
           << "with a key >= 40 is: "
           << *(p1.first) << "." << endl;
}
```

```Output
The upper bound of the element with a key of 20
in the hash_multiset hms1 is: 30.
The lower bound of the element with a key of 20
in the hash_multiset hms1 is: 20.
A direct call of upper_bound( 20 ) gives 30,
matching the 2nd element of the pair returned by equal_range( 20 ).
The hash_multiset hms1 doesn't have an element with a key less than 40.
```

## <a name="hash_multiseterase"></a><a name="erase"></a> hash_multiset:: Erase

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfıdır](../standard-library/unordered-multiset-class.md).

Belirtilen konumlardan bir hash_multiset öğeyi veya öğe aralığını kaldırır veya belirtilen bir anahtarla eşleşen öğeleri kaldırır.

```cpp
iterator erase(iterator where);

iterator erase(iterator first, iterator last);

size_type erase(const key_type& key);
```

### <a name="parameters"></a>Parametreler

*olmadığı*\
Hash_multiset kaldırılacak öğenin konumu.

*adı*\
Hash_multiset kaldırılan ilk öğenin konumu.

*soyadına*\
Hash_multiset kaldırılan son öğenin hemen ötesinde konumlandır.

*anahtar*\
Hash_multiset kaldırılacak öğelerin anahtarı.

### <a name="return-value"></a>Dönüş Değeri

İlk iki üye işlevi için, kaldırılan öğelerin dışında kalan ilk öğeyi veya böyle bir öğe yoksa hash_multiset sonuna işaretçiyi atayan çift yönlü bir yineleyici. Üçüncü üye işlevi için, hash_multiset kaldırılan öğelerin sayısı.

### <a name="remarks"></a>Açıklamalar

Üye işlevleri hiçbir şekilde özel durum oluşturmaz.

### <a name="example"></a>Örnek

Aşağıdaki örnek hash_multiset:: Erase üye işlevinin kullanımını gösterir.

```cpp
// hash_multiset_erase.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main()
{
    using namespace std;
    using namespace stdext;
    hash_multiset<int> hms1, hms2, hms3;
    hash_multiset<int> :: iterator pIter, Iter1, Iter2;
    int i;
    hash_multiset<int>::size_type n;

    for (i = 1; i < 5; i++)
    {
        hms1.insert(i);
        hms2.insert(i * i);
        hms3.insert(i - 1);
    }

    // The 1st member function removes an element at a given position
    Iter1 = ++hms1.begin();
    hms1.erase(Iter1);

    cout << "After the 2nd element is deleted,\n"
         << "the hash_multiset hms1 is:" ;
    for (pIter = hms1.begin(); pIter != hms1.end(); pIter++)
        cout << " " << *pIter;
    cout << "." << endl;

    // The 2nd member function removes elements
    // in the range [ first,  last)
    Iter1 = ++hms2.begin();
    Iter2 = --hms2.end();
    hms2.erase(Iter1, Iter2);

    cout << "After the middle two elements are deleted,\n"
         << "the hash_multiset hms2 is:" ;
    for (pIter = hms2.begin(); pIter != hms2.end(); pIter++)
        cout << " " << *pIter;
    cout << "." << endl;

    // The 3rd member function removes elements with a given  key
    n = hms3.erase(2);

    cout << "After the element with a key of 2 is deleted,\n"
         << "the hash_multiset hms3 is:" ;
    for (pIter = hms3.begin(); pIter != hms3.end(); pIter++)
        cout << " " << *pIter;
    cout << "." << endl;

    // The 3rd member function returns the number of elements removed
    cout << "The number of elements removed from hms3 is: "
         << n << "." << endl;

    // The dereferenced iterator can also be used to specify a key
    Iter1 = ++hms3.begin();
    hms3.erase(Iter1);

    cout << "After another element with a key "
         << "equal to that of the 2nd element\n"
         << "is deleted, the hash_multiset hms3 is:" ;
    for (pIter = hms3.begin(); pIter != hms3.end(); pIter++)
        cout << " " << *pIter;
    cout << "." << endl;
}
```

```Output
After the 2nd element is deleted,
the hash_multiset hms1 is: 1 3 4.
After the middle two elements are deleted,
the hash_multiset hms2 is: 16 4.
After the element with a key of 2 is deleted,
the hash_multiset hms3 is: 0 1 3.
The number of elements removed from hms3 is: 1.
After another element with a key equal to that of the 2nd element
is deleted, the hash_multiset hms3 is: 0 3.
```

## <a name="hash_multisetfind"></a><a name="find"></a> hash_multiset:: Find

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfıdır](../standard-library/unordered-multiset-class.md).

Belirtilen anahtara eşdeğer bir anahtara sahip bir hash_multiset öğenin konumunu ele alan bir yineleyici döndürür.

```cpp
iterator find(const Key& key);

const_iterator find(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*anahtar*\
Aranan hash_multiset öğenin sıralama anahtarıyla eşleştirilecek bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Anahtar için eşleşme bulunmazsa, bir öğenin belirtilen anahtara denk veya hash_multiset son öğeden geçen konumu ele alan bir [Yineleyici](#iterator) veya [const_iterator](#const_iterator) .

### <a name="remarks"></a>Açıklamalar

Üye işlevi, sıralama anahtarı, `equivalent` daha az karşılaştırılır ilişkisini temel alan bir sıralamayı karşılayan bir ikili koşulda bağımsız değişken anahtarına olan hash_multiset bir öğeyi ele alan bir yineleyici döndürür.

Dönüş değeri `find` bir öğesine atanırsa `const_iterator` , hash_multiset nesnesi değiştirilemez. Dönüş değeri `find` bir öğesine atanırsa `iterator` , hash_multiset nesnesi değiştirilebilir.

### <a name="example"></a>Örnek

```cpp
// hash_multiset_find.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hms1;
   hash_multiset <int> :: const_iterator hms1_AcIter, hms1_RcIter;

   hms1.insert( 10 );
   hms1.insert( 20 );
   hms1.insert( 30 );

   hms1_RcIter = hms1.find( 20 );
   cout << "The element of hash_multiset hms1 with a key of 20 is: "
        << *hms1_RcIter << "." << endl;

   hms1_RcIter = hms1.find( 40 );

   // If no match is found for the key, end( ) is returned
   if ( hms1_RcIter == hms1.end( ) )
      cout << "The hash_multiset hms1 doesn't have an element "
           << "with a key of 40." << endl;
   else
      cout << "The element of hash_multiset hms1 with a key of 40 is: "
           << *hms1_RcIter << "." << endl;

   // The element at a specific location in the hash_multiset can be found
   // by using a dereferenced iterator addressing the location
   hms1_AcIter = hms1.end( );
   hms1_AcIter--;
   hms1_RcIter = hms1.find( *hms1_AcIter );
   cout << "The element of hms1 with a key matching "
        << "that of the last element is: "
        << *hms1_RcIter << "." << endl;
}
```

```Output
The element of hash_multiset hms1 with a key of 20 is: 20.
The hash_multiset hms1 doesn't have an element with a key of 40.
The element of hms1 with a key matching that of the last element is: 30.
```

## <a name="hash_multisetget_allocator"></a><a name="get_allocator"></a> hash_multiset:: get_allocator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfıdır](../standard-library/unordered-multiset-class.md).

Hash_multiset oluşturmak için kullanılan ayırıcı nesnesinin bir kopyasını döndürür.

```cpp
Allocator get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sınıfın şablon parametresi olan belleği yönetmek için hash_multiset tarafından kullanılan ayırıcı `Allocator` .

Hakkında daha fazla bilgi için `Allocator` [hash_multiset sınıfı](../standard-library/hash-multiset-class.md) konusunun açıklamalar bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

Hash_multiset sınıfı için ayrıcılar, sınıfın depolamayı nasıl yönettiğini belirtir. C++ standart kitaplığı kapsayıcı sınıflarıyla birlikte sağlanan varsayılan ayrıcılar çoğu programlama ihtiyacı için yeterlidir. Kendi ayırıcı sınıfınızı yazmak ve kullanmak, gelişmiş bir C++ konudur.

### <a name="example"></a>Örnek

```cpp
// hash_multiset_get_allocator.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;

   // The following lines declare objects
   // that use the default allocator.
   hash_multiset <int, hash_compare <int, less<int> > > hms1;
   hash_multiset <int, hash_compare <int, greater<int> > > hms2;
   hash_multiset <double, hash_compare <double,
      less<double> >, allocator<double> > hms3;

   hash_multiset <int, hash_compare <int,
      greater<int> > >::allocator_type hms2_Alloc;
   hash_multiset <double>::allocator_type hms3_Alloc;
   hms2_Alloc = hms2.get_allocator( );

   cout << "The number of integers that can be allocated"
        << endl << "before free memory is exhausted: "
        << hms1.max_size( ) << "." << endl;

   cout << "The number of doubles that can be allocated"
        << endl << "before free memory is exhausted: "
        << hms3.max_size( ) <<  "." << endl;

   // The following lines create a hash_multiset hms4
   // with the allocator of hash_multiset hms1.
   hash_multiset <int>::allocator_type hms4_Alloc;
   hash_multiset <int> hms4;
   hms4_Alloc = hms2.get_allocator( );

   // Two allocators are interchangeable if
   // storage allocated from each can be
   // deallocated by the other
   if( hms2_Alloc == hms4_Alloc )
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

## <a name="hash_multisethash_multiset"></a><a name="hash_multiset"></a> hash_multiset:: hash_multiset

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfıdır](../standard-library/unordered-multiset-class.md).

`hash_multiset`Boş olan veya bir kısmının tümünün veya bir kısmının kopyası olan oluşturur `hash_multiset` .

```cpp
hash_multiset();

explicit hash_multiset(
    const Traits& Comp);

hash_multiset(
    const Traits& Comp,
    const Allocator& Al);

hash_multiset(
    const hash_multiset<Key, Traits, Allocator>& Right);

hash_multiset(
    hash_multiset&& Right
};
hash_multiset (initializer_list<Type> IList);

hash_multiset(
    initializer_list<Tu[e> IList, const Compare& Comp):
hash_multiset(
    initializer_list<Type> IList, const Compare& Comp, const Allocator& Al);

template <class InputIterator>
hash_multiset(
    InputIterator first,
    InputIterator last);

template <class InputIterator>
hash_multiset(
    InputIterator first,
    InputIterator last,
    const Traits& Comp);

template <class InputIterator>
hash_multiset(
    InputIterator first,
    InputIterator last,
    const Traits& Comp,
    const Allocator& Al);
```

### <a name="parameters"></a>Parametreler

*Eşkenar*\
Varsayılan olarak, bu nesne için kullanılacak depolama ayırıcı sınıfı `hash_multiset` `Allocator` .

*İnin*\
`const Traits`' Deki öğeleri sıralamak için kullanılan tür karşılaştırma işlevi, `hash_multiset` Varsayılan olarak `hash_compare` .

*Right*\
`hash_multiset`Oluşturulan öğesinin `hash_multiset` bir kopyalama olduğu yer.

*adı*\
Kopyalanacak öğe aralığındaki ilk öğenin konumu.

*soyadına*\
Kopyalanacak öğe aralığının ötesinde ilk öğenin konumu.

*IList*\
Kopyalanacak öğeleri içeren initializer_list.

### <a name="remarks"></a>Açıklamalar

Tüm oluşturucular, `hash_multiset` ve daha sonra [hash_multiset:: get_allocator](#get_allocator)çağırarak döndürülebilecek bellek depolamayı yöneten bir tür ayırıcı nesnesi depolar. Ayırıcı parametresi, genellikle sınıf bildirimlerinde atlanır ve alternatif ayırıcıları değiştirmek için kullanılan ön işleme makrolarıyla sonuçlanır.

Tüm oluşturucular hash_multisets başlatır.

Tüm oluşturucular `Traits` , `hash_multiset` ve daha sonra [hash_multiset:: key_comp](#key_comp)çağırarak döndürülebilecek anahtarlar arasında bir sıra oluşturmak için kullanılan türünde bir işlev nesnesi depolar. Hakkında daha fazla bilgi için `Traits` [hash_multiset sınıfı](../standard-library/hash-multiset-class.md) konusuna bakın.

İlk üç Oluşturucu boş bir başlangıç belirtir `hash_multiset` , ikinci olarak öğelerin sırasını oluşturmak için kullanılacak karşılaştırma işlevi türünü (*comp*) ve kullanılacak ayırıcı türünü (*Al*) açıkça belirten üçüncü olarak belirtin. Anahtar sözcüğü **`explicit`** bazı otomatik tür dönüştürme türlerini bastırır.

Dördüncü Oluşturucu öğesini taşımaktır `hash_multiset` `Right` .

Beşinci, altıncı ve yedinci oluşturucular bir initializer_list kullanır.

Son üç Oluşturucu, `first` ' ın [,) aralığını, `last` `hash_multiset` sınıf karşılaştırmasının ve ayırıcısının karşılaştırma işlevinin türünü belirtirken açıkça artarak kopyalar.

Karma küme kapsayıcısındaki öğelerin gerçek sırası, karma işleve, sıralama işlevine ve karma tablonun geçerli boyutuna bağlıdır ve genellikle sıralama işlevi tarafından belirlendiği şekilde, küme kapsayıcısı ile ilgili olarak tahmin edilebilir.

## <a name="hash_multisetinsert"></a><a name="insert"></a> hash_multiset:: INSERT

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfıdır](../standard-library/unordered-multiset-class.md).

Bir hash_multiset öğe veya öğe aralığı ekler.

```cpp
iterator insert(
    const Type& value);

iterator insert(
    iterator where,
    const Type& Al);

void insert(
    initializer_list<Type> IList);

iterator insert(
    const Type& value);

iterator insert(
    Iterator where,
    const Type& value);

template <class InputIterator>
void insert(
    InputIterator first,
    InputIterator last);

template <class ValTy>
iterator insert(
    ValTy&& value);

template <class ValTy>
iterator insert(
    const_iterator where,
    ValTy&& value);
```

### <a name="parameters"></a>Parametreler

*deeri*\
Hash_multiset zaten bu öğeyi veya daha genel bir öğeyi içermiyorsa, bu öğe hash_multiset Eklenecek öğenin değeri.

*olmadığı*\
Doğru ekleme noktasını aramaya başlamak için yer. (Ekleme noktası *nerede*olursa, ekleme noktası, logaritmik bir süre yerine, sabit zamanlı olarak bir araya gelebilir.)

*adı*\
Hash_multiset kopyalanacak ilk öğenin konumu.

*soyadına*\
Hash_multiset kopyalanacak son öğenin hemen ötesinde konum.

*IList*\
Kopyalanacak öğeleri içeren initializer_list.

### <a name="return-value"></a>Dönüş Değeri

İlk iki INSERT member işlevi, yeni öğenin eklendiği konuma işaret eden bir yineleyici döndürür.

Sonraki üç üye işlevi bir initializer_list kullanır.

Üçüncü üye işlevi, öğe değerlerinin dizisini belirtilen bir hash_multiset [,) aralığında bir yineleyici tarafından bahsedilen her öğeye karşılık gelen bir hash_multiset ekler `first` `last` .

### <a name="remarks"></a>Açıklamalar

Ekleme noktası *nerede*olursa, ekleme noktası, Logaritmik süre yerine, ekleme işleminin ipucu sürümü için sabit zamanlı olarak ekleme yapılabilir.

## <a name="hash_multisetiterator"></a><a name="iterator"></a> hash_multiset:: Yineleyici

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfıdır](../standard-library/unordered-multiset-class.md).

Bir hash_multiset herhangi bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleyici sağlayan bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::iterator iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir türü `iterator` , bir öğenin değerini değiştirmek için kullanılabilir.

### <a name="example"></a>Örnek

Bildirme ve kullanma hakkında bir örnek için bkz. [Başlangıç](#begin) örneği `iterator` .

## <a name="hash_multisetkey_comp"></a><a name="key_comp"></a> hash_multiset:: key_comp

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfıdır](../standard-library/unordered-multiset-class.md).

Hash_multiset anahtarları sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır.

```cpp
key_compare key_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Karma ve kapsayıcının öğelerini sıralamak için kullanılan işlev nesnelerini içeren hash_multiset şablon parametresi *nitelikleri*döndürür.

*Nitelikler* hakkında daha fazla bilgi Için [hash_multiset sınıfı](../standard-library/hash-multiset-class.md) konusuna bakın.

### <a name="remarks"></a>Açıklamalar

Saklı nesne bir üye işlevi tanımlar:

`bool operator<(const Key& _xVal, const Key& _yVal);`

Bu, **`true`** `_xVal` önceki ve sıralama düzeninde eşit değilse döndürür `_yVal` .

Hem [key_compare](#key_compare) hem de [value_compare](#value_compare) şablon parametresi *nitelikleri*için eş anlamlı olduğunu unutmayın. Her iki tür de hash_multiset ve hash_multiset sınıfları için sağlanır ve bunlar birbirinden farklı oldukları hash_map ve hash_multimap sınıflarıyla uyumluluk içindir.

### <a name="example"></a>Örnek

```cpp
// hash_multiset_key_comp.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;

   hash_multiset <int, hash_compare < int, less<int> > >hms1;
   hash_multiset<int, hash_compare < int, less<int> > >::key_compare kc1
          = hms1.key_comp( ) ;
   bool result1 = kc1( 2, 3 ) ;
   if( result1 == true )
   {
      cout << "kc1( 2,3 ) returns value of true, "
           << "where kc1 is the function object of hms1."
           << endl;
   }
   else
   {
      cout << "kc1( 2,3 ) returns value of false "
           << "where kc1 is the function object of hms1."
        << endl;
   }

   hash_multiset <int, hash_compare < int, greater<int> > > hms2;
   hash_multiset<int, hash_compare < int, greater<int> > >::key_compare
         kc2 = hms2.key_comp( ) ;
   bool result2 = kc2( 2, 3 ) ;
   if( result2 == true )
   {
      cout << "kc2( 2,3 ) returns value of true, "
           << "where kc2 is the function object of hms2."
           << endl;
   }
   else
   {
      cout << "kc2( 2,3 ) returns value of false, "
           << "where kc2 is the function object of hms2."
           << endl;
   }
}
```

## <a name="hash_multisetkey_compare"></a><a name="key_compare"></a> hash_multiset:: key_compare

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfıdır](../standard-library/unordered-multiset-class.md).

İki işlev nesnesi sağlayan bir tür, bir hash_multiset iki öğe değerini karşılaştırabilir ve öğelerin karma oluşturan birli bir koşulu tespit edebilir.

```cpp
typedef Traits key_compare;
```

### <a name="remarks"></a>Açıklamalar

`key_compare` , şablon parametresi *nitelikleri*için bir eş anlamlı.

*Nitelikler* hakkında daha fazla bilgi Için [hash_multiset sınıfı](../standard-library/hash-multiset-class.md) konusuna bakın.

Hem hem de `key_compare` value_compare şablon parametresi *nitelikleri*için eş anlamlı olduğunu unutmayın. Her iki tür de hash_set ve hash_multiset sınıfları için sağlanır ve bunlar birbirinden farklı oldukları hash_map ve hash_multimap sınıflarıyla uyumluluk içindir.

### <a name="example"></a>Örnek

Bildirme ve kullanma hakkında bir örnek için bkz. [key_comp](#key_comp) örneği `key_compare` .

## <a name="hash_multisetkey_type"></a><a name="key_type"></a> hash_multiset:: key_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfıdır](../standard-library/unordered-multiset-class.md).

Hash_multiset iki öğenin göreli sırasını belirlemede sıralama anahtarlarını karşılaştırabilen bir işlev nesnesi sağlayan bir tür.

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Açıklamalar

`key_type` , şablon parametre *anahtarı*için bir eş anlamlı.

Hem hem de `key_type` [value_type](../standard-library/hash-set-class.md#value_type) şablon parametresi *anahtarı*için eş anlamlı olduğunu unutmayın. Her iki tür de, farklı oldukları, eşleme ve multimap sınıfları ile uyumluluk için, aynı oldukları küme ve çoklu küme sınıfları için sağlanır.

*Anahtar*hakkında daha fazla bilgi Için [hash_multiset sınıfı](../standard-library/hash-multiset-class.md) konusunun açıklamalar bölümüne bakın.

### <a name="example"></a>Örnek

Bildirme ve kullanma hakkında bir örnek için bkz. [value_type](#value_type) örneği `key_type` .

## <a name="hash_multisetlower_bound"></a><a name="lower_bound"></a> hash_multiset:: lower_bound

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfıdır](../standard-library/unordered-multiset-class.md).

Bir yineleyiciyi belirtilen anahtardan daha büyük veya ona eşit bir anahtarla bir hash_multiset ilk öğeye döndürür.

```cpp
const_iterator lower_bound(const Key& key) const;

iterator lower_bound(const Key& key);
```

### <a name="parameters"></a>Parametreler

*anahtar*\
Aranan hash_multiset öğenin sıralama anahtarıyla Karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişken anahtarına eşit veya ondan daha büyük olan bir anahtarla bir hash_multiset ilk öğenin konumunu adresleyen veya anahtar için eşleşme bulunmazsa hash_multiset son öğeden sonraki konumu ele alan bir [Yineleyici](#iterator) veya [const_iterator](#const_iterator) .

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_multiset_lower_bound.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main() {
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hms1;
   hash_multiset <int> :: const_iterator hms1_AcIter, hms1_RcIter;

   hms1.insert( 10 );
   hms1.insert( 20 );
   hms1.insert( 30 );

   hms1_RcIter = hms1.lower_bound( 20 );
   cout << "The element of hash_multiset hms1 with a key of 20 is: "
        << *hms1_RcIter << "." << endl;

   hms1_RcIter = hms1.lower_bound( 40 );

   // If no match is found for the key, end( ) is returned
   if ( hms1_RcIter == hms1.end( ) )
      cout << "The hash_multiset hms1 doesn't have an element "
           << "with a key of 40." << endl;
   else
      cout << "The element of hash_multiset hms1 with a key of 40 is: "
           << *hms1_RcIter << "." << endl;

   // An element at a specific location in the hash_multiset can be found
   // by using a dereferenced iterator that addresses the location
   hms1_AcIter = hms1.end( );
   hms1_AcIter--;
   hms1_RcIter = hms1.lower_bound( *hms1_AcIter );
   cout << "The element of hms1 with a key matching "
        << "that of the last element is: "
        << *hms1_RcIter << "." << endl;
}
```

## <a name="hash_multisetmax_size"></a><a name="max_size"></a> hash_multiset:: max_size

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfıdır](../standard-library/unordered-multiset-class.md).

Hash_multiset maksimum uzunluğunu döndürür.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Hash_multiset olabilecek en uzun uzunluk.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_multiset_max_size.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hms1;
   hash_multiset <int>::size_type i;

   i = hms1.max_size( );
   cout << "The maximum possible length "
        << "of the hash_multiset is " << i << "." << endl;
}
```

## <a name="hash_multisetoperator"></a><a name="op_eq"></a> hash_multiset:: operator =

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfıdır](../standard-library/unordered-multiset-class.md).

Hash_multiset öğelerini başka bir hash_multiset kopyasıyla değiştirir.

```cpp
hash_multiset& operator=(const hash_multiset& right);

hash_multiset& operator=(hash_multiset&& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
İçine kopyalandığı [hash_multiset](../standard-library/hash-multiset-class.md) `hash_multiset` .

### <a name="remarks"></a>Açıklamalar

İçindeki varolan öğeleri sildikten sonra `hash_multiset` , ' `operator=` nin içeriğini kopyalar ya da içine *taşısa* `hash_multiset` .

### <a name="example"></a>Örnek

```cpp
// hash_multiset_operator_as.cpp
// compile with: /EHsc
#include <hash_multiset>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset<int> v1, v2, v3;
   hash_multiset<int>::iterator iter;

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

## <a name="hash_multisetpointer"></a><a name="pointer"></a> hash_multiset::p oınter

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfıdır](../standard-library/unordered-multiset-class.md).

Hash_multiset bir öğeye işaretçi sağlayan bir tür.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir türü `pointer` , bir öğenin değerini değiştirmek için kullanılabilir.

Çoğu durumda, bir [Yineleyici](#iterator) bir çoklu küme nesnesindeki öğelere erişmek için kullanılmalıdır.

## <a name="hash_multisetrbegin"></a><a name="rbegin"></a> hash_multiset:: rbegin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfıdır](../standard-library/unordered-multiset-class.md).

Ters çevrilen hash_multiset ilk öğeyi adresleyen bir yineleyici döndürür.

```cpp
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir hash_multiset ilk öğeyi ele almak veya geri alınamaz hash_multiset son öğe olduğunu ele almak için ters çift yönlü Yineleyici.

### <a name="remarks"></a>Açıklamalar

`rbegin` , [Başlangıç](#begin) olarak bir hash_multiset ile birlikte kullanılan bir ters hash_multiset ile kullanılır.

Öğesinin dönüş değeri `rbegin` öğesine atanmışsa `const_reverse_iterator` , hash_multiset nesnesi değiştirilemez. Dönüş değeri `rbegin` bir öğesine atanırsa `reverse_iterator` , hash_multiset nesnesi değiştirilebilir.

`rbegin` , bir hash_multiset geriye doğru yinelemek için kullanılabilir.

### <a name="example"></a>Örnek

```cpp
// hash_multiset_rbegin.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hms1;
   hash_multiset <int>::iterator hms1_Iter;
   hash_multiset <int>::reverse_iterator hms1_rIter;

   hms1.insert( 10 );
   hms1.insert( 20 );
   hms1.insert( 30 );

   hms1_rIter = hms1.rbegin( );
   cout << "The first element in the reversed hash_multiset is "
        << *hms1_rIter << "." << endl;

   // begin can be used to start an iteration
   // through a hash_multiset in a forward order
   cout << "The hash_multiset is: ";
   for ( hms1_Iter = hms1.begin( ) ; hms1_Iter != hms1.end( );
         hms1_Iter++ )
      cout << *hms1_Iter << " ";
   cout << endl;

   // rbegin can be used to start an iteration
   // through a hash_multiset in a reverse order
   cout << "The reversed hash_multiset is: ";
   for ( hms1_rIter = hms1.rbegin( ) ; hms1_rIter != hms1.rend( );
         hms1_rIter++ )
      cout << *hms1_rIter << " ";
   cout << endl;

   // A hash_multiset element can be erased by dereferencing to its key
   hms1_rIter = hms1.rbegin( );
   hms1.erase ( *hms1_rIter );

   hms1_rIter = hms1.rbegin( );
   cout << "After the erasure, the first element "
        << "in the reversed hash_multiset is "<< *hms1_rIter << "."
        << endl;
}
```

```Output
The first element in the reversed hash_multiset is 30.
The hash_multiset is: 10 20 30
The reversed hash_multiset is: 30 20 10
After the erasure, the first element in the reversed hash_multiset is 20.
```

## <a name="hash_multisetreference"></a><a name="reference"></a> hash_multiset:: Reference

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfıdır](../standard-library/unordered-multiset-class.md).

Hash_multiset depolanan bir öğeye başvuru sağlayan bir tür.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::reference reference;
```

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_multiset_reference.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hms1;

   hms1.insert( 10 );
   hms1.insert( 20 );

   // Declare and initialize a reference &Ref1 to the 1st element
   int &Ref1 = *hms1.begin( );

   cout << "The first element in the hash_multiset is "
        << Ref1 << "." << endl;

   // The value of the 1st element of the hash_multiset can be
   // changed by operating on its (non const) reference
   Ref1 = Ref1 + 5;

   cout << "The first element in the hash_multiset is now "
        << *hms1.begin() << "." << endl;
}
```

```Output
The first element in the hash_multiset is 10.
The first element in the hash_multiset is now 15.
```

## <a name="hash_multisetrend"></a><a name="rend"></a> hash_multiset:: rend

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfıdır](../standard-library/unordered-multiset-class.md).

Ters çevrilen hash_multiset son öğeden sonraki konumu ele alan bir yineleyici döndürür.

```cpp
const_reverse_iterator rend() const;

reverse_iterator rend();
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir hash_multiset en son öğeden sonra gelen konumu ele alan ters çift yönlü yineleyici (geri alınamaz hash_multiset ilk öğeden önce gelen konum).

### <a name="remarks"></a>Açıklamalar

`rend` , [End](#end) bir hash_multiset ile kullanıldığı gibi ters bir hash_multiset kullanılır.

Öğesinin dönüş değeri `rend` öğesine atanmışsa `const_reverse_iterator` , hash_multiset nesnesi değiştirilemez. Dönüş değeri `rend` bir öğesine atanırsa `reverse_iterator` , hash_multiset nesnesi değiştirilebilir. Tarafından döndürülen değer `rend` başvurulmamalıdır.

`rend` ters bir yineleyicinin hash_multiset sonuna kadar ulaştığı konusunda test etmek için kullanılabilir.

### <a name="example"></a>Örnek

```cpp
// hash_multiset_rend.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hms1;
   hash_multiset <int>::iterator hms1_Iter;
   hash_multiset <int>::reverse_iterator hms1_rIter;
   hash_multiset <int>::const_reverse_iterator hms1_crIter;

   hms1.insert( 10 );
   hms1.insert( 20 );
   hms1.insert( 30 );

   hms1_rIter = hms1.rend( );
   hms1_rIter--;
   cout << "The last element in the reversed hash_multiset is "
        << *hms1_rIter << "." << endl;

   // end can be used to terminate an iteration
   // through a hash_multiset in a forward order
   cout << "The hash_multiset is: ";
   for ( hms1_Iter = hms1.begin( ) ; hms1_Iter != hms1.end( );
         hms1_Iter++ )
      cout << *hms1_Iter << " ";
   cout << "." << endl;

   // rend can be used to terminate an iteration
   // through a hash_multiset in a reverse order
   cout << "The reversed hash_multiset is: ";
   for ( hms1_rIter = hms1.rbegin( ) ; hms1_rIter != hms1.rend( );
         hms1_rIter++ )
      cout << *hms1_rIter << " ";
   cout << "." << endl;

   hms1_rIter = hms1.rend( );
   hms1_rIter--;
   hms1.erase ( *hms1_rIter );

   hms1_rIter = hms1.rend( );
   hms1_rIter--;
   cout << "After the erasure, the last element in the "
        << "reversed hash_multiset is " << *hms1_rIter << "."
        << endl;
}
```

```Output
The last element in the reversed hash_multiset is 10.
The hash_multiset is: 10 20 30 .
The reversed hash_multiset is: 30 20 10 .
After the erasure, the last element in the reversed hash_multiset is 20.
```

## <a name="hash_multisetreverse_iterator"></a><a name="reverse_iterator"></a> hash_multiset:: reverse_iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfıdır](../standard-library/unordered-multiset-class.md).

Ters çevrilen bir hash_multiset bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleyici sağlayan bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::reverse_iterator reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `reverse_iterator` , ters içinde hash_multiset yinelemek için kullanılır.

### <a name="example"></a>Örnek

Bildirme ve kullanma hakkında bir örnek için bkz. [rbegin](#rbegin) örneği `reverse_iterator` .

## <a name="hash_multisetsize"></a><a name="size"></a> hash_multiset:: size

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfıdır](../standard-library/unordered-multiset-class.md).

Hash_multiset öğe sayısını döndürür.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Hash_multiset geçerli uzunluğu.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_multiset_size.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hms1;
   hash_multiset <int> :: size_type i;

   hms1.insert( 1 );
   i = hms1.size( );
   cout << "The hash_multiset length is " << i << "." << endl;

   hms1.insert( 2 );
   i = hms1.size( );
   cout << "The hash_multiset length is now " << i << "." << endl;
}
```

```Output
The hash_multiset length is 1.
The hash_multiset length is now 2.
```

## <a name="hash_multisetsize_type"></a><a name="size_type"></a> hash_multiset:: size_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfıdır](../standard-library/unordered-multiset-class.md).

Bir hash_multiset öğe sayısını temsil eden işaretsiz bir tamsayı türü.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::size_type size_type;
```

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

Bildirme ve kullanma hakkında bir [örnek için bkz](#size) . örnek `size_type`

## <a name="hash_multisetswap"></a><a name="swap"></a> hash_multiset:: swap

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfıdır](../standard-library/unordered-multiset-class.md).

İki hash_multisets öğelerini değiş tokuş eder.

```cpp
void swap(hash_multiset& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Bağımsız değişkeni, hedef hash_multiset birlikte takas edilecek öğeleri sağlayan hash_multiset.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, öğeleri takas edilmekte olan iki hash_multisets öğeleri belirten başvuruları, işaretçileri veya yineleyicileri geçersiz kılar.

### <a name="example"></a>Örnek

```cpp
// hash_multiset_swap.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hms1, hms2, hms3;
   hash_multiset <int>::iterator hms1_Iter;

   hms1.insert( 10 );
   hms1.insert( 20 );
   hms1.insert( 30 );
   hms2.insert( 100 );
   hms2.insert( 200 );
   hms3.insert( 300 );

   cout << "The original hash_multiset hms1 is:";
   for ( hms1_Iter = hms1.begin( ); hms1_Iter != hms1.end( );
         hms1_Iter++ )
         cout << " " << *hms1_Iter;
   cout   << "." << endl;

   // This is the member function version of swap
   hms1.swap( hms2 );

   cout << "After swapping with hms2, list hms1 is:";
   for ( hms1_Iter = hms1.begin( ); hms1_Iter != hms1.end( );
         hms1_Iter++ )
         cout << " " << *hms1_Iter;
   cout  << "." << endl;

   // This is the specialized template version of swap
   swap( hms1, hms3 );

   cout << "After swapping with hms3, list hms1 is:";
   for ( hms1_Iter = hms1.begin( ); hms1_Iter != hms1.end( );
         hms1_Iter++ )
         cout << " " << *hms1_Iter;
   cout   << "." << endl;
}
```

```Output
The original hash_multiset hms1 is: 10 20 30.
After swapping with hms2, list hms1 is: 200 100.
After swapping with hms3, list hms1 is: 300.
```

## <a name="hash_multisetupper_bound"></a><a name="upper_bound"></a> hash_multiset:: upper_bound

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfıdır](../standard-library/unordered-multiset-class.md).

Bir yineleyiciyi belirtilen anahtardan daha büyük bir anahtarla bir hash_multiset ilk öğeye döndürür.

```cpp
const_iterator upper_bound(const Key& key) const;

iterator upper_bound(const Key& key);
```

### <a name="parameters"></a>Parametreler

*anahtar*\
Aranan hash_multiset öğenin sıralama anahtarıyla Karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişken anahtarından daha büyük bir anahtarla bir hash_multiset ilk öğenin konumunu adresleyen veya anahtar için eşleşme bulunmazsa hash_multiset son öğeden sonraki konumu ele alan bir [Yineleyici](#iterator) veya [const_iterator](#const_iterator) .

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_multiset_upper_bound.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hms1;
   hash_multiset <int> :: const_iterator hms1_AcIter, hms1_RcIter;

   hms1.insert( 10 );
   hms1.insert( 20 );
   hms1.insert( 30 );

   hms1_RcIter = hms1.upper_bound( 20 );
   cout << "The first element of hash_multiset hms1" << endl
        << "with a key greater than 20 is: "
        << *hms1_RcIter << "." << endl;

   hms1_RcIter = hms1.upper_bound( 30 );

   // If no match is found for the key, end( ) is returned
   if ( hms1_RcIter == hms1.end( ) )
      cout << "The hash_multiset hms1 doesn't have an element\n"
           << "with a key greater than 30." << endl;
   else
      cout << "The element of hash_multiset hms1"
           << "with a key > 40 is: "
           << *hms1_RcIter << "." << endl;

   // An element at a specific location in the hash_multiset can be
   // found by using a dereferenced iterator addressing the location
   hms1_AcIter = hms1.begin( );
   hms1_RcIter = hms1.upper_bound( *hms1_AcIter );
   cout << "The first element of hms1 with a key greater than "
        << endl << "that of the initial element of hms1 is: "
        << *hms1_RcIter << "." << endl;
}
```

```Output
The first element of hash_multiset hms1
with a key greater than 20 is: 30.
The hash_multiset hms1 doesn't have an element
with a key greater than 30.
The first element of hms1 with a key greater than
that of the initial element of hms1 is: 20.
```

## <a name="hash_multisetvalue_comp"></a><a name="value_comp"></a> hash_multiset:: value_comp

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfıdır](../standard-library/unordered-multiset-class.md).

Bir hash_multiset öğe değerlerini sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır.

```cpp
value_compare value_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Karma ve kapsayıcının öğelerini sıralamak için kullanılan işlev nesnelerini içeren hash_multiset şablon parametresi *nitelikleri*döndürür.

*Nitelikler* hakkında daha fazla bilgi Için [hash_multiset sınıfı](../standard-library/hash-multiset-class.md) konusuna bakın.

### <a name="remarks"></a>Açıklamalar

Saklı nesne bir üye işlevi tanımlar:

**bool işleci**( **constKey&** `_xVal` , **const Key&** *_yVal*);

Bu, **`true`** `_xVal` önceki ve sıralama düzeninde eşit değilse döndürür `_yVal` .

Hem [key_compare](#key_compare) hem de [value_compare](#value_compare) şablon parametresi *nitelikleri*için eş anlamlı olduğunu unutmayın. Her iki tür de hash_multiset ve hash_multiset sınıfları için sağlanır ve bunlar birbirinden farklı oldukları hash_map ve hash_multimap sınıflarıyla uyumluluk içindir.

### <a name="example"></a>Örnek

```cpp
// hash_multiset_value_comp.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;

   hash_multiset <int, hash_compare < int, less<int> > > hms1;
   hash_multiset <int, hash_compare < int, less<int> > >::value_compare
      vc1 = hms1.value_comp( );
   bool result1 = vc1( 2, 3 );
   if( result1 == true )
   {
      cout << "vc1( 2,3 ) returns value of true, "
           << "where vc1 is the function object of hms1."
           << endl;
   }
   else
   {
      cout << "vc1( 2,3 ) returns value of false, "
           << "where vc1 is the function object of hms1."
           << endl;
   }

   hash_multiset <int, hash_compare < int, greater<int> > > hms2;
   hash_multiset<int, hash_compare < int, greater<int> > >::
           value_compare vc2 = hms2.value_comp( );
   bool result2 = vc2( 2, 3 );
   if( result2 == true )
   {
      cout << "vc2( 2,3 ) returns value of true, "
           << "where vc2 is the function object of hms2."
           << endl;
   }
   else
   {
      cout << "vc2( 2,3 ) returns value of false, "
           << "where vc2 is the function object of hms2."
           << endl;
   }
}
```

```Output
vc1( 2,3 ) returns value of true, where vc1 is the function object of hms1.
vc2( 2,3 ) returns value of false, where vc2 is the function object of hms2.
```

## <a name="hash_multisetvalue_compare"></a><a name="value_compare"></a> hash_multiset:: value_compare

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfıdır](../standard-library/unordered-multiset-class.md).

İki işlev nesnesi sağlayan bir tür, bir hash_multiset iki öğe değerini karşılaştırabilir ve öğelerin karma oluşturan birli bir koşulu tespit edebilir.

```cpp
typedef key_compare value_compare;
```

### <a name="remarks"></a>Açıklamalar

`value_compare` , şablon parametresi *nitelikleri*için bir eş anlamlı.

*Nitelikler* hakkında daha fazla bilgi Için [hash_multiset sınıfı](../standard-library/hash-multiset-class.md) konusuna bakın.

Hem [key_compare](#key_compare) hem de `value_compare` şablon parametresi *nitelikleri*için eş anlamlıların olduğunu unutmayın. Her iki tür de, sınıfları ve çoklu küme için, her ikisi de birbirinden farklı oldukları sınıflar haritalarının ve multimap ile uyumluluk için sağlanır.

### <a name="example"></a>Örnek

Bildirme ve kullanma hakkında bir örnek için bkz. [value_comp](#value_comp) örneği `value_compare` .

## <a name="hash_multisetvalue_type"></a><a name="value_type"></a> hash_multiset:: value_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfıdır](../standard-library/unordered-multiset-class.md).

Bir nesne olarak, bir değer olarak hash_multiset bir öğe olarak depolanan bir nesne tanımlayan tür.

```cpp
typedef Key value_type;
```

### <a name="example"></a>Örnek

```cpp
// hash_multiset_value_type.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hms1;
   hash_multiset <int>::iterator hms1_Iter;

   // Declare value_type
   hash_multiset <int> :: value_type hmsvt_Int;

   hmsvt_Int = 10;   // Initialize value_type

   // Declare key_type
   hash_multiset <int> :: key_type hmskt_Int;
   hmskt_Int = 20;             // Initialize key_type

   hms1.insert( hmsvt_Int );         // Insert value into s1
   hms1.insert( hmskt_Int );         // Insert key into s1

   // A hash_multiset accepts key_types or value_types as elements
   cout << "The hash_multiset has elements:";
   for ( hms1_Iter = hms1.begin() ; hms1_Iter != hms1.end( );
         hms1_Iter++)
      cout << " " << *hms1_Iter;
      cout << "." << endl;
}
```

```Output
The hash_multiset has elements: 10 20.
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ standart kitaplığı başvurusu](../standard-library/cpp-standard-library-reference.md)
