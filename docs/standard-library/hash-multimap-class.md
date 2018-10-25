---
title: hash_multimap sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- hash_map/stdext::hash_multimap
- hash_map/stdext::hash_multimap::allocator_type
- hash_map/stdext::hash_multimap::const_iterator
- hash_map/stdext::hash_multimap::const_pointer
- hash_map/stdext::hash_multimap::const_reference
- hash_map/stdext::hash_multimap::const_reverse_iterator
- hash_map/stdext::hash_multimap::difference_type
- hash_map/stdext::hash_multimap::iterator
- hash_map/stdext::hash_multimap::key_compare
- hash_map/stdext::hash_multimap::key_type
- hash_map/stdext::hash_multimap::mapped_type
- hash_map/stdext::hash_multimap::pointer
- hash_map/stdext::hash_multimap::reference
- hash_map/stdext::hash_multimap::reverse_iterator
- hash_map/stdext::hash_multimap::size_type
- hash_map/stdext::hash_multimap::value_type
- hash_map/stdext::hash_multimap::begin
- hash_map/stdext::hash_multimap::cbegin
- hash_map/stdext::hash_multimap::cend
- hash_map/stdext::hash_multimap::clear
- hash_map/stdext::hash_multimap::count
- hash_map/stdext::hash_multimap::crbegin
- hash_map/stdext::hash_multimap::crend
- hash_map/stdext::hash_multimap::emplace
- hash_map/stdext::hash_multimap::emplace_hint
- hash_map/stdext::hash_multimap::empty
- hash_map/stdext::hash_multimap::end
- hash_map/stdext::hash_multimap::equal_range
- hash_map/stdext::hash_multimap::erase
- hash_map/stdext::hash_multimap::find
- hash_map/stdext::hash_multimap::get_allocator
- hash_map/stdext::hash_multimap::insert
- hash_map/stdext::hash_multimap::key_comp
- hash_map/stdext::hash_multimap::lower_bound
- hash_map/stdext::hash_multimap::max_size
- hash_map/stdext::hash_multimap::rbegin
- hash_map/stdext::hash_multimap::rend
- hash_map/stdext::hash_multimap::size
- hash_map/stdext::hash_multimap::swap
- hash_map/stdext::hash_multimap::upper_bound
- hash_map/stdext::hash_multimap::value_comp
dev_langs:
- C++
helpviewer_keywords:
- stdext::hash_multimap
- stdext::hash_multimap::allocator_type
- stdext::hash_multimap::const_iterator
- stdext::hash_multimap::const_pointer
- stdext::hash_multimap::const_reference
- stdext::hash_multimap::const_reverse_iterator
- stdext::hash_multimap::difference_type
- stdext::hash_multimap::iterator
- stdext::hash_multimap::key_compare
- stdext::hash_multimap::key_type
- stdext::hash_multimap::mapped_type
- stdext::hash_multimap::pointer
- stdext::hash_multimap::reference
- stdext::hash_multimap::reverse_iterator
- stdext::hash_multimap::size_type
- stdext::hash_multimap::value_type
- stdext::hash_multimap::begin
- stdext::hash_multimap::cbegin
- stdext::hash_multimap::cend
- stdext::hash_multimap::clear
- stdext::hash_multimap::count
- stdext::hash_multimap::crbegin
- stdext::hash_multimap::crend
- stdext::hash_multimap::emplace
- stdext::hash_multimap::emplace_hint
- stdext::hash_multimap::empty
- stdext::hash_multimap::end
- stdext::hash_multimap::equal_range
- stdext::hash_multimap::erase
- stdext::hash_multimap::find
- stdext::hash_multimap::get_allocator
- stdext::hash_multimap::insert
- stdext::hash_multimap::key_comp
- stdext::hash_multimap::lower_bound
- stdext::hash_multimap::max_size
- stdext::hash_multimap::rbegin
- stdext::hash_multimap::rend
- stdext::hash_multimap::size
- stdext::hash_multimap::swap
- stdext::hash_multimap::upper_bound
- stdext::hash_multimap::value_comp
ms.assetid: f41a6db9-67aa-43a3-a3c5-dbfe9ec3ae7d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3796ba7b243305fbae75e64f44e14964a89a9805
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50075326"
---
# <a name="hashmultimap-class"></a>hash_multimap Sınıfı

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).

Kapsayıcı sınıfı hash_multimap C++ Standart Kitaplığı bir uzantısıdır ve her bir öğenin değerini benzersiz olması gerekmez sıralama anahtarına sahip olduğu bir çift olan bir koleksiyonu ve ilişkili veriler bir değer verileri hızlı alma ve depolama için kullanılır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Key,
    class Type,
    class Traits=hash_compare <Key, less <Key>>,
    class Allocator=allocator <pair  <const Key, Type>>>
class hash_multimap
```

### <a name="parameters"></a>Parametreler

*Key*<br/>
Hash_multimap içinde depolanacak anahtar veri türü.

*Türü*<br/>
Hash_multimap içinde depolanacak öğe veri türü.

*Nitelikler*<br/>
Bir sınıfın iki işlev nesneleri içeren tür *nitelikler* bir birli koşul eşleme için öğelerin anahtar değerleri olan bir karma işlevi ve kendi göreli sıralarını belirlemek için sıralama anahtarları olarak iki öğenin değerlerini karşılaştırma mümkün olan İmzasız tamsayı türünün `size_t`. Bu bağımsız değişken isteğe bağlıdır ve `hash_compare<Key, less<Key>>` varsayılan değerdir.

*Ayırıcı*<br/>
Hash_multimap'ın ayırma ve bellek ayırmayı kaldırma hakkındaki ayrıntıları içeren saklı ayırıcı nesnesini gösteren tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `allocator<pair <const Key, Type>>`.

## <a name="remarks"></a>Açıklamalar

Hash_multimap aşağıdaki gibidir:

- İlişkili bir anahtar değerine dayalı öğe değerlerinin verimli alınmasını destekleyen bir değişken boyutu kapsayıcı olan ilişkilendirilebilir bir kapsayıcı.

- Çift yönlüdür, çünkü öğelerine erişmek için çift yönlü bir yineleyici sağlar.

- Karma, çünkü öğelerine demet öğelerinin anahtar değerlere uygulanan bir karma işlevi değere göre gruplanmıştır.

- Öğelerinin benzersiz anahtarlara ihtiyacı olmaması için çokludur, böylece bir anahtar değer onunla ilişkili çok sayıda öğe verisi değerine sahip olabilir.

- Bir çift ilişkilendirilebilir kapsayıcıdır, çünkü öğelerinin değerleri kendi anahtar değerlerinden farklıdır.

- Bir şablon sınıfıdır, çünkü sağladığı işlevsellik geneldir ve böylece öğeler veya anahtarlar olarak kapsanan belirli veri türünden bağımsızdır. Öğeler ve anahtarlar için kullanılacak veri türleri, karşılaştırma işlevi ve ayırıcı ile birlikte bir sınıf şablonunda parametreler olarak belirtilir.

Sıralama üzerinden karma ana avantajı, daha verimli olur; başarılı bir karma işlevi ekleme, silme gerçekleştirir ve sabit ortalama süre değiştirmeyen bir süre içinde teknikleri sıralama kapsayıcıdaki öğelerin sayısını logaritmasını için orantılı bulur. Bir hash_multimap içindeki bir öğenin değeri, ancak ilişkili anahtar değeri, doğrudan değiştirilemez. Bunun yerine, eski öğelerle ilişkili anahtar değerleri silinmeli ve eklenen yeni öğelerle ilişkili yeni anahtar değerleri eklenmelidir.

Kapsayıcı türünün seçimi genelde uygulamanın gerektirdiği arama ve ekleme türüne dayalı olmalıdır. Karma ilişkilendirilebilir kapsayıcılar, arama, ekleme ve kaldırma işlemleri için iyileştirilmiştir. Bu işlemleri açıkça destekleyen üye işlevleri, ortalama sabit ve kapsayıcıdaki öğelerin sayısına bağlı olmayan bir zaman gerçekleştirip bir iyi tasarlanmış bir karma işlevi ile kullanıldığında verimlidir. İyi tasarlanmış bir karma işlevi, Tekdüzen karma bir değerler dağıtımı verir ve burada bir çakışma ortaya çıkar farklı anahtar değerlerini aynı karma değer ile eşlenmiş kabul edilir, çakışmaları sayısını en aza indirir. En kötü durumda, en kötü olası karma işlevi ile işlem sayısı dizideki (doğrusal zaman) öğelerin sayısını orantılıdır.

Hash_multimap, değerleri onların kendi anahtarlarıyla ilişkilendiren koşullar uygulama tarafından karşılandığında seçimin ilişkili kapsayıcısı olmalıdır. Bu tür bir yapı için model, mesela açıklamalar sağlayan dize değerleriyle ilişkili anahtar sözcüklerin sıralı bir listesidir, burada sözcükler her zaman benzersiz olarak tanımlanmamıştır. Ardından, anahtarlar benzersiz olacak şekilde bunun yerine, anahtar sözcükler benzersiz olarak tanımlanırsa, bir hash_map kapsayıcı olacaktır. Ardından, diğer taraftan, yalnızca sözcüklerin listesi depolanmaktadır, bir hash_set doğru kapsayıcı olacaktır. Ardından bir hash_multiset sözcüklerin birden çok defa geçmelerine izin verilirse, uygun bir kapsayıcı yapısı olacaktır.

Hash_multimap depolanan karma çağırarak denetlediği diziyi sıralar `Traits` türündeki nesne [value_compare](../standard-library/value-compare-class.md). Üye işlevini çağırarak depolanan bu nesne erişilebilecek [key_comp](../standard-library/hash-map-class.md#key_comp). Böyle bir işlev nesnesi aynı sınıfın bir nesnesi olarak davranmalıdır [hash_compare](../standard-library/hash-compare-class.md)`<Key, less<Key>>`. Tüm değerler için özellikle `Key` türü `Key`, çağrı `Traits (Key)` türünde bir değerler dağıtımı verir `size_t`.

Genelde, bu sıralamayı oluşturmak için öğelerin yalnızca küçüktür biçiminde karşılaştırılabilir olması gerekir; böylece, herhangi iki öğe belirtildiğinde, eşit oldukları (yani birinin diğerinden daha küçük olmadığı anlamında) veya birinin diğerinden küçük olduğu belirlenebilir. Bu bir denk olmayan öğeler arasında neden olur. Daha teknik bir not üzerinde, karşılaştırma işlevi standart matematiksel anlamda katı bir zayıf sıralama sevk eden ikili bir koşuldur. Bir ikili koşula f (x, y) iki bağımsız değişken nesnelere sahip bir işlev nesnesidir `x` ve `y` ve dönüş değeri **true** veya **false**. İkili koşul dönüşsüz, ters ve geçişli ve denklik geçişli ise, burada iki nesne sıralama katı zayıf bir hash_multimap üzerinde uygulanan sıralama olan `x` ve `y` olduğunda denk olarak tanımlanan her iki f (x y) ve f (y, x) **false**. Anahtarlar arasındaki eşitliğinin daha güçlü koşulu bu denkliğin yerini alırsa, sıralama (içindeki tüm öğelerin birbirine göre sıralanması anlamında) toplam haline gelir ve eşleşen anahtarlar birbirinden ayırt edilemez olacaktır.

Denetlenen dizideki öğelerin gerçek sırası karma işlevi ve sıralama işlevini geçerli boyutu bir kapsayıcı nesnesinde depolanan karma tablo bağlıdır. Denetlenen dizideki öğelerin sırasını genelde tahmin edemezsiniz için karma tablo geçerli boyutu belirlenemiyor. Öğelerin eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; öğelerin kaldırılması yalnızca özellikle kaldırılan öğeleri gösteren yineleyicileri geçersiz kılar.

Hash_multimap sınıfı tarafından sağlanan yineleyici çift yönlüdür, ancak sınıf üyesi işlevleri olan [Ekle](#insert) ve [hash_multimap](#hash_multimap) şablon parametresi olarak daha zayıf bir giriş alan sürümlere sahip Yineleyici, işlevsellik gereksinimleri daha az tarafından çift yönlü Yineleyicilerin sınıfında garanti edilene. Farklı yineleyici kavramları, işlevselliklerindeki iyileştirmelere göre ilgili bir aile biçimlendirir. Her yineleyici kavramının kendi hash_multimap gereksinimleri vardır ve bunlarla çalışan algoritmaların kendi varsayımlarını yineleyici türü tarafından sağlanan gereksinimlerle sınırlaması gerekir. Bir giriş yineleyicinin bazı nesnelere başvurusunun kaldırılacağı ve dizideki sonraki yineleyiciye artırılabileceği varsayılabilir. Bu işlevselliğin en az bir hash_multimap ancak Yineleyicilerin aralığı hakkında konuşabilmek için yeterlidir `[First, Last)` üye işlevleri bağlamında.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[hash_multimap](#hash_multimap)|Belirli bir boyut veya belirli bir değer öğeleriyle veya belirli bir ile bir liste oluşturur `allocator` veya diğer bir kısmının kopyası olarak `hash_multimap`.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[allocator_type](#allocator_type)|Temsil eden bir tür `allocator` sınıfının `hash_multimap` nesne.|
|[const_iterator](#const_iterator)|Çift yönlü bir yineleyici sağlayan tür okuma bir `const` öğesinde `hash_multimap`.|
|[const_pointer](#const_pointer)|Bir işaretçi sağlayan bir tür bir **const** öğesinde bir `hash_multimap`.|
|[const_reference](#const_reference)|Bir başvuru sağlayan bir tür bir **const** öğesi içinde depolanan bir `hash_multimap` okumak ve gerçekleştirmek için **const** operations.|
|[const_reverse_iterator](#const_reverse_iterator)|Çift yönlü bir yineleyici sağlayan tür herhangi okuma **const** öğesinde `hash_multimap`.|
|[difference_type](#difference_type)|Öğelerin sayısını temsil etmek için kullanılabilen işaretli bir tamsayı türü bir `hash_multimap` yineleyiciler tarafından gösterilen öğeler arasındaki bir aralıktaki.|
|[Yineleyici](#iterator)|Çift yönlü bir yineleyici sağlayan bir tür okuyabilen veya değiştirebilen herhangi bir öğenin bir `hash_multimap`.|
|[key_compare](#key_compare)|İki öğenin göreli sırasını belirlemek için iki sıralama anahtarını karşılaştıran işlev nesnesi sağlayan bir tür `hash_multimap`.|
|[key_type](#key_type)|Her öğesini oluşturan sıralama anahtarını nesnesini tanımlayan bir tür `hash_multimap`.|
|[mapped_type](#mapped_type)|İçinde depolanan veri türünü temsil eden bir tür bir `hash_multimap`.|
|[İşaretçi](#pointer)|İçindeki bir öğeye işaretçi sağlayan bir tür bir `hash_multimap`.|
|[Başvuru](#reference)|İçinde depolanan öğeye başvuru sağlayan bir tür bir `hash_multimap`.|
|[reverse_iterator](#reverse_iterator)|Çift yönlü bir yineleyici sağlayan bir tür okuyabilen veya değiştirebilen ters döndürülmüş bir öğe `hash_multimap`.|
|[size_type](#size_type)|İçindeki öğelerin sayısını temsil edebilen bir işaretsiz tamsayı türü bir `hash_multimap`.|
|[value_type](#value_type)|İki öğenin kendi göreli sıralarını belirlemek için sıralama anahtarları olarak karşılaştırabilen bir işlev nesnesi sağlayan bir tür `hash_multimap`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[başlayın](#begin)|İçindeki ilk öğeyi adresleyen bir yineleyici döndürür `hash_multimap`.|
|[cbegin](#cbegin)|İçindeki ilk öğeyi adresleyerek bir const yineleyici döndürür `hash_multimap`.|
|[cend](#cend)|İçindeki son öğeyi takip eden konumu ele alan sabit bir yineleyici döndüren bir `hash_multimap`.|
|[Temizle](#clear)|Tüm öğelerini siler bir `hash_multimap`.|
|[Sayısı](#count)|İçindeki öğelerin sayısını döndüren bir `hash_multimap` anahtarı parametre tarafından belirtilen bir anahtarla eşleşen.|
|[crbegin](#crbegin)|Ters çevrilen içindeki ilk öğeyi adresleyerek bir const yineleyici döndürür `hash_multimap`.|
|[crend](#crend)|Ters çevrilen içindeki son öğeyi takip eden konumu ele alan sabit bir yineleyici döndürür `hash_multimap`.|
|[emplace](#emplace)|İçine yerinde oluşturulmuş bir öğe ekler bir `hash_multimap`.|
|[emplace_hint](#emplace_hint)|İçine yerinde oluşturulmuş bir öğe ekler bir `hash_multimap`, bir yerleşim ipucuyla birlikte.|
|[boş](#empty)|Testleri bir `hash_multimap` boştur.|
|[Son](#end)|İçindeki son öğeyi takip eden konumu ele alan bir yineleyici döndüren bir `hash_multimap`.|
|[equal_range](#equal_range)|İçindeki son öğeyi takip eden konumu ele alan bir yineleyici döndüren bir `hash_multimap`.|
|[silme](#erase)|Bir öğenin veya öğelerin aralığını kaldırır bir `hash_multimap` belirtilen konumlardan|
|[Bul](#find)|İçindeki bir öğenin konumunu ele alan bir yineleyici döndüren bir `hash_multimap` belirtilen anahtara denk bir anahtara sahip.|
|[get_allocator](#get_allocator)|Bir kopyasını döndürür `allocator` oluşturmak için kullanılan nesne `hash_multimap`.|
|[Ekle](#insert)|Bir öğe veya bir dizi öğelerine ekler `hash_multimap` belirtilen konumda.|
|[key_comp](#key_comp)|İçindeki anahtarları sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır bir `hash_multimap`.|
|[lower_bound](#lower_bound)|İçindeki ilk öğeye bir yineleyici döndüren bir `hash_multimap` belirtilen anahtardan daha büyük ya da eşit bir anahtarla değer.|
|[max_size](#max_size)|Öğesinin maksimum uzunluğunu döndürür `hash_multimap`.|
|[rbegin](#rbegin)|Ters çevrilen içindeki ilk öğeyi adresleyen bir yineleyici döndürür `hash_multimap`.|
|[rend](#rend)|Ters çevrilen içindeki son öğeden sonra gelen konumu ele alan bir yineleyici döndürür `hash_multimap`.|
|[Boyutu](#size)|İçin yeni bir boyut belirtir bir `hash_multimap`.|
|[değiştirme](#swap)|İki öğeleri birbiriyle değiştirir `hash_multimap`s.|
|[upper_bound](#upper_bound)|İçindeki ilk öğeye bir yineleyici döndüren bir `hash_multimap` belirtilen anahtardan büyük bir anahtarla değer.|
|[value_comp](#value_comp)|İçindeki öğe değerlerini sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır bir `hash_multimap`.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[hash_multimap::operator =](#op_eq)|Öğelerinin yerini alan bir `hash_multimap` başka bir kopyasına sahip olan `hash_multimap`.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<hash_map >

**Namespace:** stdext

## <a name="allocator_type"></a>  hash_multimap::allocator_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).

Hash_multimap nesne için ayırıcı sınıf temsil eden tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::allocator_type allocator_type;
```

### <a name="remarks"></a>Açıklamalar

`allocator_type` Şablon parametresi için bir eşanlamlı olduğu `Allocator`.

Daha fazla bilgi için `Allocator`, Açıklamalar bölümüne bakın [hash_multimap sınıfı](../standard-library/hash-multimap-class.md) konu.

### <a name="example"></a>Örnek

Örneğin bakın [get_allocator](#get_allocator) bir örnek için `allocator_type`.

## <a name="begin"></a>  hash_multimap::Begin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).

Hash_multimap içindeki ilk öğeyi ele alan bir yineleyici döndürür.

```cpp
const_iterator begin() const;

iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

Hash_multimap veya sonra gelen konumu adresleyen bir boş hash_multimap içindeki ilk öğeyi ele alan bir çift yönlü yineleyici.

### <a name="remarks"></a>Açıklamalar

Varsa dönüş değeri `begin` atanan bir `const_iterator`, hash_multimap nesnedeki öğelerin değiştirilemez. Varsa dönüş değeri `begin` atanan bir `iterator`, hash_multimap nesnedeki öğelerin değiştirilebilir.

### <a name="example"></a>Örnek

```cpp
// hash_multimap_begin.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multimap <int, int> hm1;

   hash_multimap <int, int> :: iterator hm1_Iter;
   hash_multimap <int, int> :: const_iterator hm1_cIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 0, 0 ) );
   hm1.insert ( Int_Pair ( 1, 1 ) );
   hm1.insert ( Int_Pair ( 2, 4 ) );

   hm1_cIter = hm1.begin ( );
   cout << "The first element of hm1 is " << hm1_cIter -> first
        << "." << endl;

   hm1_Iter = hm1.begin ( );
   hm1.erase ( hm1_Iter );

   // The following 2 lines would err because the iterator is const
   // hm1_cIter = hm1.begin ( );
   // hm1.erase ( hm1_cIter );

   hm1_cIter = hm1.begin( );
   cout << "The first element of hm1 is now " << hm1_cIter -> first
        << "." << endl;
}
```

```Output
The first element of hm1 is 0.
The first element of hm1 is now 1.
```

## <a name="cbegin"></a>  hash_multimap::cbegin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).

Hash_multimap içindeki ilk öğeyi adresleyerek bir const yineleyici döndürür.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

İçindeki ilk öğeyi ele alan sabit bir çift yönlü yineleyici [hash_multimap](../standard-library/hash-multimap-class.md) veya sonra gelen konumu adresleyen bir boş `hash_multimap`.

### <a name="example"></a>Örnek

```cpp
// hash_multimap_cbegin.cpp
// compile with: /EHsc
#include <hash_multimap>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multimap <int, int> hm1;

   hash_multimap <int, int> :: const_iterator hm1_cIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 2, 4 ) );

   hm1_cIter = hm1.cbegin ( );
   cout << "The first element of hm1 is "
        << hm1_cIter -> first << "." << endl;
   }
```

```Output
The first element of hm1 is 2.
```

## <a name="cend"></a>  hash_multimap::cend

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).

Bir hash_multimap içindeki son öğeden sonra gelen konumu ele alan bir sabit yineleyici döndürür.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Dönüş Değeri

İçindeki son öğeyi takip eden konumu ele alan sabit bir çift yönlü yineleyici bir [hash_multimap](../standard-library/hash-multimap-class.md). Varsa `hash_multimap` boşsa `hash_multimap::cend == hash_multimap::begin`.

### <a name="remarks"></a>Açıklamalar

`cend` bir yineleyicinin kendi hash_multimap sonuna ulaştı olup olmadığını sınamak için kullanılır.

Tarafından döndürülen değer `cend` kaldırılmamalıdır.

### <a name="example"></a>Örnek

```cpp
// hash_multimap_cend.cpp
// compile with: /EHsc
#include <hash_multimap>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multimap <int, int> hm1;

   hash_multimap <int, int> :: const_iterator hm1_cIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 3, 30 ) );

   hm1_cIter = hm1.cend( );
   hm1_cIter--;
   cout << "The value of last element of hm1 is "
        << hm1_cIter -> second << "." << endl;
   }
```

```Output
The value of last element of hm1 is 30.
```

## <a name="clear"></a>  hash_multimap::Clear

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).

Bir hash_multimap tüm öğelerini siler.

```cpp
void clear();
```

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

Aşağıdaki örnek, hash_multimap::clear üye işlevinin kullanımını gösterir.

```cpp
// hash_multimap_clear.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main()
{
    using namespace std;
    using namespace stdext;
    hash_multimap<int, int> hm1;
    hash_multimap<int, int>::size_type i;
    typedef pair<int, int> Int_Pair;

    hm1.insert(Int_Pair(1, 1));
    hm1.insert(Int_Pair(2, 4));

    i = hm1.size();
    cout << "The size of the hash_multimap is initially "
         << i  << "." << endl;

    hm1.clear();
    i = hm1.size();
    cout << "The size of the hash_multimap after clearing is "
         << i << "." << endl;
}
```

```Output
The size of the hash_multimap is initially 2.
The size of the hash_multimap after clearing is 0.
```

## <a name="const_iterator"></a>  hash_multimap::const_iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).

Çift yönlü bir yineleyici sağlayan tür okuma bir **const** hash_multimap öğesinde.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_iterator const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_iterator` bir öğenin değerini değiştirmek için kullanılamaz.

`const_iterator` Nesnelerin hash_multimap noktalarına göre tanımlanan [value_type](#value_type), türü olan `pair<const Key, Type>`. Anahtar değeri ilk üye çift kullanılabilir ve eşlenen öğenin değeri çiftinin ikinci üye kullanılabilir.

Başvurulacak bir `const_iterator` `cIter` bir hash_multimap içindeki bir öğeyi işaret eden, kullanın `->` işleci.

Öğenin anahtarının değerini erişmek için `cIter->first`, eşdeğer olan `(*cIter).first`. Eşlenmiş veri öğesi için değeri erişmek için `cIter->second`, eşdeğer olan `(*cIter).second`.

### <a name="example"></a>Örnek

Örneğin bakın [başlamak](#begin) bir örnek için `const_iterator`.

## <a name="const_pointer"></a>  hash_multimap::const_pointer

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).

Bir işaretçi sağlayan bir tür bir **const** bir hash_multimap öğesinde.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::const_pointer const_pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_pointer` bir öğenin değerini değiştirmek için kullanılamaz.

Çoğu durumda bir [yineleyici](#iterator) hash_multimap nesnesindeki öğelere erişmek için kullanılmalıdır.

## <a name="const_reference"></a>  hash_multimap::const_reference

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).

Bir başvuru sağlayan bir tür bir **const** okumak ve gerçekleştirmek için bir hash_multimap içinde depolanan öğenin **const** operations.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::const_reference const_reference;
```

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_multimap_const_ref.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multimap<int, int> hm1;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );

   // Declare and initialize a const_reference &Ref1
   // to the key of the first element
   const int &Ref1 = ( hm1.begin( ) -> first );

   // The following line would cause an error because the
   // non-const_reference cannot be used to access the key
   // int &Ref1 = ( hm1.begin( ) -> first );

   cout << "The key of first element in the hash_multimap is "
        << Ref1 << "." << endl;

   // Declare and initialize a reference &Ref2
   // to the data value of the first element
   int &Ref2 = ( hm1.begin() -> second );

   cout << "The data value of 1st element in the hash_multimap is "
        << Ref2 << "." << endl;
}
```

```Output
The key of first element in the hash_multimap is 1.
The data value of 1st element in the hash_multimap is 10.
```

## <a name="const_reverse_iterator"></a>  hash_multimap::const_reverse_iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).

Çift yönlü bir yineleyici sağlayan tür herhangi okuma **const** hash_multimap öğesinde.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_reverse_iterator const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_reverse_iterator` kullanın tersten hash_multimap yinelemek için ve bir öğenin değerini değiştiremezsiniz.

`const_reverse_iterator` Nesnelerin hash_multimap noktalarına göre tanımlanan [value_type](#value_type), türü olan `pair<const Key, Type>`olan ilk üye öğe anahtarıdır ve ikinci öğe tarafından tutulan eşlenen datum üyesidir.

Başvurulacak bir `const_reverse_iterator` `crIter` bir hash_multimap içindeki bir öğeyi işaret eden, kullanın `->` işleci.

Öğenin anahtarının değerini erişmek için `crIter->first`, eşdeğer olan `(*crIter).first`. Eşlenmiş veri öğesi için değeri erişmek için `crIter->second`, eşdeğer olan `(*crIter).second`.

### <a name="example"></a>Örnek

Örneğin bakın [rend](#rend) bildirme ve kullanma konusunda bir örnek için `const_reverse_iterator`.

## <a name="count"></a>  hash_multimap::Count

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).

Anahtarı parametre tarafından belirtilen bir anahtarla eşleşen bir hash_multimap öğelerin sayısını döndürür.

```cpp
size_type count(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Hash_multimap eşleştirilecek öğe anahtarı.

### <a name="return-value"></a>Dönüş Değeri

hash_multimap sıralama anahtarı parametresi anahtarla eşleşen bir öğe içeriyorsa 1; 0 hash_multimap bir öğesi ile eşleşen bir anahtar içermiyor.

### <a name="remarks"></a>Açıklamalar

Üye işlevi aralıktaki öğelerin sayısını döndürür.

**[lower_bound (** `key` **), upper_bound (** `key` **))**

bir anahtar değere sahip *anahtar*.

### <a name="example"></a>Örnek

Aşağıdaki örnek, hash_multimap::count üye işlevinin kullanımını gösterir.

```cpp
// hash_multimap_count.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
    using namespace std;
    using namespace stdext;
    hash_multimap<int, int> hm1;
    hash_multimap<int, int>::size_type i;
    typedef pair<int, int> Int_Pair;

    hm1.insert(Int_Pair(1, 1));
    hm1.insert(Int_Pair(2, 1));
    hm1.insert(Int_Pair(1, 4));
    hm1.insert(Int_Pair(2, 1));

    // Elements do not need to have unique keys in hash_multimap,
    // so duplicates are allowed and counted
    i = hm1.count(1);
    cout << "The number of elements in hm1 with a sort key of 1 is: "
         << i << "." << endl;

    i = hm1.count(2);
    cout << "The number of elements in hm1 with a sort key of 2 is: "
         << i << "." << endl;

    i = hm1.count(3);
    cout << "The number of elements in hm1 with a sort key of 3 is: "
         << i << "." << endl;
}
```

```Output
The number of elements in hm1 with a sort key of 1 is: 2.
The number of elements in hm1 with a sort key of 2 is: 2.
The number of elements in hm1 with a sort key of 3 is: 0.
```

## <a name="crbegin"></a>  hash_multimap::crbegin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).

Ters çevrilen hash_multimap içindeki ilk öğeyi adresleyerek bir const yineleyici döndürür.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir ilk öğeyi ele alan çift yönlü yineleyici bir const [hash_multimap](../standard-library/hash-multimap-class.md) veya ne ters çevrilmeyen içindeki son öğeyi adresleyen `hash_multimap`.

### <a name="remarks"></a>Açıklamalar

`crbegin` ters çevrilen bir hash_multimap ile kullanılan gibi [hash_multimap::begin](#begin) ile kullanılan bir `hash_multimap`.

Dönüş değeri ile `crbegin`, `hash_multimap` nesnesi değiştirilemez.

`crbegin` yinelemek için kullanılabilecek bir `hash_multimap` geriye doğru.

### <a name="example"></a>Örnek

```cpp
// hash_multimap_crbegin.cpp
// compile with: /EHsc
#include <hash_multimap>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multimap <int, int> hm1;

   hash_multimap <int, int> :: const_reverse_iterator hm1_crIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 3, 30 ) );

   hm1_crIter = hm1.crbegin( );
   cout << "The first element of the reversed hash_multimap hm1 is "
        << hm1_crIter -> first << "." << endl;
}
```

```Output
The first element of the reversed hash_multimap hm1 is 3.
```

## <a name="crend"></a>  hash_multimap::crend

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).

Ters çevrilen hash_multimap içindeki son öğeyi takip eden konumu ele alan sabit bir yineleyici döndürür.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir içindeki son öğeden sonra gelen konumu ele çift yönlü yineleyici bir const [hash_multimap](../standard-library/hash-multimap-class.md) (ilk öğeyi çevrilmeyen önce gelen konum `hash_multimap`).

### <a name="remarks"></a>Açıklamalar

`crend` ters çevrilen bir hash_multimap ile kullanılan gibi [hash_multimap::end](#end) bir hash_multimap ile kullanılır.

Dönüş değeri ile `crend`, `hash_multimap` nesnesi değiştirilemez.

`crend` olup ters yineleyici kendi hash_multimap sonuna ulaşıp ulaşmadığını test etmek için kullanılabilir.

Tarafından döndürülen değer `crend` kaldırılmamalıdır.

### <a name="example"></a>Örnek

```cpp
// hash_multimap_crend.cpp
// compile with: /EHsc
#include <hash_multimap>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multimap <int, int> hm1;

   hash_multimap <int, int> :: const_reverse_iterator hm1_crIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 3, 30 ) );

   hm1_crIter = hm1.crend( );
   hm1_crIter--;
   cout << "The last element of the reversed hash_multimap hm1 is "
        << hm1_crIter -> first << "." << endl;
}
```

```Output
The last element of the reversed hash_multimap hm1 is 3.
```

## <a name="difference_type"></a>  hash_multimap::difference_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).

Bir hash_multimap yineleyiciler tarafından gösterilen öğeler arasındaki bir aralıktaki öğelerin sayısını temsil etmek için kullanılabilen işaretli bir tamsayı türü.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

`difference_type` Türü çıkarma veya kapsayıcının yineleyiciler artan döndürülür. `difference_type` Genellikle aralık içindeki öğelerin sayısını temsil etmek için kullanılan *[Soyadı)* yineleyici arasındaki `first` ve `last`, işaret ettiği öğe içeren `first` ve aralığı öğeleri kadar ancak dahil değil, öğe tarafından işaret edilen `last`.

Ancak dikkat `difference_type` kümesi, yineleyici arasındaki çıkarma yalnızca gibi ters çevrilebilir kapsayıcıları tarafından desteklenen çift yönlü Yineleyicilerin sınıfında içeren bir giriş yineleyici gereksinimlerini karşılayan tüm yineleyiciler için kullanılabilir vektör gibi bir rastgele erişim kapsayıcı tarafından sağlanan rasgele erişim yineleyicileri tarafından desteklenmiyor.

### <a name="example"></a>Örnek

```cpp
// hash_multimap_difference_type.cpp
// compile with: /EHsc
#include <iostream>
#include <hash_map>
#include <algorithm>

int main()
{
    using namespace std;
    using namespace stdext;
    hash_multimap<int, int> hm1;
    typedef pair<int, int> Int_Pair;

    hm1.insert(Int_Pair(2, 20));
    hm1.insert(Int_Pair(1, 10));
    hm1.insert(Int_Pair(3, 20));

    // The following will insert, because map keys
    // do not need to be unique
    hm1.insert(Int_Pair(2, 30));

    hash_multimap<int, int>::iterator hm1_Iter, hm1_bIter, hm1_eIter;
    hm1_bIter = hm1.begin();
    hm1_eIter = hm1.end();

    // Count the number of elements in a hash_multimap
    hash_multimap<int, int>::difference_type df_count = 0;
    hm1_Iter = hm1.begin();
    while (hm1_Iter != hm1_eIter)
    {
        df_count++;
        hm1_Iter++;
    }

    cout << "The number of elements in the hash_multimap hm1 is: "
         << df_count << "." << endl;

    cout << "The keys of the mapped elements are:";
    for (hm1_Iter= hm1.begin() ; hm1_Iter!= hm1.end();
        hm1_Iter++)
        cout << " " << hm1_Iter-> first;
    cout << "." << endl;

    cout << "The values of the mapped elements are:";
    for (hm1_Iter= hm1.begin() ; hm1_Iter!= hm1.end();
        hm1_Iter++)
        cout << " " << hm1_Iter-> second;
    cout << "." << endl;
}
```

```Output
The number of elements in the hash_multimap hm1 is: 4.
The keys of the mapped elements are: 1 2 2 3.
The values of the mapped elements are: 10 20 30 20.
```

## <a name="emplace"></a>  hash_multimap::emplace

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).

Bir hash_multimap yerinde oluşturulmuş bir öğe ekler.

```cpp
template <class ValTy>
iterator emplace(ValTy&& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*VAL*|Taşıma için kullanılan değer, a eklenmesi için bir öğe oluşturmak [hash_multimap](../standard-library/hash-multimap-class.md).|

### <a name="return-value"></a>Dönüş Değeri

`emplace` Üye işlevi, yeni bir öğe eklenir burada konumu gösteren bir yineleyici döndürür.

### <a name="remarks"></a>Açıklamalar

[Hash_multimap::value_type](#value_type) böylece bir öğenin değerini sıralı bir çift anahtar değerine eşit olan ilk bileşen ve saniye bileşenini öğenin veri değerine eşit olan bir çift öğesidir.

### <a name="example"></a>Örnek

```cpp
// hash_multimap_emplace.cpp
// compile with: /EHsc
#include<hash_multimap>
#include<iostream>
#include <string>

int main()
{
    using namespace std;
    using namespace stdext;
    hash_multimap<int, string> hm1;
    typedef pair<int, string> is1(1, "a");

    hm1.emplace(move(is1));
    cout << "After the emplace, hm1 contains:" << endl
      << " " << hm1.begin()->first
      << " => " << hm1.begin()->second
      << endl;
}
```

```Output
After the emplace insertion, hm1 contains:
1 => a
```

## <a name="emplace_hint"></a>  hash_multimap::emplace_hint

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).

Bir yerleşim ipucuyla birlikte bir hash_multimap içine yerinde oluşturulmuş bir öğe ekler.

```cpp
template <class ValTy>
iterator emplace_hint(
    const_iterator _Where,
    ValTy&& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*VAL*|Taşıma için kullanılan değer, a eklenmesi için bir öğe oluşturmak [hash_multimap](../standard-library/hash-multimap-class.md) sürece `hash_multimap` zaten o öğenin (veya daha genel anahtarı sıralı eşdeğer bir öğe) içerir.|
|*_Where*|Doğru ekleme noktasını için aramaya başlamak için yer ile ilgili bir ipucu.|

### <a name="return-value"></a>Dönüş Değeri

[Hash_multimap::emplace](#emplace) üye işlevi burada yeni bir öğe eklenir içine konumu gösteren bir yineleyici döndürür `hash_multimap`.

### <a name="remarks"></a>Açıklamalar

[Hash_multimap::value_type](#value_type) böylece bir öğenin değerini sıralı bir çift anahtar değerine eşit olan ilk bileşen ve saniye bileşenini öğenin veri değerine eşit olan bir çift öğesidir.

Ekleme oluşabilir Logaritmik süre yerine amorti edilmiş sabit zaman noktasını hemen izliyorsa *_Where*.

### <a name="example"></a>Örnek

```cpp
// hash_multimap_emplace_hint.cpp
// compile with: /EHsc
#include<hash_multimap>
#include<iostream>
#include <string>

int main()
{
    using namespace std;
    using namespace stdext;
    hash_multimap<int, string> hm1;
    typedef pair<int, string> is1(1, "a");

    hm1.emplace(hm1.begin(), move(is1));
    cout << "After the emplace insertion, hm1 contains:" << endl
      << " " << hm1.begin()->first
      << " => " << hm1.begin()->second
      << endl;
}
```

```Output
After the emplace insertion, hm1 contains:
1 => a
```

## <a name="empty"></a>  hash_multimap::empty

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).

Bir hash_multimap boş olup olmadığını sınar.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** hash_multimap boşsa; **false** hash_multimap boş ise.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_multimap_empty.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multimap <int, int> hm1, hm2;

   typedef pair <int, int> Int_Pair;
   hm1.insert ( Int_Pair ( 1, 1 ) );

   if ( hm1.empty( ) )
      cout << "The hash_multimap hm1 is empty." << endl;
   else
      cout << "The hash_multimap hm1 is not empty." << endl;

   if ( hm2.empty( ) )
      cout << "The hash_multimap hm2 is empty." << endl;
   else
      cout << "The hash_multimap hm2 is not empty." << endl;
}
```

```Output
The hash_multimap hm1 is not empty.
The hash_multimap hm2 is empty.
```

## <a name="end"></a>  hash_multimap::End

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).

Bir hash_multimap içindeki son öğeden sonra gelen konumu ele alan bir yineleyici döndürür.

```cpp
const_iterator end() const;

iterator end();
```

### <a name="return-value"></a>Dönüş Değeri

Bir hash_multimap içindeki son öğeden sonra gelen konumu ele çift yönlü bir yineleyici. Hash_multimap boş sonra hash_multimap::end ise hash_multimap::begin ==.

### <a name="remarks"></a>Açıklamalar

`end` bir yineleyicinin kendi hash_multimap sonuna ulaştı olup olmadığını sınamak için kullanılır.

Tarafından döndürülen değer `end` kaldırılmamalıdır.

### <a name="example"></a>Örnek

```cpp
// hash_multimap_end.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multimap <int, int> hm1;

   hash_multimap <int, int> :: iterator hm1_Iter;
   hash_multimap <int, int> :: const_iterator hm1_cIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );
   hm1.insert ( Int_Pair ( 3, 30 ) );

   hm1_cIter = hm1.end( );
   hm1_cIter--;
   cout << "The value of last element of hm1 is "
        << hm1_cIter -> second << "." << endl;

   hm1_Iter = hm1.end( );
   hm1_Iter--;
   hm1.erase ( hm1_Iter );

   // The following 2 lines would err because the iterator is const
   // hm1_cIter = hm1.end ( );
   // hm1_cIter--;
   // hm1.erase ( hm1_cIter );

   hm1_cIter = hm1.end( );
   hm1_cIter--;
   cout << "The value of last element of hm1 is now "
        << hm1_cIter -> second << "." << endl;
}
```

```Output
The value of last element of hm1 is 30.
The value of last element of hm1 is now 20.
```

## <a name="equal_range"></a>  hash_multimap::equal_range

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).

Yineleyicilerin bir çiftini, sırasıyla belirtilen anahtardan daha büyük bir anahtarla bir hash_multimap içindeki ilk öğeye ve anahtardan büyük veya ona eşit bir anahtarla hash_multimap içindeki ilk öğeye döndürür.

```cpp
pair <const_iterator, const_iterator> equal_range (const Key& key) const;

pair <iterator, iterator> equal_range (const Key& key);
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Aranan hash_multimap bir öğeyi sıralama anahtarı ile Karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Yineleyicilerin bir çiftini ilk güvenilecek şekilde [lower_bound](#lower_bound) , anahtar ve ikinci [upper_bound](#upper_bound) anahtarı.

Bir çiftin ilk yineleyicisi erişmeye `pr` üye işlevi tarafından döndürülen, kullanın `pr`. **İlk** ve alt sınır yineleyicinin başvuru kaldırma için \*( `pr`. **İlk**). Bir çiftin ikinci yineleyicisi erişmeye `pr` üye işlevi tarafından döndürülen, kullanın `pr`. **İkinci** ve üst sınır yineleyicinin başvuru kaldırma için \*( `pr`. **İkinci**).

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_multimap_equal_range.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   typedef hash_multimap <int, int> IntMMap;
   IntMMap hm1;
   hash_multimap <int, int> :: const_iterator hm1_RcIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );
   hm1.insert ( Int_Pair ( 3, 30 ) );

   pair <IntMMap::const_iterator, IntMMap::const_iterator> p1, p2;
   p1 = hm1.equal_range( 2 );

   cout << "The lower bound of the element with a key of 2\n"
        << "in the hash_multimap hm1 is: "
        << p1.first -> second << "." << endl;

   cout << "The upper bound of the element with a key of 2\n"
        << "in the hash_multimap hm1 is: "
        << p1.second -> second << "." << endl;

   // Compare the upper_bound called directly
   hm1_RcIter = hm1.upper_bound( 2 );

   cout << "A direct call of upper_bound( 2 ) gives "
        << hm1_RcIter -> second << "," << endl
        << "matching the 2nd element of the pair "
        << "returned by equal_range( 2 )." << endl;

   p2 = hm1.equal_range( 4 );

   // If no match is found for the key,
   // both elements of the pair return end( )
   if ( ( p2.first == hm1.end( ) ) && ( p2.second == hm1.end( ) ) )
      cout << "The hash_multimap hm1 doesn't have an element "
           << "with a key less than 4." << endl;
   else
      cout << "The element of hash_multimap hm1 with a key >= 40 is: "
           << p1.first -> first << "." << endl;
}
```

```Output
The lower bound of the element with a key of 2
in the hash_multimap hm1 is: 20.
The upper bound of the element with a key of 2
in the hash_multimap hm1 is: 30.
A direct call of upper_bound( 2 ) gives 30,
matching the 2nd element of the pair returned by equal_range( 2 ).
The hash_multimap hm1 doesn't have an element with a key less than 4.
```

## <a name="erase"></a>  hash_multimap::ERASE

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).

Bir öğenin veya öğelerin aralığını belirtilen konumlardan bir hash_multimap kaldırır veya belirtilen bir anahtarla eşleşen öğeleri kaldırır.

```cpp
iterator erase(iterator _Where);

iterator erase(iterator first, iterator last);

size_type erase(const key_type& key);
```

### <a name="parameters"></a>Parametreler

*_Where*<br/>
Hash_multimap kaldırılacak öğenin konumu.

*ilk*<br/>
Hash_multimap kaldırılan ilk öğenin konumu.

*Son*<br/>
Konum yalnızca son öğeden sonra hash_multimap kaldırıldı.

*Anahtarı*<br/>
Hash_multimap kaldırılacak öğe anahtarı.

### <a name="return-value"></a>Dönüş Değeri

İlk iki üye işlevleri için çift yönlü bir yineleyici, böyle bir öğe varsa, kaldırılan tüm öğelerin veya işaretçi hash_multimap sonuna dışında kalan ilk öğeyi belirtir.

Üye işlevi için üçüncü hash_multimap kaldırılan öğelerin sayısını döndürür.

### <a name="remarks"></a>Açıklamalar

Üye işlevleri, hiçbir zaman bir özel durum.

### <a name="example"></a>Örnek

Aşağıdaki örnek, hash_multimap::erase üye işlevinin kullanımını gösterir.

```cpp
// hash_multimap_erase.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main()
{
    using namespace std;
    using namespace stdext;
    hash_multimap<int, int> hm1, hm2, hm3;
    hash_multimap<int, int> :: iterator pIter, Iter1, Iter2;
    int i;
    hash_multimap<int, int>::size_type n;
    typedef pair<int, int> Int_Pair;

    for (i = 1; i < 5; i++)
    {
        hm1.insert(Int_Pair (i, i) );
        hm2.insert(Int_Pair (i, i*i) );
        hm3.insert(Int_Pair (i, i-1) );
    }

    // The 1st member function removes an element at a given position
    Iter1 = ++hm1.begin();
    hm1.erase(Iter1);

    cout << "After the 2nd element is deleted, "
         << "the hash_multimap hm1 is:";
    for (pIter = hm1.begin(); pIter != hm1.end(); pIter++)
        cout << " " << pIter -> second;
    cout << "." << endl;

    // The 2nd member function removes elements
    // in the range [ first,  last)
    Iter1 = ++hm2.begin();
    Iter2 = --hm2.end();
    hm2.erase(Iter1, Iter2);

    cout << "After the middle two elements are deleted, "
         << "the hash_multimap hm2 is:";
    for (pIter = hm2.begin(); pIter != hm2.end(); pIter++)
        cout << " " << pIter -> second;
    cout << "." << endl;

    // The 3rd member function removes elements with a given  key
    hm3.insert(Int_Pair (2, 5));
    n = hm3.erase(2);

    cout << "After the element with a key of 2 is deleted,\n"
         << "the hash_multimap hm3 is:";
    for (pIter = hm3.begin(); pIter != hm3.end(); pIter++)
        cout << " " << pIter -> second;
    cout << "." << endl;

    // The 3rd member function returns the number of elements removed
    cout << "The number of elements removed from hm3 is: "
         << n << "." << endl;

    // The dereferenced iterator can also be used to specify a key
    Iter1 = ++hm3.begin();
    hm3.erase(Iter1);

    cout << "After another element with a key equal to that of the"
         << endl;
    cout  << "2nd element is deleted, "
          << "the hash_multimap hm3 is:";
    for (pIter = hm3.begin(); pIter != hm3.end(); pIter++)
        cout << " " << pIter -> second;
    cout << "." << endl;
}
```

```Output
After the 2nd element is deleted, the hash_multimap hm1 is: 1 3 4.
After the middle two elements are deleted, the hash_multimap hm2 is: 1 16.
After the element with a key of 2 is deleted,
the hash_multimap hm3 is: 0 2 3.
The number of elements removed from hm3 is: 2.
After another element with a key equal to that of the
2nd element is deleted, the hash_multimap hm3 is: 0 3.
```

## <a name="find"></a>  hash_multimap::Find

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).

Belirtilen anahtara denk bir anahtara sahip bir hash_multimap içindeki bir öğenin birinci konumunu ele alan bir yineleyici döndürür.

```cpp
iterator find(const Key& key);

const_iterator find(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Aranan hash_multimap bir öğeyi sıralama anahtarı tarafından eşleştirilecek anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Bir öğenin birinci konumunu belirtilen bir anahtar veya anahtar için bir eşleşme varsa hash_multimap içindeki son öğeyi takip eden konumu ele alan bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Üye işlevi olan sıralama anahtarı hash_multimap bir öğeyi adresleyen bir yineleyici döndürür `equivalent` bağımsız değişkeni comparability ilişkisi küçüktür anahtarı altında bir sıralama sevk eden ikili bir koşula dayalı.

Varsa dönüş değerinin `find` atanan bir `const_iterator`, hash_multimap nesnesi değiştirilemez. Varsa dönüş değerinin `find` atanan bir `iterator`, hash_multimap nesnesi değiştirilebilir.

### <a name="example"></a>Örnek

```cpp
// hash_multimap_find.cpp
// compile with: /EHsc
#include <iostream>
#include <hash_map>

int main()
{
    using namespace std;
    using namespace stdext;
    hash_multimap<int, int> hm1;
    hash_multimap<int, int> :: const_iterator hm1_AcIter, hm1_RcIter;
    typedef pair<int, int> Int_Pair;

    hm1.insert(Int_Pair(1, 10));
    hm1.insert(Int_Pair(2, 20));
    hm1.insert(Int_Pair(3, 20));
    hm1.insert(Int_Pair(3, 30));

    hm1_RcIter = hm1.find(2);
    cout << "The element of hash_multimap hm1 with a key of 2 is: "
          << hm1_RcIter -> second << "." << endl;

    hm1_RcIter = hm1.find(3);
    cout << "The first element of hash_multimap hm1 with a key of 3 is: "
          << hm1_RcIter -> second << "." << endl;

    // If no match is found for the key, end() is returned
    hm1_RcIter = hm1.find(4);

    if (hm1_RcIter == hm1.end())
        cout << "The hash_multimap hm1 doesn't have an element "
             << "with a key of 4." << endl;
    else
        cout << "The element of hash_multimap hm1 with a key of 4 is: "
             << hm1_RcIter -> second << "." << endl;

    // The element at a specific location in the hash_multimap can be
    // found using a dereferenced iterator addressing the location
    hm1_AcIter = hm1.end();
    hm1_AcIter--;
    hm1_RcIter = hm1.find(hm1_AcIter -> first);
    cout << "The first element of hm1 with a key matching"
         << endl << "that of the last element is: "
         << hm1_RcIter -> second << "." << endl;

    // Note that the first element with a key equal to
    // the key of the last element is not the last element
    if (hm1_RcIter == --hm1.end())
        cout << "This is the last element of hash_multimap hm1."
             << endl;
    else
        cout << "This is not the last element of hash_multimap hm1."
             << endl;
}
```

```Output
The element of hash_multimap hm1 with a key of 2 is: 20.
The first element of hash_multimap hm1 with a key of 3 is: 20.
The hash_multimap hm1 doesn't have an element with a key of 4.
The first element of hm1 with a key matching
that of the last element is: 20.
This is not the last element of hash_multimap hm1.
```

## <a name="get_allocator"></a>  hash_multimap::get_allocator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).

Hash_multimap oluşturmak için kullanılan ayırıcı nesnesinin bir kopyasını döndürür.

```cpp
Allocator get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Hash_multimap tarafından kullanılan ayırıcı.

### <a name="remarks"></a>Açıklamalar

Hash_multimap sınıfı için ayırıcılar sınıfı depolama nasıl yönettiğini belirtin. C++ Standart Kitaplığı kapsayıcı sınıfları ile sağlanan varsayılan ayırıcılar çoğu programlama ihtiyaçları için yeterli. Yazma ve kendi allocator sınıfı kullanarak bir Gelişmiş C++ konudur.

### <a name="example"></a>Örnek

```cpp
// hash_multimap_get_allocator.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multimap <int, int>::allocator_type hm1_Alloc;
   hash_multimap <int, int>::allocator_type hm2_Alloc;
   hash_multimap <int, double>::allocator_type hm3_Alloc;
   hash_multimap <int, int>::allocator_type hm4_Alloc;

   // The following lines declare objects
   // that use the default allocator.
   hash_multimap <int, int> hm1;
   hash_multimap <int, int> hm2;
   hash_multimap <int, double> hm3;

   hm1_Alloc = hm1.get_allocator( );
   hm2_Alloc = hm2.get_allocator( );
   hm3_Alloc = hm3.get_allocator( );

   cout << "The number of integers that can be allocated"
        << endl << " before free memory is exhausted: "
        << hm2.max_size( ) << "." << endl;

   cout << "The number of doubles that can be allocated"
        << endl << " before free memory is exhausted: "
        << hm3.max_size( ) <<  "." << endl;

   // The following line creates a hash_multimap hm4
   // with the allocator of hash_multimap hm1.
   hash_multimap <int, int> hm4( less<int>( ), hm1_Alloc );

   hm4_Alloc = hm4.get_allocator( );

   // Two allocators are interchangeable if
   // storage allocated from each can be
   // deallocated by the other
   if( hm1_Alloc == hm4_Alloc )
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

## <a name="hash_multimap"></a>  hash_multimap::hash_multimap

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).

Boş olan veya bir kopyası tüm veya bazı diğer hash_multimap parçası hash_multimap oluşturur.

```cpp
hash_multimap();

explicit hash_multimap(
    const Compare& Comp);

hash_multimap(
    const Compare& Comp,
    const Allocator& Al);

hash_multimap(
    const hash_multimap& Right);

hash_multimap(
    hash_multimap&& Right);

hash_multimap(
    initializer_list<Type> IList);

hash_multimap(
    initializer_list<Type> IList,
    const Compare& Comp);

hash_multimap(
    initializer_list<Type> IList,
    const Compare& Comp,
    const Allocator& Al);

template <class InputIterator>
hash_multimap(
    InputIterator First,
    InputIterator Last);

template <class InputIterator>
hash_multimap(
    InputIterator First,
    InputIterator Last,
    const Compare& Comp);

template <class InputIterator>
hash_multimap(
    InputIterator First,
    InputIterator Last,
    const Compare& Comp,
    const Allocator& Al);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Al*|Varsayılan olarak bu hash_multimap nesne için kullanılacak depolama ayırıcı sınıf `Allocator`.|
|*Comp*|Karşılaştırma işlevi türü `const Traits` varsayılan olarak haritada öğeleri sıralamak için kullanılan `Traits`.|
|*sağ*|Oluşturulan kümesi kopyası olacak olduğu eşlemesi.|
|*ilk*|Kopyalanacak öğe aralığındaki ilk öğenin konumu.|
|*Son*|Kopyalanacak öğe aralığının dışındaki ilk öğenin konumu.|
|*IList*|Kopyalanacak initializer_list.|

### <a name="remarks"></a>Açıklamalar

Tüm Oluşturucular, hash_multimap için bellek depolama yönetir ve bu daha sonra döndürülmesi çağırarak ayırıcı nesnesi türü depolamak [get_allocator](#get_allocator). Ayırıcı parametre sınıf bildirimlerinde genellikle atlanır ve ön işleme makroları alternatif ayırıcılar yerine kullanılır.

Tüm oluşturucular kendi hash_multimap başlatın.

Tüm oluşturucular türünün işlev nesnesini depolamak `Traits` hash_multimap anahtarları arasında bir sipariş oluşturmak için kullanılır ve daha sonra çağırarak döndürülebilir [key_comp](#key_comp).

İlk üç Oluşturucu boş bir başlangıç hash_multimap belirtin. İkinci karşılaştırma işlevi türünü belirtir (*kompozisyonu*) öğeleri ve üçüncüsü sırasını açıkça oluşturmada kullanılacak ayırıcı türünü belirtir (`_Al`) kullanılacak. Anahtar sözcüğü `explicit` otomatik tür dönüştürme belirli türdeki bastırır.

Dördüncü Oluşturucu hash_multimap bir kopyasını belirtir `Right`.

Sonraki üç oluşturucular aralığını kopyalamaktadır `First, Last)` sınıfın karşılaştırma işlevinin türü belirtilirken explicitness artan eşleme `Traits` ve ayırıcı.

Hash_multimap sekizinci Oluşturucusu taşır `Right`.

Son üç oluşturucular bir initializer_list kullanır.

## <a name="insert"></a>  hash_multimap::insert

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).

Bir öğenin veya öğelerin aralığını bir hash_multimap ekler.

```cpp
iterator insert(
    const value_type& Val);

iterator insert(
    const_iterator Where,
    const value_type& Val);void insert(
    initializer_list<value_type> IList);

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
|*VAL*|Bu öğeyi zaten içeriyor veya zaten anahtarı bir öğe içeriyorsa sürece daha genel olarak, eşdeğer sıralanır sürece hash_multimap eklenecek bir öğenin değeri.|
|*Burada*|Doğru ekleme noktasını için aramaya başlamak nereye hakkında bir ipucu.|
|*ilk*|Bir eşlemden kopyalanacak ilk öğenin konumu.|
|*Son*|Yalnızca bir eşlemden kopyalanacak son öğenin ötesinde konumu.|

### <a name="return-value"></a>Dönüş Değeri

İlk iki `insert` üye işlevleri, yeni bir öğe eklenir burada konumu gösteren bir yineleyici döndürür.

Üçüncü üye işlevi, eklenecek öğeler için bir initializer_list kullanır.

Dördüncü üye işlevi aralıktaki bir yineleyici tarafından ele alınan her öğe için karşılık gelen bir harita öğe değerleri dizisi ekler `[First, Last)` belirtilen kümenin.

Son iki `insert` üye işlevleri davrandığını ilk ikisi, aynı bunlar move-yapısı eklenen değer dışında.

### <a name="remarks"></a>Açıklamalar

[Value_type](#value_type) böylece bir öğenin değeri ilk bileşen olduğu anahtar değerine eşit sıralı bir çift bir çift öğesidir ve saniye bileşenini öğenin veri değerine eşittir.

Ekleme ipucu sürümü için amorti edilmiş sabit zaman meydana gelebilir `insert`, ekleme noktasını hemen izliyorsa Logaritmik süre yerine *nerede*.

## <a name="iterator"></a>  hash_multimap::iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).

Okuyabilen veya değiştirebilen herhangi bir öğenin bir hash_multimap çift yönlü yineleyiciler sağlayan tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::iterator iterator;
```

### <a name="remarks"></a>Açıklamalar

`iterator` Nesnelerin hash_multimap noktalarına göre tanımlanan [value_type](#value_type), türü olan `pair` \< **const Key, türü**>, öğenin anahtarı, ilk üyesidir ikinci öğe tarafından tutulan eşlenen datum üyesidir.

Başvurulacak bir **yineleyici** `Iter` bir hash_multimap içindeki bir öğeyi işaret eden, kullanın `->` işleci.

Öğenin anahtarının değerini erişmek için `Iter`  ->  **ilk**, eşit olduğu (\* `Iter`). **İlk**. Eşlenmiş veri öğesi için değeri erişmek için `Iter`  ->  **ikinci**, eşit olduğu (\* `Iter`). **İlk**.

Bir tür `iterator` bir öğenin değerini değiştirmek için kullanılabilir.

### <a name="example"></a>Örnek

Örneğin bakın [başlamak](#begin) bildirme ve kullanma konusunda bir örnek için `iterator`.

## <a name="key_comp"></a>  hash_multimap::key_comp

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).

Bir hash_multimap içindeki anahtarları sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır.

```cpp
key_compare key_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Alt öğeleri düzenlemek amacıyla bir hash_multimap kullanan bir işlev nesnesi döndürür.

### <a name="remarks"></a>Açıklamalar

Depolanan nesne üyesi işlevini tanımlar.

**bool işleci (const anahtar &** `left` **, const anahtar &** `right` **);**

döndüren **true** varsa `left` önündeki ve eşit değildir `right` sıralama düzeninde.

### <a name="example"></a>Örnek

```cpp
// hash_multimap_key_comp.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;

   hash_multimap <int, int, hash_compare<int, less<int>>> hm1;
   hash_multimap <int, int, hash_compare<int, less<int>>
      >::key_compare kc1 = hm1.key_comp( ) ;
   bool result1 = kc1( 2, 3 ) ;
   if( result1 == true )
   {
      cout << "kc1( 2,3 ) returns value of true,\n"
           << "where kc1 is the function object of hm1.\n"
           << endl;
   }
   else
   {
      cout << "kc1( 2,3 ) returns value of false,\n"
           << "where kc1 is the function object of hm1.\n"
           << endl;
   }

   hash_multimap <int, int, hash_compare<int, greater<int>>> hm2;
   hash_multimap <int, int, hash_compare<int, greater<int>>
      >::key_compare kc2 = hm2.key_comp( );
   bool result2 = kc2( 2, 3 ) ;
   if( result2 == true )
   {
      cout << "kc2( 2,3 ) returns value of true,\n"
           << "where kc2 is the function object of hm2."
           << endl;
   }
   else
   {
      cout << "kc2( 2,3 ) returns value of false,\n"
           << "where kc2 is the function object of hm2."
           << endl;
   }
}
```

## <a name="key_compare"></a>  hash_multimap::key_compare

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).

Hash_multimap içindeki iki öğenin göreli sırasını belirlemek için iki sıralama anahtarını karşılaştıran işlev nesnesi sağlayan tür.

```cpp
typedef Traits key_compare;
```

### <a name="remarks"></a>Açıklamalar

`key_compare` Şablon parametresi için bir eşanlamlı olduğu *nitelikler*.

Daha fazla bilgi için *nitelikler* bkz [hash_multimap sınıfı](../standard-library/hash-multimap-class.md) konu.

### <a name="example"></a>Örnek

Örneğin bakın [key_comp](#key_comp) bildirme ve kullanma konusunda bir örnek için `key_compare`.

## <a name="key_type"></a>  hash_multimap::key_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).

Hash_multimap her öğesini oluşturan sıralama anahtarını nesnesini tanımlayan bir tür.

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Açıklamalar

`key_type` Şablon parametresi için bir eşanlamlı olduğu *anahtar*.

Daha fazla bilgi için *anahtarı*, Açıklamalar bölümüne bakın [hash_multimap sınıfı](../standard-library/hash-multimap-class.md) konu.

### <a name="example"></a>Örnek

Örneğin bakın [value_type](#value_type) bildirme ve kullanma konusunda bir örnek için `key_compare`.

## <a name="lower_bound"></a>  hash_multimap::lower_bound

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).

Bir yineleyiciyi belirtilen anahtardan daha büyük veya ona eşit bir anahtarla bir hash_multimap içindeki ilk öğeye döndürür.

```cpp
iterator lower_bound(const Key& key);

const_iterator lower_bound(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Aranan hash_multimap bir öğeyi sıralama anahtarı ile Karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Bir [yineleyici](#iterator) veya [const_iterator](#const_iterator) bağımsız değişken anahtardan daha büyük veya ona eşit olan veya sonra gelen konumu adresleyen son adresleri bir anahtarla bir hash_multimap içindeki bir öğenin konumunu ele hash_multimap anahtar için bir eşleşme varsa öğe.

Varsa dönüş değerinin `lower_bound` atanan bir `const_iterator`, hash_multimap nesnesi değiştirilemez. Varsa dönüş değerinin `lower_bound` atanan bir `iterator`, hash_multimap nesnesi değiştirilebilir.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_multimap_lower_bound.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multimap <int, int> hm1;
   hash_multimap <int, int> :: const_iterator hm1_AcIter,
      hm1_RcIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );
   hm1.insert ( Int_Pair ( 3, 20 ) );
   hm1.insert ( Int_Pair ( 3, 30 ) );

   hm1_RcIter = hm1.lower_bound( 2 );
   cout << "The element of hash_multimap hm1 with a key of 2 is: "
        << hm1_RcIter -> second << "." << endl;

   hm1_RcIter = hm1.lower_bound( 3 );
   cout << "The first element of hash_multimap hm1 with a key of 3 is: "
        << hm1_RcIter -> second << "." << endl;

   // If no match is found for the key, end( ) is returned
   hm1_RcIter = hm1.lower_bound( 4 );

   if ( hm1_RcIter == hm1.end( ) )
      cout << "The hash_multimap hm1 doesn't have an element "
           << "with a key of 4." << endl;
   else
      cout << "The element of hash_multimap hm1 with a key of 4 is: "
           << hm1_RcIter -> second << "." << endl;

   // The element at a specific location in the hash_multimap can be
   // found using a dereferenced iterator addressing the location
   hm1_AcIter = hm1.end( );
   hm1_AcIter--;
   hm1_RcIter = hm1.lower_bound( hm1_AcIter -> first );
   cout << "The first element of hm1 with a key matching"
        << endl << "that of the last element is: "
        << hm1_RcIter -> second << "." << endl;

   // Note that the first element with a key equal to
   // the key of the last element is not the last element
   if ( hm1_RcIter == --hm1.end( ) )
      cout << "This is the last element of hash_multimap hm1."
           << endl;
   else
      cout << "This is not the last element of hash_multimap hm1."
           << endl;
}
```

```Output
The element of hash_multimap hm1 with a key of 2 is: 20.
The first element of hash_multimap hm1 with a key of 3 is: 20.
The hash_multimap hm1 doesn't have an element with a key of 4.
The first element of hm1 with a key matching
that of the last element is: 20.
This is not the last element of hash_multimap hm1.
```

## <a name="mapped_type"></a>  hash_multimap::mapped_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).

Bir hash_multimap içinde depolanan veri türünü temsil eden tür.

```cpp
typedef Type mapped_type;
```

### <a name="remarks"></a>Açıklamalar

`mapped_type` Şablon parametresi için bir eşanlamlı olduğu *türü*.

Daha fazla bilgi için *türü* bkz [hash_multimap sınıfı](../standard-library/hash-multimap-class.md) konu.

### <a name="example"></a>Örnek

Örneğin bakın [value_type](#value_type) bildirme ve kullanma konusunda bir örnek için `key_type`.

## <a name="max_size"></a>  hash_multimap::max_size

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).

Hash_multimap maksimum uzunluğunu döndürür.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Hash_multimap maksimum olası uzunluğu.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_multimap_max_size.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multimap <int, int> hm1;
   hash_multimap <int, int> :: size_type i;

   i = hm1.max_size( );
   cout << "The maximum possible length "
        << "of the hash_multimap is " << i << "." << endl;
}
```

## <a name="op_eq"></a>  hash_multimap::operator =

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).

Hash_multimap öğelerini başka bir hash_multimap kopyasıyla değiştirir.

```cpp
hash_multimap& operator=(const hash_multimap& right);

hash_multimap& operator=(hash_multimap&& right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*sağ*|[Hash_multimap](../standard-library/hash-multimap-class.md) içine kopyalanan `hash_multimap`.|

### <a name="remarks"></a>Açıklamalar

Var olan tüm öğeleri silme sonra bir `hash_multimap`, `operator=` kopyalar veya içeriğini hareket *doğru* içine `hash_multimap`.

### <a name="example"></a>Örnek

```cpp
// hash_multimap_operator_as.cpp
// compile with: /EHsc
#include <hash_multimap>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multimap<int, int> v1, v2, v3;
   hash_multimap<int, int>::iterator iter;

   v1.insert(pair<int, int>(1, 10));

   cout << "v1 = " ;
   for (iter = v1.begin(); iter != v1.end(); iter++)
      cout << iter->second << " ";
   cout << endl;

   v2 = v1;
   cout << "v2 = ";
   for (iter = v2.begin(); iter != v2.end(); iter++)
      cout << iter->second << " ";
   cout << endl;

// move v1 into v2
   v2.clear();
   v2 = move(v1);
   cout << "v2 = ";
   for (iter = v2.begin(); iter != v2.end(); iter++)
      cout << iter->second << " ";
   cout << endl;
}
```

## <a name="pointer"></a>  hash_multimap::pointer

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).

Hash_multimap bir öğeye işaretçi sağlayan bir tür.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `pointer` bir öğenin değerini değiştirmek için kullanılabilir.

Çoğu durumda bir [yineleyici](#iterator) hash_multimap nesnesindeki öğelere erişmek için kullanılmalıdır.

## <a name="rbegin"></a>  hash_multimap::rbegin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).

Ters çevrilen hash_multimap içindeki ilk öğeyi ele alan bir yineleyici döndürür.

```cpp
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen hash_multimap ilk öğeyi ele alan veya ne ters çevrilmeyen hash_multimap içindeki son öğeyi adresleyen ters iki yönlü yineleyici.

### <a name="remarks"></a>Açıklamalar

`rbegin` ters çevrilen bir hash_multimap ile kullanılan gibi [başlamak](#begin) bir hash_multimap ile kullanılır.

Varsa dönüş değeri `rbegin` atanan bir `const_reverse_iterator`, sonra da hash_multimap nesnesi değiştirilemez. Varsa dönüş değeri `rbegin` atanan bir `reverse_iterator`, ardından hash_multimap nesnesi değiştirilebilir.

`rbegin` bir hash_multimap geriye doğru gezinmek için kullanılabilir.

### <a name="example"></a>Örnek

```cpp
// hash_multimap_rbegin.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multimap <int, int> hm1;

   hash_multimap <int, int> :: iterator hm1_Iter;
   hash_multimap <int, int> :: reverse_iterator hm1_rIter;
   hash_multimap <int, int> :: const_reverse_iterator hm1_crIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );
   hm1.insert ( Int_Pair ( 3, 30 ) );

   hm1_rIter = hm1.rbegin( );
   cout << "The first element of the reversed hash_multimap hm1 is "
        << hm1_rIter -> first << "." << endl;

   // begin can be used to start an iteration
   // through a hash_multimap in a forward order
   cout << "The hash_multimap is: ";
   for ( hm1_Iter = hm1.begin( ) ; hm1_Iter != hm1.end( ); hm1_Iter++)
      cout << hm1_Iter -> first << " ";
      cout << "." << endl;

   // rbegin can be used to start an iteration
   // through a hash_multimap in a reverse order
   cout << "The reversed hash_multimap is: ";
   for ( hm1_rIter = hm1.rbegin( ) ; hm1_rIter != hm1.rend( ); hm1_rIter++)
      cout << hm1_rIter -> first << " ";
      cout << "." << endl;

   // A hash_multimap element can be erased by dereferencing its key
   hm1_rIter = hm1.rbegin( );
   hm1.erase ( hm1_rIter -> first );

   hm1_rIter = hm1.rbegin( );
   cout << "After the erasure, the first element\n"
        << "in the reversed hash_multimap is "
        << hm1_rIter -> first << "." << endl;
}
```

```Output
The first element of the reversed hash_multimap hm1 is 3.
The hash_multimap is: 1 2 3 .
The reversed hash_multimap is: 3 2 1 .
After the erasure, the first element
in the reversed hash_multimap is 2.
```

## <a name="reference"></a>  hash_multimap::Reference

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).

Bir hash_multimap içinde depolanan öğeye başvuru sağlayan bir tür.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::reference reference;
```

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_multimap_reference.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multimap <int, int> hm1;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );

   // Declare and initialize a const_reference &Ref1
   // to the key of the first element
   const int &Ref1 = ( hm1.begin( ) -> first );

   // The following line would cause an error as the
   // non-const_reference cannot be used to access the key
   // int &Ref1 = ( hm1.begin( ) -> first );

   cout << "The key of first element in the hash_multimap is "
        << Ref1 << "." << endl;

   // Declare and initialize a reference &Ref2
   // to the data value of the first element
   int &Ref2 = ( hm1.begin( ) -> second );

   cout << "The data value of first element in the hash_multimap is "
        << Ref2 << "." << endl;

   //The non-const_reference can be used to modify the
   //data value of the first element
   Ref2 = Ref2 + 5;
   cout << "The modified data value of first element is "
        << Ref2 << "." << endl;
}
```

```Output
The key of first element in the hash_multimap is 1.
The data value of first element in the hash_multimap is 10.
The modified data value of first element is 15.
```

## <a name="rend"></a>  hash_multimap::rend

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).

Ters çevrilen hash_multimap içindeki son öğeden sonra gelen konumu ele alan bir yineleyici döndürür.

```cpp
const_reverse_iterator rend() const;

reverse_iterator rend();
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir hash_multimap (ters çevrilmeyen hash_multimap ilk öğeyi önce gelen konum) içindeki son öğeden sonra gelen konumu ele ters iki yönlü yineleyici.

### <a name="remarks"></a>Açıklamalar

`rend` ters çevrilen bir hash_multimap ile kullanılan gibi [son](#end) bir hash_multimap ile kullanılır.

Varsa dönüş değeri `rend` atanan bir [const_reverse_iterator](#const_reverse_iterator), sonra da hash_multimap nesnesi değiştirilemez. Varsa dönüş değeri `rend` atanan bir [reverse_iterator](#reverse_iterator), ardından hash_multimap nesnesi değiştirilebilir.

`rend` olup ters yineleyici kendi hash_multimap sonuna ulaşıp ulaşmadığını test etmek için kullanılabilir.

Tarafından döndürülen değer `rend` kaldırılmamalıdır.

### <a name="example"></a>Örnek

```cpp
// hash_multimap_rend.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multimap <int, int> hm1;

   hash_multimap <int, int> :: iterator hm1_Iter;
   hash_multimap <int, int> :: reverse_iterator hm1_rIter;
   hash_multimap <int, int> :: const_reverse_iterator hm1_crIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );
   hm1.insert ( Int_Pair ( 3, 30 ) );

   hm1_rIter = hm1.rend( );
   hm1_rIter--;
   cout << "The last element of the reversed hash_multimap hm1 is "
        << hm1_rIter -> first << "." << endl;

   // begin can be used to start an iteration
   // through a hash_multimap in a forward order
   cout << "The hash_multimap is: ";
   for ( hm1_Iter = hm1.begin( ) ; hm1_Iter != hm1.end( ); hm1_Iter++)
      cout << hm1_Iter -> first << " ";
      cout << "." << endl;

   // rbegin can be used to start an iteration
   // through a hash_multimap in a reverse order
   cout << "The reversed hash_multimap is: ";
   for ( hm1_rIter = hm1.rbegin( ) ; hm1_rIter != hm1.rend( ); hm1_rIter++)
      cout << hm1_rIter -> first << " ";
      cout << "." << endl;

   // A hash_multimap element can be erased by dereferencing its key
   hm1_rIter = --hm1.rend( );
   hm1.erase ( hm1_rIter -> first );

   hm1_rIter = hm1.rend( );
   hm1_rIter--;
   cout << "After the erasure, the last element "
        << "in the reversed hash_multimap is "
        << hm1_rIter -> first << "." << endl;
}
```

```Output
The last element of the reversed hash_multimap hm1 is 1.
The hash_multimap is: 1 2 3 .
The reversed hash_multimap is: 3 2 1 .
After the erasure, the last element in the reversed hash_multimap is 2.
```

## <a name="reverse_iterator"></a>  hash_multimap::reverse_iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).

Okuyabilen veya değiştirebilen bir ters hash_multimap içindeki bir öğeyi çift yönlü yineleyiciler sağlayan tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::reverse_iterator reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `reverse_iterator` tersten hash_multimap yinelemek için kullanılır.

`reverse_iterator` Nesnelerin hash_multimap noktalarına göre tanımlanan [value_type](#value_type), türü olan `pair` \< **const Key, türü**>. Anahtar değeri ilk üye çift kullanılabilir ve eşlenen öğenin değeri çiftinin ikinci üye kullanılabilir.

### <a name="example"></a>Örnek

Örneğin bakın [rbegin](#rbegin) bildirme ve kullanma konusunda bir örnek için `reverse_iterator`.

## <a name="size"></a>  hash_multimap::size

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).

Hash_multimap öğelerin sayısını döndürür.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Hash_multimap geçerli uzunluğu.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

Aşağıdaki örnek, hash_multimap::size üye işlevinin kullanımını gösterir.

```cpp
// hash_multimap_size.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
    using namespace std;
    using namespace stdext;
    hash_multimap<int, int> hm1, hm2;
    hash_multimap<int, int>::size_type i;
    typedef pair<int, int> Int_Pair;

    hm1.insert(Int_Pair(1, 1));
    i = hm1.size();
    cout << "The hash_multimap length is " << i << "." << endl;

    hm1.insert(Int_Pair(2, 4));
    i = hm1.size();
    cout << "The hash_multimap length is now " << i << "." << endl;
}
```

```Output
The hash_multimap length is 1.
The hash_multimap length is now 2.
```

## <a name="size_type"></a>  hash_multimap::size_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).

Bir hash_multimap içindeki öğelerin sayısını sayar bir işaretsiz tamsayı türü.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::size_type size_type;
```

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

Örneğin bakın [boyutu](#size) bildirme ve kullanma örneği `size_type`

## <a name="swap"></a>  hash_multimap::Swap

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).

İki hash_multimaps öğelerini birbiriyle değiştirir.

```cpp
void swap(hash_multimap& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Değiştirilecek öğeleri sağlayan hash_multimap veya öğeleri hash_multimap olanlar değiştirilecek olan hash_multimap.

### <a name="remarks"></a>Açıklamalar

Üye işlev hiçbir başvurular, işaretçiler veya öğeleri değiştirilen iki hash_multimaps öğelerinde belirlemek yineleyicileri geçersiz kılar.

### <a name="example"></a>Örnek

```cpp
// hash_multimap_swap.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multimap <int, int> hm1, hm2, hm3;
   hash_multimap <int, int>::iterator hm1_Iter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );
   hm1.insert ( Int_Pair ( 3, 30 ) );
   hm2.insert ( Int_Pair ( 10, 100 ) );
   hm2.insert ( Int_Pair ( 20, 200 ) );
   hm3.insert ( Int_Pair ( 30, 300 ) );

   cout << "The original hash_multimap hm1 is:";
   for ( hm1_Iter = hm1.begin( ); hm1_Iter != hm1.end( ); hm1_Iter++ )
      cout << " " << hm1_Iter -> second;
   cout   << "." << endl;

   // This is the member function version of swap
   hm1.swap( hm2 );

   cout << "After swapping with hm2, hash_multimap hm1 is:";
   for ( hm1_Iter = hm1.begin( ); hm1_Iter != hm1.end( ); hm1_Iter++ )
      cout << " " << hm1_Iter -> second;
   cout  << "." << endl;

   // This is the specialized template version of swap
   swap( hm1, hm3 );

   cout << "After swapping with hm3, hash_multimap hm1 is:";
   for ( hm1_Iter = hm1.begin( ); hm1_Iter != hm1.end( ); hm1_Iter++ )
      cout << " " << hm1_Iter -> second;
   cout   << "." << endl;
}
```

```Output
The original hash_multimap hm1 is: 10 20 30.
After swapping with hm2, hash_multimap hm1 is: 100 200.
After swapping with hm3, hash_multimap hm1 is: 300.
```

## <a name="upper_bound"></a>  hash_multimap::upper_bound

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).

Bir yineleyiciyi belirtilen anahtardan daha büyük bir anahtarla bir hash_multimap içindeki ilk öğeye döndürür.

```cpp
iterator upper_bound(const Key& key);

const_iterator upper_bound(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Aranan hash_multimap bir öğeyi sıralama anahtarı ile Karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Bir [yineleyici](#iterator) veya [const_iterator](#const_iterator) bağımsız değişken anahtardan daha büyük veya içindeki son öğeyi takip eden konumu ele bir anahtara sahip bir hash_multimap içindeki bir öğenin konumunu adresleri hash_multimap anahtar için bir eşleşme.

Varsa dönüş değerinin `upper_bound` atanan bir `const_iterator`, hash_multimap nesnesi değiştirilemez. Varsa dönüş değerinin `upper_bound` atanan bir `iterator`, hash_multimap nesnesi değiştirilebilir.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_multimap_upper_bound.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multimap <int, int> hm1;
   hash_multimap <int, int> :: const_iterator hm1_AcIter, hm1_RcIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );
   hm1.insert ( Int_Pair ( 3, 30 ) );
   hm1.insert ( Int_Pair ( 3, 40 ) );

   hm1_RcIter = hm1.upper_bound( 1 );
   cout << "The 1st element of hash_multimap hm1 with "
        << "a key greater than 1 is: "
        << hm1_RcIter -> second << "." << endl;

   hm1_RcIter = hm1.upper_bound( 2 );
   cout << "The first element of hash_multimap hm1\n"
        << "with a key greater than 2 is: "
        << hm1_RcIter -> second << "." << endl;

   // If no match is found for the key, end( ) is returned
   hm1_RcIter = hm1.lower_bound( 4 );

   if ( hm1_RcIter == hm1.end( ) )
      cout << "The hash_multimap hm1 doesn't have an element "
           << "with a key of 4." << endl;
   else
      cout << "The element of hash_multimap hm1 with a key of 4 is: "
           << hm1_RcIter -> second << "." << endl;

   // The element at a specific location in the hash_multimap can be
   // found using a dereferenced iterator addressing the location
   hm1_AcIter = hm1.begin( );
   hm1_RcIter = hm1.upper_bound( hm1_AcIter -> first );
   cout << "The first element of hm1 with a key greater than"
        << endl << "that of the initial element of hm1 is: "
        << hm1_RcIter -> second << "." << endl;
}
```

```Output
The 1st element of hash_multimap hm1 with a key greater than 1 is: 20.
The first element of hash_multimap hm1
with a key  greater than 2 is: 30.
The hash_multimap hm1 doesn't have an element with a key of 4.
The first element of hm1 with a key greater than
that of the initial element of hm1 is: 20.
```

## <a name="value_comp"></a>  hash_multimap::value_comp

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).

Üye işlevi, anahtar değerlerini karşılaştırarak bir hash_multimap içindeki öğelerin sırasını belirleyen bir işlev nesnesi döndürür.

```cpp
value_compare value_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Alt öğeleri düzenlemek amacıyla bir hash_multimap kullanan karşılaştırma işlevi nesnesini döndürür.

### <a name="remarks"></a>Açıklamalar

Bir hash_multimap için *m*, iki öğe *e1* (*k1*, *d1*) ve *e2*(*k2* , *d2*) türündeki nesneler [value_type](#value_type)burada *k1* ve *k2* türü kendianahtarları[key_type](#key_type) ve *d1* ve *d2* kendi veri türü olan [mapped_type](#mapped_type), ardından `m.value_comp()(e1, e2)` eşdeğerdir `m.key_comp()(k1, k2)` . Depolanan bir nesne üye işlevini tanımlar.

`bool operator( value_type& left, value_type& right);`

döndüren **true** , anahtar değerini `left` önündeki ve anahtar değerine eşit değil `right` sıralama düzeninde.

### <a name="example"></a>Örnek

```cpp
// hash_multimap_value_comp.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;

   hash_multimap <int, int, hash_compare<int, less<int>>> hm1;
   hash_multimap <int, int, hash_compare<int, less<int>>
      >::value_compare vc1 = hm1.value_comp( );
   hash_multimap <int,int>::iterator Iter1, Iter2;

   Iter1= hm1.insert ( hash_multimap <int, int> :: value_type ( 1, 10 ) );
   Iter2= hm1.insert ( hash_multimap <int, int> :: value_type ( 2, 5 ) );

   if( vc1( *Iter1, *Iter2 ) == true )
   {
      cout << "The element ( 1,10 ) precedes the element ( 2,5 )."
           << endl;
   }
   else
   {
      cout << "The element ( 1,10 ) does "
           << "not precede the element ( 2,5 )."
           << endl;
   }

   if( vc1( *Iter2, *Iter1 ) == true )
   {
      cout << "The element ( 2,5 ) precedes the element ( 1,10 )."
           << endl;
   }
   else
   {
      cout << "The element ( 2,5 ) does "
           << "not precede the element ( 1,10 )."
           << endl;
   }
}
```

## <a name="value_type"></a>  hash_multimap::value_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).

İçinde bir hash_multimap depolanan nesne türünü temsil eden tür.

```cpp
typedef pair<const Key, Type> value_type;
```

### <a name="remarks"></a>Açıklamalar

`value_type` çifti olarak bildirilmiştir\<const [key_type](#key_type), [mapped_type](#mapped_type)> ve değil eşleştirin\<key_type, mapped_type > ilişkilendirilebilir bir kapsayıcı anahtarları değiştirilemez çünkü nonconstant yineleyici ya da başvuru kullanıyor.

### <a name="example"></a>Örnek

```cpp
// hash_multimap_value_type.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   typedef pair <const int, int> cInt2Int;
   hash_multimap <int, int> hm1;
   hash_multimap <int, int> :: key_type key1;
   hash_multimap <int, int> :: mapped_type mapped1;
   hash_multimap <int, int> :: value_type value1;
   hash_multimap <int, int> :: iterator pIter;

   // value_type can be used to pass the correct type
   // explicitely to avoid implicit type conversion
   hm1.insert ( hash_multimap <int, int> :: value_type ( 1, 10 ) );

   // Compare another way to insert objects into a hash_multimap
   hm1.insert ( cInt2Int ( 2, 20 ) );

   // Initializing key1 and mapped1
   key1 = ( hm1.begin( ) -> first );
   mapped1 = ( hm1.begin( ) -> second );

   cout << "The key of first element in the hash_multimap is "
        << key1 << "." << endl;

   cout << "The data value of first element in the hash_multimap is "
        << mapped1 << "." << endl;

   // The following line would cause an error because
   // the value_type is not assignable
   // value1 = cInt2Int ( 4, 40 );

   cout  << "The keys of the mapped elements are:";
   for ( pIter = hm1.begin( ) ; pIter != hm1.end( ) ; pIter++ )
      cout << " " << pIter -> first;
   cout << "." << endl;

   cout  << "The values of the mapped elements are:";
   for ( pIter = hm1.begin( ) ; pIter != hm1.end( ) ; pIter++ )
      cout << " " << pIter -> second;
   cout << "." << endl;
}
```

```Output
The key of first element in the hash_multimap is 1.
The data value of first element in the hash_multimap is 10.
The keys of the mapped elements are: 1 2.
The values of the mapped elements are: 10 20.
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
