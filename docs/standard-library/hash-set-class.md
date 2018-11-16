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
ms.openlocfilehash: c7d5df87dc6c8529d18b9f5fb960148c7362129a
ms.sourcegitcommit: d441305fb19131afbd7fc259d8cda63ea26f2343
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2018
ms.locfileid: "51678580"
---
# <a name="hashset-class"></a>hash_set Sınıfı

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Kapsayıcı sınıfı hash_set C++ Standart Kitaplığı bir uzantısıdır ve hızlı, içerdiği öğelerin değerlerinin benzersiz olduğu ve anahtar değerler olarak hizmet verdikleri bir koleksiyondan verilerin alınmasını ve depolama için kullanılır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Key,
    class Traits=hash_compare<Key, less<Key>>,
    class Allocator=allocator<Key>>
class hash_set
```

### <a name="parameters"></a>Parametreler

*Key*<br/>
Hash_set içinde depolanacak öğe veri türü.

*Nitelikler*<br/>
İki işlev nesneleri içeren, bir sınıfın karşılaştırma türü diğer bir deyişle bir ikili koşula birli koşul eşleştirme anahtar değerleri öğelerin işaretsiz bir karma işlevi ve kendi göreli sıralarını belirlemek için sıralama anahtarları olarak iki öğenin değerlerini karşılaştırmak için tamsayı türü `size_t`. Bu bağımsız değişken isteğe bağlıdır ve `hash_compare<Key, less<Key> >` varsayılan değerdir.

*Ayırıcı*<br/>
Hash_set'ın ayırma ve bellek ayırmayı kaldırma hakkındaki ayrıntıları içeren saklı ayırıcı nesnesini gösteren tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `allocator<Key>`.

## <a name="remarks"></a>Açıklamalar

Hash_set aşağıdaki gibidir:

- İlişkili bir anahtar değerine dayalı öğe değerlerinin verimli alınmasını destekleyen bir değişken boyutu kapsayıcı olan ilişkilendirilebilir bir kapsayıcı. Dahası, basit bir ilişkilendirilebilir kapsayıcıdır, çünkü öğelerinin değerleri kendi anahtar değerleridir.

- Çift yönlüdür, çünkü öğelerine erişmek için çift yönlü bir yineleyici sağlar.

- Karma, çünkü öğelerine demet öğelerinin anahtar değerlere uygulanan bir karma işlevi değere göre gruplanmıştır.

- Benzersizdir, çünkü öğelerinin her birinde benzersiz bir anahtar olması gerekir. Hash_set de basit ilişkilendirilebilir bir kapsayıcı olduğundan, da öğeleri benzersizdir.

- Bir şablon sınıfı, çünkü sağladığı işlevsellik geneldir ve böylece veri öğeler veya anahtarlar olarak kapsanan belirli türdeki bağımsız. Öğeler ve anahtarlar için kullanılacak veri türleri, karşılaştırma işlevi ve ayırıcı ile birlikte bir sınıf şablonunda parametreler olarak belirtilir.

Sıralama üzerinden karma ana avantajı, daha verimli olur; başarılı bir karma işlevi ekleme, silme gerçekleştirir ve sabit ortalama süre değiştirmeyen bir süre içinde teknikleri sıralama kapsayıcıdaki öğelerin sayısını logaritmasını için orantılı bulur. Bir kümedeki bir öğenin değeri doğrudan değiştirilemez. Bunun yerine, eski değerleri silmeniz ve yeni değerlere sahip öğeler eklemeniz gerekir.

Kapsayıcı türünün seçimi genelde uygulamanın gerektirdiği arama ve ekleme türüne dayalı olmalıdır. Karma ilişkilendirilebilir kapsayıcılar, arama, ekleme ve kaldırma işlemleri için iyileştirilmiştir. Bu işlemleri açıkça destekleyen üye işlevleri, ortalama sabit ve kapsayıcıdaki öğelerin sayısına bağlı olmayan bir zaman gerçekleştirip bir iyi tasarlanmış bir karma işlevi ile kullanıldığında verimlidir. İyi tasarlanmış bir karma işlevi, Tekdüzen karma bir değerler dağıtımı verir ve burada bir çakışma ortaya çıkar farklı anahtar değerlerini aynı karma değer ile eşlenmiş kabul edilir, çakışmaları sayısını en aza indirir. En kötü durumda, en kötü olası karma işlevi ile işlem sayısı dizideki (doğrusal zaman) öğelerin sayısını orantılıdır.

Hash_set, değerleri onların kendi anahtarlarıyla ilişkilendiren koşullar uygulama tarafından karşılandığında seçimin ilişkili kapsayıcısı olmalıdır. Bir hash_set öğeleri benzersizdir ve kendi sıralama anahtarı olarak hizmet eder. Bu tür bir yapı modeli, sözcüklerin yalnızca bir defa geçebildiği sıralı bir sözcükler listesindedir. Ardından bir hash_multiset sözcüklerin birden çok defa geçmelerine izin verilirse, uygun bir kapsayıcı yapısı olacaktır. Ardından bir hash_map değerlerin benzersiz anahtar sözcükler listesine eklenmesi gerekirse, verileri kapsayacak uygun bir yapı olacaktır. Bunun yerine anahtarlar benzersiz değilse, bir hash_multimap kapsayıcı olması.

Hash_set depolanan karma çağırarak denetlediği diziyi sıralar `Traits` türündeki nesne [value_compare](#value_compare). Üye işlevini çağırarak depolanan bu nesne erişilebilecek [key_comp](#key_comp). Böyle bir işlev nesnesi aynı sınıfın bir nesnesi olarak davranmalıdır *hash_compare < daha az anahtar\<anahtarı >>.* Tüm değerler için özellikle `key` anahtarı, ' % s'çağrı nitelik türü (`key`) türü size_t bir değerler dağıtımı verir.

Genelde, bu sıralamayı oluşturmak için öğelerin yalnızca küçüktür biçiminde karşılaştırılabilir olması gerekir; böylece, herhangi iki öğe belirtildiğinde, eşit oldukları (yani birinin diğerinden daha küçük olmadığı anlamında) veya birinin diğerinden küçük olduğu belirlenebilir. Bu bir denk olmayan öğeler arasında neden olur. Daha teknik bir not üzerinde, karşılaştırma işlevi standart matematiksel anlamda katı bir zayıf sıralama sevk eden ikili bir koşuldur. Bir ikili koşula *f*( *x*, *y*) iki bağımsız değişken nesnelere sahip bir işlev nesnesi x ve y ve dönüş değeri true veya false. İkili koşul dönüşsüz, ters ve geçişli ve denklik geçişli ise, burada iki nesne sıralama katı zayıf bir hash_set üzerinde uygulanan sıralama olan *x* ve *y* tanımlanır olduğunda denk olarak hem de *f*( *x*, *y*) ve *f*( *y*, *x*) yanlış ise. Anahtarlar arasındaki eşitliğinin daha güçlü koşulu bu denkliğin yerini alırsa, sıralama (içindeki tüm öğelerin birbirine göre sıralanması anlamında) toplam haline gelir ve eşleşen anahtarlar birbirinden ayırt edilemez olacaktır.

Denetlenen dizideki öğelerin gerçek sırası karma işlevi ve sıralama işlevini geçerli boyutu bir kapsayıcı nesnesinde depolanan karma tablo bağlıdır. Denetlenen dizideki öğelerin sırasını genelde tahmin edemezsiniz için karma tablo geçerli boyutu belirlenemiyor. Öğelerin eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; öğelerin kaldırılması yalnızca özellikle kaldırılan öğeleri gösteren yineleyicileri geçersiz kılar.

Hash_set sınıfı tarafından sağlanan yineleyici çift yönlüdür, ancak sınıf üyesi işlevleri olan [Ekle](#insert) ve [hash_set](#hash_set) şablon parametresi olarak daha zayıf bir giriş yineleyicisini alan sürümlere sahip işlevsellik gereksinimleri daha az tarafından çift yönlü Yineleyicilerin sınıfında garanti edilene. Farklı yineleyici kavramları, işlevselliklerindeki iyileştirmelere göre ilgili bir aile biçimlendirir. Her yineleyici kavramının kendi gereksinimler kümesi vardır ve bunlarla çalışan algoritmaların kendi varsayımlarını yineleyici türü tarafından sağlanan gereksinimlerle sınırlaması gerekir. Bir giriş yineleyicinin bazı nesnelere başvurusunun kaldırılacağı ve dizideki sonraki yineleyiciye artırılabileceği varsayılabilir. Bu bir en düşük işlevsellik kümesidir, ancak Yineleyicilerin aralığı hakkında konuşabilmek için yeterlidir [ `first`, `last`) bağlamında, sınıf üyesi işlevleri.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[hash_set](#hash_set)|Oluşturur bir `hash_set` boş veya diğer bir deyişle bir kopyasını tüm veya diğer bir kısmının parçası `hash_set`.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[allocator_type](#allocator_type)|Temsil eden bir tür `allocator` sınıfının `hash_set` nesne.|
|[const_iterator](#const_iterator)|Çift yönlü bir yineleyici sağlayan tür okuma bir `const` öğesinde `hash_set`.|
|[const_pointer](#const_pointer)|Bir işaretçi sağlayan bir tür bir **const** öğesinde bir `hash_set`.|
|[const_reference](#const_reference)|Bir başvuru sağlayan bir tür bir **const** öğesi içinde depolanan bir `hash_set` okumak ve gerçekleştirmek için **const** operations.|
|[const_reverse_iterator](#const_reverse_iterator)|Çift yönlü bir yineleyici sağlayan tür herhangi okuma **const** öğesinde `hash_set`.|
|[difference_type](#difference_type)|Öğelerin sayısını temsil etmek için kullanılabilen işaretli bir tamsayı türü bir `hash_set` yineleyiciler tarafından gösterilen öğeler arasındaki bir aralıktaki.|
|[Yineleyici](#iterator)|Çift yönlü bir yineleyici sağlayan bir tür okuyabilen veya değiştirebilen herhangi bir öğenin bir `hash_set`.|
|[key_compare](#key_compare)|İki öğenin göreli sırasını belirlemek için iki sıralama anahtarını karşılaştıran işlev nesnesi sağlayan bir tür `hash_set`.|
|[key_type](#key_type)|Bir öğesi olarak depolanan nesneyi tanımlayan bir tür bir `hash_set` sıralama anahtarı olarak kapasitesi dahilinde.|
|[İşaretçi](#pointer)|İçindeki bir öğeye işaretçi sağlayan bir tür bir `hash_set`.|
|[Başvuru](#reference)|İçinde depolanan öğeye başvuru sağlayan bir tür bir `hash_set`.|
|[reverse_iterator](#reverse_iterator)|Çift yönlü bir yineleyici sağlayan bir tür okuyabilen veya değiştirebilen ters döndürülmüş bir öğe `hash_set`.|
|[size_type](#size_type)|İçindeki öğelerin sayısını temsil edebilen bir işaretsiz tamsayı türü bir `hash_set`.|
|[value_compare](#value_compare)|İkili koşulu, iki öğenin değerlerini karşılaştırabilen sınıfı karşılaştırma, iki işlev nesnesi sağlayan bir tür bir `hash_set` göreli belirlemek için sıralama ve bir birli öğeleri karma koşulu.|
|[value_type](#value_type)|Bir öğesi olarak depolanan nesneyi tanımlayan bir tür bir `hash_set` bir değer olarak kapasitesi dahilinde.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[başlayın](#begin)|İçindeki ilk öğeyi adresleyen bir yineleyici döndüren `hash_set`.|
|[cbegin](#cbegin)|İçindeki ilk öğeyi adresleyerek bir const yineleyici döndürür `hash_set`.|
|[cend](#cend)|İçindeki son öğeyi takip eden konumu ele alan sabit bir yineleyici döndüren bir `hash_set`.|
|[Temizle](#clear)|Tüm öğelerini siler bir `hash_set`.|
|[Sayısı](#count)|İçindeki öğelerin sayısını döndüren bir `hash_set` anahtarı parametre tarafından belirtilen bir anahtarla eşleşen.|
|[crbegin](#crbegin)|Ters çevrilen içindeki ilk öğeyi adresleyerek bir const yineleyici döndürür `hash_set`.|
|[crend](#crend)|Ters çevrilen içindeki son öğeyi takip eden konumu ele alan sabit bir yineleyici döndürür `hash_set`.|
|[emplace](#emplace)|İçine yerinde oluşturulmuş bir öğe ekler bir `hash_set`.|
|[emplace_hint](#emplace_hint)|İçine yerinde oluşturulmuş bir öğe ekler bir `hash_set`, bir yerleşim ipucuyla birlikte.|
|[boş](#empty)|Testleri bir `hash_set` boştur.|
|[Son](#end)|İçindeki son öğeyi takip eden konumu ele alan bir yineleyici döndüren bir `hash_set`.|
|[equal_range](#equal_range)|Yineleyicilerin bir çiftini, sırasıyla içindeki ilk öğeye döndürür bir `hash_set` içindeki ilk öğeye ve belirtilen anahtardan daha büyük bir anahtarla `hash_set` anahtardan daha büyük veya ona eşit bir anahtara sahip.|
|[silme](#erase)|Bir öğenin veya öğelerin aralığını kaldırır bir `hash_set` belirtilen konumları veya belirtilen bir anahtarla eşleşen öğeleri kaldırır.|
|[Bul](#find)|İçindeki bir öğenin konumunu ele alan bir yineleyici döndüren bir `hash_set` belirtilen anahtara denk bir anahtara sahip.|
|[get_allocator](#get_allocator)|Bir kopyasını döndürür `allocator` oluşturmak için kullanılan nesne `hash_set`.|
|[Ekle](#insert)|Bir öğe veya bir dizi öğelerine ekler bir `hash_set`.|
|[key_comp](#key_comp)|İçindeki anahtarları sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır bir `hash_set`.|
|[lower_bound](#lower_bound)|İçindeki ilk öğeye bir yineleyici döndüren bir `hash_set` belirtilen anahtardan daha büyük veya ona eşit bir anahtara sahip.|
|[max_size](#max_size)|Öğesinin maksimum uzunluğunu döndürür `hash_set`.|
|[rbegin](#rbegin)|Ters çevrilen içindeki ilk öğeyi adresleyen bir yineleyici döndürür `hash_set`.|
|[rend](#rend)|Ters çevrilen içindeki son öğeden sonra gelen konumu ele alan bir yineleyici döndürür `hash_set`.|
|[Boyutu](#size)|İçindeki öğelerin sayısını döndürür `hash_set`.|
|[değiştirme](#swap)|İki öğeleri birbiriyle değiştirir `hash_set`s.|
|[upper_bound](#upper_bound)|İçindeki ilk öğeye bir yineleyici döndüren bir `hash_set` belirtilen anahtardan daha büyük veya ona eşit bir anahtarla.|
|[value_comp](#value_comp)|Karma ve anahtar değerlerini öğesini sıralamak için kullanılan karma özellikleri nesnesinin bir kopyasını alır bir `hash_set`.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[hash_set::operator=](#op_eq)|Öğelerinin yerini alan bir `hash_set` başka bir kopyasına sahip olan `hash_set`.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<hash_set >

**Namespace:** stdext

## <a name="allocator_type"></a>  hash_set::allocator_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Hash_set nesne için ayırıcı sınıf temsil eden tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::allocator_type allocator_type;
```

### <a name="remarks"></a>Açıklamalar

`allocator_type` Şablon parametresi için bir eşanlamlı olduğu *ayırıcı*.

Daha fazla bilgi için *ayırıcı*, Açıklamalar bölümüne bakın [hash_set sınıfı](../standard-library/hash-set-class.md) konu.

### <a name="example"></a>Örnek

Örneğin bakın [get_allocator](#get_allocator) kullanan bir örnek için `allocator_type`.

## <a name="begin"></a>  hash_set::Begin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Hash_set içindeki ilk öğeyi adresleyen bir yineleyici döndürür.

```cpp
const_iterator begin() const;

iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

Hash_set veya sonra gelen konumu adresleyen bir boş hash_set içindeki ilk öğeyi ele alan bir çift yönlü yineleyici.

### <a name="remarks"></a>Açıklamalar

Varsa dönüş değeri `begin` atanan bir `const_iterator`, hash_set nesnedeki öğelerin değiştirilemez. Varsa dönüş değeri `begin` atanan bir `iterator`, hash_set nesnedeki öğelerin değiştirilebilir.

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

## <a name="cbegin"></a>  hash_set::cbegin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Hash_set ilk öğeyi adresleyen bir const yineleyici döndürür.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

İçindeki ilk öğeyi ele alan sabit bir çift yönlü yineleyici [hash_set](../standard-library/hash-set-class.md) veya sonra gelen konumu adresleyen bir boş `hash_set`.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri ile `cbegin`, öğeleri `hash_set` nesnesi değiştirilemez.

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

## <a name="cend"></a>  hash_set::cend

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Bir hash_set içindeki son öğeden sonra gelen konumu ele alan bir sabit yineleyici döndürür.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Dönüş Değeri

İçindeki son öğeyi takip eden konumu ele alan sabit bir çift yönlü yineleyici bir [hash_set](../standard-library/hash-set-class.md). Varsa `hash_set` boşsa `hash_set::cend == hash_set::begin`.

### <a name="remarks"></a>Açıklamalar

`cend` sonuna bir yineleyici olup olmadığını test etmek için kullanılan kendi `hash_set`. Tarafından döndürülen değer `cend` kaldırılmamalıdır.

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

## <a name="clear"></a>  hash_set::Clear

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Bir hash_set tüm öğelerini siler.

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

## <a name="const_iterator"></a>  hash_set::const_iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Çift yönlü bir yineleyici sağlayan tür okuma bir **const** hash_set öğesinde.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_iterator const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_iterator` bir öğenin değerini değiştirmek için kullanılamaz.

### <a name="example"></a>Örnek

Örneğin bakın [başlamak](#begin) kullanan bir örnek için `const_iterator`.

## <a name="const_pointer"></a>  hash_set::const_pointer

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Bir işaretçi sağlayan bir tür bir **const** bir hash_set öğesinde.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_pointer const_pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_pointer` bir öğenin değerini değiştirmek için kullanılamaz.

Çoğu durumda bir [const_iterator](#const_iterator) öğelere erişmek için kullanılması gereken bir **const** hash_set nesne.

## <a name="const_reference"></a>  hash_set::const_reference

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Bir başvuru sağlayan bir tür bir **const** okumak ve gerçekleştirmek için bir hash_set içinde depolanan öğenin **const** operations.

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

## <a name="const_reverse_iterator"></a>  hash_set::const_reverse_iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Çift yönlü bir yineleyici sağlayan tür herhangi okuma **const** hash_set öğesinde.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_reverse_iterator const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_reverse_iterator` kullanın tersten hash_set yinelemek için ve bir öğenin değerini değiştiremezsiniz.

### <a name="example"></a>Örnek

Örneğin bakın [rend](#rend) bildirme ve kullanma örneği `const_reverse_iterator`

## <a name="count"></a>  hash_set::Count

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Anahtarı parametre tarafından belirtilen bir anahtarla eşleşen bir hash_set öğelerin sayısını döndürür.

```cpp
size_type count(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Hash_set eşleştirilecek öğe anahtarı.

### <a name="return-value"></a>Dönüş Değeri

hash_set sıralama anahtarı parametresi anahtarla eşleşen bir öğe içeriyorsa 1.

hash_set eşleşen bir anahtar ile bir öğe yoksa 0.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, şu aralıktaki öğelerin sayısını döndürür:

\[ lower_bound (*anahtarı*), upper_bound (*anahtarı*)).

### <a name="example"></a>Örnek

Aşağıdaki örnek, hash_set::count üye işlevinin kullanımını gösterir.

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

## <a name="crbegin"></a>  hash_set::crbegin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Ters çevrilen hash_set içindeki ilk öğeyi adresleyerek bir const yineleyici döndürür.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir ilk öğeyi ele alan çift yönlü yineleyici bir const [hash_set](../standard-library/hash-set-class.md) veya ne ters çevrilmeyen içindeki son öğeyi adresleyen `hash_set`.

### <a name="remarks"></a>Açıklamalar

`crbegin` ters çevrilen bir hash_set ile kullanılan gibi [hash_set::begin](#begin) bir hash_set ile kullanılır.

Dönüş değeri ile `crbegin`, `hash_set` nesnesi değiştirilemez.

`crbegin` yinelemek için kullanılabilecek bir `hash_set` geriye doğru.

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

## <a name="crend"></a>  hash_set::crend

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Ters çevrilen hash_set içindeki son öğeyi takip eden konumu ele alan sabit bir yineleyici döndürür.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir içindeki son öğeden sonra gelen konumu ele çift yönlü yineleyici bir const [hash_set](../standard-library/hash-set-class.md) (ilk öğeyi çevrilmeyen önce gelen konum `hash_set`).

### <a name="remarks"></a>Açıklamalar

`crend` kullanılan bir ters ile `hash_set` gibi [hash_set::end](#end) ile kullanılan bir `hash_set`.

Dönüş değeri ile `crend`, `hash_set` nesnesi değiştirilemez.

`crend` olup ters yineleyici sonuna ulaşıp ulaşmadığını test etmek için kullanılan kendi `hash_set`.

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

## <a name="difference_type"></a>  hash_set::difference_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Bir hash_set yineleyiciler tarafından gösterilen öğeler arasındaki bir aralıktaki öğelerin sayısını temsil etmek için kullanılabilen işaretli bir tamsayı türü.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

`difference_type` Türü çıkarma veya kapsayıcının yineleyiciler artan döndürülür. `difference_type` Genellikle aralık içindeki öğelerin sayısını temsil etmek için kullanılan [ `first`, `last`) yineleyici arasındaki `first` ve `last`, işaret ettiği öğe içerir `first` ve en fazla öğe aralığı , ancak dahil değil tarafından işaret edilen öğeyi `last`.

Ancak dikkat `difference_type` kümesi, yineleyici arasındaki çıkarma yalnızca gibi ters çevrilebilir kapsayıcıları tarafından desteklenen çift yönlü Yineleyicilerin sınıfında içeren bir giriş yineleyici gereksinimlerini karşılayan tüm yineleyiciler için kullanılabilir vektör veya deque gibi bir rastgele erişim kapsayıcı tarafından sağlanan rasgele erişim yineleyicileri tarafından desteklenmiyor.

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

## <a name="emplace"></a>  hash_set::emplace

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Bir hash_set yerinde oluşturulmuş bir öğe ekler.

```cpp
template <class ValTy>
pair <iterator, bool>
emplace(
    ValTy&& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*VAL*|İçine eklenecek bir öğenin değerini [hash_set](../standard-library/hash-set-class.md) sürece `hash_set` o öğe veya daha genel anahtarı sıralı eşdeğer bir öğe zaten içeriyor.|

### <a name="return-value"></a>Dönüş Değeri

`emplace` Üye işlevi bir çiftini döndürür, **bool** bileşenini döndürür **true** ekleme yapma ise ve **false** varsa `hash_set` zaten bir öğenin anahtarı sıralama, eşdeğer bir değer vardı ve burada yeni bir öğe eklendi yineleyici bileşeni adresini döndürür yer alan veya öğenin zaten bulunduğu.

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

## <a name="emplace_hint"></a>  hash_set::emplace_hint

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Bir hash_set yerinde oluşturulmuş bir öğe ekler.

```cpp
template <class ValTy>
iterator emplace(
    const_iterator _Where,
    ValTy&& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*VAL*|İçine eklenecek bir öğenin değerini [hash_set](../standard-library/hash-set-class.md) sürece `hash_set` o öğe veya daha genel anahtarı sıralı eşdeğer bir öğe zaten içeriyor.|
|*_Where*|Doğru ekleme noktasını için aramaya başlamak için bir yerde. (Ekleme oluşabilir Logaritmik süre yerine amorti edilmiş sabit zaman noktasını hemen izliyorsa *_Where*.)|

### <a name="return-value"></a>Dönüş Değeri

[Hash_set::emplace](#emplace) üye işlevi burada yeni bir öğe eklenir içine konumu gösteren bir yineleyici döndürür `hash_set`, ya da eşdeğer sıralamaya sahip var olan öğenin bulunduğu.

### <a name="remarks"></a>Açıklamalar

Ekleme oluşabilir Logaritmik süre yerine amorti edilmiş sabit zaman noktasını hemen izliyorsa *_Where*.

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

## <a name="empty"></a>  hash_set::empty

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Bir hash_set boş olup olmadığını sınar.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** hash_set boşsa; **false** hash_set boş ise.

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

## <a name="end"></a>  hash_set::End

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Bir hash_set içindeki son öğeden sonra gelen konumu ele alan bir yineleyici döndürür.

```cpp
const_iterator end() const;

iterator end();
```

### <a name="return-value"></a>Dönüş Değeri

Bir hash_set içindeki son öğeden sonra gelen konumu ele çift yönlü bir yineleyici. Hash_set boş sonra hash_set::end ise hash_set::begin ==.

### <a name="remarks"></a>Açıklamalar

`end` bir yineleyicinin kendi hash_set sonuna ulaştı olup olmadığını sınamak için kullanılır. Tarafından döndürülen değer `end` kaldırılmamalıdır.

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

## <a name="equal_range"></a>  hash_set::equal_range

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Yineleyicilerin bir çiftini, sırasıyla bir karma değer eşit olan belirtilen anahtar ve ilk öğeye anahtardan daha büyük bir anahtarla ayarlamak karma bir anahtar kümesi içindeki ilk öğeye döndürür.

```cpp
pair <const_iterator, const_iterator> equal_range (const Key& key) const;

pair <iterator, iterator> equal_range (const Key& key);
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Aranan hash_set bir öğeyi sıralama anahtarı ile Karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

İlk olduğu Yineleyicilerin bir çiftini [lower_bound](../standard-library/set-class.md#lower_bound) , anahtar ve ikinci [upper_bound](../standard-library/set-class.md#upper_bound) anahtarı.

Üye işlevi tarafından döndürülen bir çifti çekme isteğinin ilk yineleyici erişmek için `pr`. **İlk**ve alt sınır yineleyicinin başvuru kaldırma için \*( `pr`. **İlk**). Bir çiftin ikinci yineleyicisi erişmeye `pr` üye işlevi tarafından döndürülen, kullanın `pr`. **İkinci**ve üst sınır yineleyicinin başvuru kaldırma için \*( `pr`. **İkinci**).

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

## <a name="erase"></a>  hash_set::ERASE

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Bir öğenin veya öğelerin aralığını belirtilen konumlardan bir hash_set kaldırır veya belirtilen bir anahtarla eşleşen öğeleri kaldırır.

```cpp
iterator erase(iterator _Where);

iterator erase(iterator first, iterator last);

size_type erase(const key_type& key);
```

### <a name="parameters"></a>Parametreler

*_Where*<br/>
Hash_set kaldırılacak öğenin konumu.

*ilk*<br/>
Hash_set kaldırılan ilk öğenin konumu.

*Son*<br/>
Konum yalnızca son öğeden sonra hash_set kaldırıldı.

*Anahtarı*<br/>
Hash_set kaldırılacak öğe anahtarı.

### <a name="return-value"></a>Dönüş Değeri

İlk iki üye işlevleri için çift yönlü bir yineleyici, böyle bir öğe varsa, kaldırılan tüm öğelerin veya işaretçi hash_set sonuna dışında kalan ilk öğeyi belirtir. Üçüncü üye işlevi için hash_set kaldırılan öğelerin sayısı.

### <a name="remarks"></a>Açıklamalar

Üye işlevleri, hiçbir zaman bir özel durum.

### <a name="example"></a>Örnek

Aşağıdaki örnek, hash_set::erase üye işlevinin kullanımını gösterir.

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

## <a name="find"></a>  hash_set::Find

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Belirtilen anahtara denk bir anahtara sahip bir hash_set içindeki bir öğenin konumunu ele alan bir yineleyici döndürür.

```cpp
iterator find(const Key& key);

const_iterator find(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Aranan hash_set bir öğeyi sıralama anahtarı olarak eşleşen bağımsız değişken anahtar.

### <a name="return-value"></a>Dönüş Değeri

Bir `iterator` veya `const_iterator` , belirtilen anahtara denk bir öğenin konumu ele alan veya anahtar için bir eşleşme varsa hash_set içindeki son öğeyi takip eden konumu ele.

### <a name="remarks"></a>Açıklamalar

Üye işlevi olan sıralama anahtarı hash_set bir öğeyi adresleyen bir yineleyici döndürür `equivalent` bağımsız değişkeni üzerinde daha az bir sıralama sevk eden ikili bir koşul altında anahtar temel-comparability ilişkisi daha.

Varsa dönüş değerinin `find` atanan bir `const_iterator`, hash_set nesnesi değiştirilemez. Varsa dönüş değerinin `find` atanan bir `iterator`, hash_set nesnesi değiştirilebilir.

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

## <a name="get_allocator"></a>  hash_set::get_allocator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Hash_set oluşturmak için kullanılan ayırıcı nesnesinin bir kopyasını döndürür.

```cpp
Allocator get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şablon parametresi, bellek, yönetilecek hash_set tarafından kullanılan ayırıcı *ayırıcı*.

Daha fazla bilgi için *ayırıcı*, Açıklamalar bölümüne bakın [hash_set sınıfı](../standard-library/hash-set-class.md) konu.

### <a name="remarks"></a>Açıklamalar

Hash_set sınıfı için ayırıcılar sınıfı depolama nasıl yönettiğini belirtin. C++ Standart Kitaplığı kapsayıcı sınıfları ile sağlanan varsayılan ayırıcılar çoğu programlama ihtiyaçları için yeterli. Yazma ve kendi allocator sınıfı kullanarak bir Gelişmiş C++ konudur.

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

## <a name="hash_set"></a>  hash_set::hash_set

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Oluşturur bir `hash_set` boş veya diğer bir deyişle bir kopyasını tüm veya diğer bir kısmının parçası `hash_set`.

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
|*Al*|Bunun için kullanılacak depolama ayırıcı sınıf `hash_set` varsayılan olarak nesne `Allocator`.|
|*Comp*|Karşılaştırma işlevi türü `const Traits` öğeleri sıralamak için kullanılan `hash_set`, bunun varsayılan `hash_compare`.|
|*sağ*|`hash_set` Biri oluşturulmuş `hash_set` bir kopyası olacak.|
|*ilk*|Kopyalanacak öğe aralığındaki ilk öğenin konumu.|
|*Son*|Kopyalanacak öğe aralığının dışındaki ilk öğenin konumu.|

### <a name="remarks"></a>Açıklamalar

Tüm oluşturucular bir tür için bellek depolama yöneten ayırıcı nesnesini depolar `hash_set` ve, daha sonra döndürülmesi çağırarak [hash_set::get_allocator](#get_allocator). Allocator parametresi, sınıf bildirimleri ve diğer ayırıcılar yerine kullanılan ön işleme makroları genellikle atlanır.

Tüm oluşturucular kendi hash_sets başlatın.

Tüm oluşturucular türünün işlev nesnesini depolamak `Traits` anahtarları arasında bir sıralamayı oluşturmak için kullanılan `hash_set` ve, daha sonra döndürülmesi çağırarak [hash_set::key_comp](#key_comp). Daha fazla bilgi için `Traits` bkz [hash_set sınıfı](../standard-library/hash-set-class.md) konu.

İlk Oluşturucu boş bir ilk oluşturur `hash_set` ikinci karşılaştırma işlevi türünü belirtir ( `Comp`) öğeleri ve üçüncüsü sırasını açıkça oluşturmada kullanılacak ayırıcı türünü belirtir ( `Al`) olması kullanılır. Anahtar sözcük `explicit` otomatik tür dönüştürme belirli türdeki bastırır.

Dördüncü ve beşinci oluşturucular bir kopyasını belirtin `hash_set` `Right`.

Son altıncı, yedinci ve sekizinci oluşturucular öğeleri için bir initializer_list kullanır.

Aralığın son oluşturucuları kopyalama [ `First`, `Last`), bir `hash_set` sınıfı nitelikler ve ayırıcı karşılaştırma işlevinin türü belirtilirken explicitness artan.

Sekizinci Oluşturucusu taşır `hash_set` `Right`.

Öğelerin gerçek sırası bir `hash_set` kapsayıcı karma işlev bağlıdır, sıralama işlevi ve geçerli boyutu karma tablo ve burada belirlenmiştir sıralama kümesi kapsayıcısı ile verebilir gibi genel olarak, tahmin edilemez tek başına işlevi.

## <a name="insert"></a>  hash_set::insert

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Bir öğe veya bir dizi öğelerine ekler bir `hash_set`.

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
|*VAL*|İçine eklenecek bir öğenin değerini `hash_set` sürece `hash_set` o öğe veya daha genel anahtarı sıralı eşdeğer bir öğe zaten içeriyor.|
|*Burada*|Doğru ekleme noktasını için aramaya başlamak için bir yerde. (Ekleme oluşabilir Logaritmik süre yerine amorti edilmiş sabit zaman noktasını hemen izliyorsa `_Where`.)|
|*ilk*|Kopyalanacak ilk öğenin konumunu bir `hash_set`.|
|*Son*|Konuma kopyalanacak son öğenin ötesinde bir `hash_set`.|
|*IList*|Öğelerin kopyalanacağı initializer_list.|

### <a name="return-value"></a>Dönüş Değeri

İlk `insert` üye işlevi bir çiftini döndürür, **bool** bileşenini döndürür **true** ekleme yapma ise ve **false** varsa `hash_set` zaten bir öğenin anahtarı sıralama, eşdeğer bir değer vardı ve burada yeni bir öğe eklendi yineleyici bileşeni adresini döndürür yer alan veya öğenin zaten bulunduğu.

Yineleyici bileşen çifti erişmeye `pr` bu üye işlevi tarafından döndürülen, kullanın `pr.first` ve bu başvuru için `*(pr.first)`. Erişim için **bool** bileşen çifti `pr` bu üye işlevi tarafından döndürülen, kullanın `pr.second`ve bu başvuru için `*(pr.second)`.

İkinci `insert` üye işlevi burada yeni bir öğe eklenir içine konumu gösteren bir yineleyici döndürür `hash_set`.

### <a name="remarks"></a>Açıklamalar

Üçüncü üye işlevi öğeleri içinde bir initializer_list ekler.

Üçüncü üye işlevi bir dizi öğesi değerlerini ekler bir `hash_set` aralığında bir yineleyici tarafından ele alınan her öğe için karşılık gelen [ `First`, `Last`) belirli bir `hash_set`.

## <a name="iterator"></a>  hash_set::iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Okuyabilen veya değiştirebilen herhangi bir öğenin bir hash_set çift yönlü yineleyiciler sağlayan tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::iterator iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `iterator` bir öğenin değerini değiştirmek için kullanılabilir.

### <a name="example"></a>Örnek

Örneğin bakın [başlamak](#begin) bildirme ve kullanma konusunda bir örnek için `iterator`.

## <a name="key_comp"></a>  hash_set::key_comp

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Karma ve öğesi içinde bir hash_set anahtar değerlerini sıralamak için kullanılan karma özellikleri nesnesinin bir kopyasını alır.

```cpp
key_compare key_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şablon parametresi olan bir hash_set alt öğeleri düzenlemek amacıyla kullanan işlev nesnesini döndürür *nitelikler*.

Daha fazla bilgi için *nitelikler* bkz [hash_set sınıfı](../standard-library/hash-set-class.md) konu.

### <a name="remarks"></a>Açıklamalar

Depolanan nesne üyesi işlevini tanımlar:

`bool operator( const Key& _xVal, const Key& _yVal );`

döndüren **true** varsa `_xVal` önündeki ve eşit değildir `_yVal` sıralama düzeninde.

Unutmayın hem [key_compare](#key_compare) ve [value_compare](#value_compare) şablon parametresi için eş anlamlı sözcükler olan *nitelikler*. Her iki ayrı oldukları hash_map ve hash_multimap sınıfları ile uyumluluk için aynı oldukları hash_set ve hash_multiset sınıfları için sağlanır.

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

## <a name="key_compare"></a>  hash_set::key_compare

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Hash_set içindeki iki öğenin göreli sırasını belirlemek için iki sıralama anahtarını karşılaştıran işlev nesnesi sağlayan tür.

```cpp
typedef Traits key_compare;
```

### <a name="remarks"></a>Açıklamalar

`key_compare` Şablon parametresi için bir eşanlamlı olduğu *nitelikler*.

Daha fazla bilgi için *nitelikler* bkz [hash_set sınıfı](../standard-library/hash-set-class.md) konu.

Unutmayın hem `key_compare` ve [value_compare](#value_compare) şablon parametresi için eş anlamlı sözcükler olan *nitelikler*. Her iki tür kümesi ve farklı olduğu multimap sınıfları ve eşleme ile uyumluluk için aynı oldukları multiset sınıfları için sağlanır.

### <a name="example"></a>Örnek

Örneğin bakın [key_comp](#key_comp) bildirme ve kullanma konusunda bir örnek için `key_compare`.

## <a name="key_type"></a>  hash_set::key_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Öğesi sıralama anahtarı olarak kapasitesi dahilinde bir hash_set şeklinde depolanan nesneyi tanımlayan tür.

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Açıklamalar

`key_type` Şablon parametresi için bir eşanlamlı olduğu *anahtar*.

Daha fazla bilgi için *anahtarı*, Açıklamalar bölümüne bakın [hash_set sınıfı](../standard-library/hash-set-class.md) konu.

Unutmayın hem `key_type` ve [value_type](#value_type) şablon parametresi için eş anlamlı sözcükler olan *anahtar*. Her iki ayrı oldukları hash_map ve hash_multimap sınıfları ile uyumluluk için aynı oldukları hash_set ve hash_multiset sınıfları için sağlanır.

### <a name="example"></a>Örnek

Örneğin bakın [value_type](#value_type) bildirme ve kullanma konusunda bir örnek için `key_type`.

## <a name="lower_bound"></a>  hash_set::lower_bound

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Bir yineleyiciyi belirtilen anahtardan daha büyük veya ona eşit bir anahtarla bir hash_set içindeki ilk öğeye döndürür.

```cpp
const_iterator lower_bound(const Key& key) const;

iterator lower_bound(const Key& key);
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Aranan hash_set bir öğeyi sıralama anahtarı ile Karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Bir `iterator` veya `const_iterator` adresleri anahtar için bağımsız değişken anahtardan daha büyük veya ona eşit olan veya hiçbir hash_set içindeki son öğeyi takip eden konumu ele bir anahtar ile eşleştiğinden emin bir hash_set içindeki bir öğenin konumu bulunamadı.

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

## <a name="max_size"></a>  hash_set::max_size

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

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

## <a name="op_eq"></a>  hash_set::operator =

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Hash_set öğelerini başka bir hash_set kopyasıyla değiştirir.

```cpp
hash_set& operator=(const hash_set& right);

hash_set& operator=(hash_set&& right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*sağ*|[Hash_set](../standard-library/hash-set-class.md) içine kopyalanan `hash_set`.|

### <a name="remarks"></a>Açıklamalar

Var olan tüm öğeleri silme sonra bir `hash_set`, `operator=` kopyalar veya içeriğini hareket *doğru* içine `hash_set`.

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

## <a name="pointer"></a>  hash_set::pointer

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Bir hash_set öğeye işaretçi sağlayan bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `pointer` bir öğenin değerini değiştirmek için kullanılabilir.

Çoğu durumda bir [yineleyici](#iterator) hash_set nesnesindeki öğelere erişmek için kullanılmalıdır.

## <a name="rbegin"></a>  hash_set::rbegin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Ters çevrilen hash_set içindeki ilk öğeyi ele alan bir yineleyici döndürür.

```cpp
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen hash_set ilk öğeyi ele alan veya ne ters çevrilmeyen hash_set içindeki son öğeyi adresleyen ters iki yönlü yineleyici.

### <a name="remarks"></a>Açıklamalar

`rbegin` ters çevrilen bir hash_set ile kullanılan gibi [başlamak](#begin) bir hash_set ile kullanılır.

Varsa dönüş değeri `rbegin` atanan bir `const_reverse_iterator`, sonra da hash_set nesnesi değiştirilemez. Varsa dönüş değeri `rbegin` atanan bir `reverse_iterator`, ardından hash_set nesnesi değiştirilebilir.

`rbegin` bir hash_set geriye doğru gezinmek için kullanılabilir.

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

## <a name="reference"></a>  hash_set::Reference

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Bir hash_set içinde depolanan öğeye başvuru sağlayan bir tür.

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

## <a name="rend"></a>  hash_set::rend

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Ters çevrilen hash_set içindeki son öğeden sonra gelen konumu ele alan bir yineleyici döndürür.

```cpp
const_reverse_iterator rend() const;

reverse_iterator rend();
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir hash_set (ters çevrilmeyen hash_set ilk öğeyi önce gelen konum) içindeki son öğeden sonra gelen konumu ele ters iki yönlü yineleyici.

### <a name="remarks"></a>Açıklamalar

`rend` ters çevrilen bir hash_set ile kullanılan gibi [son](#end) bir hash_set ile kullanılır.

Varsa dönüş değeri `rend` atanan bir `const_reverse_iterator`, sonra da hash_set nesnesi değiştirilemez. Varsa dönüş değeri `rend` atanan bir `reverse_iterator`, ardından hash_set nesnesi değiştirilebilir. Tarafından döndürülen değer `rend` kaldırılmamalıdır.

`rend` olup ters yineleyici kendi hash_set sonuna ulaşıp ulaşmadığını test etmek için kullanılabilir.

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

## <a name="reverse_iterator"></a>  hash_set::reverse_iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Okuyabilen veya değiştirebilen bir ters hash_set içindeki bir öğeyi çift yönlü yineleyiciler sağlayan tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::reverse_iterator reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `reverse_iterator` kullanın tersten hash_set yinelemek için.

### <a name="example"></a>Örnek

Örneğin bakın [rbegin](#rbegin) bildirme ve kullanma konusunda bir örnek için `reverse_iterator`.

## <a name="size"></a>  hash_set::size

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Hash_set öğelerin sayısını döndürür.

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

## <a name="size_type"></a>  hash_set::size_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Bir hash_set içindeki öğelerin sayısını temsil edebilen bir işaretsiz tamsayı türü.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::size_type size_type;
```

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

Örneğin bakın [boyutu](#size) bildirme ve kullanma örneği `size_type`

## <a name="swap"></a>  hash_set::Swap

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

İki hash_sets öğelerini birbiriyle değiştirir.

```cpp
void swap(hash_set& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Hedef hash_set ile değiştirilecek öğeleri sağlayan bağımsız değişken hash_set.

### <a name="remarks"></a>Açıklamalar

Üye işlev hiçbir başvurular, işaretçiler veya öğeleri değiştirilen iki hash_sets öğelerinde belirlemek yineleyicileri geçersiz kılar.

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

## <a name="upper_bound"></a>  hash_set::upper_bound

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Bir yineleyici ilk öğeye bir hash_set içinde belirtilen anahtardan daha büyük bir anahtarla döndürür.

```cpp
const_iterator upper_bound(const Key& key) const;

iterator upper_bound(const Key& key);
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Aranan hash_set bir öğeyi sıralama anahtarı ile Karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Bir `iterator` veya `const_iterator` adresleri anahtar için bağımsız değişken anahtardan daha büyük veya ona eşit olan veya hiçbir hash_set içindeki son öğeyi takip eden konumu ele bir anahtar ile eşleştiğinden emin bir hash_set içindeki bir öğenin konumu bulunamadı.

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

## <a name="value_comp"></a>  hash_set::value_comp

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Bir hash_set içindeki öğe değerlerini sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır.

```cpp
value_compare value_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şablon parametresi olan bir hash_set alt öğeleri düzenlemek amacıyla kullanan işlev nesnesini döndürür *karşılaştırma*.

Daha fazla bilgi için *karşılaştırma*, Açıklamalar bölümüne bakın [hash_set sınıfı](../standard-library/hash-set-class.md) konu.

### <a name="remarks"></a>Açıklamalar

Depolanan nesne üyesi işlevini tanımlar:

`bool operator( const Key& _xVal, const Key& _yVal );`

döndüren **true** varsa `_xVal` önündeki ve eşit değildir `_yVal` sıralama düzeninde.

Unutmayın hem [value_compare](../standard-library/set-class.md#value_compare) ve [key_compare](../standard-library/set-class.md#key_compare) şablon parametresi için eş anlamlı sözcükler olan *karşılaştırma*. Her iki ayrı oldukları hash_map ve hash_multimap sınıfları ile uyumluluk için aynı oldukları hash_set ve hash_multiset sınıfları için sağlanır.

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

## <a name="value_compare"></a>  hash_set::value_compare

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

İki işlev nesnesi sağlayan bir tür bir ikili koşul, bir hash_set kendi göreli sıralarını belirlemek için iki öğenin değerlerini karşılaştırabilen sınıfı karşılaştırma ve öğeleri karma birli koşulu.

```cpp
typedef key_compare value_compare;
```

### <a name="remarks"></a>Açıklamalar

`value_compare` Şablon parametresi için bir eşanlamlı olduğu *nitelikler*.

Daha fazla bilgi için *nitelikler* bkz [hash_set sınıfı](../standard-library/hash-set-class.md) konu.

Unutmayın hem [key_compare](#key_compare) ve `value_compare` şablon parametresi için eş anlamlı sözcükler olan *nitelikler*. Her iki ayrı oldukları hash_map ve hash_multimap sınıfları ile uyumluluk için aynı oldukları hash_set ve hash_multiset sınıfları için sağlanır.

### <a name="example"></a>Örnek

Örneğin bakın [value_comp](#value_comp) bildirme ve kullanma konusunda bir örnek için `value_compare`.

## <a name="value_type"></a>  hash_set::value_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Öğesi bir değer olarak kapasitesi dahilinde bir hash_set şeklinde depolanan nesneyi tanımlayan tür.

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

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
