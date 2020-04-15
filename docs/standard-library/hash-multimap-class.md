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
ms.openlocfilehash: 2fe9056996876d24fba285c0c7aaec8607b2509c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375444"
---
# <a name="hash_multimap-class"></a>hash_multimap Sınıfı

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](../standard-library/unordered-multimap-class.md).

Kapsayıcı sınıfı hash_multimap C++ Standart Kitaplığı'nın bir uzantısıdır ve her öğenin değeri benzersiz olmayan bir sıralama anahtarı ve ilişkili bir veri değeri olan bir çifti olan bir koleksiyondan veri depolama ve hızlı alma için kullanılır.

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
hash_multimap depolanacak anahtar veri türü.

*Türü*\
hash_multimap depolanacak öğe veri türü.

*Özellik*\
İki işlev nesnesi içeren tür, bir sınıf özellikleri göreli sıralarını belirlemek için sıra anahtarları olarak iki öğe değerleri ve tür imzasız tamsayılar için öğelerin unary yüklem eşleme anahtar değerleri olan bir karma işlevi karşılaştırmak mümkün *özellikleri* `size_t`. Bu bağımsız değişken isteğe bağlıdır ve varsayılan `hash_compare<Key, less<Key>>` değerdir.

*Ayırıcı*\
hash_multimap ayırma ve bellek ayırma ile ilgili ayrıntıları kapsülleyen depolanan ayırıcı nesneyi temsil eden tür. Bu bağımsız değişken isteğe bağlıdır `allocator<pair <const Key, Type>>`ve varsayılan değer .

## <a name="remarks"></a>Açıklamalar

hash_multimap:

- İlişkili bir anahtar değerine dayalı öğe değerlerinin verimli alınmasını destekleyen bir değişken boyutu kapsayıcı olan ilişkilendirilebilir bir kapsayıcı.

- Çift yönlüdür, çünkü öğelerine erişmek için çift yönlü bir yineleyici sağlar.

- Karma, çünkü elemanları, öğelerin temel değerlerine uygulanan karma işlevin değerine göre kovalar halinde gruplandırılır.

- Öğelerinin benzersiz anahtarlara ihtiyacı olmaması için çokludur, böylece bir anahtar değer onunla ilişkili çok sayıda öğe verisi değerine sahip olabilir.

- Bir çift birleştirici kapsayıcı, çünkü öğe değerleri anahtar değerlerinden farklıdır.

- Sağladığı işlevsellik genel olduğundan ve öğe veya anahtar olarak bulunan belirli veri türünden bağımsız olduğundan, sınıf şablonu. Öğeler ve anahtarlar için kullanılacak veri türleri, karşılaştırma işlevi ve ayırıcı ile birlikte bir sınıf şablonunda parametreler olarak belirtilir.

Sıralama üzerinde karma temel avantajı daha fazla verimlilik; başarılı bir karma eklemeler, silmeler gerçekleştirir ve sıralama teknikleri için kapsayıcıdaki eleman sayısının logaritma ile orantılı bir süre ile karşılaştırıldığında sabit ortalama zaman bulur. Bir hash_multimap öğenin değeri, ancak ilişkili anahtar değeri, doğrudan değiştirilebilir. Bunun yerine, eski öğelerle ilişkili anahtar değerleri silinmeli ve eklenen yeni öğelerle ilişkili yeni anahtar değerleri eklenmelidir.

Kapsayıcı türünün seçimi genelde uygulamanın gerektirdiği arama ve ekleme türüne dayalı olmalıdır. Haşdi hashed musociative kaplar arama, ekleme ve kaldırma işlemleri için optimize edilmiştir. Bu işlemleri açıkça destekleyen üye işlevler, iyi tasarlanmış bir karma işlevle kullanıldığında verimlidir ve bunları ortalama sabit olan ve kapsayıcıdaki öğe sayısına bağlı olmayan bir zamanda gerçekleştirir. İyi tasarlanmış karma işlev karma değerlerin tek tip dağılımını üretir ve farklı anahtar değerleri aynı karma değere eşlendiğinde çakışacağı söylenen çarpışma sayısını en aza indirir. En kötü durumda, mümkün olan en kötü karma işlevi ile, işlem sayısı dizideki eleman sayısıyla (doğrusal zaman) orantılıdır.

Hash_multimap, değerleri anahtarlarıyla ilişkilendiren koşullar uygulama tarafından karşılandığında tercih edilen ilişkisel kapsayıcı olmalıdır. Bu tür bir yapı için model, mesela açıklamalar sağlayan dize değerleriyle ilişkili anahtar sözcüklerin sıralı bir listesidir, burada sözcükler her zaman benzersiz olarak tanımlanmamıştır. Bunun yerine, anahtar kelimeler benzersiz olacak şekilde benzersiz olarak tanımlanmışsa, hash_map tercih edilen kapsayıcı olacaktır. Diğer taraftan, yalnızca sözcük listesi depolanıyorsa, hash_set doğru kapsayıcı olurdu. Sözcüklerin birden çok oluşumuna izin verilirse, hash_multiset uygun kapsayıcı yapısı olacaktır.

hash_multimap, denetlediği sırayı, value_compare türündeki depolanmış karma `Traits` nesneyi çağırarak sıralar. [value_compare](../standard-library/value-compare-class.md) Bu depolanan nesneye üye işlev [key_comp](../standard-library/hash-map-class.md#key_comp)çağırılarak erişilebilir. Böyle bir işlev nesnesi [sınıf hash_compare](../standard-library/hash-compare-class.md)`<Key, less<Key>>`bir nesne olarak aynı şekilde olmalıdır. Özellikle, `Key` tür `Key`tüm değerleri için, çağrı `Traits (Key)` türü `size_t`değerlerinin bir dağıtım verir.

Genelde, bu sıralamayı oluşturmak için öğelerin yalnızca küçüktür biçiminde karşılaştırılabilir olması gerekir; böylece, herhangi iki öğe belirtildiğinde, eşit oldukları (yani birinin diğerinden daha küçük olmadığı anlamında) veya birinin diğerinden küçük olduğu belirlenebilir. Bu, eşdeğer olmayan öğeler arasında bir sıralama ile sonuçlanır. Daha teknik bir not üzerinde, karşılaştırma işlevi standart matematiksel anlamda katı bir zayıf sıralama sevk eden ikili bir koşuldur. İkili yüklem f(x, y) iki bağımsız değişken `x` nesnesi `y` ve **doğru** veya **yanlışın**dönüş değeri olan bir işlev nesnesidir. Bir hash_multimap uygulanan bir sıralama, ikili yüklem inreflexive, antisimetrik ve geçişli ve eşdeğerlik geçişli ise, iki nesne `x` ve `y` hem f(x, y, x) **yanlış**olduğunda eşdeğer olarak tanımlanır sıkı bir zayıf sıralamadır. Anahtarlar arasındaki eşitliğinin daha güçlü koşulu bu denkliğin yerini alırsa, sıralama (içindeki tüm öğelerin birbirine göre sıralanması anlamında) toplam haline gelir ve eşleşen anahtarlar birbirinden ayırt edilemez olacaktır.

Denetlenmiş dizideki öğelerin gerçek sırası karma işlevine, sıralama işlevine ve kapsayıcı nesnesinde depolanan karma tablonun geçerli boyutuna bağlıdır. Karma tablonun geçerli boyutunu belirleyemezsiniz, bu nedenle genel olarak denetitilen dizideki öğelerin sırasını tahmin edemezsiniz. Öğelerin eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; öğelerin kaldırılması yalnızca özellikle kaldırılan öğeleri gösteren yineleyicileri geçersiz kılar.

hash_multimap sınıfı tarafından sağlanan yineleme iki yönlü bir yinelemedir, ancak sınıf üye işlevleri [şablon](#insert) parametreleri olarak alan sürümlere [sahip](#hash_multimap) hash_multimap, işlevsellik gereksinimleri çift yönlü yineleyiciler sınıfı tarafından garanti edilenden daha az olan daha zayıf bir giriş yinelemesi alır. Farklı yineleyici kavramları, işlevselliklerindeki iyileştirmelere göre ilgili bir aile biçimlendirir. Her yineleyici kavramının kendi gereksinimleri hash_multimap vardır ve onlarla çalışan algoritmalar varsayımlarını bu tür bir yineleyici tarafından sağlanan gereksinimlerle sınırlandırmalıdır. Bir giriş yineleyicinin bazı nesnelere başvurusunun kaldırılacağı ve dizideki sonraki yineleyiciye artırılabileceği varsayılabilir. Bu, en az işlevsellik hash_multimap, ancak üye işlevler bağlamında bir dizi `[First, Last)` yineleyici hakkında anlamlı bir şekilde konuşabilmek için yeterlidir.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[Hash_multimap](#hash_multimap)|Belirli bir boyutun veya belirli bir değerin öğeleriyle `allocator` veya belirli bir boyutun veya başka `hash_multimap`bir boyutun bir kopyasının bir listesini içerir.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[Allocator_type](#allocator_type)|Nesnenin sınıfını `allocator` `hash_multimap` temsil eden bir tür.|
|[const_iterator](#const_iterator)|Bir öğeyi okuyabilen çift yönlü bir yineleme `const` sağlayan `hash_multimap`bir tür.|
|[Const_pointer](#const_pointer)|Bir **const** öğesine işaretçi sağlayan `hash_multimap`bir tür .|
|[const_reference](#const_reference)|Const **işlemleri** okumak ve gerçekleştirmek için bir `hash_multimap` **const** öğesinde depolanan bir öğeye başvuru sağlayan bir tür.|
|[Const_reverse_iterator](#const_reverse_iterator)|Herhangi bir const öğeyi okuyabilen çift yönlü bir yineleme sağlayan bir tür. **const** `hash_multimap`|
|[difference_type](#difference_type)|Yineleyiciler tarafından işaret edilen öğeler arasındaki aralıktaki bir `hash_multimap` aralığın öğelerinin sayısını temsil etmek için kullanılabilecek imzalı bir tamsayı türü.|
|[Yineleyici](#iterator)|Bir 'deki herhangi bir öğeyi okuyabilen veya değiştirebilen `hash_multimap`çift yönlü bir yineleme sağlayan bir tür.|
|[Key_compare](#key_compare)|İki öğenin göreli sırasını belirlemek için iki sıralama anahtarını karşılaştırabilen bir işlev nesnesi `hash_multimap`sağlayan bir tür.|
|[Key_type](#key_type)|`hash_multimap`Her öğeyi oluşturan sıralama anahtar nesnesini açıklayan bir tür.|
|[mapped_type](#mapped_type)|Bir 'de depolanan veri türünü `hash_multimap`temsil eden bir tür|
|[pointer](#pointer)|Bir öğedeki bir öğeye işaretçi sağlayan bir `hash_multimap`tür|
|[Başvuru](#reference)|Bir 'de depolanan bir öğeye `hash_multimap`başvuru sağlayan bir tür|
|[Reverse_iterator](#reverse_iterator)|Ters bir öğedeki bir öğeyi okuyabilen veya değiştirebilen `hash_multimap`çift yönlü bir yineleme sağlayan bir tür.|
|[size_type](#size_type)|Bir 'deki öğe sayısını temsil eden imzasız `hash_multimap`bir tamsayı türü|
|[value_type](#value_type)|İki öğeyi sıraanahtarları olarak karşılaştırabilen bir işlev nesnesi `hash_multimap`sağlayan bir tür.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[Başlamak](#begin)|'deki ilk öğeyi ele alan bir `hash_multimap`yineleyici döndürür.|
|[cbegin](#cbegin)|'deki ilk öğeyi ele alan bir const yineleyici döndürür. `hash_multimap`|
|[cend](#cend)|Bir `hash_multimap`'deki son öğeyi yerine getiren konumu gideren bir const yineleyici döndürür.|
|[Temizleyin](#clear)|Bir' `hash_multimap`nin tüm öğelerini siler.|
|[Sayısı](#count)|Anahtarı parametre yle `hash_multimap` belirtilen bir anahtarla eşleşen bir öğedeki öğe sayısını döndürür.|
|[crbegin](#crbegin)|Ters bir ilk öğeyi ele alan bir const yineleyici döndürür. `hash_multimap`|
|[crend](#crend)|Ters bir önceki son öğeyi yerine getiren konumu gideren bir `hash_multimap`const yineleyici döndürür.|
|[emplace](#emplace)|Yerinde inşa edilmiş bir öğeyi `hash_multimap`bir .|
|[emplace_hint](#emplace_hint)|Yerinde `hash_multimap`oluşturulmuş bir öğeyi yerleştirme ipucuyla ekler.|
|[empty](#empty)|A boşsa `hash_multimap` sınar.|
|[Son -unda](#end)|Bir 'deki son öğeyi yerine getiren konumu adresleyen `hash_multimap`bir yineleyici döndürür.|
|[equal_range](#equal_range)|Bir 'deki son öğeyi yerine getiren konumu adresleyen `hash_multimap`bir yineleyici döndürür.|
|[Silmek](#erase)|Belirli `hash_multimap` konumlardaki bir öğeyi veya bir dizi öğeyi kaldırır|
|[find](#find)|Belirtilen bir anahtara eşdeğer anahtara sahip bir `hash_multimap` öğedeki öğenin konumunu ele alan bir yineleyici döndürür.|
|[Get_allocator](#get_allocator)|Oluşturmak için kullanılan `allocator` nesnenin bir `hash_multimap`kopyasını döndürür.|
|[Ekle](#insert)|Belirli bir konumda bir öğe veya `hash_multimap` eleman aralığı ekler.|
|[Key_comp](#key_comp)|Bir `hash_multimap`'deki anahtarları sipariş etmek için kullanılan karşılaştırma nesnesinin bir kopyasını alır.|
|[lower_bound](#lower_bound)|Bir yineleyiciyi, belirtilen bir anahtara eşit veya daha büyük bir anahtar değerine sahip olan ilk `hash_multimap` öğeye döndürür.|
|[max_size](#max_size)|Maksimum uzunluğu `hash_multimap`verir.|
|[rbegin](#rbegin)|Ters bir ilk öğeyi ele alan bir `hash_multimap`yineleyici döndürür.|
|[Rend](#rend)|Ters çevrilmiş bir son öğedeki son öğeyi yerine `hash_multimap`getiren konumu adresleyen bir yineleyici döndürür.|
|[Boyutu](#size)|Bir `hash_multimap`.|
|[Takas](#swap)|İki `hash_multimap`s'nin öğelerini değiştirir.|
|[upper_bound](#upper_bound)|Bir yineleyiciyi, belirtilen bir anahtardan daha büyük bir anahtar değerine sahip olan ilk `hash_multimap` öğeye döndürür.|
|[value_comp](#value_comp)|Bir `hash_multimap`' deki öğe değerlerini sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[hash_multimap::operator=](#op_eq)|Bir `hash_multimap` öğenin öğelerini başka `hash_multimap`bir kopyayla değiştirir.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<hash_map>

**Ad alanı:** stdext

## <a name="hash_multimapallocator_type"></a><a name="allocator_type"></a>hash_multimap:allocator_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](../standard-library/unordered-multimap-class.md).

hash_multimap nesnesi için ayırıcı sınıfını temsil eden bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::allocator_type allocator_type;
```

### <a name="remarks"></a>Açıklamalar

`allocator_type`şablon parametresi `Allocator`ile eş anlamlıdır.

Daha fazla `Allocator`bilgi için [hash_multimap Sınıfı](../standard-library/hash-multimap-class.md) konusunun Açıklamalar bölümüne bakın.

### <a name="example"></a>Örnek

get_allocator örneğini [get_allocator](#get_allocator) kullanarak `allocator_type`bir örneğe bakın.

## <a name="hash_multimapbegin"></a><a name="begin"></a>hash_multimap::başla

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](../standard-library/unordered-multimap-class.md).

hash_multimap ilk öğeyi ele alan bir yineleyici döndürür.

```cpp
const_iterator begin() const;

iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

boş bir hash_multimap başaran hash_multimap veya konumuilk öğeyi ele alan çift yönlü bir yineleyici.

### <a name="remarks"></a>Açıklamalar

`begin` Bir `const_iterator`, hash_multimap nesnesindeki öğelere atanırsa değiştirilemez. Bir `begin` `iterator`, hash_multimap nesnesindeki öğelere atanırsa değiştirilebilir.

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

## <a name="hash_multimapcbegin"></a><a name="cbegin"></a>hash_multimap::cbegin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](../standard-library/unordered-multimap-class.md).

hash_multimap'daki ilk öğeyi ele alan bir const yineleyici döndürür.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

[hash_multimap'daki](../standard-library/hash-multimap-class.md) ilk öğeyi veya boş `hash_multimap`bir konumdan sonra gelen bir konst çift yönlü yineleme.

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

## <a name="hash_multimapcend"></a><a name="cend"></a>hash_multimap::cend

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](../standard-library/unordered-multimap-class.md).

Bir hash_multimap son öğeyi yerine getiren konumu gideren bir const yineleyici döndürür.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Dönüş Değeri

[Bir hash_multimap](../standard-library/hash-multimap-class.md)son öğeyi yerine getiren konumu gideren bir konst çift yönlü yineleme. Eğer `hash_multimap` boşsa, `hash_multimap::cend == hash_multimap::begin`o zaman.

### <a name="remarks"></a>Açıklamalar

`cend`bir yineleyicinin hash_multimap sonuna ulaşıp ulaşmadığını test etmek için kullanılır.

Döndürülen `cend` değer dereferenced olmamalıdır.

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

## <a name="hash_multimapclear"></a><a name="clear"></a>hash_multimap::açık

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](../standard-library/unordered-multimap-class.md).

Bir hash_multimap tüm öğelerini siler.

```cpp
void clear();
```

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

Aşağıdaki örnek, hash_multimap::clear üye işlevinin kullanımını göstermektedir.

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

## <a name="hash_multimapconst_iterator"></a><a name="const_iterator"></a>hash_multimap:const_iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](../standard-library/unordered-multimap-class.md).

hash_multimap bir **const** öğeyi okuyabilen çift yönlü bir yineleme sağlayan bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_iterator const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir `const_iterator` tür, bir öğenin değerini değiştirmek için kullanılamaz.

hash_multimap `const_iterator` tarafından tanımlanan value_type nesneleri [,](#value_type)hangi türde `pair<const Key, Type>`. Anahtarın değeri ilk üye çift aracılığıyla kullanılabilir ve eşlenen öğenin değeri çiftin ikinci üyesi aracılığıyla kullanılabilir.

bir hash_multimap `const_iterator` `cIter` bir öğeyi işaret eden bir `->` ifadeyi belirtmek için işleci kullanın.

Öğe için anahtarın değerine erişmek `cIter->first`için, 'ye `(*cIter).first`eşdeğer olan ' ı kullanın. Öğe için eşlenen datum değerine erişmek için, 'ye `cIter->second` `(*cIter).second`eşdeğer olan ' ı kullanın.

### <a name="example"></a>Örnek

Bir örneğin [ikullanarak](#begin) `const_iterator`başlatılamıörneğine bakın.

## <a name="hash_multimapconst_pointer"></a><a name="const_pointer"></a>hash_multimap:const_pointer

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](../standard-library/unordered-multimap-class.md).

hash_multimap bir **const** öğesiiçin işaretçi sağlayan bir tür.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::const_pointer const_pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir `const_pointer` tür, bir öğenin değerini değiştirmek için kullanılamaz.

Çoğu durumda, hash_multimap bir nesnedeki öğelere erişmek için bir [yineleyici](#iterator) kullanılmalıdır.

## <a name="hash_multimapconst_reference"></a><a name="const_reference"></a>hash_multimap:const_reference

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](../standard-library/unordered-multimap-class.md).

**Const** işlemleri okumak ve gerçekleştirmek için hash_multimap depolanan **bir const** öğesine başvuru sağlayan bir tür.

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

## <a name="hash_multimapconst_reverse_iterator"></a><a name="const_reverse_iterator"></a>hash_multimap:const_reverse_iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](../standard-library/unordered-multimap-class.md).

hash_multimap herhangi bir **const** öğeyi okuyabilen çift yönlü bir yineleme sağlayan bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_reverse_iterator const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir `const_reverse_iterator` tür bir öğenin değerini değiştiremez ve ters hash_multimap ile yinelemek için kullanılır.

hash_multimap `const_reverse_iterator` tarafından tanımlanan, ilk üyesi öğenin anahtarı `pair<const Key, Type>`olan ve ikinci üyesi öğetarafından tutulan eşlenmiş datum olan [value_type](#value_type)nesneleri için işaret eder.

bir hash_multimap `const_reverse_iterator` `crIter` bir öğeyi işaret eden bir `->` ifadeyi belirtmek için işleci kullanın.

Öğe için anahtarın değerine erişmek `crIter->first`için, 'ye `(*crIter).first`eşdeğer olan ' ı kullanın. Öğe için eşlenen datum değerine erişmek için, 'ye `crIter->second` `(*crIter).second`eşdeğer olan ' ı kullanın.

### <a name="example"></a>Örnek

Nasıl beyan edilip kullanılacağına bir örnek için `const_reverse_iterator` [rend](#rend) örneğine bakın.

## <a name="hash_multimapcount"></a><a name="count"></a>hash_multimap::say

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](../standard-library/unordered-multimap-class.md).

Anahtarı parametre yle belirtilen anahtarla eşleşen bir hash_multimap öğe sayısını verir.

```cpp
size_type count(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*Anahtar*\
hash_multimap eşleşecek öğelerin anahtarı.

### <a name="return-value"></a>Dönüş Değeri

1 hash_multimap, sıralama anahtarı parametre anahtarıyla eşleşen bir öğe içeriyorsa; 0 hash_multimap eşleşen bir anahtar ile bir öğe içermiyorsa.

### <a name="remarks"></a>Açıklamalar

Üye işlev aralıktaki eleman sayısını döndürür

**[lower_bound (** `key` **), upper_bound (** `key` **)**

anahtar *değeri anahtarı*olan.

### <a name="example"></a>Örnek

Aşağıdaki örnek, hash_multimap::count üye işlevinin kullanımını göstermektedir.

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

## <a name="hash_multimapcrbegin"></a><a name="crbegin"></a>hash_multimap::crbegin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](../standard-library/unordered-multimap-class.md).

Ters hash_multimap ilk öğeyi ele alan bir const yineleyici döndürür.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters [hash_multimap](../standard-library/hash-multimap-class.md) ilk öğeyi ele alan veya tersine çevrilmemiş `hash_multimap`son öğeyi ele alan const ters çift yönlü bir yineleme.

### <a name="remarks"></a>Açıklamalar

`crbegin`hash_multimap gibi ters hash_multimap ile [kullanılır::begin](#begin) ile `hash_multimap`kullanılır .

İade değeri ile `crbegin` `hash_multimap` nesne değiştirilemez.

`crbegin``hash_multimap` geriye doğru doğrulamak için kullanılabilir.

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

## <a name="hash_multimapcrend"></a><a name="crend"></a>hash_multimap::crend

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](../standard-library/unordered-multimap-class.md).

Ters hash_multimap son öğeyi yerine getiren konumu gideren bir const yineleyici döndürür.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters [hash_multimap](../standard-library/hash-multimap-class.md) 'deki son öğeyi başaran konumu (ters çevrilmemiş `hash_multimap`ilk öğeden önce gelen konum) gideren const ters çift yönlü yineleme.

### <a name="remarks"></a>Açıklamalar

`crend`hash_multimap gibi ters hash_multimap ile [kullanılır::end](#end) bir hash_multimap ile kullanılır.

İade değeri ile `crend` `hash_multimap` nesne değiştirilemez.

`crend`ters yineleyicinin hash_multimap sonuna ulaşıp ulaşmadığını test etmek için kullanılabilir.

Döndürülen `crend` değer dereferenced olmamalıdır.

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

## <a name="hash_multimapdifference_type"></a><a name="difference_type"></a>hash_multimap::difference_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](../standard-library/unordered-multimap-class.md).

Yineleyiciler tarafından işaret edilen öğeler arasındaki aralıkta bir hash_multimap öğelerinin sayısını temsil etmek için kullanılabilecek imzalı bir tamsayı türü.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

Kapsayıcının `difference_type` yineleyicileri arasından çıkarılırken veya artarken döndürülen türdür. Genellikle `difference_type` yineleyiciler `first` arasındaki *[ilk, son)* aralığındaki öğelerin sayısını temsil `last`etmek için kullanılır ve `first` , işaret eden öğe ve öğe aralığı kadar, `last`ancak dahil değil, öğe tarafından işaret içerir.

Küme gibi `difference_type` geri döndürülebilir kapsayıcılar tarafından desteklenen çift yönlü yineleyiciler sınıfını içeren bir giriş yineleyicisinin gereksinimlerini karşılayan tüm yineleyiciler için kullanılabilir olmasına rağmen, yineleyiciler arasındaki çıkarma yalnızca vektör gibi rasgele erişimli bir kapsayıcı tarafından sağlanan rasgele erişim yinelemeleri tarafından desteklenir.

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

## <a name="hash_multimapemplace"></a><a name="emplace"></a>hash_multimap::emplace

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](../standard-library/unordered-multimap-class.md).

Yerinde inşa edilmiş bir öğeyi hash_multimap içine ekler.

```cpp
template <class ValTy>
iterator emplace(ValTy&& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Val*|hash_multimap eklenecek bir öğeyi taşımak için kullanılan [değer.](../standard-library/hash-multimap-class.md)|

### <a name="return-value"></a>Dönüş Değeri

Üye `emplace` işlev, yeni öğenin eklendiği konumu gösteren bir yineleyici döndürür.

### <a name="remarks"></a>Açıklamalar

[hash_multimap::value_type](#value_type) bir öğedir, böylece bir öğenin değeri ilk bileşen anahtar değerine eşit, ikinci bileşen ise öğenin veri değerine eşit olan sıralı bir çift olacaktır.

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

## <a name="hash_multimapemplace_hint"></a><a name="emplace_hint"></a>hash_multimap:emplace_hint

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](../standard-library/unordered-multimap-class.md).

Yerinde oluşturulmuş bir öğeyi bir hash_multimap, bir yerleşim ipucuyla ekler.

```cpp
template <class ValTy>
iterator emplace_hint(
    const_iterator _Where,
    ValTy&& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Val*|Zaten bu öğeyi (veya daha genel olarak, anahtarı `hash_multimap` eşdeğer sıralanmış bir öğe) içermediği [sürece, hash_multimap](../standard-library/hash-multimap-class.md) eklenecek bir öğeyi taşımak için kullanılan değer.|
|*_Where*|Doğru ekleme noktasını aramaya başlamak için yerle ilgili bir ipucu.|

### <a name="return-value"></a>Dönüş Değeri

[hash_multimap::emplace](#emplace) üye işlevi, yeni öğenin eklendiği konumu gösteren bir yineleyici `hash_multimap`döndürür.

### <a name="remarks"></a>Açıklamalar

[hash_multimap::value_type](#value_type) bir öğedir, böylece bir öğenin değeri ilk bileşen anahtar değerine eşit, ikinci bileşen ise öğenin veri değerine eşit olan sıralı bir çift olacaktır.

Ekleme noktası hemen *_Where*takip ederse, logaritmik zaman yerine, amortismana tabi sabit zaman oluşabilir.

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

## <a name="hash_multimapempty"></a><a name="empty"></a>hash_multimap::boş

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](../standard-library/unordered-multimap-class.md).

bir hash_multimap boş olup olmadığını sınar.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

hash_multimap boşsa **doğrudur;** hash_multimap boş değilse **yanlış.**

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

## <a name="hash_multimapend"></a><a name="end"></a>hash_multimap::sonu

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](../standard-library/unordered-multimap-class.md).

Hash_multimap son öğeyi yerine getiren konumu adresleyen bir yineleyici döndürür.

```cpp
const_iterator end() const;

iterator end();
```

### <a name="return-value"></a>Dönüş Değeri

Bir hash_multimap son öğesini yerine getiren konumu ele alan çift yönlü bir yineleyici. hash_multimap boşsa, hash_multimap::end == hash_multimap::begin.

### <a name="remarks"></a>Açıklamalar

`end`bir yineleyicinin hash_multimap sonuna ulaşıp ulaşmadığını test etmek için kullanılır.

Döndürülen `end` değer dereferenced olmamalıdır.

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

## <a name="hash_multimapequal_range"></a><a name="equal_range"></a>hash_multimap:equal_range

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](../standard-library/unordered-multimap-class.md).

Bir hash_multimap ilk öğeye sırasıyla bir çift yineleyici, belirtilen bir anahtardan büyük bir anahtarla ve anahtara eşit veya daha büyük bir anahtarla hash_multimap ilk öğeye döndürür.

```cpp
pair <const_iterator, const_iterator> equal_range (const Key& key) const;

pair <iterator, iterator> equal_range (const Key& key);
```

### <a name="parameters"></a>Parametreler

*Anahtar*\
Aranın hash_multimap bir öğenin tür anahtarıyla karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

İlki anahtarın [lower_bound,](#lower_bound) ikincisi anahtarın [upper_bound](#upper_bound) olacak şekilde bir çift yineleyici.

Üye işlev tarafından döndürülen bir `pr` çiftin ilk yineleyicisine `pr`erişmek için. **ilk** ve alt sınır yineleyici dereference \*için, kullanın ( `pr`. **ilk**). Üye işlev tarafından döndürülen bir `pr` çiftin ikinci yineleyicisine `pr`erişmek için. **ikinci** ve üst sınır yineleyici dereference \*için, kullanın ( `pr`. **ikinci**).

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

## <a name="hash_multimaperase"></a><a name="erase"></a>hash_multimap::silme

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](../standard-library/unordered-multimap-class.md).

Hash_multimap bir öğeyi veya bir öğe aralığını belirtilen konumlardan kaldırır veya belirtilen anahtarla eşleşen öğeleri kaldırır.

```cpp
iterator erase(iterator _Where);

iterator erase(iterator first, iterator last);

size_type erase(const key_type& key);
```

### <a name="parameters"></a>Parametreler

*_Where*\
Hash_multimap kaldırılacak öğenin konumu.

*Ilk*\
hash_multimap kaldırılan ilk öğenin konumu.

*Son*\
hash_multimap kaldırılan son öğenin hemen ötesine yerleştirin.

*Anahtar*\
hash_multimap kaldırılacak öğelerin anahtarı.

### <a name="return-value"></a>Dönüş Değeri

İlk iki üye işlev için, kaldırılan öğelerin ötesinde kalan ilk öğeyi belirleyen çift yönlü bir yineleyici veya böyle bir öğe yoksa hash_multimap sonuna işaretçi.

Üçüncü üye işlev için, hash_multimap kaldırılan öğelerin sayısını döndürür.

### <a name="remarks"></a>Açıklamalar

Üye işlevler hiçbir zaman bir özel durum atmaz.

### <a name="example"></a>Örnek

Aşağıdaki örnek, hash_multimap::delete üye işlevinin kullanımını gösterir.

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

## <a name="hash_multimapfind"></a><a name="find"></a>hash_multimap::bul

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](../standard-library/unordered-multimap-class.md).

Bir öğenin ilk konumunu adresleyen bir hash_multimap, belirli bir anahtara eşdeğer anahtara sahip bir yineleyici döndürür.

```cpp
iterator find(const Key& key);

const_iterator find(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*Anahtar*\
Aranmakta olan hash_multimap öğenin tür anahtarıyla eşleşecek anahtar.

### <a name="return-value"></a>Dönüş Değeri

Belirli bir anahtarla bir öğenin ilk konumunu veya anahtar için eşleşme bulunamazsa hash_multimap son öğeyi başaran konumu adresleyen bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Üye işlev, hash_multimap bir öğeyi ele alan ve karşılaştırmalı `equivalent` ilişkiden daha az bir ilişkiye dayalı bir sıralamayı sağlayan ikili yüklem altında bağımsız değişken anahtarıolan bir öğeyi döndürür.

Bir `const_iterator`, hash_multimap `find` nesnesinin geri dönüş değeri ne olursa olsun değiştirilemez. Bir `iterator`, hash_multimap `find` nesnesi için döndürülen değer atanır.

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

## <a name="hash_multimapget_allocator"></a><a name="get_allocator"></a>hash_multimap:get_allocator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](../standard-library/unordered-multimap-class.md).

hash_multimap oluşturmak için kullanılan ayırıcı nesnenin bir kopyasını döndürür.

```cpp
Allocator get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

hash_multimap tarafından kullanılan ayırıcı.

### <a name="remarks"></a>Açıklamalar

hash_multimap sınıfının ayırıcıları sınıfın depolamayı nasıl yönettiğini belirtir. C++ Standart Kitaplık kapsayıcı sınıfları ile birlikte verilen varsayılan ayırıcılar çoğu programlama gereksinimleri için yeterlidir. Kendi ayırıcı sınıfınızı yazmak ve kullanmak gelişmiş bir C++ konusudur.

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

## <a name="hash_multimaphash_multimap"></a><a name="hash_multimap"></a>hash_multimap:hash_multimap

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](../standard-library/unordered-multimap-class.md).

Boş veya başka bir hash_multimap tamamının veya bir kısmının kopyası olan bir hash_multimap kurar.

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
|*Al*|Bu hash_multimap nesneiçin kullanılacak depolama ayırıcı sınıfı varsayılan `Allocator`olarak .|
|*Comp*|Eşdeki öğeleri `const Traits` sıralamak için kullanılan tür deki karşılaştırma `Traits`işlevi, varsayılan olarak .|
|*Doğru*|Yapılandırılan kümenin bir kopyası olması gereken harita.|
|*Ilk*|Kopyalanacak öğeler aralığındaki ilk öğenin konumu.|
|*Son*|İlk öğenin kopyalanacak öğe aralığının ötesindeki konumu.|
|*ılist*|Kopyalamak için initializer_list.|

### <a name="remarks"></a>Açıklamalar

Tüm oluşturucular, hash_multimap için bellek depolamayı yöneten ve daha sonra [get_allocator](#get_allocator)çağırarak döndürülebilen bir allocator nesnesi türünü depolar. Ayırıcı parametresi genellikle sınıf bildirimlerinde atlanır ve alternatif ayırıcıların yerine ön işleme makroları kullanılır.

Tüm yapıcılar hash_multimap.

Tüm oluşturucular, hash_multimap tuşları `Traits` arasında bir düzen oluşturmak için kullanılan ve daha sonra [key_comp](#key_comp)çağırarak döndürülebilen bir işlev nesnesi depolarlar.

İlk üç yapıcı boş bir başlangıç hash_multimap belirtir; ikincisi, elementlerin sırasını belirlemede kullanılacak karşılaştırma fonksiyonunun *(Comp)* türünü belirtir ve üçüncü sisini kullanılacak`_Al`ayırıcı türü ( ) açıkça belirtir. Anahtar kelime, `explicit` belirli türde otomatik tür dönüştürmeyi bastırır.

Dördüncü oluşturucu hash_multimap `Right`bir kopyasını belirtir.

Sonraki üç oluşturucu, sınıf `First, Last)` `Traits` ve ayırıcının karşılaştırma işlevinin türünü belirtirken artan açıklıkla bir haritanın aralığını kopyalar.

Sekizinci yapıcı hash_multimap `Right`hareket eder.

Son üç yapıcı bir initializer_list kullanır.

## <a name="hash_multimapinsert"></a><a name="insert"></a>hash_multimap::ekle

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](../standard-library/unordered-multimap-class.md).

Bir öğeyi veya bir öğe aralığını hash_multimap ekler.

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
|*Val*|Bir öğenin hash_multimap eklenecek değeri, bu öğeyi zaten içermediği sürece veya daha genel olarak, anahtarı eşdeğer sıralanmış bir öğe içermediği sürece.|
|*Nerede*|Doğru ekleme noktasını aramaya nereden başlayacağına dair ipucu.|
|*Ilk*|Bir haritadan kopyalanacak ilk öğenin konumu.|
|*Son*|Bir haritadan kopyalanacak son öğenin hemen ötesindeki konum.|

### <a name="return-value"></a>Dönüş Değeri

İlk iki `insert` üye işlev, yeni öğenin eklendiği konumu gösteren bir yineleyici döndürür.

Üçüncü üye işlev, eklenecek öğeler için bir initializer_list kullanır.

Dördüncü üye işlev, öğe değerlerinin dizisini, belirli bir küme aralığında `[First, Last)` bir yineleyici tarafından adreslenen her öğeye karşılık gelen bir eşlebe ekler.

Son iki `insert` üye işlev, eklenen değeri hareket ettirdikleri-oluşturmaları dışında, ilk ikisiyle aynı şekilde çalışır.

### <a name="remarks"></a>Açıklamalar

Bir öğenin [value_type](#value_type) bir çifttir, böylece bir öğenin değeri ilk bileşenin anahtar değerine eşit, ikinci bileşenise öğenin veri değerine eşit olan sıralı bir çift olacaktır.

Ekleme ipucu sürümü için amortismana tabi sabit zaman `insert`oluşabilir , logaritmik zaman yerine, ekleme noktası hemen *nerede*izlereğer .

## <a name="hash_multimapiterator"></a><a name="iterator"></a>hash_multimap::iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](../standard-library/unordered-multimap-class.md).

hash_multimap herhangi bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleme sağlayan bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::iterator iterator;
```

### <a name="remarks"></a>Açıklamalar

hash_multimap `iterator` tarafından tanımlanan [value_type](#value_type)nesneleri için , hangi `pair` \< tür **const Anahtar, Tip**>, ilk üyesi öğenin anahtarı ve ikinci üyesi öğe tarafından düzenlenen eşlenen datum olan.

hash_multimap bir öğeyi işaret eden bir **yineleyiciyi** `Iter` `->` dereference etmek için işleci kullanın.

Öğe için anahtarın değerine erişmek `Iter`  -> için, **ilk**olarak\* `Iter`( ) değerine eşdeğer olan kullanın. **ilk**. Öğe için eşlenen datum değerine erişmek için, `Iter`  ->  **ikinci**, eşdeğer\* `Iter`( ). **ilk**.

Bir `iterator` tür, bir öğenin değerini değiştirmek için kullanılabilir.

### <a name="example"></a>Örnek

Nasıl bildirilir [begin](#begin) ve kullanılacağına `iterator`bir örnek için başlangıç örneğine bakın.

## <a name="hash_multimapkey_comp"></a><a name="key_comp"></a>hash_multimap:key_comp

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](../standard-library/unordered-multimap-class.md).

Hash_multimap anahtarları sipariş etmek için kullanılan karşılaştırma nesnesinin bir kopyasını alır.

```cpp
key_compare key_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

bir hash_multimap öğelerini sıralamak için kullandığı işlev nesnesini döndürür.

### <a name="remarks"></a>Açıklamalar

Depolanan nesne üye işlevi tanımlar

**bool operator(const Key&** `left` **, const Key** `right` **&);**

önce yse ve sıralama `right` sırasına eşit değilse doğru döndürür. **true** `left`

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

## <a name="hash_multimapkey_compare"></a><a name="key_compare"></a>hash_multimap::key_compare

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](../standard-library/unordered-multimap-class.md).

hash_multimap iki öğenin göreli sırasını belirlemek için iki sıralama anahtarını karşılaştırabilen bir işlev nesnesi sağlayan bir tür.

```cpp
typedef Traits key_compare;
```

### <a name="remarks"></a>Açıklamalar

`key_compare`şablon parametresi *Özellikleri*ile eş anlamlıdır.

*Özellikler* hakkında daha fazla bilgi için [hash_multimap Sınıfı](../standard-library/hash-multimap-class.md) konusuna bakın.

### <a name="example"></a>Örnek

Nasıl bildirilir [key_comp](#key_comp) ve kullanılacağına `key_compare`ilgili bir örnek için key_comp örneğine bakın.

## <a name="hash_multimapkey_type"></a><a name="key_type"></a>hash_multimap:key_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](../standard-library/unordered-multimap-class.md).

hash_multimap her öğesini oluşturan sıralama anahtar nesnesi açıklayan bir tür.

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Açıklamalar

`key_type`şablon parametre *Anahtarı*ile eş anlamlıdır.

*Anahtar*hakkında daha fazla bilgi için [hash_multimap Sınıfı](../standard-library/hash-multimap-class.md) konusunun Açıklamalar bölümüne bakın.

### <a name="example"></a>Örnek

[Nasıl](#value_type) beyan value_type ve kullanılacağına `key_compare`bir örnek için bkz.

## <a name="hash_multimaplower_bound"></a><a name="lower_bound"></a>hash_multimap:lower_bound

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](../standard-library/unordered-multimap-class.md).

Bir hash_multimap ilk öğeye, belirli bir anahtara eşit veya daha büyük bir anahtarla bir yineleyici döndürür.

```cpp
iterator lower_bound(const Key& key);

const_iterator lower_bound(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*Anahtar*\
Aranın hash_multimap bir öğenin tür anahtarıyla karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Bir öğenin konumunu, bağımsız değişken anahtarına eşit veya daha büyük bir anahtarla hash_multimap veya anahtar için eşleşme bulunamazsa hash_multimap'daki son öğeyi başaran konumu gideren bir [yineleyici](#iterator) veya [const_iterator.](#const_iterator)

Bir `const_iterator`, hash_multimap `lower_bound` nesnesinin geri dönüş değeri ne olursa olsun değiştirilemez. Bir `iterator`, hash_multimap `lower_bound` nesnesi için döndürülen değer atanır.

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

## <a name="hash_multimapmapped_type"></a><a name="mapped_type"></a>hash_multimap:mapped_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](../standard-library/unordered-multimap-class.md).

hash_multimap depolanan veri türünü temsil eden bir tür.

```cpp
typedef Type mapped_type;
```

### <a name="remarks"></a>Açıklamalar

`mapped_type`şablon parametresi *Türü*ile eş anlamlıdır.

*Türü* hakkında daha fazla bilgi için [hash_multimap Sınıf](../standard-library/hash-multimap-class.md) konusuna bakın.

### <a name="example"></a>Örnek

[Nasıl](#value_type) beyan value_type ve kullanılacağına `key_type`bir örnek için bkz.

## <a name="hash_multimapmax_size"></a><a name="max_size"></a>hash_multimap::max_size

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](../standard-library/unordered-multimap-class.md).

hash_multimap maksimum uzunluğunu verir.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Mümkün olan en yüksek hash_multimap uzunluğu.

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

## <a name="hash_multimapoperator"></a><a name="op_eq"></a>hash_multimap::operator=

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](../standard-library/unordered-multimap-class.md).

hash_multimap öğelerini başka bir hash_multimap kopyasıyla değiştirir.

```cpp
hash_multimap& operator=(const hash_multimap& right);

hash_multimap& operator=(hash_multimap&& right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Doğru*|[hash_multimap](../standard-library/hash-multimap-class.md) `hash_multimap`kopyalanıyor.|

### <a name="remarks"></a>Açıklamalar

Bir'deki varolan öğeleri `hash_multimap`silersonra , `operator=` *''nin* içeriğini `hash_multimap`kopyalar veya 'ye taşır.

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

## <a name="hash_multimappointer"></a><a name="pointer"></a>hash_multimap::pointer

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](../standard-library/unordered-multimap-class.md).

hash_multimap bir öğeiçin işaretçi sağlayan bir tür.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir `pointer` tür, bir öğenin değerini değiştirmek için kullanılabilir.

Çoğu durumda, hash_multimap bir nesnedeki öğelere erişmek için bir [yineleyici](#iterator) kullanılmalıdır.

## <a name="hash_multimaprbegin"></a><a name="rbegin"></a>hash_multimap::rbegin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](../standard-library/unordered-multimap-class.md).

Ters hash_multimap ilk öğeyi ele alan bir yineleyici döndürür.

```cpp
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```

### <a name="return-value"></a>Dönüş Değeri

Ters hash_multimap ilk öğeyi ele alan veya tersine çevrilmemiş hash_multimap son öğesini ele alan ters çift yönlü bir yineleyici.

### <a name="remarks"></a>Açıklamalar

`rbegin`bir hash_multimap ile [başolarak](#begin) ters hash_multimap kullanılır.

Bir `const_reverse_iterator`,'ye `rbegin` atanırsa, hash_multimap nesnesi değiştirilemez. Bir `reverse_iterator`, hash_multimap `rbegin` nesnesinin geri dönüş değeri ne olursa olsun değiştirilebilir.

`rbegin`geriye doğru bir hash_multimap ile yinelemek için kullanılabilir.

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

## <a name="hash_multimapreference"></a><a name="reference"></a>hash_multimap::başvuru

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](../standard-library/unordered-multimap-class.md).

hash_multimap depolanan bir öğeye başvuru sağlayan bir tür.

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

## <a name="hash_multimaprend"></a><a name="rend"></a>hash_multimap::rend

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](../standard-library/unordered-multimap-class.md).

Ters hash_multimap son öğeyi yerine getiren konumu adresleyen bir yineleyici döndürür.

```cpp
const_reverse_iterator rend() const;

reverse_iterator rend();
```

### <a name="return-value"></a>Dönüş Değeri

Ters hash_multimap 'deki son öğeyi (tersine çevrilmemiş hash_multimap ilk öğeden önce gelen konum) yerine gelen konumu gideren ters çift yönlü bir yineleme.

### <a name="remarks"></a>Açıklamalar

`rend`[uç](#end) bir hash_multimap ile kullanıldığı gibi ters hash_multimap ile kullanılır.

Bir const_reverse_iterator geri `rend` dönüş değeri [const_reverse_iterator](#const_reverse_iterator)atanmışsa, hash_multimap nesnesi değiştirilemez. Bir `rend` [reverse_iterator'a](#reverse_iterator)geri dönüş değeri atanmışsa, hash_multimap nesnesi değiştirilebilir.

`rend`ters yineleyicinin hash_multimap sonuna ulaşıp ulaşmadığını test etmek için kullanılabilir.

Döndürülen `rend` değer dereferenced olmamalıdır.

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

## <a name="hash_multimapreverse_iterator"></a><a name="reverse_iterator"></a>hash_multimap:reverse_iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](../standard-library/unordered-multimap-class.md).

Ters hash_multimap bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleme sağlayan bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::reverse_iterator reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir `reverse_iterator` tür ters hash_multimap ile yinelemek için kullanılır.

hash_multimap `reverse_iterator` tarafından tanımlanan value_type nesneleri için puan [,](#value_type)hangi tür `pair` \< **const Anahtar, Tip**>. Anahtarın değeri ilk üye çift aracılığıyla kullanılabilir ve eşlenen öğenin değeri çiftin ikinci üyesi aracılığıyla kullanılabilir.

### <a name="example"></a>Örnek

Nasıl bildirilir ve kullanılacağına `reverse_iterator`bir örnek için [rbegin](#rbegin) örneğine bakın.

## <a name="hash_multimapsize"></a><a name="size"></a>hash_multimap::boyut

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](../standard-library/unordered-multimap-class.md).

hash_multimap'daki öğe sayısını verir.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Dönüş Değeri

hash_multimap geçerli uzunluğu.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

Aşağıdaki örnek, hash_multimap:boyut üye işlevinin kullanımını göstermektedir.

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

## <a name="hash_multimapsize_type"></a><a name="size_type"></a>hash_multimap:size_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](../standard-library/unordered-multimap-class.md).

Bir hash_multimap öğe sayısını sayan imzasız bir tamsayı türü.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::size_type size_type;
```

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

Nasıl beyan edilip kullanılacağına ilgili bir örnek için [boyut](#size) örneğine bakın`size_type`

## <a name="hash_multimapswap"></a><a name="swap"></a>hash_multimap::takas

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](../standard-library/unordered-multimap-class.md).

İki hash_multimaps öğelerini değiştirir.

```cpp
void swap(hash_multimap& right);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Değiştirilecek unsurları veya hash_multimap unsurları ile değiş tokuş edilecek hash_multimap sağlayan hash_multimap.

### <a name="remarks"></a>Açıklamalar

Üye işlev, öğeleri değiştirilen iki hash_multimaps öğeleri belirleyen hiçbir başvuru, işaretçi veya yineleyicigeçersiz olur.

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

## <a name="hash_multimapupper_bound"></a><a name="upper_bound"></a>hash_multimap:upper_bound

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](../standard-library/unordered-multimap-class.md).

Bir ilk hash_multimap öğeye belirtilen anahtardan büyük bir anahtarla döndürür.

```cpp
iterator upper_bound(const Key& key);

const_iterator upper_bound(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*Anahtar*\
Aranın hash_multimap bir öğenin tür anahtarıyla karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Bir öğenin konumunu bağımsız değişken anahtarından büyük bir anahtarla hash_multimap veya anahtar için eşleşme bulunamazsa hash_multimap'daki son öğeyi başaran konumu gideren bir [yineleyici](#iterator) veya [const_iterator.](#const_iterator)

Bir `const_iterator`, hash_multimap `upper_bound` nesnesinin geri dönüş değeri ne olursa olsun değiştirilemez. Bir `iterator`, hash_multimap `upper_bound` nesnesinin geri dönüş değeri ne olursa olsun değiştirilebilir.

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

## <a name="hash_multimapvalue_comp"></a><a name="value_comp"></a>hash_multimap:value_comp

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](../standard-library/unordered-multimap-class.md).

Üye işlev, anahtar değerlerini karşılaştırarak hash_multimap öğelerin sırasını belirleyen bir işlev nesnesi döndürür.

```cpp
value_compare value_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir hash_multimap öğelerini sıralamak için kullandığı karşılaştırma işlevi nesnesini döndürür.

### <a name="remarks"></a>Açıklamalar

Bir hash_multimap *m*için , eğer iki eleman *e1* (*k1*, *d1*) ve *e2*(*k2*, *d2*) türü [value_type](#value_type)nesneleri, *k1* ve *k2* tip [key_type](#key_type) ve d1 ve *d2* türü [mapped_type](#mapped_type)kendi verileri olan nesneleri , o zaman `m.value_comp()(e1, e2)` eşdeğerdir `m.key_comp()(k1, k2)`. *d2* Depolanan nesne üye işlevi tanımlar

`bool operator( value_type& left, value_type& right);`

anahtar **true** değeri `left` önce yse ve sıralama sırasına `right` eşit değilse doğru döndürür.

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

## <a name="hash_multimapvalue_type"></a><a name="value_type"></a>hash_multimap:value_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](../standard-library/unordered-multimap-class.md).

bir hash_multimap depolanan nesne türünü temsil eden bir tür.

```cpp
typedef pair<const Key, Type> value_type;
```

### <a name="remarks"></a>Açıklamalar

`value_type`çift\<const [key_type](#key_type)olarak bildirilir, [mapped_type](#mapped_type) \<> ve key_type çifti değil, mapped_type>, çünkü bir bağdaştırıcı kapsayıcının anahtarları sabit olmayan bir yineleme veya referans kullanılarak değiştirilemez.

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

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ Standart Kütüphane Başvurusu](../standard-library/cpp-standard-library-reference.md)
