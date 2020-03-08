---
title: hash_multimap Sınıfı
ms.date: 10/18/2018
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
ms.openlocfilehash: b42dd5ba4aa3df12e3ef1aba930b2214dde19756
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78856752"
---
# <a name="hash_multimap-class"></a>hash_multimap Sınıfı

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](../standard-library/unordered-multimap-class.md).

Kapsayıcı sınıfı hash_multimap C++ standart kitaplığın bir uzantısıdır ve her bir öğenin, değeri benzersiz olması gereken bir sıralama anahtarına ve ilişkili bir veri değerine sahip olan bir çifte veri depolama ve hızlı şekilde alınması için kullanılır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Key,
    class Type,
    class Traits=hash_compare <Key, less <Key>>,
    class Allocator=allocator <pair  <const Key, Type>>>
class hash_multimap
```

### <a name="parameters"></a>Parametreler

*Anahtar*\
Hash_multimap depolanacak anahtar veri türü.

*Tür*\
Hash_multimap depolanacak öğe veri türü.

*Nitelikler*\
İki işlev nesnesi içeren tür, iki öğe değerini, öğelerin bir birli koşul eşleme anahtar değerleri olan `size_t`türünde işaretsiz tamsayılar olan bir karma işlevi ve kendi göreli sıralarını ve bir karma işlevini tespit etmek için sıralama anahtarları olarak karşılaştırabilen bir sınıf *nitelikleri* . Bu bağımsız değişken isteğe bağlıdır ve `hash_compare<Key, less<Key>>` varsayılan değerdir.

*Ayırıcı*\
Hash_multimap, bellek ayırma ve ayırmayı kaldırma hakkındaki ayrıntıları kapsülleyen saklı ayırıcı nesnesini temsil eden tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `allocator<pair <const Key, Type>>`.

## <a name="remarks"></a>Açıklamalar

Hash_multimap:

- İlişkili bir anahtar değerine dayalı öğe değerlerinin verimli alınmasını destekleyen bir değişken boyutu kapsayıcı olan ilişkilendirilebilir bir kapsayıcı.

- Çift yönlüdür, çünkü öğelerine erişmek için çift yönlü bir yineleyici sağlar.

- Karma değeri, öğelerinin anahtar değerlerine uygulanan bir karma işlevin değerine bağlı olarak demet halinde gruplandığından karma hale getirilir.

- Öğelerinin benzersiz anahtarlara ihtiyacı olmaması için çokludur, böylece bir anahtar değer onunla ilişkili çok sayıda öğe verisi değerine sahip olabilir.

- Öğe değerleri anahtar değerlerinden farklı olduğundan, çift ilişkilendirilebilir bir kapsayıcı.

- Sınıf şablonu, sağladığı işlevsellik geneldir ve bu nedenle öğe veya anahtar olarak içerilen belirli veri türünden bağımsızdır. Öğeler ve anahtarlar için kullanılacak veri türleri, karşılaştırma işlevi ve ayırıcı ile birlikte bir sınıf şablonunda parametreler olarak belirtilir.

Sıralama üzerinden karmalamanın başlıca avantajı daha fazla verimlilik; başarılı bir karma değer ekleme, silme işlemleri gerçekleştirir ve sabit ortalama süre içinde, sıralama teknikleri için kapsayıcıdaki öğelerin sayısının logaritmasına kıyasla bir zaman orantılı olarak bulur. Bir hash_multimap öğenin değeri, ancak ilişkili anahtar değerini değil doğrudan değiştirilebilir. Bunun yerine, eski öğelerle ilişkili anahtar değerleri silinmeli ve eklenen yeni öğelerle ilişkili yeni anahtar değerleri eklenmelidir.

Kapsayıcı türünün seçimi genelde uygulamanın gerektirdiği arama ve ekleme türüne dayalı olmalıdır. Karma olarak ilişkilendirilebilir kapsayıcılar, arama, ekleme ve kaldırma işlemleri için iyileştirilmiştir. Bu işlemleri açıkça destekleyen üye işlevleri, iyi tasarlanmış bir karma işlevi ile kullanıldığında etkili olur ve bunları ortalama Sabitte olan ve kapsayıcıdaki öğelerin sayısına bağımlı olmayan bir zaman içinde gerçekleştiriyor. İyi tasarlanmış bir karma işlevi, karma değerler için Tekdüzen bir dağıtım üretir ve ayrı anahtar değerleri aynı karma değere eşlendiğinde bir çarpışmanın oluşmasına neden olan çakışmaların sayısını en aza indirir. En kötü durumda, mümkün olan en kötü karma işlevi olan işlem sayısı, dizideki öğelerin sayısıyla orantılıdır (doğrusal saat).

Değerleri, anahtar ile ilişkilendirirken, uygulama tarafından karşılandıkları durumlarda seçeneğin ilişkilendirilebilir kapsayıcısı olmalıdır. hash_multimap Bu tür bir yapı için model, mesela açıklamalar sağlayan dize değerleriyle ilişkili anahtar sözcüklerin sıralı bir listesidir, burada sözcükler her zaman benzersiz olarak tanımlanmamıştır. Bunun yerine, anahtar sözcükler benzersiz olacak şekilde benzersiz şekilde tanımlanmışsa, bir hash_map seçim kapsayıcısı olur. Diğer taraftan, yalnızca sözcüklerin listesi depolanmakta olduğundan, doğru kapsayıcı hash_set. Sözcüklerin birden çok örneğine izin veriliyorsa, hash_multiset uygun kapsayıcı yapısı olur.

Hash_multimap, [value_compare](../standard-library/value-compare-class.md)türünde depolanan bir karma `Traits` nesnesini çağırarak denetlediği sırayı sıralar. Bu saklı nesneye [key_comp](../standard-library/hash-map-class.md#key_comp)üye işlevi çağırarak erişilebilir. Böyle bir işlev nesnesi [hash_compare](../standard-library/hash-compare-class.md)`<Key, less<Key>>`sınıfının bir nesnesi ile aynı şekilde davranmalıdır. Özellikle, `Key`türündeki tüm değerler `Key`, çağrı `Traits (Key)` `size_t`bir değer dağıtımı verir.

Genelde, bu sıralamayı oluşturmak için öğelerin yalnızca küçüktür biçiminde karşılaştırılabilir olması gerekir; böylece, herhangi iki öğe belirtildiğinde, eşit oldukları (yani birinin diğerinden daha küçük olmadığı anlamında) veya birinin diğerinden küçük olduğu belirlenebilir. Bu, denk olmayan öğeler arasında bir sıralamaya neden olur. Daha teknik bir not üzerinde, karşılaştırma işlevi standart matematiksel anlamda katı bir zayıf sıralama sevk eden ikili bir koşuldur. Bir ikili koşul f (x, y), iki bağımsız değişken nesnesi olan bir işlev nesnesidir `x` ve `y` ve **true** ya da **false**dönüş değeri. İkili koşul geri dönüşsüz, antisimetrik ve geçişli ve denklik geçişli ise, hash_multimap uygulanan bir sıralama katı zayıf bir sıradır, burada iki nesne `x` ve `y` ikisi de f (x, y) ve f (y, x) **false**olduğunda denk olarak tanımlanır. Anahtarlar arasındaki eşitliğinin daha güçlü koşulu bu denkliğin yerini alırsa, sıralama (içindeki tüm öğelerin birbirine göre sıralanması anlamında) toplam haline gelir ve eşleşen anahtarlar birbirinden ayırt edilemez olacaktır.

Denetlenen dizideki öğelerin gerçek sırası, karma işleve, sıralama işlevine ve kapsayıcı nesnesinde depolanan karma tablonun geçerli boyutuna bağlıdır. Karma tablonun geçerli boyutunu belirleyemez, bu nedenle denetimli dizideki öğelerin sırasını genel olarak tahmin edemezsiniz. Öğelerin eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; öğelerin kaldırılması yalnızca özellikle kaldırılan öğeleri gösteren yineleyicileri geçersiz kılar.

Hash_multimap sınıfı tarafından verilen yineleyici çift yönlü bir yineleyicidir, ancak [Insert](#insert) ve [hash_multimap](#hash_multimap) sınıf üyesi işlevleri, şablon parametresi olarak daha zayıf bir giriş yineleyicisini alan, işlevsellik gereksinimleri çift yönlü yineleyicilerin sınıfına göre garantiden daha düşük olan sürümlere sahiptir. Farklı yineleyici kavramları, işlevselliklerindeki iyileştirmelere göre ilgili bir aile biçimlendirir. Her Yineleyici kavramının kendi gereksinimleri hash_multimap vardır ve bunlarla çalışan algoritmaların kendi varsayımları, bu tür Yineleyici tarafından belirtilen gereksinimlere göre sınırlandırmalıdır. Bir giriş yineleyicinin bazı nesnelere başvurusunun kaldırılacağı ve dizideki sonraki yineleyiciye artırılabileceği varsayılabilir. Bu, işlevselliğin en az bir hash_multimap, ancak üye işlevleri bağlamında `[First, Last)` bir dizi yineleyiciler hakkında anlamlı bir şekilde konuşabilmek için yeterlidir.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[hash_multimap](#hash_multimap)|Belirli bir boyutun veya belirli bir değere sahip olan ya da belirli bir `allocator` veya başka bir `hash_multimap`kopyası olan öğelerin bir listesini oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[allocator_type](#allocator_type)|`hash_multimap` nesnesi için `allocator` sınıfını temsil eden bir tür.|
|[const_iterator](#const_iterator)|`hash_multimap``const` bir öğeyi okuyabilen çift yönlü bir yineleyici sağlayan bir tür.|
|[const_pointer](#const_pointer)|`hash_multimap`bir **const** öğesine işaretçi sağlayan bir tür.|
|[const_reference](#const_reference)|**Const** işlemlerini okumak ve gerçekleştirmek için bir `hash_multimap` depolanan **const** öğesine başvuru sağlayan bir tür.|
|[const_reverse_iterator](#const_reverse_iterator)|`hash_multimap`herhangi bir **const** öğesini okuyabilen çift yönlü bir yineleyici sağlayan bir tür.|
|[difference_type](#difference_type)|Yineleyiciler tarafından gösterilen öğeler arasındaki bir aralıktaki `hash_multimap` öğelerinin sayısını temsil etmek için kullanılabilen işaretli bir tamsayı türü.|
|[iden](#iterator)|Bir `hash_multimap`herhangi bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleyici sağlayan bir tür.|
|[key_compare](#key_compare)|`hash_multimap`iki öğenin göreli sırasını belirleyebilmek için iki sıralama anahtarını karşılaştıran bir işlev nesnesi sağlayan bir tür.|
|[key_type](#key_type)|`hash_multimap`her bir öğesini oluşturan sıralama anahtarı nesnesini açıklayan bir tür.|
|[mapped_type](#mapped_type)|`hash_multimap`depolanan veri türünü temsil eden bir tür.|
|[çağrısı](#pointer)|`hash_multimap`bir öğeye işaretçi sağlayan bir tür.|
|[başvurunun](#reference)|`hash_multimap`depolanan bir öğeye başvuru sağlayan bir tür.|
|[reverse_iterator](#reverse_iterator)|Ters çevrilen bir `hash_multimap`bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleyici sağlayan bir tür.|
|[size_type](#size_type)|Bir `hash_multimap`öğe sayısını temsil eden işaretsiz bir tamsayı türü.|
|[value_type](#value_type)|`hash_multimap`ilişkili sıralarını belirleyebilmek için sıralama anahtarları olarak iki öğeyi karşılaştıran bir işlev nesnesi sağlayan bir tür.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[başladı](#begin)|`hash_multimap`ilk öğeyi adresleyen bir yineleyici döndürür.|
|[cbegin](#cbegin)|`hash_multimap`ilk öğeyi adresleyen bir const yineleyici döndürür.|
|[cend](#cend)|`hash_multimap`son öğeden sonraki konumu ele alan bir const yineleyici döndürür.|
|[lediğiniz](#clear)|`hash_multimap`tüm öğelerini siler.|
|[count](#count)|Anahtarı parametre tarafından belirtilen anahtarla eşleşen bir `hash_multimap` öğe sayısını döndürür.|
|[crbegin](#crbegin)|Ters çevrilen `hash_multimap`ilk öğeyi adresleyen bir const yineleyici döndürür.|
|[crend](#crend)|Ters çevrilen `hash_multimap`son öğeden sonraki konumu ele alan bir const yineleyici döndürür.|
|[Emplace](#emplace)|Bir `hash_multimap`içinde oluşturulmuş bir öğe ekler.|
|[emplace_hint](#emplace_hint)|Yerleştirme ipucuyla birlikte `hash_multimap`oluşturulan bir öğe ekler.|
|[olmamalıdır](#empty)|`hash_multimap` boş ise sınar.|
|[erer](#end)|`hash_multimap`son öğeden sonraki konumu ele alan bir yineleyici döndürür.|
|[equal_range](#equal_range)|`hash_multimap`son öğeden sonraki konumu ele alan bir yineleyici döndürür.|
|[silme](#erase)|Belirtilen konumlardan bir `hash_multimap` öğe veya öğe aralığını kaldırır|
|[find](#find)|Belirtilen anahtara eşdeğer bir anahtara sahip bir `hash_multimap` öğenin konumunu ele alan bir yineleyici döndürür.|
|[get_allocator](#get_allocator)|`hash_multimap`oluşturmak için kullanılan `allocator` nesnesinin bir kopyasını döndürür.|
|[ekleyin](#insert)|Belirtilen konumdaki `hash_multimap` bir öğe veya öğe aralığı ekler.|
|[key_comp](#key_comp)|`hash_multimap`anahtarları sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır.|
|[lower_bound](#lower_bound)|Bir yineleyiciyi belirtilen anahtardan daha büyük veya ona eşit bir anahtar değeri olan bir `hash_multimap` ilk öğeye döndürür.|
|[max_size](#max_size)|`hash_multimap`maksimum uzunluğunu döndürür.|
|[rbegin](#rbegin)|Ters çevrilen `hash_multimap`ilk öğeyi adresleyen bir yineleyici döndürür.|
|[rend](#rend)|Ters çevrilen `hash_multimap`son öğeden sonraki konumu ele alan bir yineleyici döndürür.|
|[boyutla](#size)|`hash_multimap`için yeni bir boyut belirtir.|
|[Kur](#swap)|İki `hash_multimap`öğelerini değiş tokuş eder.|
|[upper_bound](#upper_bound)|Bir yineleyiciyi belirtilen anahtardan daha büyük bir anahtar değeri olan bir `hash_multimap` ilk öğeye döndürür.|
|[value_comp](#value_comp)|Bir `hash_multimap`öğe değerlerini sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[hash_multimap:: operator =](#op_eq)|`hash_multimap` öğelerini başka bir `hash_multimap`kopyasıyla değiştirir.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<hash_map >

**Ad alanı:** stdext

## <a name="allocator_type"></a>hash_multimap:: allocator_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](../standard-library/unordered-multimap-class.md).

Hash_multimap nesnesinin ayırıcı sınıfını temsil eden bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::allocator_type allocator_type;
```

### <a name="remarks"></a>Açıklamalar

`allocator_type`, şablon parametresi `Allocator`için bir eş anlamlı.

`Allocator`hakkında daha fazla bilgi için [hash_multimap sınıfı](../standard-library/hash-multimap-class.md) konusunun açıklamalar bölümüne bakın.

### <a name="example"></a>Örnek

`allocator_type`kullanarak bir örnek için [get_allocator](#get_allocator) örneğe bakın.

## <a name="begin"></a>hash_multimap:: Begin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](../standard-library/unordered-multimap-class.md).

Hash_multimap ilk öğeyi adresleyen bir yineleyici döndürür.

```cpp
const_iterator begin() const;

iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

Hash_multimap ilk öğeyi adresleyen çift yönlü yineleyici veya konum boş bir hash_multimap başarılı oluyor.

### <a name="remarks"></a>Açıklamalar

`begin` dönüş değeri bir `const_iterator`atanırsa hash_multimap nesnesindeki öğeler değiştirilemez. `begin` dönüş değeri bir `iterator`atanırsa hash_multimap nesnesindeki öğeler değiştirilebilir.

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

## <a name="cbegin"></a>hash_multimap:: cbegin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](../standard-library/unordered-multimap-class.md).

Hash_multimap ilk öğeyi adresleyen bir const yineleyici döndürür.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

[Hash_multimap](../standard-library/hash-multimap-class.md) ilk öğeyi adresleyen bir const çift yönlü yineleyici veya konum boş bir `hash_multimap`başarılı oluyor.

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

## <a name="cend"></a>hash_multimap:: cend

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](../standard-library/unordered-multimap-class.md).

Hash_multimap son öğeden sonraki konumu ele alan bir const yineleyici döndürür.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir [hash_multimap](../standard-library/hash-multimap-class.md)son öğeden sonraki konumu ele alan bir const çift yönlü Yineleyici. `hash_multimap` boşsa, `hash_multimap::cend == hash_multimap::begin`.

### <a name="remarks"></a>Açıklamalar

`cend`, bir yineleyicinin hash_multimap sonuna ulaşılıp ulaşılmadığını test etmek için kullanılır.

`cend` tarafından döndürülen değer başvurulmamalıdır.

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

## <a name="clear"></a>hash_multimap:: Clear

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](../standard-library/unordered-multimap-class.md).

Hash_multimap tüm öğelerini siler.

```cpp
void clear();
```

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

Aşağıdaki örnek hash_multimap:: Clear üye işlevinin kullanımını gösterir.

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

## <a name="const_iterator"></a>hash_multimap:: const_iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](../standard-library/unordered-multimap-class.md).

Hash_multimap bir **const** öğesini okuyabilen çift yönlü bir yineleyici sağlayan bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_iterator const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_iterator`, bir öğenin değerini değiştirmek için kullanılamaz.

Hash_multimap tarafından tanımlanan `const_iterator`, `pair<const Key, Type>`türünde olan [value_type](#value_type)nesnelerine işaret eder. Anahtarın değeri ilk üye çifti üzerinden kullanılabilir ve eşlenmiş öğenin değeri, çiftin ikinci üyesi üzerinden kullanılabilir.

Bir `const_iterator` başvuru yapmak için, bir hash_multimap bir öğeye işaret eden `cIter` `->` işlecini kullanın.

Öğesinin anahtar değerine erişmek için, `(*cIter).first`eşdeğer olan `cIter->first`kullanın. Öğesi için eşlenen veri değerine erişmek için, `(*cIter).second`eşdeğer olan `cIter->second`kullanın.

### <a name="example"></a>Örnek

`const_iterator`kullanarak bir örnek için [Begin](#begin) örneğine bakın.

## <a name="const_pointer"></a>hash_multimap:: const_pointer

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](../standard-library/unordered-multimap-class.md).

Hash_multimap bir **const** öğesine işaretçi sağlayan bir tür.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::const_pointer const_pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_pointer`, bir öğenin değerini değiştirmek için kullanılamaz.

Çoğu durumda, bir [yineleyici](#iterator) hash_multimap nesnesindeki öğelere erişmek için kullanılmalıdır.

## <a name="const_reference"></a>hash_multimap:: const_reference

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](../standard-library/unordered-multimap-class.md).

**Const** işlemlerini okumak ve gerçekleştirmek için bir hash_multimap depolanan **const** öğesine başvuru sağlayan bir tür.

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

## <a name="const_reverse_iterator"></a>hash_multimap:: const_reverse_iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](../standard-library/unordered-multimap-class.md).

Hash_multimap herhangi bir **const** öğesini okuyabilen çift yönlü bir yineleyici sağlayan bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_reverse_iterator const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_reverse_iterator`, bir öğenin değerini değiştiremez ve hash_multimap geri doğru bir şekilde yinelemek için kullanılır.

Hash_multimap tarafından tanımlanan `const_reverse_iterator`, ilk üyesi öğe için anahtar olan ve ikinci üye öğesi tarafından tutulan eşlenmiş veri olan `pair<const Key, Type>`türünde olan [value_type](#value_type)nesnelerine işaret eder.

Bir `const_reverse_iterator` başvuru yapmak için, bir hash_multimap bir öğeye işaret eden `crIter` `->` işlecini kullanın.

Öğesinin anahtar değerine erişmek için, `(*crIter).first`eşdeğer olan `crIter->first`kullanın. Öğesi için eşlenen veri değerine erişmek için, `(*crIter).second`eşdeğer olan `crIter->second`kullanın.

### <a name="example"></a>Örnek

`const_reverse_iterator`bildirme ve kullanma hakkında bir örnek için bkz. [rend](#rend) örneği.

## <a name="count"></a>hash_multimap:: Count

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](../standard-library/unordered-multimap-class.md).

Anahtarı parametre tarafından belirtilen anahtarla eşleşen bir hash_multimap öğe sayısını döndürür.

```cpp
size_type count(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*anahtar*\
Hash_multimap eşleştirilecek öğelerin anahtarı.

### <a name="return-value"></a>Dönüş Değeri

hash_multimap sıralama anahtarı parametre anahtarıyla eşleşen bir öğe içeriyorsa, 1. hash_multimap eşleşen bir anahtara sahip bir öğe içermiyorsa 0.

### <a name="remarks"></a>Açıklamalar

Üye işlevi aralıktaki öğe sayısını döndürür

**[lower_bound (** `key` **), upper_bound (** `key` **))**

bir anahtar değeri *anahtarına*sahiptir.

### <a name="example"></a>Örnek

Aşağıdaki örnek hash_multimap:: Count üye işlevinin kullanımını gösterir.

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

## <a name="crbegin"></a>hash_multimap:: crbegin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](../standard-library/unordered-multimap-class.md).

Ters çevrilen hash_multimap ilk öğeyi adresleyen bir const yineleyici döndürür.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir [hash_multimap](../standard-library/hash-multimap-class.md) ilk öğeyi ele alarak veya geri alınamaz `hash_multimap`son öğe olduğunu adresleyen bir const ters çift yönlü Yineleyici.

### <a name="remarks"></a>Açıklamalar

`crbegin`, [hash_multimap:: Begin](#begin) bir `hash_multimap`ile birlikte kullanılan bir ters hash_multimap ile kullanılır.

`crbegin`dönüş değeri ile `hash_multimap` nesnesi değiştirilemez.

`crbegin`, `hash_multimap` geriye doğru yinelemek için kullanılabilir.

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

## <a name="crend"></a>hash_multimap:: crend

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](../standard-library/unordered-multimap-class.md).

Ters çevrilen hash_multimap son öğeden sonraki konumu ele alan bir const yineleyici döndürür.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir [hash_multimap](../standard-library/hash-multimap-class.md) en son öğeden sonra gelen konumu ele alan sabit ters çift yönlü yineleyici (geri alınamaz `hash_multimap`ilk öğeden önce gelen konum).

### <a name="remarks"></a>Açıklamalar

`crend`, [hash_multimap:: End](#end) bir hash_multimap ile birlikte kullanılan ters bir hash_multimap ile kullanılır.

`crend`dönüş değeri ile `hash_multimap` nesnesi değiştirilemez.

`crend`, geriye doğru bir yineleyicinin hash_multimap sonuna ulaşıp ulaşılmadığını test etmek için kullanılabilir.

`crend` tarafından döndürülen değer başvurulmamalıdır.

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

## <a name="difference_type"></a>hash_multimap::d ifference_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](../standard-library/unordered-multimap-class.md).

Yineleyiciler tarafından gösterilen öğeler arasındaki bir aralıktaki hash_multimap öğelerinin sayısını temsil etmek için kullanılabilen işaretli bir tamsayı türü.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

`difference_type` kapsayıcının yineleyiciler aracılığıyla çıkartılacak veya arttırılarak döndürülen türdür. `difference_type`, genellikle yineleyiciler `first` ve `last`arasındaki *[ilk, son)* aralıktaki öğelerin sayısını temsil etmek için kullanılır, `first` tarafından işaret edilen öğe ve dahil olmak üzere öğe aralığı, `last`tarafından işaret edilen öğeyi içerir.

Bir giriş yineleyicisinin gereksinimlerini karşılayan tüm yineleyiciler için `difference_type` kullanılabilir olsa da, yineleyiciler arasındaki çıkarma işlemi, yineleyiciler arasındaki çıkarma, yalnızca vektör gibi bir rastgele erişim kapsayıcısı tarafından sağlanan rastgele erişim yineleyiciler tarafından desteklenir.

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

## <a name="emplace"></a>hash_multimap:: emplace

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](../standard-library/unordered-multimap-class.md).

Bir hash_multimap içinde oluşturulmuş bir öğe ekler.

```cpp
template <class ValTy>
iterator emplace(ValTy&& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Acil*|[Hash_multimap](../standard-library/hash-multimap-class.md)içine eklenecek bir öğe oluşturmak için kullanılan değer.|

### <a name="return-value"></a>Dönüş Değeri

`emplace` member işlevi, yeni öğenin eklendiği konuma işaret eden bir yineleyici döndürür.

### <a name="remarks"></a>Açıklamalar

Bir öğenin [hash_multimap:: value_type](#value_type) bir çifttir, böylece bir öğe değeri, ilk bileşeni anahtar değerine eşit olan ve ikinci bileşen öğenin veri değerine eşit olan bir sıralı çift olacaktır.

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

## <a name="emplace_hint"></a>hash_multimap:: emplace_hint

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](../standard-library/unordered-multimap-class.md).

Yerleştirme ipucuyla birlikte hash_multimap oluşturulan bir öğe ekler.

```cpp
template <class ValTy>
iterator emplace_hint(
    const_iterator _Where,
    ValTy&& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Acil*|`hash_multimap` zaten bu öğeyi (veya daha genel olarak, anahtarı equivalently sıralı bir öğe) içermiyorsa, bir öğeyi [hash_multimap](../standard-library/hash-multimap-class.md) içine eklenecek şekilde taşıma için kullanılan değer.|
|*_Where*|Doğru ekleme noktasını aramaya başlamak için yer hakkında bir ipucu.|

### <a name="return-value"></a>Dönüş Değeri

[Hash_multimap:: emplace](#emplace) üye işlevi, yeni öğenin `hash_multimap`eklendiği konuma işaret eden bir yineleyici döndürür.

### <a name="remarks"></a>Açıklamalar

Bir öğenin [hash_multimap:: value_type](#value_type) bir çifttir, böylece bir öğe değeri, ilk bileşeni anahtar değerine eşit olan ve ikinci bileşen öğenin veri değerine eşit olan bir sıralı çift olacaktır.

Ekleme noktası *_Where*hemen ardından, ekleme noktası, logaritmik bir süre yerine, sabit zamanlı olarak meydana gelebilir.

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

## <a name="empty"></a>hash_multimap:: boş

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](../standard-library/unordered-multimap-class.md).

Hash_multimap boş ise sınar.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

hash_multimap boşsa **true** ; hash_multimap boş değilse **false** .

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

## <a name="end"></a>hash_multimap:: End

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](../standard-library/unordered-multimap-class.md).

Hash_multimap son öğeden sonraki konumu ele alan bir yineleyici döndürür.

```cpp
const_iterator end() const;

iterator end();
```

### <a name="return-value"></a>Dönüş Değeri

Bir hash_multimap son öğeden sonraki konumu ele alan çift yönlü bir yineleyici. Hash_multimap boşsa, hash_multimap:: End = = hash_multimap:: BEGIN.

### <a name="remarks"></a>Açıklamalar

`end`, bir yineleyicinin hash_multimap sonuna ulaşılıp ulaşılmadığını test etmek için kullanılır.

`end` tarafından döndürülen değer başvurulmamalıdır.

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

## <a name="equal_range"></a>hash_multimap:: equal_range

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](../standard-library/unordered-multimap-class.md).

Belirtilen anahtardan daha büyük bir anahtarla ve anahtardan daha büyük veya ona eşit olan bir anahtarla hash_multimap ilk öğe olan bir hash_multimap yineleyicilerin bir çiftini döndürür.

```cpp
pair <const_iterator, const_iterator> equal_range (const Key& key) const;

pair <iterator, iterator> equal_range (const Key& key);
```

### <a name="parameters"></a>Parametreler

*anahtar*\
Aranan hash_multimap öğenin sıralama anahtarıyla Karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Birincisi anahtarın [lower_bound](#lower_bound) , ikincisi ise anahtarın [upper_bound](#upper_bound) olan yinelemelerin bir çiftinden biridir.

Üye işlevi tarafından döndürülen bir çiftin ilk Yineleyici `pr` erişmek için `pr`kullanın. **ilk** olarak, alt sınır yineleyicisini başvuru için \*(`pr`kullanın. **ilk**). Üye işlevi tarafından döndürülen bir çiftin ikinci Yineleyici `pr` erişmek için `pr`kullanın. **ikincisi** ve üst sınır yineleyicisinin başvurusu için \*(`pr`kullanın. **ikinci**).

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

## <a name="erase"></a>hash_multimap:: Erase

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](../standard-library/unordered-multimap-class.md).

Belirtilen konumlardan bir hash_multimap öğeyi veya öğe aralığını kaldırır veya belirtilen bir anahtarla eşleşen öğeleri kaldırır.

```cpp
iterator erase(iterator _Where);

iterator erase(iterator first, iterator last);

size_type erase(const key_type& key);
```

### <a name="parameters"></a>Parametreler

*_Where*\
Hash_multimap kaldırılacak öğenin konumu.

*ilk*\
Hash_multimap kaldırılan ilk öğenin konumu.

*son*\
Hash_multimap kaldırılan son öğenin hemen ötesinde konumlandır.

*anahtar*\
Hash_multimap kaldırılacak öğelerin anahtarı.

### <a name="return-value"></a>Dönüş Değeri

İlk iki üye işlevi için, kaldırılan öğelerin dışında kalan ilk öğeyi veya böyle bir öğe yoksa hash_multimap sonuna işaretçiyi atayan çift yönlü bir yineleyici.

Üçüncü üye işlevi için, hash_multimap kaldırılan öğelerin sayısını döndürür.

### <a name="remarks"></a>Açıklamalar

Üye işlevleri hiçbir şekilde özel durum oluşturmaz.

### <a name="example"></a>Örnek

Aşağıdaki örnek hash_multimap:: Erase üye işlevinin kullanımını gösterir.

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

## <a name="find"></a>hash_multimap:: Find

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](../standard-library/unordered-multimap-class.md).

Belirtilen anahtara eşdeğer bir anahtara sahip bir hash_multimap öğenin ilk konumunu ele alan bir yineleyici döndürür.

```cpp
iterator find(const Key& key);

const_iterator find(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*anahtar*\
Aranan hash_multimap öğenin sıralama anahtarıyla eşleştirilecek anahtar.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen bir anahtarla bir öğenin ilk konumunu adresleyen veya anahtar için eşleşme bulunmazsa hash_multimap son öğeden geçen konumda bulunan bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, sıralama anahtarı karşılaştırıdan daha az bir ilişkiye göre bir sıralamayı karşılayan bir ikili koşul altındaki bağımsız değişken anahtarına `equivalent` olan hash_multimap bir öğeyi ele alan bir yineleyici döndürür.

`find` dönüş değeri bir `const_iterator`atanırsa hash_multimap nesnesi değiştirilemez. `find` dönüş değeri bir `iterator`atanırsa hash_multimap nesnesi değiştirilebilir.

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

## <a name="get_allocator"></a>hash_multimap:: get_allocator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](../standard-library/unordered-multimap-class.md).

Hash_multimap oluşturmak için kullanılan ayırıcı nesnesinin bir kopyasını döndürür.

```cpp
Allocator get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Hash_multimap tarafından kullanılan ayırıcı.

### <a name="remarks"></a>Açıklamalar

Hash_multimap sınıfı için ayrıcılar, sınıfın depolamayı nasıl yönettiğini belirtir. C++ Standart kitaplık kapsayıcı sınıflarıyla sağlanan varsayılan ayrıcılar çoğu programlama ihtiyacı için yeterlidir. Kendi ayırıcı sınıfınızı yazmak ve kullanmak Gelişmiş C++ bir konudur.

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

## <a name="hash_multimap"></a>hash_multimap:: hash_multimap

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](../standard-library/unordered-multimap-class.md).

Boş bir hash_multimap oluşturur veya diğer bir hash_multimap tümünün veya bir kısmının kopyasıdır.

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
|*Eşkenar*|`Allocator`varsayılan olarak bu hash_multimap nesnesi için kullanılacak depolama ayırıcı sınıfı.|
|*İnin*|`Traits`varsayılan olarak, haritadaki öğeleri sıralamak için kullanılan `const Traits` türü karşılaştırma işlevi.|
|*Right*|Oluşturulan kümesinin bir kopya olması gereken harita.|
|*Adı*|Kopyalanacak öğe aralığındaki ilk öğenin konumu.|
|*Soyadına*|Kopyalanacak öğe aralığının ötesinde ilk öğenin konumu.|
|*IList*|Kopyalamanın initializer_list.|

### <a name="remarks"></a>Açıklamalar

Tüm oluşturucular, hash_multimap bellek depolamayı yöneten ve daha sonra [get_allocator](#get_allocator)çağırarak geri döndürülebilecek bir tür ayırıcı nesnesi depolar. Ayırıcı parametresi genellikle sınıf bildirimlerinde atlanır ve alternatif ayrıcılar yerine ön işleme makroları kullanılır.

Tüm oluşturucular hash_multimap başlatır.

Tüm oluşturucular, hash_multimap anahtarları arasında bir sıra oluşturmak için kullanılan `Traits` türünde bir işlev nesnesi depolar ve daha sonra [key_comp](#key_comp)çağırarak döndürülür.

İlk üç Oluşturucu boş bir ilk hash_multimap belirtir; İkincisi, öğelerin sırasını oluşturmak için kullanılacak karşılaştırma işlevinin türünü (*comp*) belirtir ve üçüncüsü açık olarak kullanılacak ayırıcı türünü belirtir (`_Al`). Anahtar sözcüğü `explicit` bazı otomatik tür dönüştürme türlerini bastırır.

Dördüncü Oluşturucu hash_multimap `Right`bir kopyasını belirtir.

Sonraki üç Oluşturucu, sınıf `Traits` ve ayırıcısının karşılaştırma işlevinin türünü belirtirken açıkça artan bir haritanın `First, Last)` aralığını kopyalar.

Sekizinci Oluşturucu hash_multimap `Right`taşımaktır.

Son üç Oluşturucu bir initializer_list kullanır.

## <a name="insert"></a>hash_multimap:: INSERT

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](../standard-library/unordered-multimap-class.md).

Bir hash_multimap öğe veya öğe aralığı ekler.

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
|*Acil*|Zaten bu öğeyi içermediği veya daha önce anahtarı equivalently sıralı bir öğe içermediğinden, hash_multimap eklenecek öğenin değeri.|
|*Olmadığı*|Doğru ekleme noktasını aramanın başlayacağı hakkında ipucu.|
|*Adı*|Bir haritadan kopyalanacak ilk öğenin konumu.|
|*Soyadına*|Bir haritadan kopyalanacak son öğenin hemen ötesinde konum.|

### <a name="return-value"></a>Dönüş Değeri

İlk iki `insert` üye işlevi, yeni öğenin eklendiği konuma işaret eden bir yineleyici döndürür.

Üçüncü üye işlevi, eklenecek öğeler için bir initializer_list kullanır.

Dördüncü üye işlevi, öğe değerlerinin dizisini belirtilen bir küme `[First, Last)` bir yineleyici tarafından bahsedilen her öğeye karşılık gelen bir haritaya ekler.

Son iki `insert` üye işlevleri, eklenen değeri taşımaları dışında, ilk ikisi ile aynı şekilde davranır.

### <a name="remarks"></a>Açıklamalar

Bir öğenin [value_type](#value_type) çifttir, böylece bir öğe değeri, ilk bileşenin anahtar değere eşit olduğu ve ikinci bileşen öğenin veri değerine eşit olduğu sıralı bir çift olacaktır.

Ekleme noktası *nerede*olursa, ekleme noktası, Logaritmik süre yerine `insert`ipucu sürümü için, sabit zamanlı olarak ekleme yapılabilir.

## <a name="iterator"></a>hash_multimap:: Yineleyici

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](../standard-library/unordered-multimap-class.md).

Bir hash_multimap herhangi bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleyici sağlayan bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::iterator iterator;
```

### <a name="remarks"></a>Açıklamalar

Hash_multimap tarafından tanımlanan `iterator`, `pair`\< **const Key**türünde olan [value_type](#value_type)nesnelerine işaret eder, ilk üyesi öğe için anahtar olan ve ikinci üye öğesi tarafından tutulan eşlenmiş veri olan > yazın.

Bir **yineleyiciye** başvuru yapmak`Iter` hash_multimap bir öğeye işaret eden `->` işlecini kullanın.

Öğe için anahtarın değerine erişmek üzere, (\* `Iter`) eşdeğerdir `Iter`**önce** -> kullanın. **ilk**olarak. Öğe için eşlenen veri değerine erişmek için, (\* `Iter`) denk olan `Iter` -> **ikincisini**kullanın. **ilk**olarak.

Bir tür `iterator`, bir öğenin değerini değiştirmek için kullanılabilir.

### <a name="example"></a>Örnek

`iterator`bildirme ve kullanma hakkında bir [örnek için bkz](#begin) . örnek.

## <a name="key_comp"></a>hash_multimap:: key_comp

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](../standard-library/unordered-multimap-class.md).

Hash_multimap anahtarları sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır.

```cpp
key_compare key_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Hash_multimap öğelerini sıralamak için kullandığı işlev nesnesini döndürür.

### <a name="remarks"></a>Açıklamalar

Saklı nesne, üye işlevini tanımlar

**bool işleci (const key &** `left` **, const Key &** `right` **);**

`left` önce varsa **true** , sıralama düzeninde `right` eşit değildir.

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

## <a name="key_compare"></a>hash_multimap:: key_compare

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](../standard-library/unordered-multimap-class.md).

Hash_multimap iki öğenin göreli sırasını belirleyebilmek için iki sıralama anahtarını karşılaştıran bir işlev nesnesi sağlayan bir tür.

```cpp
typedef Traits key_compare;
```

### <a name="remarks"></a>Açıklamalar

`key_compare` şablon parametresi *nitelikleri*için bir eş anlamlı.

*Nitelikler* hakkında daha fazla bilgi Için [hash_multimap sınıfı](../standard-library/hash-multimap-class.md) konusuna bakın.

### <a name="example"></a>Örnek

`key_compare`bildirme ve kullanma hakkında bir örnek için bkz. [key_comp](#key_comp) örneği.

## <a name="key_type"></a>hash_multimap:: key_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](../standard-library/unordered-multimap-class.md).

Hash_multimap her bir öğesini oluşturan sıralama anahtarı nesnesini açıklayan bir tür.

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Açıklamalar

`key_type`, şablon parametre *anahtarı*için bir eş anlamlı.

*Anahtar*hakkında daha fazla bilgi Için [hash_multimap sınıfı](../standard-library/hash-multimap-class.md) konusunun açıklamalar bölümüne bakın.

### <a name="example"></a>Örnek

`key_compare`bildirme ve kullanma hakkında bir örnek için bkz. [value_type](#value_type) örneği.

## <a name="lower_bound"></a>hash_multimap:: lower_bound

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](../standard-library/unordered-multimap-class.md).

Bir yineleyiciyi belirtilen anahtardan daha büyük veya ona eşit bir anahtarla bir hash_multimap ilk öğeye döndürür.

```cpp
iterator lower_bound(const Key& key);

const_iterator lower_bound(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*anahtar*\
Aranan hash_multimap öğenin sıralama anahtarıyla Karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişken anahtarına eşit veya ondan daha büyük bir anahtarla bir hash_multimap içindeki bir öğenin konumunu ele alan veya anahtar için eşleşme bulunmazsa hash_multimap son öğeden sonraki konumu ele alan bir [Yineleyici](#iterator) veya [const_iterator](#const_iterator) .

`lower_bound` dönüş değeri bir `const_iterator`atanırsa hash_multimap nesnesi değiştirilemez. `lower_bound` dönüş değeri bir `iterator`atanırsa hash_multimap nesnesi değiştirilebilir.

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

## <a name="mapped_type"></a>hash_multimap:: mapped_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](../standard-library/unordered-multimap-class.md).

Hash_multimap depolanan veri türünü temsil eden bir tür.

```cpp
typedef Type mapped_type;
```

### <a name="remarks"></a>Açıklamalar

`mapped_type`, şablon parametre *türü*için bir eş anlamlı.

*Tür* hakkında daha fazla bilgi Için [hash_multimap sınıfı](../standard-library/hash-multimap-class.md) konusuna bakın.

### <a name="example"></a>Örnek

`key_type`bildirme ve kullanma hakkında bir örnek için bkz. [value_type](#value_type) örneği.

## <a name="max_size"></a>hash_multimap:: max_size

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](../standard-library/unordered-multimap-class.md).

Hash_multimap maksimum uzunluğunu döndürür.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Hash_multimap olabilecek en uzun uzunluk.

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

## <a name="op_eq"></a>hash_multimap:: operator =

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](../standard-library/unordered-multimap-class.md).

Hash_multimap öğelerini başka bir hash_multimap kopyasıyla değiştirir.

```cpp
hash_multimap& operator=(const hash_multimap& right);

hash_multimap& operator=(hash_multimap&& right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Right*|`hash_multimap`kopyalandığı [hash_multimap](../standard-library/hash-multimap-class.md) .|

### <a name="remarks"></a>Açıklamalar

Bir `hash_multimap`var olan öğeleri sildikten sonra, `operator=` içeriğini kopyalar veya `hash_multimap`içine *taşısa* .

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

## <a name="pointer"></a>hash_multimap::p oınter

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](../standard-library/unordered-multimap-class.md).

Hash_multimap bir öğeye işaretçi sağlayan bir tür.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `pointer`, bir öğenin değerini değiştirmek için kullanılabilir.

Çoğu durumda, bir [yineleyici](#iterator) hash_multimap nesnesindeki öğelere erişmek için kullanılmalıdır.

## <a name="rbegin"></a>hash_multimap:: rbegin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](../standard-library/unordered-multimap-class.md).

Ters çevrilen hash_multimap ilk öğeyi adresleyen bir yineleyici döndürür.

```cpp
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir hash_multimap ilk öğeyi ele almak veya geri alınamaz hash_multimap son öğe olduğunu ele almak için ters çift yönlü Yineleyici.

### <a name="remarks"></a>Açıklamalar

`rbegin`, [Başlangıç](#begin) olarak bir hash_multimap kullanıldığı gibi tersine çevrilmiş bir hash_multimap ile kullanılır.

`rbegin` dönüş değeri bir `const_reverse_iterator`atanırsa hash_multimap nesnesi değiştirilemez. `rbegin` dönüş değeri bir `reverse_iterator`atanırsa hash_multimap nesnesi değiştirilebilir.

`rbegin`, hash_multimap geriye doğru yinelemek için kullanılabilir.

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

## <a name="reference"></a>hash_multimap:: Reference

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](../standard-library/unordered-multimap-class.md).

Hash_multimap depolanan bir öğeye başvuru sağlayan bir tür.

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

## <a name="rend"></a>hash_multimap:: rend

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](../standard-library/unordered-multimap-class.md).

Ters çevrilen hash_multimap son öğeden sonraki konumu ele alan bir yineleyici döndürür.

```cpp
const_reverse_iterator rend() const;

reverse_iterator rend();
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir hash_multimap en son öğeden sonra gelen konumu ele alan ters çift yönlü yineleyici (geri alınamaz hash_multimap ilk öğeden önce gelen konum).

### <a name="remarks"></a>Açıklamalar

`rend`, [son](#end) olarak bir hash_multimap ile kullanıldığı gibi ters bir hash_multimap ile kullanılır.

`rend` dönüş değeri bir [const_reverse_iterator](#const_reverse_iterator)atanırsa hash_multimap nesnesi değiştirilemez. `rend` dönüş değeri bir [reverse_iterator](#reverse_iterator)atanırsa hash_multimap nesnesi değiştirilebilir.

`rend`, geriye doğru bir yineleyicinin hash_multimap sonuna ulaşıp ulaşılmadığını test etmek için kullanılabilir.

`rend` tarafından döndürülen değer başvurulmamalıdır.

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

## <a name="reverse_iterator"></a>hash_multimap:: reverse_iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](../standard-library/unordered-multimap-class.md).

Ters çevrilen bir hash_multimap bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleyici sağlayan bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::reverse_iterator reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `reverse_iterator`, ters hash_multimap üzerinde yinelemek için kullanılır.

Hash_multimap tarafından tanımlanan `reverse_iterator`, `pair`\< **const anahtar**türünde olan [value_type](#value_type)nesnelerine Işaret eder, > yazın. Anahtarın değeri, ilk üye çifti ile kullanılabilir ve eşlenmiş öğenin değeri, çiftin ikinci üyesi üzerinden kullanılabilir.

### <a name="example"></a>Örnek

`reverse_iterator`bildirme ve kullanma hakkında bir örnek için bkz. [rbegin](#rbegin) örneği.

## <a name="size"></a>hash_multimap:: size

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](../standard-library/unordered-multimap-class.md).

Hash_multimap öğe sayısını döndürür.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Hash_multimap geçerli uzunluğu.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

Aşağıdaki örnek hash_multimap:: size üye işlevinin kullanımını gösterir.

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

## <a name="size_type"></a>hash_multimap:: size_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](../standard-library/unordered-multimap-class.md).

Bir hash_multimap öğe sayısını sayan işaretsiz bir tamsayı türü.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::size_type size_type;
```

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

Nasıl bildirilemeyeceğini ve kullanılacağına ilişkin bir örnek için [Boyut](#size) örneğine bakın `size_type`

## <a name="swap"></a>hash_multimap:: swap

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](../standard-library/unordered-multimap-class.md).

İki hash_multimaps öğelerini değiş tokuş eder.

```cpp
void swap(hash_multimap& right);
```

### <a name="parameters"></a>Parametreler

*sağ*\
Değiştirilecek öğeleri veya öğelerin hash_multimap birlikte alışverişi yapılacak hash_multimap sağlayan hash_multimap.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, öğeleri takas edilmekte olan iki hash_multimaps öğeleri belirten başvuruları, işaretçileri veya yineleyicileri geçersiz kılar.

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

## <a name="upper_bound"></a>hash_multimap:: upper_bound

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](../standard-library/unordered-multimap-class.md).

Bir yineleyiciyi belirtilen anahtardan daha büyük bir anahtarla bir hash_multimap ilk öğeye döndürür.

```cpp
iterator upper_bound(const Key& key);

const_iterator upper_bound(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*anahtar*\
Aranan hash_multimap öğenin sıralama anahtarıyla Karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişken anahtarından daha büyük bir anahtarla bir hash_multimap içindeki bir öğenin konumunu adresleyen veya anahtar için eşleşme bulunmazsa hash_multimap son öğeden sonraki konumu ele alan bir [Yineleyici](#iterator) veya [const_iterator](#const_iterator) .

`upper_bound` dönüş değeri bir `const_iterator`atanırsa hash_multimap nesnesi değiştirilemez. `upper_bound` dönüş değeri bir `iterator`atanırsa hash_multimap nesnesi değiştirilebilir.

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

## <a name="value_comp"></a>hash_multimap:: value_comp

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](../standard-library/unordered-multimap-class.md).

Üye işlevi, anahtar değerlerini karşılaştırarak bir hash_multimap öğelerinin sırasını belirleyen bir işlev nesnesi döndürür.

```cpp
value_compare value_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Hash_multimap öğelerini sıralamak için kullandığı karşılaştırma işlevi nesnesini döndürür.

### <a name="remarks"></a>Açıklamalar

Hash_multimap *d*için, iki öğe *E1* (*K1*, *D1*) ve *E2*(*K2*, *D2*), [value_type](#value_type)türündeki nesnelerdir; burada *K1* ve *K2* [key_type](#key_type) , *D1* ve *D2* türü [mapped_type](#mapped_type), `m.value_comp()(e1, e2)` `m.key_comp()(k1, k2)`eşdeğerdir. Saklı nesne üye işlevini tanımlar

`bool operator( value_type& left, value_type& right);`

`left` anahtar değeri ' nin önüne dönerse **true** , sıralama düzeninde `right` anahtar değerine eşit değildir.

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

## <a name="value_type"></a>hash_multimap:: value_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](../standard-library/unordered-multimap-class.md).

Hash_multimap depolanan nesne türünü temsil eden bir tür.

```cpp
typedef pair<const Key, Type> value_type;
```

### <a name="remarks"></a>Açıklamalar

`value_type`, bir ilişkilendirilebilir kapsayıcının anahtarları sabit olmayan bir yineleyici veya başvuru kullanılarak değiştirilemediği için,\<const [key_type](#key_type), [mapped_type](#mapped_type)> ve çiftinin\<olmayan key_type mapped_type, > eşleştirilmeyen bir şekilde bildirilmiştir.

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
   // explicitly to avoid implicit type conversion
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

[Standart kitaplıkta Iş parçacığı güvenliği\ C++ ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)
