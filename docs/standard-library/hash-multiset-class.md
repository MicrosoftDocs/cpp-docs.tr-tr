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
ms.openlocfilehash: b12c782ff7071987214acfe1ef8c52ca391b25ad
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51333569"
---
# <a name="hashmultiset-class"></a>hash_multiset Sınıfı

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).

Kapsayıcı sınıfı hash_multiset C++ Standart Kitaplığı bir uzantısıdır ve hızlı, içerdiği öğelerin değerlerinin anahtar değerler olarak hizmet veren ve benzersiz olması gerekmez, bir koleksiyondaki verileri alma ve depolama için kullanılır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Key, class Traits =hash_compare<Key, less <Key>>, class Allocator =allocator <Key>>
class hash_multiset
```

### <a name="parameters"></a>Parametreler

*Key*<br/>
Hash_multiset içinde depolanacak öğe veri türü.

*Nitelikler*<br/>
İki işlev nesneleri içeren, bir sınıfın karşılaştırma türü diğer bir deyişle bir ikili koşula birli koşul eşleştirme anahtar değerleri öğelerin işaretsiz bir karma işlevi ve kendi göreli sıralarını belirlemek için sıralama anahtarları olarak iki öğenin değerlerini karşılaştırmak için tamsayı türü `size_t`. Bu bağımsız değişken isteğe bağlıdır ve `hash_compare<Key, less<Key> >` varsayılan değerdir.

*Ayırıcı*<br/>
Hash_multiset'ın ayırma ve bellek ayırmayı kaldırma hakkındaki ayrıntıları içeren saklı ayırıcı nesnesini gösteren tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `allocator<Key>`.

## <a name="remarks"></a>Açıklamalar

Hash_multiset aşağıdaki gibidir:

- İlişkili bir anahtar değerine dayalı öğe değerlerinin verimli alınmasını destekleyen bir değişken boyutu kapsayıcı olan ilişkilendirilebilir bir kapsayıcı. Dahası, basit bir ilişkilendirilebilir kapsayıcıdır, çünkü öğelerinin değerleri kendi anahtar değerleridir.

- Çift yönlüdür, çünkü öğelerine erişmek için çift yönlü bir yineleyici sağlar.

- Karma, çünkü öğelerine demet öğelerinin anahtar değerlere uygulanan bir karma işlevi değere göre gruplanmıştır.

- Benzersizdir, çünkü öğelerinin her birinde benzersiz bir anahtar olması gerekir. Hash_multiset de basit ilişkilendirilebilir bir kapsayıcı olduğundan, da öğeleri benzersizdir.

- Bir şablon sınıfı, çünkü sağladığı işlevsellik geneldir ve böylece veri öğeler veya anahtarlar olarak kapsanan belirli türdeki bağımsız. Öğeler ve anahtarlar için kullanılacak veri türleri, karşılaştırma işlevi ve ayırıcı ile birlikte bir sınıf şablonunda parametreler olarak belirtilir.

Daha fazla verimlilik üzerinde sıralama karma ana avantajı olduğu: başarılı bir karma işlevi ekleme, silme gerçekleştirir ve sabit ortalama süre değiştirmeyen bir süre içinde sıralamak için kapsayıcı öğe sayısı için logaritmasını orantılı bulur teknikleri. Bir kümedeki bir öğenin değeri doğrudan değiştirilemez. Bunun yerine, eski değerleri silmeniz ve yeni değerlere sahip öğeler eklemeniz gerekir.

Kapsayıcı türünün seçimi genelde uygulamanın gerektirdiği arama ve ekleme türüne dayalı olmalıdır. Karma ilişkilendirilebilir kapsayıcılar, arama, ekleme ve kaldırma işlemleri için iyileştirilmiştir. Bu işlemleri açıkça destekleyen üye işlevleri, ortalama sabit ve kapsayıcıdaki öğelerin sayısına bağlı olmayan bir zaman gerçekleştirip bir iyi tasarlanmış bir karma işlevi ile kullanıldığında verimlidir. İyi tasarlanmış bir karma işlevi, Tekdüzen karma bir değerler dağıtımı verir ve burada bir çakışma ortaya çıkar farklı anahtar değerlerini aynı karma değer ile eşlenmiş kabul edilir, çakışmaları sayısını en aza indirir. En kötü durumda, en kötü olası karma işlevi ile işlem sayısı dizideki (doğrusal zaman) öğelerin sayısını orantılıdır.

Hash_multiset ilişkilendirilebilir kapsayıcı değerleri onların kendi anahtarlarıyla ilişkilendiren koşullar uygulama tarafından karşılandığında olmalıdır. Bir hash_multiset öğelerini birden çok olabilir ve anahtarlar benzersiz olmadıklarından kendi sıralama anahtarları hizmet eder. Bu tür bir yapı modeli, sözcüklerin birden çok defa geçebildiği sıralı bir sözcükler listesindedir. Uygun bir kapsayıcı yapısı bir hash_set olabilirdi sonra sözcüklerin birden çok defa geçmelerine izin yok. Ardından bir hash_map benzersiz tanımlar benzersiz anahtar sözcükler listesine değerler olarak eklendiyse, verileri kapsayacak uygun bir yapı olacaktır. Bunun yerine tanımlar benzersiz değilse, bir hash_multimap kapsayıcı olması.

Hash_multiset türünde bir depolanan karma nitelikler nesnesi çağırarak denetlediği diziyi sıralar [value_compare](#value_compare). Üye işlevini çağırarak depolanan bu nesne erişilebilecek [key_comp](#key_comp). Böyle bir işlev nesnesi aynı sınıfın bir nesnesi olarak davranmalıdır `hash_compare<Key, less<Key> >`. Tüm değerler için özellikle *anahtarı* türü `Key`, çağrı `Trait(Key)` türünde bir değerler dağıtımı verir `size_t`.

Genelde, bu sıralamayı oluşturmak için öğelerin yalnızca küçüktür biçiminde karşılaştırılabilir olması gerekir; böylece, herhangi iki öğe belirtildiğinde, eşit oldukları (yani birinin diğerinden daha küçük olmadığı anlamında) veya birinin diğerinden küçük olduğu belirlenebilir. Bu, denk olmayan öğeler arasında bir sıralamaya neden olur. Daha teknik bir not üzerinde, karşılaştırma işlevi standart matematiksel anlamda katı bir zayıf sıralama sevk eden ikili bir koşuldur. Bir ikili koşula *f*( *x*, *y*) iki bağımsız değişken nesnelere sahip bir işlev nesnesi x ve y ve dönüş değeri true veya false. İkili koşul dönüşsüz, ters ve geçişli ve denklik geçişli ise, burada iki nesne sıralama katı zayıf bir hash_multiset üzerinde uygulanan sıralama olduğu x ve y olduğunda denk olarak tanımlanan her ikisi de *f* ( *x*, *y*) ve *f*( *y*, *x*) false. Anahtarlar arasındaki eşitliğinin daha güçlü koşulu bu denkliğin yerini alırsa, sıralama (içindeki tüm öğelerin birbirine göre sıralanması anlamında) toplam haline gelir ve eşleşen anahtarlar birbirinden ayırt edilemez olacaktır.

Denetlenen dizideki öğelerin gerçek sırası karma işlevi ve sıralama işlevini geçerli boyutu bir kapsayıcı nesnesinde depolanan karma tablo bağlıdır. Denetlenen dizideki öğelerin sırasını genelde tahmin edemezsiniz için karma tablo geçerli boyutu belirlenemiyor. Öğelerin eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; öğelerin kaldırılması yalnızca özellikle kaldırılan öğeleri gösteren yineleyicileri geçersiz kılar.

Hash_multiset sınıfı tarafından sağlanan yineleyici çift yönlüdür, olan ancak sınıf üyesi işlevleri eklemek ve hash_multiset sahip şablon parametresi olarak alan, işlevsellik gereksinimleri daha zayıf bir giriş yineleyici sürümleri Bu tarafından çift yönlü Yineleyicilerin sınıfında garanti edilir. Farklı yineleyici kavramları, işlevselliklerindeki iyileştirmelere göre ilgili bir aile biçimlendirir. Her yineleyici kavramının kendi hash_multiset gereksinimleri vardır ve bunlarla çalışan algoritmaların kendi varsayımlarını yineleyici türü tarafından sağlanan gereksinimlerle sınırlaması gerekir. Bir giriş yineleyicinin bazı nesnelere başvurusunun kaldırılacağı ve dizideki sonraki yineleyiciye artırılabileceği varsayılabilir. Bu işlevselliğin en az bir hash_multiset ancak Yineleyicilerin aralığı hakkında konuşabilmek için yeterlidir [ `first`, `last`) bağlamında, sınıf üyesi işlevleri.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[hash_multiset](#hash_multiset)|Oluşturur bir `hash_multiset` boş veya diğer bir deyişle bir kopyasını tüm veya diğer bir kısmının parçası `hash_multiset`.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[allocator_type](#allocator_type)|Temsil eden bir tür `allocator` sınıfının `hash_multiset` nesne.|
|[const_iterator](#const_iterator)|Çift yönlü bir yineleyici sağlayan tür okuma bir **const** öğesinde `hash_multiset`.|
|[const_pointer](#const_pointer)|Bir işaretçi sağlayan bir tür bir **const** öğesinde bir `hash_multiset`.|
|[const_reference](#const_reference)|Bir başvuru sağlayan bir tür bir **const** öğesi içinde depolanan bir `hash_multiset` okumak ve gerçekleştirmek için **const** operations.|
|[const_reverse_iterator](#const_reverse_iterator)|Çift yönlü bir yineleyici sağlayan tür herhangi okuma **const** öğesinde `hash_multiset`.|
|[difference_type](#difference_type)|Öğeler aynı adres iki yineleyici arasındaki farkı sağlayan bir işaretli tamsayı tür `hash_multiset`.|
|[Yineleyici](#iterator)|Çift yönlü bir yineleyici sağlayan bir tür okuyabilen veya değiştirebilen herhangi bir öğenin bir `hash_multiset`.|
|[key_compare](#key_compare)|İki öğenin göreli sırasını belirlemek için iki sıralama anahtarını karşılaştıran işlev nesnesi sağlayan bir tür `hash_multiset`.|
|[key_type](#key_type)|Bir öğesi olarak depolanan nesneyi tanımlayan bir tür bir `hash_set` sıralama anahtarı olarak kapasitesi dahilinde.|
|[İşaretçi](#pointer)|İçindeki bir öğeye işaretçi sağlayan bir tür bir `hash_multiset`.|
|[Başvuru](#reference)|İçinde depolanan öğeye başvuru sağlayan bir tür bir `hash_multiset`.|
|[reverse_iterator](#reverse_iterator)|Çift yönlü bir yineleyici sağlayan bir tür okuyabilen veya değiştirebilen ters döndürülmüş bir öğe `hash_multiset`.|
|[size_type](#size_type)|İçindeki öğelerin sayısını temsil edebilen bir işaretsiz tamsayı türü bir `hash_multiset`.|
|[value_compare](#value_compare)|İkili koşulu, iki öğenin değerlerini karşılaştırabilen sınıfı karşılaştırma, iki işlev nesnesi sağlayan bir tür bir `hash_multiset` göreli belirlemek için sıralama ve bir birli öğeleri karma koşulu.|
|[value_type](#value_type)|Bir öğesi olarak depolanan nesneyi tanımlayan bir tür bir `hash_multiset` bir değer olarak kapasitesi dahilinde.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[başlayın](#begin)|İçindeki ilk öğeyi adresleyen bir yineleyici döndüren `hash_multiset`.|
|[cbegin](#cbegin)|İçindeki ilk öğeyi adresleyerek bir const yineleyici döndürür `hash_multiset`.|
|[cend](#cend)|İçindeki son öğeyi takip eden konumu ele alan sabit bir yineleyici döndüren bir `hash_multiset`.|
|[Temizle](#clear)|Tüm öğelerini siler bir `hash_multiset`.|
|[Sayısı](#count)|İçindeki öğelerin sayısını döndüren bir `hash_multiset` anahtarı parametre tarafından belirtilen bir anahtarla eşleşen|
|[crbegin](#crbegin)|Ters çevrilen içindeki ilk öğeyi adresleyerek bir const yineleyici döndürür `hash_multiset`.|
|[crend](#crend)|Ters çevrilen içindeki son öğeyi takip eden konumu ele alan sabit bir yineleyici döndürür `hash_multiset`.|
|[emplace](#emplace)|İçine yerinde oluşturulmuş bir öğe ekler bir `hash_multiset`.|
|[emplace_hint](#emplace_hint)|İçine yerinde oluşturulmuş bir öğe ekler bir `hash_multiset`, bir yerleşim ipucuyla birlikte.|
|[boş](#empty)|Testleri bir `hash_multiset` boştur.|
|[Son](#end)|İçindeki son öğeyi takip eden konumu ele alan bir yineleyici döndüren bir `hash_multiset`.|
|[equal_range](#equal_range)|Yineleyicilerin bir çiftini, sırasıyla içindeki ilk öğeye döndürür bir `hash_multiset` içindeki ilk öğeye ve belirtilen anahtardan daha büyük bir anahtarla `hash_multiset` anahtardan daha büyük veya ona eşit bir anahtara sahip.|
|[silme](#erase)|Bir öğenin veya öğelerin aralığını kaldırır bir `hash_multiset` belirtilen konumları veya belirtilen bir anahtarla eşleşen öğeleri kaldırır.|
|[Bul](#find)|İçindeki bir öğenin konumunu ele alan bir yineleyici döndüren bir `hash_multiset` belirtilen anahtara denk bir anahtara sahip.|
|[get_allocator](#get_allocator)|Bir kopyasını döndürür `allocator` oluşturmak için kullanılan nesne `hash_multiset`.|
|[Ekle](#insert)|Bir öğe veya bir dizi öğelerine ekler bir `hash_multiset`.|
|[key_comp](#key_compare)|İçindeki anahtarları sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır bir `hash_multiset`.|
|[lower_bound](#lower_bound)|İçindeki ilk öğeye bir yineleyici döndüren bir `hash_multiset` belirtilen anahtardan daha büyük veya ona eşit bir anahtara sahip.|
|[max_size](#max_size)|Öğesinin maksimum uzunluğunu döndürür `hash_multiset`.|
|[rbegin](#rbegin)|Ters çevrilen içindeki ilk öğeyi adresleyen bir yineleyici döndürür `hash_multiset`.|
|[rend](#rend)|Ters çevrilen içindeki son öğeden sonra gelen konumu ele alan bir yineleyici döndürür `hash_multiset`.|
|[Boyutu](#size)|İçindeki öğelerin sayısını döndürür `hash_multiset`.|
|[değiştirme](#swap)|İki öğeleri birbiriyle değiştirir `hash_multiset`s.|
|[upper_bound](#upper_bound)|İçindeki ilk öğeye bir yineleyici döndüren bir `hash_multiset` belirtilen anahtardan daha büyük veya ona eşit bir anahtarla.|
|[value_comp](#value_comp)|Karma ve anahtar değerlerini öğesini sıralamak için kullanılan karma özellikleri nesnesinin bir kopyasını alır bir `hash_multiset`.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[hash_multiset::operator =](#op_eq)|Hash_multiset öğelerini başka bir hash_multiset kopyasıyla değiştirir.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<hash_set >

**Namespace:** stdext

## <a name="allocator_type"></a>  hash_multiset::allocator_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).

Hash_multiset nesne için ayırıcı sınıf temsil eden tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::allocator_type allocator_type;
```

### <a name="example"></a>Örnek

Örneğin bakın [get_allocator](#get_allocator) bir örnek için `allocator_type`

## <a name="begin"></a>  hash_multiset::Begin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).

Hash_multiset içindeki ilk öğeyi adresleyen bir yineleyici döndürür.

```cpp
const_iterator begin() const;

iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

Hash_multiset veya sonra gelen konumu adresleyen bir boş hash_multiset içindeki ilk öğeyi ele alan bir çift yönlü yineleyici.

### <a name="remarks"></a>Açıklamalar

Varsa dönüş değeri `begin` atanan bir `const_iterator`, hash_multiset nesnedeki öğelerin değiştirilemez. Varsa dönüş değeri `begin` atanan bir `iterator`, hash_multiset nesnedeki öğelerin değiştirilebilir.

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

## <a name="cbegin"></a>  hash_multiset::cbegin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).

Hash_multiset ilk öğeyi adresleyen bir const yineleyici döndürür.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

İçindeki ilk öğeyi ele alan sabit bir çift yönlü yineleyici [hash_multiset](../standard-library/hash-multiset-class.md) veya sonra gelen konumu adresleyen bir boş `hash_multiset`.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri ile `cbegin`, öğeleri `hash_multiset` nesnesi değiştirilemez.

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

## <a name="cend"></a>  hash_multiset::cend

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).

Bir hash_multiset içindeki son öğeden sonra gelen konumu ele alan bir sabit yineleyici döndürür.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Dönüş Değeri

İçindeki son öğeyi takip eden konumu ele alan sabit bir çift yönlü yineleyici bir [hash_multiset](../standard-library/hash-multiset-class.md). Varsa `hash_multiset` boşsa `hash_multiset::cend == hash_multiset::begin`.

### <a name="remarks"></a>Açıklamalar

`cend` sonuna bir yineleyici olup olmadığını test etmek için kullanılan kendi `hash_multiset`. Tarafından döndürülen değer `cend` kaldırılmamalıdır.

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

## <a name="clear"></a>  hash_multiset::Clear

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).

Bir hash_multiset tüm öğelerini siler.

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

## <a name="const_iterator"></a>  hash_multiset::const_iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).

Çift yönlü bir yineleyici sağlayan tür okuma bir **const** hash_multiset öğesinde.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_iterator const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_iterator` bir öğenin değerini değiştirmek için kullanılamaz.

### <a name="example"></a>Örnek

Örneğin bakın [başlamak](#begin) bir örnek için `const_iterator`.

## <a name="const_pointer"></a>  hash_multiset::const_pointer

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).

Bir işaretçi sağlayan bir tür bir **const** bir hash_multiset öğesinde.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::const_pointer const_pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_pointer` bir öğenin değerini değiştirmek için kullanılamaz.

Çoğu durumda bir [const_iterator](#const_iterator) öğelere erişmek için kullanılması gereken bir **const** hash_multiset nesne.

## <a name="const_reference"></a>  hash_multiset::const_reference

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).

Bir başvuru sağlayan bir tür bir **const** okumak ve gerçekleştirmek için bir hash_multiset içinde depolanan öğenin **const** operations.

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

## <a name="const_reverse_iterator"></a>  hash_multiset::const_reverse_iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).

Çift yönlü bir yineleyici sağlayan tür herhangi okuma **const** hash_multiset öğesinde.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_reverse_iterator const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_reverse_iterator` kullanın tersten hash_multiset yinelemek için ve bir öğenin değerini değiştiremezsiniz.

### <a name="example"></a>Örnek

Örneğin bakın [rend](#rend) bildirme ve kullanma konusunda bir örnek için `const_reverse_iterator`.

## <a name="count"></a>  hash_multiset::Count

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).

Anahtarı parametre tarafından belirtilen bir anahtarla eşleşen bir hash_multiset öğelerin sayısını döndürür.

```cpp
size_type count(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Hash_multiset eşleştirilecek öğe anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Hash_multiset parametre tarafından belirtilen anahtara sahip öğeleri sayısı.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, şu aralıktaki öğelerin sayısını döndürür:

\[ lower_bound (*anahtarı*), upper_bound (*anahtarı*)).

### <a name="example"></a>Örnek

Aşağıdaki örnek, hash_multiset::count üye işlevinin kullanımını gösterir.

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

## <a name="crbegin"></a>  hash_multiset::crbegin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).

Ters çevrilen hash_multiset içindeki ilk öğeyi adresleyerek bir const yineleyici döndürür.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir ilk öğeyi ele alan çift yönlü yineleyici bir const [hash_multiset](../standard-library/hash-multiset-class.md) veya ne ters çevrilmeyen içindeki son öğeyi adresleyen `hash_multiset`.

### <a name="remarks"></a>Açıklamalar

`crbegin` kullanılan bir ters ile `hash_multiset` gibi [hash_multiset::begin](#begin) ile kullanılan bir `hash_multiset`.

Dönüş değeri ile `crbegin`, `hash_multiset` nesnesi değiştirilemez.

`crbegin` yinelemek için kullanılabilecek bir `hash_multiset` geriye doğru.

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

## <a name="crend"></a>  hash_multiset::crend

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).

Ters çevrilen hash_multiset içindeki son öğeyi takip eden konumu ele alan sabit bir yineleyici döndürür.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir içindeki son öğeden sonra gelen konumu ele çift yönlü yineleyici bir const [hash_multiset](../standard-library/hash-multiset-class.md) (ilk öğeyi çevrilmeyen önce gelen konum `hash_multiset`).

### <a name="remarks"></a>Açıklamalar

`crend` kullanılan bir ters ile `hash_multiset` gibi [hash_multiset::end](#end) ile kullanılan bir `hash_multiset`.

Dönüş değeri ile `crend`, `hash_multiset` nesnesi değiştirilemez.

`crend` olup ters yineleyici kendi hash_multiset sonuna ulaşıp ulaşmadığını test etmek için kullanılabilir.

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

## <a name="difference_type"></a>  hash_multiset::difference_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).

Aynı hash_multiset içindeki öğelere yönelik iki yineleyici arasındaki farkı sağlayan bir işaretli tamsayı türü.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

`difference_type` Türü çıkarma veya kapsayıcının yineleyiciler artan döndürülür. `difference_type` Genellikle aralık içindeki öğelerin sayısını temsil etmek için kullanılan [ `first`, `last`) yineleyici arasındaki `first` ve `last`, işaret ettiği öğe içerir `first` ve en fazla öğe aralığı , ancak dahil değil tarafından işaret edilen öğeyi `last`.

Ancak dikkat `difference_type` kümesi gibi ters çevrilebilir kapsayıcıları tarafından desteklenen çift yönlü Yineleyicilerin sınıfında içeren bir giriş yineleyici gereksinimlerini karşılayan tüm yineleyiciler için kullanılabilir. Yineleyici arasındaki çıkarma, yalnızca bir rastgele erişim kapsayıcı vektör veya deque gibi tarafından sağlanan rasgele erişim yineleyicileri tarafından desteklenir.

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

## <a name="emplace"></a>  hash_multiset::emplace

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).

Bir hash_multiset yerinde oluşturulmuş bir öğe ekler.

```cpp
template <class ValTy>
iterator insert(ValTy&& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*VAL*|İçine eklenecek bir öğenin değerini [hash_multiset](../standard-library/hash-multiset-class.md) sürece `hash_multiset` o öğe veya daha genel anahtarı sıralı eşdeğer bir öğe zaten içeriyor.|

### <a name="return-value"></a>Dönüş Değeri

`emplace` Üye işlevi, yeni bir öğe eklenir burada konumu gösteren bir yineleyici döndürür.

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

## <a name="emplace_hint"></a>  hash_multiset::emplace_hint

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).

Bir yerleşim ipucuyla birlikte bir hash_multiset içine yerinde oluşturulmuş bir öğe ekler.

```cpp
template <class ValTy>
iterator insert(
    const_iterator _Where,
    ValTy&& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*VAL*|İçine eklenecek bir öğenin değerini [hash_multiset](../standard-library/hash-multiset-class.md) sürece `hash_multiset` o öğe veya daha genel anahtarı sıralı eşdeğer bir öğe zaten içeriyor.|
|*_Where*|Doğru ekleme noktasını için aramaya başlamak için bir yerde. (Ekleme oluşabilir Logaritmik süre yerine amorti edilmiş sabit zaman noktasını hemen izliyorsa *_Where*.)|

### <a name="return-value"></a>Dönüş Değeri

[Hash_multiset::emplace](#emplace) üye işlevi burada yeni bir öğe eklenir içine konumu gösteren bir yineleyici döndürür `hash_multiset`.

### <a name="remarks"></a>Açıklamalar

Ekleme oluşabilir Logaritmik süre yerine amorti edilmiş sabit zaman noktasını hemen izliyorsa *_Where*.

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

## <a name="empty"></a>  hash_multiset::empty

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).

Bir hash_multiset boş olup olmadığını sınar.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** hash_multiset boşsa; **false** hash_multiset boş ise.

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

## <a name="end"></a>  hash_multiset::End

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).

Bir hash_multiset içindeki son öğeden sonra gelen konumu ele alan bir yineleyici döndürür.

```cpp
const_iterator end() const;

iterator end();
```

### <a name="return-value"></a>Dönüş Değeri

Bir hash_multiset içindeki son öğeden sonra gelen konumu ele çift yönlü bir yineleyici. Hash_multiset boş sonra hash_multiset::end ise hash_multiset::begin ==.

### <a name="remarks"></a>Açıklamalar

`end` bir yineleyicinin kendi hash_multiset sonuna ulaştı olup olmadığını sınamak için kullanılır. Tarafından döndürülen değer `end` kaldırılmamalıdır.

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

## <a name="equal_range"></a>  hash_multiset::equal_range

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).

Yineleyicilerin bir çiftini, sırasıyla belirtilen anahtardan daha büyük bir anahtarla bir hash_multiset içindeki ilk öğeye ve anahtardan büyük veya ona eşit bir anahtarla hash_multiset içindeki ilk öğeye döndürür.

```cpp
pair <const_iterator, const_iterator> equal_range (const Key& key) const;

pair <iterator, iterator> equal_range (const Key& key);
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Aranan hash_multiset bir öğeyi sıralama anahtarı ile Karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

İlk olduğu Yineleyicilerin bir çiftini [lower_bound](#lower_bound) , anahtar ve ikinci [upper_bound](#upper_bound) anahtarı.

Bir çiftin ilk yineleyicisi erişmeye `pr` üye işlevi tarafından döndürülen, kullanın `pr`. **İlk** ve alt sınır yineleyicinin başvuru kaldırma için \*( `pr`. **İlk**). Bir çiftin ikinci yineleyicisi erişmeye `pr` üye işlevi tarafından döndürülen, kullanın `pr`. **İkinci** ve üst sınır yineleyicinin başvuru kaldırma için \*( `pr`. **İkinci**).

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

## <a name="erase"></a>  hash_multiset::ERASE

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).

Bir öğenin veya öğelerin aralığını belirtilen konumlardan bir hash_multiset kaldırır veya belirtilen bir anahtarla eşleşen öğeleri kaldırır.

```cpp
iterator erase(iterator _Where);

iterator erase(iterator first, iterator last);

size_type erase(const key_type& key);
```

### <a name="parameters"></a>Parametreler

*_Where*<br/>
Hash_multiset kaldırılacak öğenin konumu.

*ilk*<br/>
Hash_multiset kaldırılan ilk öğenin konumu.

*Son*<br/>
Konum yalnızca son öğeden sonra hash_multiset kaldırıldı.

*Anahtarı*<br/>
Hash_multiset kaldırılacak öğe anahtarı.

### <a name="return-value"></a>Dönüş Değeri

İlk iki üye işlevleri için çift yönlü bir yineleyici, böyle bir öğe varsa, kaldırılan tüm öğelerin veya işaretçi hash_multiset sonuna dışında kalan ilk öğeyi belirtir. Üçüncü üye işlevi için hash_multiset kaldırılan öğelerin sayısı.

### <a name="remarks"></a>Açıklamalar

Üye işlevleri, hiçbir zaman bir özel durum.

### <a name="example"></a>Örnek

Aşağıdaki örnek, hash_multiset::erase üye işlevinin kullanımını gösterir.

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

## <a name="find"></a>  hash_multiset::Find

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).

Belirtilen anahtara denk bir anahtara sahip bir hash_multiset içindeki bir öğenin konumunu ele alan bir yineleyici döndürür.

```cpp
iterator find(const Key& key);

const_iterator find(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Aranan hash_multiset bir öğeyi sıralama anahtarı olarak eşleşen bağımsız değişken anahtar.

### <a name="return-value"></a>Dönüş Değeri

Bir [yineleyici](#iterator) veya [const_iterator](#const_iterator) , belirtilen anahtara denk bir öğenin konumu ele alan veya eşleşme olması durumunda hash_multiset içindeki son öğeyi takip eden konumu ele anahtarı bulundu.

### <a name="remarks"></a>Açıklamalar

Üye işlevi olan sıralama anahtarı hash_multiset bir öğeyi adresleyen bir yineleyici döndürür `equivalent` bağımsız değişkeni üzerinde daha az bir sıralama sevk eden ikili bir koşul altında anahtar temel-comparability ilişkisi daha.

Varsa dönüş değerinin `find` atanan bir `const_iterator`, hash_multiset nesnesi değiştirilemez. Varsa dönüş değerinin `find` atanan bir `iterator`, hash_multiset nesnesi değiştirilebilir.

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

## <a name="get_allocator"></a>  hash_multiset::get_allocator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).

Hash_multiset oluşturmak için kullanılan ayırıcı nesnesinin bir kopyasını döndürür.

```cpp
Allocator get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Hash_multiset tarafından sınıfın şablon parametresi, bellek, yönetmek için kullanılan ayırıcı `Allocator`.

Daha fazla bilgi için `Allocator`, Açıklamalar bölümüne bakın [hash_multiset sınıfı](../standard-library/hash-multiset-class.md) konu.

### <a name="remarks"></a>Açıklamalar

Hash_multiset sınıfı için ayırıcılar sınıfı depolama nasıl yönettiğini belirtin. C++ Standart Kitaplığı kapsayıcı sınıfları ile sağlanan varsayılan ayırıcılar çoğu programlama ihtiyaçları için yeterli. Yazma ve kendi allocator sınıfı kullanarak bir Gelişmiş C++ konudur.

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

## <a name="hash_multiset"></a>  hash_multiset::hash_multiset

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).

Oluşturur bir `hash_multiset` boş veya diğer bir deyişle bir kopyasını tüm veya diğer bir kısmının parçası `hash_multiset`.

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
    InputIterator First,
    InputIterator Last);

template <class InputIterator>
hash_multiset(
    InputIterator First,
    InputIterator Last,
    const Traits& Comp);

template <class InputIterator>
hash_multiset(
    InputIterator First,
    InputIterator Last,
    const Traits& Comp,
    const Allocator& Al);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Al*|Bunun için kullanılacak depolama ayırıcı sınıf `hash_multiset` varsayılan olarak nesne `Allocator`.|
|*Comp*|Karşılaştırma işlevi türü `const Traits` öğeleri sıralamak için kullanılan `hash_multiset`, bunun varsayılan `hash_compare`.|
|*sağ*|`hash_multiset` Biri oluşturulmuş `hash_multiset` bir kopyası olacak.|
|*ilk*|Kopyalanacak öğe aralığındaki ilk öğenin konumu.|
|*Son*|Kopyalanacak öğe aralığının dışındaki ilk öğenin konumu.|
|*IList*|Kopyalanacak öğe içeren initializer_list.|

### <a name="remarks"></a>Açıklamalar

Tüm oluşturucular bir tür için bellek depolama yöneten ayırıcı nesnesini depolar `hash_multiset` ve, daha sonra döndürülmesi çağırarak [hash_multiset::get_allocator](#get_allocator). Allocator parametresi, sınıf bildirimleri ve diğer ayırıcılar yerine kullanılan ön işleme makroları genellikle atlanır.

Tüm oluşturucular kendi hash_multisets başlatın.

Tüm oluşturucular türünün işlev nesnesini depolamak `Traits` anahtarları arasında bir sıralamayı oluşturmak için kullanılan `hash_multiset` ve, daha sonra döndürülmesi çağırarak [hash_multiset::key_comp](#key_comp). Daha fazla bilgi için `Traits` bkz [hash_multiset sınıfı](../standard-library/hash-multiset-class.md) konu.

İlk üç Oluşturucu boş bir ilk belirtin `hash_multiset`, ikinci karşılaştırma işlevinin türü belirtme (*kompozisyonu*) öğeleri ve üçüncü açıkça belirtilmesi sırasını oluşturmada kullanılacak ayırıcı türünü (*Al*) kullanılacak. Anahtar sözcüğü **açık** otomatik tür dönüştürme belirli türdeki bastırır.

Dördüncü Oluşturucu taşır `hash_multiset` `Right`.

Beşinci, altıncı ve yedinci oluşturucular bir initializer_list kullanır.

Son üç oluşturucular aralığını kopyalamaktadır [ `First`, `Last`), bir `hash_multiset` sınıf karşılaştırma ve ayırıcı karşılaştırma işlevinin türü belirtilirken explicitness artan.

Bir karma kümesi kapsayıcıdaki öğelerin gerçek sırası karma tablo geçerli boyutu ve sıralama işlevini karma işleve bağlı olarak değişir ve sıralama işlevi tarafından belirlendiği kümesi kapsayıcısı ile verebilir gibi genel olarak, tahmin edilemez tek başına.

## <a name="insert"></a>  hash_multiset::insert

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).

Bir öğenin veya öğelerin aralığını bir hash_multiset ekler.

```cpp
iterator insert(
    const Type& Val);

iterator insert(
    iterator Where,
    const Type& Al);

void insert(
    initializer_list<Type> IList);

iterator insert(
    const Type& Val);

iterator insert(
    Iterator Where,
    const Type& Val);

template <class InputIterator>
void insert(
    InputIterator First,
    InputIterator Last);

template <class ValTy>
iterator insert(
    ValTy&& Val);

template <class ValTy>
iterator insert(
    const_iterator Where,
    ValTy&& Val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*VAL*|Hash_multiset o öğe veya daha fazla genel anahtarı eşdeğer sıralı bir öğe zaten içermiyorsa hash_multiset eklenecek bir öğenin değeri.|
|*Burada*|Doğru ekleme noktasını için aramaya başlamak için bir yerde. (Ekleme oluşabilir Logaritmik süre yerine amorti edilmiş sabit zaman noktasını hemen izliyorsa `_Where`.)|
|*ilk*|Bir hash_multiset kopyalanacak ilk öğenin konumu.|
|*Son*|Yalnızca bir hash_multiset kopyalanacak son öğenin ötesinde konumu.|
|*IList*|Kopyalanacak öğe içeren initializer_list.|

### <a name="return-value"></a>Dönüş Değeri

İlk iki INSERT üye işlevleri, yeni bir öğe nereye yerleştirildiğini konumu gösteren bir yineleyici döndürür.

Sonraki üç üye işlevleri bir initializer_list kullanır.

Üçüncü üye işlevi bir hash_multiset aralığında bir yineleyici tarafından ele alınan her öğe için karşılık gelen öğe değerleri dizisi ekler [ `First`, `Last`), belirtilen hash_multiset.

### <a name="remarks"></a>Açıklamalar

Ekleme oluşabilir Logaritmik süre yerine INSERT ipucu sürümü için amorti edilmiş sabit zaman noktasını hemen izliyorsa *nerede*.

## <a name="iterator"></a>  hash_multiset::iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).

Okuyabilen veya değiştirebilen herhangi bir öğenin bir hash_multiset çift yönlü yineleyiciler sağlayan tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::iterator iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `iterator` bir öğenin değerini değiştirmek için kullanılabilir.

### <a name="example"></a>Örnek

Örneğin bakın [başlamak](#begin) bildirme ve kullanma konusunda bir örnek için `iterator`.

## <a name="key_comp"></a>  hash_multiset::key_comp

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).

Bir hash_multiset içindeki anahtarları sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır.

```cpp
key_compare key_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Hash_multiset şablon parametresi döndürür *nitelikler*, karma ve kapsayıcının öğelerine sıralamak için kullanılan işlev nesneleri içerir.

Daha fazla bilgi için *nitelikler* bkz [hash_multiset sınıfı](../standard-library/hash-multiset-class.md) konu.

### <a name="remarks"></a>Açıklamalar

Depolanan nesne üyesi işlevini tanımlar:

**bool işleci**( **const anahtar &** *_xVal,* **const anahtar &** _ `yVal`);

döndüren **true** varsa `_xVal` önündeki ve eşit değildir `_yVal` sıralama düzeninde.

Unutmayın hem [key_compare](#key_compare) ve [value_compare](#value_compare) şablon parametresi için eş anlamlı sözcükler olan *nitelikler*. Hash_multiset ve farklı olduğu hash_map ve hash_multimap sınıfları ile uyumluluk için aynı oldukları hash_multiset sınıfları için iki türü de sağlanır.

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

## <a name="key_compare"></a>  hash_multiset::key_compare

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).

İki işlev nesnesi sağlayan bir tür bir ikili koşul, bir hash_multiset kendi göreli sıralarını belirlemek için iki öğenin değerlerini karşılaştırabilen sınıfı karşılaştırma ve öğeleri karma birli koşulu.

```cpp
typedef Traits key_compare;
```

### <a name="remarks"></a>Açıklamalar

`key_compare` Şablon parametresi için bir eşanlamlı olduğu *nitelikler*.

Daha fazla bilgi için *nitelikler* bkz [hash_multiset sınıfı](../standard-library/hash-multiset-class.md) konu.

Unutmayın hem `key_compare` ve value_compare şablon parametresi için eş anlamlı sözcükler *nitelikler*. Her iki ayrı oldukları hash_map ve hash_multimap sınıfları ile uyumluluk için aynı oldukları hash_set ve hash_multiset sınıfları için sağlanır.

### <a name="example"></a>Örnek

Örneğin bakın [key_comp](#key_comp) bildirme ve kullanma konusunda bir örnek için `key_compare`.

## <a name="key_type"></a>  hash_multiset::key_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).

Hash_multiset içindeki iki öğenin göreli sırasını belirlemek için sıralama anahtarları olarak karşılaştırabilen bir işlev nesnesi sağlayan tür.

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Açıklamalar

`key_type` Şablon parametresi için bir eşanlamlı olduğu *anahtar*.

Unutmayın hem `key_type` ve [value_type](../standard-library/hash-set-class.md#value_type) şablon parametresi için eş anlamlı sözcükler olan *anahtar*. Her iki tür kümesi ve farklı olduğu multimap sınıfları ve eşleme ile uyumluluk için aynı oldukları multiset sınıfları için sağlanır.

Daha fazla bilgi için *anahtarı*, Açıklamalar bölümüne bakın [hash_multiset sınıfı](../standard-library/hash-multiset-class.md) konu.

### <a name="example"></a>Örnek

Örneğin bakın [value_type](#value_type) bildirme ve kullanma konusunda bir örnek için `key_type`.

## <a name="lower_bound"></a>  hash_multiset::lower_bound

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).

Bir yineleyiciyi belirtilen anahtardan daha büyük veya ona eşit bir anahtarla bir hash_multiset içindeki ilk öğeye döndürür.

```cpp
const_iterator lower_bound(const Key& key) const;

iterator lower_bound(const Key& key);
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Aranan hash_multiset bir öğeyi sıralama anahtarı ile Karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Bir [yineleyici](#iterator) veya [const_iterator](#const_iterator) bağımsız değişken anahtardan daha büyük veya ona eşit olan veya konumu adresleyen adresleri bir anahtarla bir hash_multiset ilk öğenin konumu adresleri anahtar için bir eşleşme varsa hash_multiset içerisindeki son öğe.

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

## <a name="max_size"></a>  hash_multiset::max_size

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).

Hash_multiset maksimum uzunluğunu döndürür.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Hash_multiset maksimum olası uzunluğu.

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

## <a name="op_eq"></a>  hash_multiset::operator =

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).

Hash_multiset öğelerini başka bir hash_multiset kopyasıyla değiştirir.

```cpp
hash_multiset& operator=(const hash_multiset& right);

hash_multiset& operator=(hash_multiset&& right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*sağ*|[Hash_multiset](../standard-library/hash-multiset-class.md) içine kopyalanan `hash_multiset`.|

### <a name="remarks"></a>Açıklamalar

Var olan tüm öğeleri silme sonra bir `hash_multiset`, `operator=` kopyalar veya içeriğini hareket *doğru* içine `hash_multiset`.

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

## <a name="pointer"></a>  hash_multiset::pointer

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).

Hash_multiset bir öğeye işaretçi sağlayan bir tür.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `pointer` bir öğenin değerini değiştirmek için kullanılabilir.

Çoğu durumda bir [yineleyici](#iterator) multiset nesnesindeki öğelere erişmek için kullanılmalıdır.

## <a name="rbegin"></a>  hash_multiset::rbegin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).

Ters çevrilen hash_multiset içindeki ilk öğeyi ele alan bir yineleyici döndürür.

```cpp
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen hash_multiset ilk öğeyi ele alan veya ne ters çevrilmeyen hash_multiset içindeki son öğeyi adresleyen ters iki yönlü yineleyici.

### <a name="remarks"></a>Açıklamalar

`rbegin` ters çevrilen bir hash_multiset ile kullanılan gibi [başlamak](#begin) bir hash_multiset ile kullanılır.

Varsa dönüş değeri `rbegin` atanan bir `const_reverse_iterator`, sonra da hash_multiset nesnesi değiştirilemez. Varsa dönüş değeri `rbegin` atanan bir `reverse_iterator`, ardından hash_multiset nesnesi değiştirilebilir.

`rbegin` bir hash_multiset geriye doğru gezinmek için kullanılabilir.

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
   // throught a hash_multiset in a forward order
   cout << "The hash_multiset is: ";
   for ( hms1_Iter = hms1.begin( ) ; hms1_Iter != hms1.end( );
         hms1_Iter++ )
      cout << *hms1_Iter << " ";
   cout << endl;

   // rbegin can be used to start an iteration
   // throught a hash_multiset in a reverse order
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

## <a name="reference"></a>  hash_multiset::Reference

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).

Bir hash_multiset içinde depolanan öğeye başvuru sağlayan bir tür.

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

## <a name="rend"></a>  hash_multiset::rend

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).

Ters çevrilen hash_multiset içindeki son öğeden sonra gelen konumu ele alan bir yineleyici döndürür.

```cpp
const_reverse_iterator rend() const;

reverse_iterator rend();
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir hash_multiset (ters çevrilmeyen hash_multiset ilk öğeyi önce gelen konum) içindeki son öğeden sonra gelen konumu ele ters iki yönlü yineleyici.

### <a name="remarks"></a>Açıklamalar

`rend` ters çevrilen bir hash_multiset ile kullanılan gibi [son](#end) bir hash_multiset ile kullanılır.

Varsa dönüş değeri `rend` atanan bir `const_reverse_iterator`, sonra da hash_multiset nesnesi değiştirilemez. Varsa dönüş değeri `rend` atanan bir `reverse_iterator`, ardından hash_multiset nesnesi değiştirilebilir. Tarafından döndürülen değer `rend` kaldırılmamalıdır.

`rend` olup ters yineleyici kendi hash_multiset sonuna ulaşıp ulaşmadığını test etmek için kullanılabilir.

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
   // throught a hash_multiset in a reverse order
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

## <a name="reverse_iterator"></a>  hash_multiset::reverse_iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).

Okuyabilen veya değiştirebilen bir ters hash_multiset içindeki bir öğeyi çift yönlü yineleyiciler sağlayan tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::reverse_iterator reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `reverse_iterator` kullanın tersten hash_multiset yinelemek için.

### <a name="example"></a>Örnek

Örneğin bakın [rbegin](#rbegin) bildirme ve kullanma konusunda bir örnek için `reverse_iterator`.

## <a name="size"></a>  hash_multiset::size

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).

Hash_multiset öğelerin sayısını döndürür.

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

## <a name="size_type"></a>  hash_multiset::size_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).

Bir hash_multiset içindeki öğelerin sayısını temsil edebilen bir işaretsiz tamsayı türü.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::size_type size_type;
```

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

Örneğin bakın [boyutu](#size) bildirme ve kullanma örneği `size_type`

## <a name="swap"></a>  hash_multiset::Swap

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).

İki hash_multisets öğelerini birbiriyle değiştirir.

```cpp
void swap(hash_multiset& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Hedef hash_multiset ile değiştirilecek öğeleri sağlayan bağımsız değişken hash_multiset.

### <a name="remarks"></a>Açıklamalar

Üye işlev hiçbir başvurular, işaretçiler veya öğeleri değiştirilen iki hash_multisets öğelerinde belirlemek yineleyicileri geçersiz kılar.

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

## <a name="upper_bound"></a>  hash_multiset::upper_bound

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).

Bir yineleyiciyi belirtilen anahtardan daha büyük bir anahtarla bir hash_multiset içindeki ilk öğeye döndürür.

```cpp
const_iterator upper_bound(const Key& key) const;

iterator upper_bound(const Key& key);
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Aranan hash_multiset bir öğeyi sıralama anahtarı ile Karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Bir [yineleyici](#iterator) veya [const_iterator](#const_iterator) bağımsız değişken anahtardan daha büyük bir anahtarla bir hash_multiset ilk öğenin konumu adresleri veya içindeki son öğeyi takip eden konumu ele hash_multiset anahtar için bir eşleşme.

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

## <a name="value_comp"></a>  hash_multiset::value_comp

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).

Bir hash_multiset içindeki öğe değerlerini sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır.

```cpp
value_compare value_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Hash_multiset şablon parametresi döndürür *nitelikler*, karma ve kapsayıcının sırası öğeleri için kullanılan işlev nesneleri içerir.

Daha fazla bilgi için *nitelikler* bkz [hash_multiset sınıfı](../standard-library/hash-multiset-class.md) konu.

### <a name="remarks"></a>Açıklamalar

Depolanan nesne üyesi işlevini tanımlar:

**bool işleci**( **constKey &**`_xVal`, **const anahtar &** *_yVal*);

döndüren **true** varsa `_xVal` önündeki ve eşit değildir `_yVal` sıralama düzeninde.

Unutmayın hem [key_compare](#key_compare) ve [value_compare](#value_compare) şablon parametresi için eş anlamlı sözcükler olan *nitelikler*. Hash_multiset ve farklı olduğu hash_map ve hash_multimap sınıfları ile uyumluluk için aynı oldukları hash_multiset sınıfları için iki türü de sağlanır.

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

## <a name="value_compare"></a>  hash_multiset::value_compare

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).

İki işlev nesnesi sağlayan bir tür bir ikili koşul, bir hash_multiset kendi göreli sıralarını belirlemek için iki öğenin değerlerini karşılaştırabilen sınıfı karşılaştırma ve öğeleri karma birli koşulu.

```cpp
typedef key_compare value_compare;
```

### <a name="remarks"></a>Açıklamalar

`value_compare` Şablon parametresi için bir eşanlamlı olduğu *nitelikler*.

Daha fazla bilgi için *nitelikler* bkz [hash_multiset sınıfı](../standard-library/hash-multiset-class.md) konu.

Unutmayın hem [key_compare](#key_compare) ve `value_compare` şablon parametresi için eş anlamlı sözcükler olan *nitelikler*. Multimap, farklı olduğu ve eşleme sınıfları ile uyumluluk için aynı olan, multiset ve sınıfları kümesi için her iki türü de sağlanır.

### <a name="example"></a>Örnek

Örneğin bakın [value_comp](#value_comp) bildirme ve kullanma konusunda bir örnek için `value_compare`.

## <a name="value_type"></a>  hash_multiset::value_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).

Öğe bir değer olarak kapasitesi dahilinde bir hash_multiset şeklinde depolanan nesneyi tanımlayan tür.

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

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
