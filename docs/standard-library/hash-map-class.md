---
title: hash_map Sınıfı
ms.date: 11/04/2016
f1_keywords:
- hash_map/stdext::hash_map
- hash_map/stdext::hash_map::allocator_type
- hash_map/stdext::hash_map::const_iterator
- hash_map/stdext::hash_map::const_pointer
- hash_map/stdext::hash_map::const_reference
- hash_map/stdext::hash_map::const_reverse_iterator
- hash_map/stdext::hash_map::difference_type
- hash_map/stdext::hash_map::iterator
- hash_map/stdext::hash_map::key_compare
- hash_map/stdext::hash_map::key_type
- hash_map/stdext::hash_map::mapped_type
- hash_map/stdext::hash_map::pointer
- hash_map/stdext::hash_map::reference
- hash_map/stdext::hash_map::reverse_iterator
- hash_map/stdext::hash_map::size_type
- hash_map/stdext::hash_map::value_type
- hash_map/stdext::hash_map::at
- hash_map/stdext::hash_map::begin
- hash_map/stdext::hash_map::cbegin
- hash_map/stdext::hash_map::cend
- hash_map/stdext::hash_map::clear
- hash_map/stdext::hash_map::count
- hash_map/stdext::hash_map::crbegin
- hash_map/stdext::hash_map::crend
- hash_map/stdext::hash_map::emplace
- hash_map/stdext::hash_map::emplace_hint
- hash_map/stdext::hash_map::empty
- hash_map/stdext::hash_map::end
- hash_map/stdext::hash_map::equal_range
- hash_map/stdext::hash_map::erase
- hash_map/stdext::hash_map::find
- hash_map/stdext::hash_map::get_allocator
- hash_map/stdext::hash_map::insert
- hash_map/stdext::hash_map::key_comp
- hash_map/stdext::hash_map::lower_bound
- hash_map/stdext::hash_map::max_size
- hash_map/stdext::hash_map::rbegin
- hash_map/stdext::hash_map::rend
- hash_map/stdext::hash_map::size
- hash_map/stdext::hash_map::swap
- hash_map/stdext::hash_map::upper_bound
- hash_map/stdext::hash_map::value_comp
helpviewer_keywords:
- stdext::hash_map
- stdext::hash_map::allocator_type
- stdext::hash_map::const_iterator
- stdext::hash_map::const_pointer
- stdext::hash_map::const_reference
- stdext::hash_map::const_reverse_iterator
- stdext::hash_map::difference_type
- stdext::hash_map::iterator
- stdext::hash_map::key_compare
- stdext::hash_map::key_type
- stdext::hash_map::mapped_type
- stdext::hash_map::pointer
- stdext::hash_map::reference
- stdext::hash_map::reverse_iterator
- stdext::hash_map::size_type
- stdext::hash_map::value_type
- stdext::hash_map::at
- stdext::hash_map::begin
- stdext::hash_map::cbegin
- stdext::hash_map::cend
- stdext::hash_map::clear
- stdext::hash_map::count
- stdext::hash_map::crbegin
- stdext::hash_map::crend
- stdext::hash_map::emplace
- stdext::hash_map::emplace_hint
- stdext::hash_map::empty
- stdext::hash_map::end
- stdext::hash_map::equal_range
- stdext::hash_map::erase
- stdext::hash_map::find
- stdext::hash_map::get_allocator
- stdext::hash_map::insert
- stdext::hash_map::key_comp
- stdext::hash_map::lower_bound
- stdext::hash_map::max_size
- stdext::hash_map::rbegin
- stdext::hash_map::rend
- stdext::hash_map::size
- stdext::hash_map::swap
- stdext::hash_map::upper_bound
- stdext::hash_map::value_comp
ms.assetid: 40879dfc-51ba-4a59-9f9e-26208de568a8
ms.openlocfilehash: e8c0da199d8a1e9ba388b960fe07ab6ad6fcf4bc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375462"
---
# <a name="hash_map-class"></a>hash_map Sınıfı

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

Her öğenin değeri benzersiz ve ilişkili bir veri değeri olan bir sıralama anahtarı olan bir çifti olduğu bir koleksiyondan hızlı bir şekilde veri depolar ve alır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Key,
    class Type,
    class Traits=hash_compare<Key, less<Key>>,
    class Allocator=allocator<pair <const Key, Type>>>
class hash_map
```

### <a name="parameters"></a>Parametreler

*Anahtar*\
hash_map depolanacak anahtar veri türü.

*Türü*\
hash_map depolanacak öğe veri türü.

*Özellik*\
İki işlev nesneleri içeren tür, bir sınıf karşılaştırın iki öğe değerleri göreli sırasını belirlemek için sıra anahtarları ve tür imzasız tamsayılar için öğelerin unary `size_t`yüklem anahtar değerleri eşleme bir karma işlevi karşılaştırmak mümkün . Bu bağımsız değişken isteğe `Key`bağlıdır `Key` ve hash_compare<,> > daha az<varsayılan değerdir.

*Ayırıcı*\
hash_map ayırma ve bellek ayırma ile ilgili ayrıntıları kapsülleyen depolanan ayırıcı nesneyi temsil eden tür. Bu bağımsız değişken isteğe bağlıdır ve\<varsayılan değer `Key` `Type` ayırıcı çifti const <,>>.

## <a name="remarks"></a>Açıklamalar

hash_map:

- İlişkili bir anahtar değerine dayalı öğe değerlerinin verimli alınmasını destekleyen bir değişken boyutu kapsayıcı olan ilişkilendirilebilir bir kapsayıcı.

- Çift yönlüdür, çünkü öğelerine erişmek için çift yönlü bir yineleyici sağlar.

- Karma, çünkü elemanları, öğelerin temel değerlerine uygulanan karma işlevin değerine göre kovalar halinde gruplandırılır.

- Benzersizdir, çünkü öğelerinin her birinde benzersiz bir anahtar olması gerekir.

- Bir çift ilişkilendirilebilir kapsayıcıdır, çünkü veri öğelerinin değerleri kendi anahtar değerlerinden farklıdır.

- Sağladığı işlevsellik genel olduğundan ve öğe veya anahtar olarak bulunan belirli veri türünden bağımsız olduğundan, sınıf şablonu. Öğeler ve anahtarlar için kullanılacak veri türleri, karşılaştırma işlevi ve ayırıcı ile birlikte bir sınıf şablonunda parametreler olarak belirtilir.

Sıralama üzerinde karma temel avantajı daha fazla verimlilik; başarılı bir karma eklemeler, silmeler gerçekleştirir ve sıralama teknikleri için kapsayıcıdaki eleman sayısının logaritma ile orantılı bir süre ile karşılaştırıldığında sabit ortalama zaman bulur. Bir hash_map bir öğenin değeri, ancak ilişkili anahtar değeri, doğrudan değiştirilebilir. Bunun yerine, eski öğelerle ilişkili anahtar değerleri silinmeli ve eklenen yeni öğelerle ilişkili yeni anahtar değerleri eklenmelidir.

Kapsayıcı türünün seçimi genelde uygulamanın gerektirdiği arama ve ekleme türüne dayalı olmalıdır. Haşdi hashed musociative kaplar arama, ekleme ve kaldırma işlemleri için optimize edilmiştir. Bu işlemleri açıkça destekleyen üye işlevler, iyi tasarlanmış bir karma işlevle kullanıldığında verimlidir ve bunları ortalama sabit olan ve kapsayıcıdaki öğe sayısına bağlı olmayan bir zamanda gerçekleştirir. İyi tasarlanmış karma işlev karma değerlerin tek tip dağılımını üretir ve farklı anahtar değerleri aynı karma değere eşlendiğinde çakışacağı söylenen çarpışma sayısını en aza indirir. En kötü durumda, mümkün olan en kötü karma işlevi ile, işlem sayısı dizideki eleman sayısıyla (doğrusal zaman) orantılıdır.

Hash_map, değerleri anahtarlarıyla ilişkilendiren koşullar uygulama tarafından karşılandığında tercih edilen ilişkisel kapsayıcı olmalıdır. Bu tür bir yapı için bir model, örneğin, tanımlar sağlayan ilişkili dize değerleri ile benzersiz olarak oluşan anahtar kelimeler sıralı bir listedir. Bunun yerine, sözcüklerin birden fazla doğru tanımı varsa, böylece anahtarlar benzersiz değildi, o zaman bir hash_multimap tercih edilen kapsayıcı olacaktır. Diğer taraftan, yalnızca sözcük listesi depolanıyorsa, hash_set doğru kapsayıcı olurdu. Sözcüklerin birden çok oluşumuna izin verilirse, hash_multiset uygun kapsayıcı yapısı olacaktır.

hash_map, denetlediği sırayı, sınıfın depolanmış karma [value_compare](../standard-library/value-compare-class.md) *Özellikleri* nesnesini value_compare çağırarak sıralar. Bu depolanan nesneye üye işlev [key_comp](#key_comp)çağırılarak erişilebilir. Böyle bir işlev nesnesi, daha az [hash_compare](../standard-library/hash-compare-class.md) Anahtar hash_compare\<daha az Anahtar>> sınıf<hash_compare bir nesne gibi aynı şekilde olmalıdır. Özellikle, tüm değerler için *Anahtar* türü `Traits` `Key` *Anahtar*, çağrı ( ) `size_t`türü değerlerinin bir dağıtım verir.

Genelde, bu sıralamayı oluşturmak için öğelerin yalnızca küçüktür biçiminde karşılaştırılabilir olması gerekir; böylece, herhangi iki öğe belirtildiğinde, eşit oldukları (yani birinin diğerinden daha küçük olmadığı anlamında) veya birinin diğerinden küçük olduğu belirlenebilir. Bu, denk olmayan öğeler arasında bir sıralamaya neden olur. Daha teknik bir not üzerinde, karşılaştırma işlevi standart matematiksel anlamda katı bir zayıf sıralama sevk eden ikili bir koşuldur. İkili yüklem f(x y) iki bağımsız değişken `x` nesnesi `y` ve **doğru** veya **yanlışın**dönüş değeri olan bir işlev nesnesidir. Bir hash_map uygulanan bir sıralama, ikili yüklem inreflexive, antisimetrik ve geçişli ve eşdeğerlik geçişli ise, iki nesne x ve y hem f(x, y) ve f(y, x) yanlış olduğunda eşdeğer olarak tanımlanır sıkı bir zayıf sıralamadır. Anahtarlar arasındaki eşitliğinin daha güçlü koşulu bu denkliğin yerini alırsa, sıralama (içindeki tüm öğelerin birbirine göre sıralanması anlamında) toplam haline gelir ve eşleşen anahtarlar birbirinden ayırt edilemez olacaktır.

Denetlenmiş dizideki öğelerin gerçek sırası karma işlevine, sıralama işlevine ve kapsayıcı nesnesinde depolanan karma tablonun geçerli boyutuna bağlıdır. Karma tablonun geçerli boyutunu belirleyemezsiniz, bu nedenle genel olarak denetitilen dizideki öğelerin sırasını tahmin edemezsiniz. Öğelerin eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; öğelerin kaldırılması yalnızca özellikle kaldırılan öğeleri gösteren yineleyicileri geçersiz kılar.

hash_map sınıfı tarafından sağlanan yineleme iki yönlü bir yinelemedir, ancak sınıf üye işlevleri [şablon](#insert) parametreleri olarak alan sürümlere [sahip](#hash_map) hash_map, işlevsellik gereksinimleri çift yönlü yineleyiciler sınıfı tarafından garanti edilenden daha az olan daha zayıf bir giriş yinelemesi alır. Farklı yineleyici kavramları, işlevselliklerindeki iyileştirmelere göre ilgili bir aile biçimlendirir. Her yineleyici kavramının kendi gereksinimler kümesi vardır ve bunlarla çalışan algoritmaların kendi varsayımlarını yineleyici türü tarafından sağlanan gereksinimlerle sınırlaması gerekir. Bir giriş yineleyicinin bazı nesnelere başvurusunun kaldırılacağı ve dizideki sonraki yineleyiciye artırılabileceği varsayılabilir. Bu en az işlevsellik kümesidir, ancak sınıf üye işlevleri bağlamında bir dizi `[First, Last)` yineleyici hakkında anlamlı bir şekilde konuşabilmek yeterlidir.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[Hash_map](#hash_map)|Boş olan `hash_map` veya başka `hash_map`bir şeyin tamamının veya bir kısmının kopyası olan bir yapı.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[Allocator_type](#allocator_type)|Nesnenin sınıfını `allocator` `hash_map` temsil eden bir tür.|
|[const_iterator](#const_iterator)|Bir öğeyi okuyabilen çift yönlü bir yineleme `const` sağlayan `hash_map`bir tür.|
|[Const_pointer](#const_pointer)|Bir **const** öğesine işaretçi sağlayan `hash_map`bir tür .|
|[const_reference](#const_reference)|Const **işlemleri** okumak ve gerçekleştirmek için bir `hash_map` **const** öğesinde depolanan bir öğeye başvuru sağlayan bir tür.|
|[Const_reverse_iterator](#const_reverse_iterator)|Herhangi bir const öğeyi okuyabilen çift yönlü bir yineleme sağlayan bir tür. **const** `hash_map`|
|[difference_type](#difference_type)|Yineleyiciler tarafından işaret edilen öğeler arasındaki aralıktaki bir `hash_map` aralığın öğelerinin sayısını temsil etmek için kullanılabilecek imzalı bir tamsayı türü.|
|[Yineleyici](#iterator)|Bir 'deki herhangi bir öğeyi okuyabilen veya değiştirebilen `hash_map`çift yönlü bir yineleme sağlayan bir tür.|
|[Key_compare](#key_compare)|İki öğenin göreli sırasını belirlemek için iki sıralama anahtarını karşılaştırabilen bir işlev nesnesi `hash_map`sağlayan bir tür.|
|[Key_type](#key_type)|Bir `hash_map`tür, .'ın her öğesini oluşturan sıralama anahtar nesnesini açıklar.|
|[mapped_type](#mapped_type)|Bir 'de depolanan veri türünü `hash_map`temsil eden bir tür|
|[pointer](#pointer)|Bir öğedeki bir öğeye işaretçi sağlayan bir `hash_map`tür|
|[Başvuru](#reference)|Bir 'de depolanan bir öğeye `hash_map`başvuru sağlayan bir tür|
|[Reverse_iterator](#reverse_iterator)|Ters bir öğedeki bir öğeyi okuyabilen veya değiştirebilen `hash_map`çift yönlü bir yineleme sağlayan bir tür.|
|[size_type](#size_type)|Bir 'deki öğe sayısını temsil eden imzasız `hash_map`bir tamsayı türü|
|[value_type](#value_type)|İki öğeyi sıraanahtarları olarak karşılaştırabilen bir işlev nesnesi `hash_map`sağlayan bir tür.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[at](#at)|Belirli bir anahtar `hash_map` değeri olan bir öğeyi bulur.|
|[Başlamak](#begin)|'deki ilk öğeyi ele alan bir `hash_map`yineleyici döndürür.|
|[cbegin](#cbegin)|'deki ilk öğeyi ele alan bir const yineleyici döndürür. `hash_map`|
|[cend](#cend)|Bir `hash_map`'deki son öğeyi yerine getiren konumu gideren bir const yineleyici döndürür.|
|[Temizleyin](#clear)|Bir' `hash_map`nin tüm öğelerini siler.|
|[Sayısı](#count)|Anahtarı parametre yle `hash_map` belirtilen bir anahtarla eşleşen bir öğedeki öğe sayısını döndürür.|
|[crbegin](#crbegin)|Ters bir ilk öğeyi ele alan bir const yineleyici döndürür. `hash_map`|
|[crend](#crend)|Ters bir önceki son öğeyi yerine getiren konumu gideren bir `hash_map`const yineleyici döndürür.|
|[emplace](#emplace)|Yerinde inşa edilmiş bir öğeyi `hash_map`bir .|
|[emplace_hint](#emplace_hint)|Yerinde `hash_map`oluşturulmuş bir öğeyi yerleştirme ipucuyla ekler.|
|[empty](#empty)|A boşsa `hash_map` sınar.|
|[Son -unda](#end)|Bir 'deki son öğeyi yerine getiren konumu adresleyen `hash_map`bir yineleyici döndürür.|
|[equal_range](#equal_range)|Bir çift yineleyiciyi, sırasıyla, belirtilen bir `hash_map` anahtardan büyük bir anahtarla ilk öğeye ve `hash_map` anahtara eşit veya daha büyük bir anahtarla ilk öğeye döndürür.|
|[Silmek](#erase)|Belirli `hash_map` konumlardaki bir öğeyi veya bir dizi öğeyi kaldırır|
|[find](#find)|Belirtilen bir anahtara eşdeğer anahtara sahip bir `hash_map` öğedeki öğenin konumunu ele alan bir yineleyici döndürür.|
|[Get_allocator](#get_allocator)|Oluşturmak için kullanılan `allocator` nesnenin bir `hash_map`kopyasını döndürür.|
|[Ekle](#insert)|Bir öğeye veya bir dizi öğeye `hash_map`bir öğe ekler.|
|[Key_comp](#key_comp)|Bir yineleyiciyi, belirtilen bir anahtara eşit veya daha büyük bir anahtar değeriolan ilk `hash_map` öğeye döndürür.|
|[lower_bound](#lower_bound)|Bir yineleyiciyi, belirtilen bir anahtara eşit veya daha büyük bir anahtar değeriolan ilk `hash_map` öğeye döndürür.|
|[max_size](#max_size)|Maksimum uzunluğu `hash_map`verir.|
|[rbegin](#rbegin)|Ters bir ilk öğeyi ele alan bir `hash_map`yineleyici döndürür.|
|[Rend](#rend)|Ters çevrilmiş bir son öğedeki son öğeyi yerine `hash_map`getiren konumu adresleyen bir yineleyici döndürür.|
|[Boyutu](#size)|`hash_map`'deki öğe sayısını verir.|
|[Takas](#swap)|İki `hash_map`s'nin öğelerini değiştirir.|
|[upper_bound](#upper_bound)|Bir yineleyiciyi, belirtilen bir anahtardan daha büyük bir anahtar değerine sahip olan ilk `hash_map` öğeye döndürür.|
|[value_comp](#value_comp)|Bir `hash_map`' deki öğe değerlerini sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operatör&#91;&#93;](#op_at)|Bir öğeyi belirli `hash_map` bir anahtar değeri olan bir öğeye ekler.|
|[hash_map::operator=](#op_eq)|Bir `hash_map` öğenin öğelerini başka `hash_map`bir kopyayla değiştirir.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<hash_map>

**Ad alanı:** stdext

## <a name="hash_mapallocator_type"></a><a name="allocator_type"></a>hash_map:allocator_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

hash_map nesnesinin ayırıcı sınıfını temsil eden bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::allocator_type allocator_type;
```

### <a name="example"></a>Örnek

Get_allocator için [get_allocator](#get_allocator) örnek bkz. `allocator_type`

## <a name="hash_mapat"></a><a name="at"></a>hash_map::at

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

Belirli bir anahtar değeri olan bir hash_map öğesini bulur.

```cpp
Type& at(const Key& key);

const Type& at(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*anahtar*|Bulunacak öğenin anahtar değeri.|

### <a name="return-value"></a>Dönüş Değeri

Bulunan öğenin veri değerine bir başvuru.

### <a name="remarks"></a>Açıklamalar

Bağımsız değişken anahtar değeri bulunamazsa, işlev [sınıf out_of_range](../standard-library/out-of-range-class.md)bir nesne atar.

### <a name="example"></a>Örnek

```cpp
// hash_map_at.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   typedef pair <const int, int> cInt2Int;
   hash_map <int, int> hm1;

   // Insert data values
   hm1.insert ( cInt2Int ( 1, 10 ) );
   hm1.insert ( cInt2Int ( 2, 20 ) );
   hm1.insert ( cInt2Int ( 3, 30 ) );

   cout  << "The values of the mapped elements are:";
   for ( int i = 1 ; i <= hm1.size() ; i++ )
      cout << " " << hm1.at(i);
   cout << "." << endl;
}
```

## <a name="hash_mapbegin"></a><a name="begin"></a>hash_map::başlangıç

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

hash_map'daki ilk öğeyi ele alan bir yineleyici döndürür.

```cpp
const_iterator begin() const;

iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

boş bir hash_map hash_map veya konumuilk öğeyi ele alan çift yönlü bir yineleyici.

### <a name="example"></a>Örnek

```cpp
// hash_map_begin.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1;

   hash_map <int, int> :: iterator hm1_Iter;
   hash_map <int, int> :: const_iterator hm1_cIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 0, 0 ) );
   hm1.insert ( Int_Pair ( 1, 1 ) );
   hm1.insert ( Int_Pair ( 2, 4 ) );

   hm1_cIter = hm1.begin ( );
   cout << "The first element of hm1 is "
        << hm1_cIter -> first << "." << endl;

   hm1_Iter = hm1.begin ( );
   hm1.erase ( hm1_Iter );

   // The following 2 lines would err because the iterator is const
   // hm1_cIter = hm1.begin ( );
   // hm1.erase ( hm1_cIter );

   hm1_cIter = hm1.begin( );
   cout << "The first element of hm1 is now "
        << hm1_cIter -> first << "." << endl;
}
```

```Output
The first element of hm1 is 0.
The first element of hm1 is now 1.
```

## <a name="hash_mapcbegin"></a><a name="cbegin"></a>hash_map::cbegin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

hash_map ilk öğeyi ele alan bir const yineleyici döndürür.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

[hash_map'daki](../standard-library/hash-map-class.md) ilk öğeyi veya boş `hash_map`bir konumdan sonra gelen bir konst çift yönlü yineleme.

### <a name="example"></a>Örnek

```cpp
// hash_map_cbegin.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1;

   hash_map <int, int> :: const_iterator hm1_cIter;
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

## <a name="hash_mapcend"></a><a name="cend"></a>hash_map::cend

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

Hash_map son öğeyi yerine getiren konumu gideren bir const yineleyici döndürür.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Dönüş Değeri

[Bir hash_map](../standard-library/hash-map-class.md)son öğeyi yerine getiren konumu gideren bir const çift yönlü yineleme. Eğer `hash_map` boşsa, `hash_map::cend == hash_map::begin`o zaman.

### <a name="remarks"></a>Açıklamalar

`cend`bir yineleyicinin sonuna ulaşıp ulaşmadığını test `hash_map`etmek için kullanılır.

Döndürülen `cend` değer dereferenced olmamalıdır.

### <a name="example"></a>Örnek

```cpp
// hash_map_cend.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1;

   hash_map <int, int> :: const_iterator hm1_cIter;
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

## <a name="hash_mapclear"></a><a name="clear"></a>hash_map::açık

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

bir hash_map tüm öğelerini siler.

```cpp
void clear();
```

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

Aşağıdaki örnek, hash_map::clear üye işlevinin kullanımını göstermektedir.

```cpp
// hash_map_clear.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
    using namespace std;
    using namespace stdext;
    hash_map<int, int> hm1;
    hash_map<int, int>::size_type i;
    typedef pair<int, int> Int_Pair;

    hm1.insert(Int_Pair(1, 1));
    hm1.insert(Int_Pair(2, 4));

    i = hm1.size();
    cout << "The size of the hash_map is initially "
         << i << "." << endl;

    hm1.clear();
    i = hm1.size();
    cout << "The size of the hash_map after clearing is "
         << i << "." << endl;
}
```

```Output
The size of the hash_map is initially 2.
The size of the hash_map after clearing is 0.
```

## <a name="hash_mapconst_iterator"></a><a name="const_iterator"></a>hash_map:const_iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

hash_map bir **const** öğeyi okuyabilen çift yönlü bir yineleme sağlayan bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_iterator const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir `const_iterator` tür, bir öğenin değerini değiştirmek için kullanılamaz.

hash_map `const_iterator` tarafından tanımlanan value_type nesneleri olan [value_type](#value_type), yani tür `pair< const Key, Type >`, ilk üyesi öğenin anahtarı dır ve ikinci üyesi öğe tarafından tutulan eşlenen datum olan öğelere işaret eder.

hash_map bir `const_iterator` `cIter` öğeyi işaret eden bir öğeyi `->` belirtmek için işleci kullanın.

Öğe için anahtarın değerine erişmek `cIter->first`için, 'ye `(*cIter).first`eşdeğer olan ' ı kullanın. Öğe için eşlenen datum değerine erişmek için, 'ye `cIter->second` `(*cIter).second`eşdeğer olan ' ı kullanın.

### <a name="example"></a>Örnek

Bir `const_iterator`örnek kullanarak [başlamak](#begin) için örneğe bakın.

## <a name="hash_mapconst_pointer"></a><a name="const_pointer"></a>hash_map:const_pointer

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

bir hash_map bir **const** öğesi için bir işaretçi sağlayan bir tür.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::const_pointer const_pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir `const_pointer` tür, bir öğenin değerini değiştirmek için kullanılamaz.

Çoğu durumda, bir hash_map nesnesindeki öğelere erişmek için bir [yineleyici](#iterator) kullanılmalıdır.

## <a name="hash_mapconst_reference"></a><a name="const_reference"></a>hash_map:const_reference

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

**Const** işlemleri okumak ve gerçekleştirmek için hash_map depolanan **bir const** öğesine başvuru sağlayan bir tür.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::const_reference const_reference;
```

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_map_const_ref.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map<int, int> hm1;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );

   // Declare and initialize a const_reference &Ref1
   // to the key of the first element
   const int &Ref1 = ( hm1.begin( ) -> first );

   // The following line would cause an error because the
   // non-const_reference cannot be used to access the key
   // int &Ref1 = ( hm1.begin( ) -> first );

   cout << "The key of the first element in the hash_map is "
        << Ref1 << "." << endl;

   // Declare and initialize a reference &Ref2
   // to the data value of the first element
   int &Ref2 = ( hm1.begin( ) -> second );

   cout << "The data value of the first element in the hash_map is "
        << Ref2 << "." << endl;
}
```

```Output
The key of the first element in the hash_map is 1.
The data value of the first element in the hash_map is 10.
```

## <a name="hash_mapconst_reverse_iterator"></a><a name="const_reverse_iterator"></a>hash_map::const_reverse_iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

hash_map herhangi bir **const** öğeyi okuyabilen çift yönlü bir yineleme sağlayan bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_reverse)iterator const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir `const_reverse_iterator` tür bir öğenin değerini değiştiremez ve hash_map ters olarak yinelemek için kullanılır.

hash_map `const_reverse_iterator` tarafından tanımlanan value_type nesneleri olan elemanlar [için](#value_type) `pair` \< tanımlanan , bu tür **const Anahtar, Tip**>, ilk üyesi öğenin anahtarı ve ikinci üyesi öğe tarafından düzenlenen eşlenen datum olduğunu.

hash_map bir `const_reverse_iterator` `crIter` öğeyi işaret eden bir öğeyi **->** belirtmek için işleci kullanın.

Öğe için anahtarın değerine erişmek `crIter`  -> için, **önce**(\* `crIter`) **.first'e**eşdeğer olan ' ı kullanın. Öğe için eşlenen datum değerine erişmek için, `crIter`  ->  **ikinci**, eşdeğer\* `crIter`( ). **ilk**.

### <a name="example"></a>Örnek

Nasıl beyan edilip kullanılacağına bir örnek için `const_reverse_iterator` [rend](#rend) örneğine bakın.

## <a name="hash_mapcount"></a><a name="count"></a>hash_map::say

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

Anahtarı parametre yle belirtilen anahtarla eşleşen bir hash_map öğe sayısını verir.

```cpp
size_type count(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*Anahtar*\
hash_map eşleşecek öğelerin temel değeri.

### <a name="return-value"></a>Dönüş Değeri

1 hash_map, sıralama anahtarı parametre anahtarıyla eşleşen bir öğe içeriyorsa; 0 hash_map eşleşen bir anahtar ile bir öğe içermiyorsa.

### <a name="remarks"></a>Açıklamalar

Üye işlev aralıktaki *x* eleman sayısını döndürür

\[lower_bound (*anahtar*), upper_bound (*anahtar*)

benzersiz bir bağdaştırıcı konteyner olan hash_map durumunda 0 veya 1'dir.

### <a name="example"></a>Örnek

Aşağıdaki örnek, hash_map::count üye işlevinin kullanımını göstermektedir.

```cpp
// hash_map_count.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main()
{
    using namespace std;
    using namespace stdext;
    hash_map<int, int> hm1;
    hash_map<int, int>::size_type i;
    typedef pair<int, int> Int_Pair;

    hm1.insert(Int_Pair (1, 1));
    hm1.insert(Int_Pair (2, 1));
    hm1.insert(Int_Pair (1, 4));
    hm1.insert(Int_Pair (2, 1));

    // Keys must be unique in hash_map, so duplicates are ignored
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
The number of elements in hm1 with a sort key of 1 is: 1.
The number of elements in hm1 with a sort key of 2 is: 1.
The number of elements in hm1 with a sort key of 3 is: 0.
```

## <a name="hash_mapcrbegin"></a><a name="crbegin"></a>hash_map::crbegin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

Ters hash_map ilk öğeyi ele alan bir const yineleyici döndürür.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters [hash_map](../standard-library/hash-map-class.md) ilk öğeyi ele alan veya tersine çevrilmemiş `hash_map`son öğeyi ele alan const ters yönlü bir yineleme.

### <a name="remarks"></a>Açıklamalar

`crbegin`bir ile kullanılır [gibi](#begin) ters hash_map ile `hash_map`kullanılır .

İade değeri ile `crbegin` `hash_map` nesne değiştirilemez.

`crbegin``hash_map` geriye doğru doğrulamak için kullanılabilir.

### <a name="example"></a>Örnek

```cpp
// hash_map_crbegin.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1;

   hash_map <int, int> :: const_reverse_iterator hm1_crIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 3, 30 ) );

   hm1_crIter = hm1.crbegin( );
   cout << "The first element of the reversed hash_map hm1 is "
        << hm1_crIter -> first << "." << endl;
}
```

```Output
The first element of the reversed hash_map hm1 is 3.
```

## <a name="hash_mapcrend"></a><a name="crend"></a>hash_map::crend

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

Ters hash_map son öğeyi yerine getiren konumu gideren bir const yineleyici döndürür.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters [hash_map](../standard-library/hash-map-class.md) 'deki son öğeyi başaran konumu (ters çevrilmemiş `hash_map`ilk öğeden önce gelen konum) gideren const ters çift yönlü bir yineleme.

### <a name="remarks"></a>Açıklamalar

`crend`hash_map gibi ters `hash_map` bir ile [kullanılır::end](#end) `hash_map`ile kullanılır .

İade değeri ile `crend` `hash_map` nesne değiştirilemez.

`crend`ters yineleyicinin sonuna ulaşıp ulaşmadığını test etmek için `hash_map`kullanılabilir.

Döndürülen `crend` değer dereferenced olmamalıdır.

### <a name="example"></a>Örnek

```cpp
// hash_map_crend.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1;

   hash_map <int, int> :: const_reverse_iterator hm1_crIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 3, 30 ) );

   hm1_crIter = hm1.crend( );
   hm1_crIter--;
   cout << "The last element of the reversed hash_map hm1 is "
        << hm1_crIter -> first << "." << endl;
}
```

```Output
The last element of the reversed hash_map hm1 is 3.
```

## <a name="hash_mapdifference_type"></a><a name="difference_type"></a>hash_map::difference_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

Yineleyiciler tarafından işaret edilen öğeler arasında bir aralıkta bir hash_map öğelerinin sayısını temsil etmek için kullanılabilecek imzalı bir tamsayı türü.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::difference_type difference_type;
```

### <a name="example"></a>Örnek

```cpp
// hash_map_diff_type.cpp
// compile with: /EHsc
#include <iostream>
#include <hash_map>
#include <algorithm>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 2, 20 ) );
   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 3, 20 ) );

   // The following won't insert, because map keys are unique
   hm1.insert ( Int_Pair ( 2, 30 ) );

   hash_map <int, int>::iterator hm1_Iter, hm1_bIter, hm1_eIter;
   hm1_bIter = hm1.begin( );
   hm1_eIter = hm1.end( );

   // Count the number of elements in a hash_map
   hash_map <int, int>::difference_type  df_count = 0;
   hm1_Iter = hm1.begin( );
   while ( hm1_Iter != hm1_eIter)
   {
      df_count++;
      hm1_Iter++;
   }

   cout << "The number of elements in the hash_map hm1 is: "
        << df_count << "." << endl;

   cout  << "The keys of the mapped elements are:";
   for ( hm1_Iter= hm1.begin( ) ; hm1_Iter!= hm1.end( ) ;
         hm1_Iter++)
      cout << " " << hm1_Iter-> first;
   cout << "." << endl;

   cout  << "The values of the mapped elements are:";
   for ( hm1_Iter= hm1.begin( ) ; hm1_Iter!= hm1.end( ) ;
         hm1_Iter++)
      cout << " " << hm1_Iter-> second;
   cout << "." << endl;
}
```

```Output
The number of elements in the hash_map hm1 is: 3.
The keys of the mapped elements are: 1 2 3.
The values of the mapped elements are: 10 20 20.
```

## <a name="hash_mapemplace"></a><a name="emplace"></a>hash_map::emplace

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

Yerinde inşa edilmiş bir öğeyi hash_map ekler.

```cpp
template <class ValTy>
pair <iterator, bool>
emplace(
    ValTy&& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Val*|Zaten bu öğeyi (veya daha genel olarak, anahtarı `hash_map` eşdeğer sıralanmış bir öğe) içermediği [sürece, hash_map](../standard-library/hash-map-class.md) eklenecek bir öğeyi taşımak için kullanılan değer.|

### <a name="return-value"></a>Dönüş Değeri

Üye `emplace` işlev, ekleme yapılmışsa bool bileşeni doğru döndüren ve `hash_map` anahtar siparişte eşdeğer değere sahip bir öğe yi içeren ve yineleme bileşeni yeni bir öğenin eklendiği veya öğenin bulunduğu adresi döndüren bir öğe varsa yanlış olan bir çifti döndürür.

Bu üye işlev tarafından döndürülen `pr` bir çiftin yineleyici `pr.first`bileşenine erişmek için, `*(pr.first)`bunu kullanmak ve dereference için, kullanın . Bu üye işlev tarafından döndürülen bir çiftin `pr` **bool** bileşenine erişmek için, bunu kullanmak `pr.second`ve dereference için, kullanın `*(pr.second)`.

### <a name="remarks"></a>Açıklamalar

Bir öğenin [hash_map::value_type](#value_type) bir çifttir, böylece bir öğenin değeri, ilk bileşen anahtar değerine eşit, ikinci bileşen ise öğenin veri değerine eşit olan sıralı bir çift olacaktır.

### <a name="example"></a>Örnek

```cpp
// hash_map_emplace.cpp
// compile with: /EHsc
#include<hash_map>
#include<iostream>
#include <string>

int main()
{
    using namespace std;
    using namespace stdext;
    hash_map<int, string> hm1;
    typedef pair<int, string> is1(1, "a");

    hm1.emplace(move(is1));
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

## <a name="hash_mapemplace_hint"></a><a name="emplace_hint"></a>hash_map:emplace_hint

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

Bir yerleşim ipucu ile, bir hash_map içine yerinde inşa edilmiş bir öğe ekler.

```cpp
template <class ValTy>
iterator emplace_hint(
    const_iterator _Where,
    ValTy&& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Val*|Zaten bu öğeyi (veya daha genel olarak, anahtarı `hash_map` eşdeğer sıralanmış bir öğe) içermediği [sürece, hash_map](../standard-library/hash-map-class.md) eklenecek bir öğeyi taşımak için kullanılan değer.|
|*_Where*|Doğru ekleme noktasını aramaya başlamak için yerle ilgili bir ipucu.|

### <a name="return-value"></a>Dönüş Değeri

[hash_multimap::emplace](../standard-library/hash-multimap-class.md#emplace) üye işlevi, yeni öğenin eklendiği `hash_map`veya eşdeğer sıralamaya sahip varolan öğenin bulunduğu konumu gösteren bir yineleyici döndürür.

### <a name="remarks"></a>Açıklamalar

Bir öğenin [hash_map::value_type](#value_type) bir çifttir, böylece bir öğenin değeri, ilk bileşen anahtar değerine eşit, ikinci bileşen ise öğenin veri değerine eşit olan sıralı bir çift olacaktır.

Ekleme noktası hemen *_Where*takip ederse, logaritmik zaman yerine, amortismana tabi sabit zaman oluşabilir.

### <a name="example"></a>Örnek

```cpp
// hash_map_emplace_hint.cpp
// compile with: /EHsc
#include<hash_map>
#include<iostream>
#include <string>

int main()
{
    using namespace std;
    using namespace stdext;
    hash_map<int, string> hm1;
    typedef pair<int, string> is1(1, "a");

    hm1.emplace(hm1.begin(), move(is1));
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

## <a name="hash_mapempty"></a><a name="empty"></a>hash_map::boş

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

hash_map boşolup hash_map.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

hash_map boşsa **doğrudur;** hash_map boş değilse **yanlış.**

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_map_empty.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1, hm2;

   typedef pair <int, int> Int_Pair;
   hm1.insert ( Int_Pair ( 1, 1 ) );

   if ( hm1.empty( ) )
      cout << "The hash_map hm1 is empty." << endl;
   else
      cout << "The hash_map hm1 is not empty." << endl;

   if ( hm2.empty( ) )
      cout << "The hash_map hm2 is empty." << endl;
   else
      cout << "The hash_map hm2 is not empty." << endl;
}
```

```Output
The hash_map hm1 is not empty.
The hash_map hm2 is empty.
```

## <a name="hash_mapend"></a><a name="end"></a>hash_map::sonu

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

Hash_map son öğeyi yerine getiren konumu adresleyen bir yineleyici döndürür.

```cpp
const_iterator end() const;

iterator end();
```

### <a name="return-value"></a>Dönüş Değeri

Bir hash_map son öğesini yerine getiren konumu ele alan çift yönlü bir yineleyici. hash_map boşsa, hash_map::end == hash_map::begin.

### <a name="remarks"></a>Açıklamalar

`end`bir yineleyicinin hash_map sonuna ulaşıp ulaşmadığını test etmek için kullanılır.

Döndürülen `end` değer dereferenced olmamalıdır.

### <a name="example"></a>Örnek

```cpp
// hash_map_end.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1;

   hash_map <int, int> :: iterator hm1_Iter;
   hash_map <int, int> :: const_iterator hm1_cIter;
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

## <a name="hash_mapequal_range"></a><a name="equal_range"></a>hash_map:equal_range

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

Bir hash_map ilk öğeye sırasıyla bir çift yineleyici, belirtilen bir anahtardan büyük bir anahtarla ve anahtara eşit veya daha büyük bir anahtarla hash_map ilk öğeye döndürür.

```cpp
pair <const_iterator, const_iterator> equal_range (const Key& key) const;

pair <iterator, iterator> equal_range (const Key& key);
```

### <a name="parameters"></a>Parametreler

*Anahtar*\
Bağımsız değişken anahtar değeri, aranmakta olan hash_map bir öğenin tür anahtarıyla karşılaştırılacak.

### <a name="return-value"></a>Dönüş Değeri

İlki anahtarın [lower_bound,](#lower_bound) ikincisi anahtarın [upper_bound](#upper_bound) olacak şekilde bir çift yineleyici.

Üye işlev tarafından döndürülen bir `pr` çiftin ilk yineleyicisine `pr`erişmek için. **ilk** ve alt sınır yineleyici dereference \*için, kullanın ( `pr`. **ilk**). Üye işlev tarafından döndürülen bir `pr` çiftin ikinci yineleyicisine `pr`erişmek için. **ikinci** ve üst sınır yineleyici dereference \*için, kullanın ( `pr`. **ikinci**).

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_map_equal_range.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   typedef hash_map <int, int> IntMap;
   IntMap hm1;
   hash_map <int, int> :: const_iterator hm1_RcIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );
   hm1.insert ( Int_Pair ( 3, 30 ) );

   pair <IntMap::const_iterator, IntMap::const_iterator> p1, p2;
   p1 = hm1.equal_range( 2 );

   cout << "The lower bound of the element with "
        << "a key of 2 in the hash_map hm1 is: "
        << p1.first -> second << "." << endl;

   cout << "The upper bound of the element with "
        << "a key of 2 in the hash_map hm1 is: "
        << p1.second -> second << "." << endl;

   // Compare the upper_bound called directly
   hm1_RcIter = hm1.upper_bound( 2 );

   cout << "A direct call of upper_bound( 2 ) gives "
        << hm1_RcIter -> second << "," << endl
        << "matching the 2nd element of the pair"
        << " returned by equal_range( 2 )." << endl;

   p2 = hm1.equal_range( 4 );

   // If no match is found for the key,
   // both elements of the pair return end( )
   if ( ( p2.first == hm1.end( ) ) && ( p2.second == hm1.end( ) ) )
      cout << "The hash_map hm1 doesn't have an element "
             << "with a key less than 40." << endl;
   else
      cout << "The element of hash_map hm1 with a key >= 40 is: "
           << p1.first -> first << "." << endl;
}
```

```Output
The lower bound of the element with a key of 2 in the hash_map hm1 is: 20.
The upper bound of the element with a key of 2 in the hash_map hm1 is: 30.
A direct call of upper_bound( 2 ) gives 30,
matching the 2nd element of the pair returned by equal_range( 2 ).
The hash_map hm1 doesn't have an element with a key less than 40.
```

## <a name="hash_maperase"></a><a name="erase"></a>hash_map::silme

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

Hash_map bir öğeyi veya bir öğe aralığını belirtilen konumlardan kaldırır veya belirtilen anahtarla eşleşen öğeleri kaldırır.

```cpp
iterator erase(iterator _Where);

iterator erase(iterator first, iterator last);

size_type erase(const key_type& key);
```

### <a name="parameters"></a>Parametreler

*_Where*\
Hash_map kaldırılacak öğenin konumu.

*Ilk*\
hash_map kaldırılan ilk öğenin konumu.

*Son*\
hash_map kaldırılan son öğenin hemen ötesine yerleştirin.

*Anahtar*\
hash_map kaldırılacak öğelerin temel değeri.

### <a name="return-value"></a>Dönüş Değeri

İlk iki üye işlev için, kaldırılan öğelerin ötesinde kalan ilk öğeyi belirleyen çift yönlü bir yineleyici veya böyle bir öğe yoksa hash_map sonuna işaretçi.

Üçüncü üye işlev için, hash_map kaldırılan öğelerin sayısını döndürür.

### <a name="remarks"></a>Açıklamalar

Üye işlevler hiçbir zaman bir özel durum atmaz.

### <a name="example"></a>Örnek

Aşağıdaki örnek, hash_map::delete üye işlevinin kullanımını göstermektedir.

```cpp
// hash_map_erase.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main()
{
    using namespace std;
    using namespace stdext;
    hash_map<int, int> hm1, hm2, hm3;
    hash_map<int, int> :: iterator pIter, Iter1, Iter2;
    int i;
    hash_map<int, int>::size_type n;
    typedef pair<int, int> Int_Pair;

    for (i = 1; i < 5; i++)
    {
        hm1.insert(Int_Pair (i, i));
        hm2.insert(Int_Pair (i, i*i));
        hm3.insert(Int_Pair (i, i-1));
    }

    // The 1st member function removes an element at a given position
    Iter1 = ++hm1.begin();
    hm1.erase(Iter1);

    cout << "After the 2nd element is deleted, the hash_map hm1 is:";
    for (pIter = hm1.begin(); pIter != hm1.end(); pIter++)
        cout << " " << pIter -> second;
    cout << "." << endl;

    // The 2nd member function removes elements
    // in the range [ first,  last)
    Iter1 = ++hm2.begin();
    Iter2 = --hm2.end();
    hm2.erase(Iter1, Iter2);

    cout << "After the middle two elements are deleted, "
         << "the hash_map hm2 is:";
    for (pIter = hm2.begin(); pIter != hm2.end(); pIter++)
        cout << " " << pIter -> second;
    cout << "." << endl;

    // The 3rd member function removes elements with a given  key
    n = hm3.erase(2);

    cout << "After the element with a key of 2 is deleted,\n"
         << "the hash_map hm3 is:";
    for (pIter = hm3.begin(); pIter != hm3.end(); pIter++)
        cout << " " << pIter -> second;
    cout << "." << endl;

    // The 3rd member function returns the number of elements removed
    cout << "The number of elements removed from hm3 is: "
         << n << "." << endl;

    // The dereferenced iterator can also be used to specify a key
    Iter1 = ++hm3.begin();
    hm3.erase(Iter1);

    cout << "After another element with a key equal to that"
         << endl;
    cout  << "of the 2nd element is deleted, "
          << "the hash_map hm3 is:";
    for (pIter = hm3.begin(); pIter != hm3.end(); pIter++)
        cout << " " << pIter -> second;
    cout << "." << endl;
}
```

```Output
After the 2nd element is deleted, the hash_map hm1 is: 1 3 4.
After the middle two elements are deleted, the hash_map hm2 is: 1 16.
After the element with a key of 2 is deleted,
the hash_map hm3 is: 0 2 3.
The number of elements removed from hm3 is: 1.
After another element with a key equal to that
of the 2nd element is deleted, the hash_map hm3 is: 0 3.
```

## <a name="hash_mapfind"></a><a name="find"></a>hash_map::bul

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

Belirli bir anahtara eşdeğer anahtara sahip bir hash_map öğenin konumunu ele alan bir yineleyici döndürür.

```cpp
iterator find(const Key& key);

const_iterator find(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*Anahtar*\
Aranmakta olan hash_map öğenin tür anahtarıyla eşleşecek anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

Belirli bir anahtarla bir öğenin konumunu veya anahtar için eşleşme bulunamazsa hash_map'daki son öğeyi başaran konumu adresleyen bir yineleyici.

### <a name="remarks"></a>Açıklamalar

`find`hash_map bir öğeyi ele alan ve sıralama anahtarı, karşılaştırılabilirlik ilişkisinden daha az bir ilişkiye dayalı bir sıralamayı neden eden ikili bir yüklem altında bağımsız değişken anahtarına eşdeğer olan bir öğeyi döndürür.

Bir const_iterator geri `find` dönüş değeri [const_iterator](#const_iterator)atanırsa, hash_map nesnesi değiştirilemez. Bir `find` [yineleyiciye](#iterator)atanan geri dönüş değeri, hash_map nesnesi değiştirilebilir

### <a name="example"></a>Örnek

```cpp
// hash_map_find.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1;
   hash_map <int, int> :: const_iterator hm1_AcIter, hm1_RcIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );
   hm1.insert ( Int_Pair ( 3, 30 ) );

   hm1_RcIter = hm1.find( 2 );
   cout << "The element of hash_map hm1 with a key of 2 is: "
        << hm1_RcIter -> second << "." << endl;

   // If no match is found for the key, end( ) is returned
   hm1_RcIter = hm1.find( 4 );

   if ( hm1_RcIter == hm1.end( ) )
      cout << "The hash_map hm1 doesn't have an element "
           << "with a key of 4." << endl;
   else
      cout << "The element of hash_map hm1 with a key of 4 is: "
           << hm1_RcIter -> second << "." << endl;

   // The element at a specific location in the hash_map can be found
   // using a dereferenced iterator addressing the location
   hm1_AcIter = hm1.end( );
   hm1_AcIter--;
   hm1_RcIter = hm1.find( hm1_AcIter -> first );
   cout << "The element of hm1 with a key matching "
        << "that of the last element is: "
        << hm1_RcIter -> second << "." << endl;
}
```

```Output
The element of hash_map hm1 with a key of 2 is: 20.
The hash_map hm1 doesn't have an element with a key of 4.
The element of hm1 with a key matching that of the last element is: 30.
```

## <a name="hash_mapget_allocator"></a><a name="get_allocator"></a>hash_map:get_allocator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

hash_map oluşturmak için kullanılan ayırıcı nesnenin bir kopyasını döndürür.

```cpp
Allocator get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

hash_map tarafından kullanılan ayırıcı.

### <a name="remarks"></a>Açıklamalar

hash_map sınıfının ayırıcıları sınıfın depolamayı nasıl yönettiğini belirtir. C++ Standart Kitaplık kapsayıcı sınıfları ile birlikte verilen varsayılan ayırıcılar çoğu programlama gereksinimleri için yeterlidir. Kendi ayırıcı sınıfınızı yazmak ve kullanmak gelişmiş bir C++ konusudur.

### <a name="example"></a>Örnek

```cpp
// hash_map_get_allocator.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int>::allocator_type hm1_Alloc;
   hash_map <int, int>::allocator_type hm2_Alloc;
   hash_map <int, double>::allocator_type hm3_Alloc;
   hash_map <int, int>::allocator_type hm4_Alloc;

   // The following lines declare objects
   // that use the default allocator.
   hash_map <int, int> hm1;
   hash_map <int, int> hm2;
   hash_map <int, double> hm3;

   hm1_Alloc = hm1.get_allocator( );
   hm2_Alloc = hm2.get_allocator( );
   hm3_Alloc = hm3.get_allocator( );

   cout << "The number of integers that can be allocated"
        << endl << "before free memory is exhausted: "
        << hm2.max_size( ) << "." << endl;

   cout << "The number of doubles that can be allocated"
        << endl << "before free memory is exhausted: "
        << hm3.max_size( ) <<  "." << endl;

   // The following line creates a hash_map hm4
   // with the allocator of hash_map hm1.
   hash_map <int, int> hm4( less<int>( ), hm1_Alloc );

   hm4_Alloc = hm4.get_allocator( );

   // Two allocators are interchangeable if
   // storage allocated from each can be
   // deallocated with the other
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

## <a name="hash_maphash_map"></a><a name="hash_map"></a>hash_map:hash_map

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

Boş veya başka bir hash_map tamamının veya bir kısmının kopyası olan bir hash_map kurar.

```cpp
hash_map();

explicit hash_map(
    const Traits& Comp);

hash_map(
    const Traits& Comp,
    const Allocator& Al);

hash_map(
    const hash_map& Right);

hash_map(
    hash_map&& Right);

hash_map(
    initializer_list<Type> IList);hash_map(initializer_list<Type> IList,
    const key_compare& Comp);

hash_map(
    initializer_list<Type> IList,
    const key_compare& Comp,
    const allocator_type& Al);

template <class InputIterator>
hash_map(
    InputIterator First,
    InputIterator Last);

template <class InputIterator>
hash_map(
    InputIterator First,
    InputIterator Last,
    const Traits& Comp);

template <class InputIterator>
hash_map(
    InputIterator First,
    InputIterator Last,
    const Traits& Comp,
    const Allocator& Al
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Al*|Varsayılan olarak `Allocator`bu hash_map nesne için kullanılacak depolama ayırıcı sınıfı.|
|*Comp*|hash_map öğeleri ni sıralamak için kullanılan tür const'un `Traits` `hash_compare`karşılaştırma işlevi varsayılan olarak .|
|*Doğru*|Hash_map hangi yapılandırılan harita bir kopyası olmaktır.|
|*Ilk*|Kopyalanacak öğeler aralığındaki ilk öğenin konumu.|
|*Son*|İlk öğenin kopyalanacak öğe aralığının ötesindeki konumu.|
|*ılist*|initializer_list|

### <a name="remarks"></a>Açıklamalar

Tüm oluşturucular, hash_map için bellek depolamayı yöneten bir allocator nesnesi türünü depolar ve daha sonra [get_allocator](#get_allocator)çağırarak döndürülebilir. Ayırıcı parametresi genellikle sınıf bildirimlerinde ve alternatif ayırıcıların yerine kullanılan ön işleme makrolarında atlanır.

Tüm yapıcılar hash_map.

Tüm oluşturucular, hash_map tuşları `Traits` arasında bir düzen oluşturmak için kullanılan ve daha sonra [key_comp](#key_comp)çağırarak döndürülebilen bir işlev nesnesi depolar.

İlk üç oluşturucu boş bir başlangıç hash_map belirtir, buna ek olarak, ikinci karşılaştırma fonksiyonu nun türünü belirtir *(Comp*) elemanların sırasını oluştururken, üçüncü açıkça kullanılacak ayırıcı türü *(Al)* belirtir. Anahtar kelime **açık** otomatik tür dönüştürme belirli türleri bastırır.

Dördüncü oluşturucu hash_map *Hakkı'nın*bir kopyasını belirtir.

Sonraki üç oluşturucu, sınıf `[First, Last)` `Traits` ve ayırıcının karşılaştırma işlevinin türünü belirtirken giderek daha açık bir şekilde hash_map aralığını kopyalar.

Son yapıcı hash_map *Sağa*hareket ettirir.

## <a name="hash_mapinsert"></a><a name="insert"></a>hash_map::ekle

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

Bir öğeyi veya bir öğe aralığını hash_map ekler.

```cpp
pair <iterator, bool> insert(
    const value_type& val);

iterator insert(
    const_iterator _Where,
    const value_type& val);

template <class InputIterator>
void insert(
    InputIterator first,
    InputIterator last);

template <class ValTy>
pair <iterator, bool>
insert(
    ValTy&& val);

template <class ValTy>
iterator insert(
    const_iterator _Where,
    ValTy&& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Val*|hash_map zaten bu öğeyi (veya daha genel olarak, anahtarı eşdeğer sıralanmış bir öğe) içermediği sürece hash_map eklenecek bir öğenin değeri.|
|*_Where*|Doğru ekleme noktasını aramaya başlamak için yerle ilgili bir ipucu.|
|*Ilk*|Bir hash_map kopyalanacak ilk öğenin konumu.|
|*Son*|Bir hash_map kopyalanacak son öğenin hemen ötesindeki konum.|

### <a name="return-value"></a>Dönüş Değeri

İlk `insert` üye işlev, bir ekleme yapılmışsa bool bileşeni doğru döndüren ve hash_map zaten anahtar siparişte eşdeğer değere sahip bir öğe içeriyorsa ve yineleyici bileşeni yeni bir öğenin eklendiği veya öğenin bulunduğu adresi döndüren bir öğeyi döndürür.

Bu üye işlev tarafından döndürülen `pr` bir çiftin yineleyici `pr`bileşenine erişmek için. **ilk**, ve dereference \*için, kullanmak ( `pr`. **ilk**). Bu üye işlev tarafından döndürülen bir çiftin `pr` **bool** bileşenine erişmek `pr`için. **ikinci**, ve dereference \*için, kullanmak ( `pr`. **ikinci**).

İkinci `insert` üye işlev, ipucu sürümü, yeni öğenin hash_map eklendiği konumu gösteren bir yineleyici döndürür.

Son iki `insert` üye işlev, eklenen değeri hareket ettirdikleri dışında ilk ikisiyle aynı şekilde çalışır.

### <a name="remarks"></a>Açıklamalar

Bir öğenin [value_type](../standard-library/map-class.md#value_type) bir çifttir, böylece bir öğenin değeri ilk bileşen anahtar değerine eşit, ikinci bileşen ise öğenin veri değerine eşit sıralı bir çift olacaktır.

Ekleme noktası hemen *_Where*takip ederse, ekleme noktası logaritmik zaman yerine, eklemek ipucu sürümü için amortismana tabi sabit zaman oluşabilir.

Üçüncü üye işlev, öğe değerlerinin dizisini, belirli bir kümenin *[İlk, Son)* aralığındaki bir yineleyici tarafından adreslenen her öğeye karşılık gelen bir hash_map ekler.

### <a name="example"></a>Örnek

```cpp
// hash_map_insert.cpp
// compile with: /EHsc
#include<hash_map>
#include<iostream>
#include <string>

int main()
{
    using namespace std;
    using namespace stdext;
    hash_map<int, int>::iterator hm1_pIter, hm2_pIter;

    hash_map<int, int> hm1, hm2;
    typedef pair<int, int> Int_Pair;

    hm1.insert(Int_Pair(1, 10));
    hm1.insert(Int_Pair(2, 20));
    hm1.insert(Int_Pair(3, 30));
    hm1.insert(Int_Pair(4, 40));

    cout << "The original elements (Key => Value) of hm1 are:";
    for (hm1_pIter = hm1.begin(); hm1_pIter != hm1.end(); hm1_pIter++)
        cout << endl << " " << hm1_pIter -> first << " => "
             << hm1_pIter->second;
    cout << endl;

    pair< hash_map<int,int>::iterator, bool > pr;
    pr = hm1.insert(Int_Pair(1, 10));

    if (pr.second == true)
    {
        cout << "The element 10 was inserted in hm1 successfully."
            << endl;
    }
    else
    {
        cout << "The element 10 already exists in hm1\n"
            << "with a key value of "
            << "((pr.first) -> first) = " << (pr.first)->first
            << "." << endl;
    }

    // The hint version of insert
    hm1.insert(--hm1.end(), Int_Pair(5, 50));

    cout << "After the insertions, the elements of hm1 are:";
    for (hm1_pIter = hm1.begin(); hm1_pIter != hm1.end(); hm1_pIter++)
        cout << endl << hm1_pIter -> first << " => "
             << hm1_pIter->second;
    cout << endl;

    hm2.insert(Int_Pair(10, 100));

    // The templatized version inserting a range
    hm2.insert( ++hm1.begin(), --hm1.end() );

    cout << "After the insertions, the elements of hm2 are:";
    for (hm2_pIter = hm2.begin(); hm2_pIter != hm2.end(); hm2_pIter++)
        cout << endl << hm2_pIter -> first << " => "
             << hm2_pIter->second;
    cout << endl;

    // The templatized versions move constructing elements
    hash_map<int, string> hm3, hm4;
    pair<int, string> is1(1, "a"), is2(2, "b");

    hm3.insert(move(is1));
    cout << "After the move insertion, hm3 contains:" << endl
      << hm3.begin()->first
      << " => " << hm3.begin()->second
      << endl;

    hm4.insert(hm4.begin(), move(is2));
    cout << "After the move insertion, hm4 contains:" << endl
      << hm4.begin()->first
      << " => " << hm4.begin()->second
      << endl;
}
```

```Output
The original elements (Key => Value) of hm1 are:
1 => 10
2 => 20
3 => 30
4 => 40
The element 10 already exists in hm1
with a key value of ((pr.first) -> first) = 1.
After the insertions, the elements of hm1 are:
1 => 10
2 => 20
3 => 30
4 => 40
5 => 50
After the insertions, the elements of hm2 are:
2 => 20
10 => 100
3 => 30
4 => 40
After the move insertion, hm3 contains:
1 => a
After the move insertion, hm4 contains:
2 => b
```

## <a name="hash_mapiterator"></a><a name="iterator"></a>hash_map::iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

hash_map herhangi bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleme sağlayan bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::iterator iterator;
```

### <a name="remarks"></a>Açıklamalar

hash_map `iterator` tarafından tanımlanan value_type nesneleri olan, [value_type](#value_type)yani tür **çifti\<const Key, Type>,** ilk üyesi öğenin anahtarı dır ve ikinci üyesi öğe tarafından tutulan eşlenen datum olan öğeler.

Çok eşlemedeki bir öğeyi işaret eden bir **yineleyiciyi** `Iter` `->` dereference etmek için işleci kullanın.

Öğe için anahtarın değerine erişmek `Iter`  -> için, **ilk**olarak\* `Iter`( ) değerine eşdeğer olan kullanın. **ilk**. Öğe için eşlenen datum değerine erişmek için, `Iter`  ->  **ikinci**, eşdeğer\* `Iter`( ). **ikinci**.

Bir `iterator` tür, bir öğenin değerini değiştirmek için kullanılabilir.

### <a name="example"></a>Örnek

Nasıl bildirilir ve kullanılacağına bir örnek `iterator`için [bkz.](#begin)

## <a name="hash_mapkey_comp"></a><a name="key_comp"></a>hash_map:key_comp

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

Hash_map anahtarları sipariş etmek için kullanılan karşılaştırma nesnesinin bir kopyasını alır.

```cpp
key_compare key_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

bir hash_map öğelerini sıralamak için kullandığı işlev nesnesini döndürür.

### <a name="remarks"></a>Açıklamalar

Depolanan nesne üye işlevi tanımlar

**bool operator**( **const Key&** `left` **, const Key&** `right`);

önce yse ve sıralama `right` sırasına eşit değilse doğru döndürür. **true** `left`

### <a name="example"></a>Örnek

```cpp
// hash_map_key_comp.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;

   hash_map <int, int, hash_compare<int, less<int> > > hm1;
   hash_map <int, int, hash_compare<int, less<int> > >::key_compare
      kc1 = hm1.key_comp( ) ;

   // Operator stored in kc1 tests order & returns bool value
   bool result1 = kc1( 2, 3 ) ;
   if( result1 == true )
   {
      cout << "kc1( 2,3 ) returns value of true,"
           << "\n where kc1 is the function object of hm1"
           << " of type key_compare." << endl;
   }
   else
   {
      cout << "kc1( 2,3 ) returns value of false"
           << "\n where kc1 is the function object of hm1"
           << " of type key_compare." << endl;
   }

   hash_map <int, int, hash_compare<int, greater<int> > > hm2;
   hash_map <int, int, hash_compare<int, greater<int> > >
      ::key_compare kc2 = hm2.key_comp( );

   // Operator stored in kc2 tests order & returns bool value
   bool result2 = kc2( 2, 3 ) ;
   if( result2 == true )
   {
      cout << "kc2( 2,3 ) returns value of true,"
           << "\n where kc2 is the function object of hm2"
           << " of type key_compare." << endl;
   }
   else
   {
      cout << "kc2( 2,3 ) returns value of false,"
           << "\n where kc2 is the function object of hm2"
           << " of type key_compare." << endl;
   }
}
```

## <a name="hash_mapkey_compare"></a><a name="key_compare"></a>hash_map:key_compare

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

Eşdeki iki öğenin göreli sırasını belirlemek için iki sıralama anahtarını karşılaştırabilen bir işlev nesnesi sağlayan bir tür.

```cpp
typedef Traits key_compare;
```

### <a name="remarks"></a>Açıklamalar

`key_compare`şablon parametresi `Traits`ile eş anlamlıdır.

[hash_map Sınıfı](../standard-library/hash-map-class.md) `Traits` konusu hakkında daha fazla bilgi için bkz.

### <a name="example"></a>Örnek

Nasıl bildirilir ve kullanılır? `key_compare` [key_comp](#key_comp)

## <a name="hash_mapkey_type"></a><a name="key_type"></a>hash_map::key_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

Bir tür, hash_map her öğesini oluşturan sıralama anahtar nesnesini açıklar.

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Açıklamalar

`key_type`şablon parametresi `Key`ile eş anlamlıdır.

Daha fazla `Key`bilgi için [hash_map Sınıfı](../standard-library/hash-map-class.md) konusunun Açıklamalar bölümüne bakın.

### <a name="example"></a>Örnek

Nasıl bildirilir ve kullanılacağına `key_type`bir örnek için [value_type](#value_type) örneğe bakın.

## <a name="hash_maplower_bound"></a><a name="lower_bound"></a>hash_map:lower_bound

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

Bir hash_map ilk öğeye, belirtilen anahtara eşit veya daha büyük bir anahtar değeriyle bir yineleyici döndürür.

```cpp
iterator lower_bound(const Key& key);

const_iterator lower_bound(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*Anahtar*\
Bağımsız değişken anahtar değeri, aranmakta olan hash_map bir öğenin tür anahtarıyla karşılaştırılacak.

### <a name="return-value"></a>Dönüş Değeri

Bir öğenin konumunu, bağımsız değişken anahtarına eşit veya daha büyük bir anahtarla veya anahtar için eşleşme bulunamazsa hash_map'daki son öğeyi başaran konumu gideren bir hash_map öğenin konumunu ele alan bir [yineleyici](#iterator) veya [const_iterator.](#const_iterator)

Bir `const_iterator`, hash_map `lower_bound` nesnesinin geri dönüş değeri ne olursa olsun değiştirilemez. Bir `iterator`, hash_map `lower_bound` nesnesinin geri dönüş değeri ne olursa olsun değiştirilebilir.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_map_lower_bound.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1;
   hash_map <int, int> :: const_iterator hm1_AcIter, hm1_RcIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );
   hm1.insert ( Int_Pair ( 3, 30 ) );

   hm1_RcIter = hm1.lower_bound( 2 );
   cout << "The first element of hash_map hm1 with a key of 2 is: "
        << hm1_RcIter -> second << "." << endl;

   // If no match is found for the key, end( ) is returned
   hm1_RcIter = hm1. lower_bound ( 4 );

   if ( hm1_RcIter == hm1.end( ) )
      cout << "The hash_map hm1 doesn't have an element "
           << "with a key of 4." << endl;
   else
      cout << "The element of hash_map hm1 with a key of 4 is: "
           << hm1_RcIter -> second << "." << endl;

   // An element at a specific location in the hash_map can be
   // found using a dereferenced iterator addressing the location
   hm1_AcIter = hm1.end( );
   hm1_AcIter--;
   hm1_RcIter = hm1. lower_bound ( hm1_AcIter -> first );
   cout << "The element of hm1 with a key matching "
        << "that of the last element is: "
        << hm1_RcIter -> second << "." << endl;
}
```

```Output
The first element of hash_map hm1 with a key of 2 is: 20.
The hash_map hm1 doesn't have an element with a key of 4.
The element of hm1 with a key matching that of the last element is: 30.
```

## <a name="hash_mapmapped_type"></a><a name="mapped_type"></a>hash_map:mapped_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

hash_map depolanan veri türünü temsil eden bir tür.

```cpp
typedef Type mapped_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, `mapped_type` şablon parametresi `Type`ile eş anlamlıdır.

[hash_map Sınıfı](../standard-library/hash-map-class.md) `Type` konusu hakkında daha fazla bilgi için bkz.

### <a name="example"></a>Örnek

Nasıl bildirilir ve kullanılacağına `key_type`bir örnek için [value_type](#value_type) örneğe bakın.

## <a name="hash_mapmax_size"></a><a name="max_size"></a>hash_map:max_size

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

hash_map maksimum uzunluğu verir.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Hash_map mümkün olan maksimum uzunluğu.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_map_max_size.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1;
   hash_map <int, int> :: size_type i;

   i = hm1.max_size( );
   cout << "The maximum possible length "
        << "of the hash_map is " << i << "."
        << endl << "(Magnitude is machine specific.)";
}
```

## <a name="hash_mapoperator"></a><a name="op_at"></a>hash_map::operatör[]

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

Bir öğeyi belirli `hash_map` bir anahtar değeri olan bir öğeye ekler.

```cpp
Type& operator[](const Key& key);

Type& operator[](Key&& key);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*anahtar*|Eklenecek öğenin anahtar değeri.|

### <a name="return-value"></a>Dönüş Değeri

Eklenen öğenin veri değerine başvuru.

### <a name="remarks"></a>Açıklamalar

Bağımsız değişken anahtar değeri bulunamazsa, değer veri türünün varsayılan değeriyle birlikte eklenir.

`operator[]`kullanarak bir `hash_map m` içine öğeleri eklemek için kullanılabilir

`m[ key] = DataValue`;

DataValue anahtar değeri ile `mapped_type` öğenin değeri dir. *key*

Öğeleri `operator[]` eklemek için kullanılırken, döndürülen başvuru eklemenin önceden varolan bir öğeyi değiştirip değiştirmediğini veya yeni bir öğe oluşturup oluşturmadığını göstermez. Üye işlevler [bul](../standard-library/map-class.md#find) ve [ekle,](../standard-library/map-class.md#insert) eklemeden önce belirli bir anahtara sahip bir öğenin zaten mevcut olup olmadığını belirlemek için kullanılabilir.

### <a name="example"></a>Örnek

```cpp
// hash_map_op_ref.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>
#include <string>

int main( )
{
   using namespace std;
   using namespace stdext;
   typedef pair <const int, int> cInt2Int;
   hash_map <int, int> hm1;
   hash_map <int, int> :: iterator pIter;

   // Insert a data value of 10 with a key of 1
   // into a hash_map using the operator[] member function
   hm1[ 1 ] = 10;

   // Compare other ways to insert objects into a hash_map
   hm1.insert ( hash_map <int, int> :: value_type ( 2, 20 ) );
   hm1.insert ( cInt2Int ( 3, 30 ) );

   cout  << "The keys of the mapped elements are:";
   for ( pIter = hm1.begin( ) ; pIter != hm1.end( ) ; pIter++ )
      cout << " " << pIter -> first;
   cout << "." << endl;

   cout  << "The values of the mapped elements are:";
   for ( pIter = hm1.begin( ) ; pIter != hm1.end( ) ; pIter++ )
      cout << " " << pIter -> second;
   cout << "." << endl;

   // If the key already exists, operator[]
   // changes the value of the datum in the element
   hm1[ 2 ] = 40;

   // operator[] will also insert the value of the data
   // type's default constructor if the value is unspecified
   hm1[5];

   cout  << "The keys of the mapped elements are now:";
   for ( pIter = hm1.begin( ) ; pIter != hm1.end( ) ; pIter++ )
      cout << " " << pIter -> first;
   cout << "." << endl;

   cout  << "The values of the mapped elements are now:";
   for ( pIter = hm1.begin( ) ; pIter != hm1.end( ) ; pIter++ )
      cout << " " << pIter -> second;
   cout << "." << endl;

   // operator[] will also insert by moving a key
   hash_map <string, int> hm2;
   string str("a");
   hm2[move(str)] = 1;
   cout << "The moved key is " << hm2.begin()->first
      << ", with value " << hm2.begin()->second << endl;
}
```

## <a name="hash_mapoperator"></a><a name="op_eq"></a>hash_map::operator=

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

hash_map öğelerini başka bir hash_map kopyasıyla değiştirir.

```cpp
hash_map& operator=(const hash_map& right);

hash_map& operator=(hash_map&& right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Doğru*|[hash_map Sınıfı](../standard-library/hash-map-class.md) `hash_map`kopyalanıyor.|

### <a name="remarks"></a>Açıklamalar

Bir'deki varolan öğeleri `hash_map`silersonra , `operator=` *''nin* içeriğini `hash_map`kopyalar veya 'ye taşır.

### <a name="example"></a>Örnek

```cpp
// hash_map_operator_as.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map<int, int> v1, v2, v3;
   hash_map<int, int>::iterator iter;

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

## <a name="hash_mappointer"></a><a name="pointer"></a>hash_map::pointer

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

hash_map bir öğeiçin işaretçi sağlayan bir tür.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir `pointer` tür, bir öğenin değerini değiştirmek için kullanılabilir.

Çoğu durumda, bir hash_map nesnesindeki öğelere erişmek için bir [yineleyici](#iterator) kullanılmalıdır.

## <a name="hash_maprbegin"></a><a name="rbegin"></a>hash_map::rbegin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

Ters hash_map ilk öğeyi ele alan bir yineleyici döndürür.

```cpp
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```

### <a name="return-value"></a>Dönüş Değeri

Ters hash_map ilk öğeyi ele alan veya ters çevrilmemiş hash_map son öğesini ele alan ters çift yönlü bir yineleme.

### <a name="remarks"></a>Açıklamalar

`rbegin`[bir](#begin) hash_map ile kullanıldığı gibi ters hash_map ile kullanılır.

Bir const_reverse_iterator geri `rbegin` dönüş değeri [const_reverse_iterator](#const_reverse_iterator)atanmışsa, hash_map nesnesi değiştirilemez. Bir reverse_iterator geri `rbegin` dönüş değeri [reverse_iterator](#reverse_iterator)atanmışsa, hash_map nesnesi değiştirilebilir.

`rbegin`geriye doğru hash_map ile yinelemek için kullanılabilir.

### <a name="example"></a>Örnek

```cpp
// hash_map_rbegin.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1;

   hash_map <int, int> :: iterator hm1_Iter;
   hash_map <int, int> :: reverse_iterator hm1_rIter;
   hash_map <int, int> :: const_reverse_iterator hm1_crIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );
   hm1.insert ( Int_Pair ( 3, 30 ) );

   hm1_rIter = hm1.rbegin( );
   cout << "The first element of the reversed hash_map hm1 is "
        << hm1_rIter -> first << "." << endl;

   // begin can be used to start an iteration
   // through a hash_map in a forward order
   cout << "The hash_map is: ";
   for ( hm1_Iter = hm1.begin( ) ; hm1_Iter != hm1.end( ); hm1_Iter++)
      cout << hm1_Iter -> first << " ";
      cout << "." << endl;

   // rbegin can be used to start an iteration
   // through a hash_map in a reverse order
   cout << "The reversed hash_map is: ";
   for ( hm1_rIter = hm1.rbegin( ) ; hm1_rIter != hm1.rend( ); hm1_rIter++)
      cout << hm1_rIter -> first << " ";
      cout << "." << endl;

   // A hash_map element can be erased by dereferencing to its key
   hm1_rIter = hm1.rbegin( );
   hm1.erase ( hm1_rIter -> first );

   hm1_rIter = hm1.rbegin( );
   cout << "After the erasure, the first element "
        << "in the reversed hash_map is "
        << hm1_rIter -> first << "." << endl;
}
```

```Output
The first element of the reversed hash_map hm1 is 3.
The hash_map is: 1 2 3 .
The reversed hash_map is: 3 2 1 .
After the erasure, the first element in the reversed hash_map is 2.
```

## <a name="hash_mapreference"></a><a name="reference"></a>hash_map::referans

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

hash_map depolanan bir öğeye başvuru sağlayan bir tür.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::reference reference;
```

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_map_reference.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );

   // Declare and initialize a const_reference &Ref1
   // to the key of the first element
   const int &Ref1 = ( hm1.begin( ) -> first );

   // The following line would cause an error as the
   // non-const_reference cannot be used to access the key
   // int &Ref1 = ( hm1.begin( ) -> first );

   cout << "The key of first element in the hash_map is "
        << Ref1 << "." << endl;

   // Declare and initialize a reference &Ref2
   // to the data value of the first element
   int &Ref2 = ( hm1.begin( ) -> second );

   cout << "The data value of first element in the hash_map is "
        << Ref2 << "." << endl;

   // The non-const_reference can be used to modify the
   // data value of the first element
   Ref2 = Ref2 + 5;
   cout << "The modified data value of first element is "
        << Ref2 << "." << endl;
}
```

```Output
The key of first element in the hash_map is 1.
The data value of first element in the hash_map is 10.
The modified data value of first element is 15.
```

## <a name="hash_maprend"></a><a name="rend"></a>hash_map::rend

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

Ters hash_map son öğeyi yerine getiren konumu adresleyen bir yineleyici döndürür.

```cpp
const_reverse_iterator rend() const;

reverse_iterator rend();
```

### <a name="return-value"></a>Dönüş Değeri

Ters hash_map 'deki son öğeyi (ters çevrilmemiş hash_map ilk öğeden önce gelen konum) yerine gelen konumu gideren ters çift yönlü bir yineleme.

### <a name="remarks"></a>Açıklamalar

`rend`[uç](#end) bir hash_map ile kullanıldığı gibi ters hash_map ile kullanılır.

Bir const_reverse_iterator geri `rend` dönüş değeri [const_reverse_iterator](#const_reverse_iterator)atanmışsa, hash_map nesnesi değiştirilemez. Bir reverse_iterator geri `rend` dönüş değeri [reverse_iterator](#reverse_iterator)atanmışsa, hash_map nesnesi değiştirilebilir.

`rend`ters yineleyicinin hash_map sonuna ulaşıp ulaşmadığını test etmek için kullanılabilir.

Döndürülen `rend` değer dereferenced olmamalıdır.

### <a name="example"></a>Örnek

```cpp
// hash_map_rend.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1;

   hash_map <int, int> :: iterator hm1_Iter;
   hash_map <int, int> :: reverse_iterator hm1_rIter;
   hash_map <int, int> :: const_reverse_iterator hm1_crIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );
   hm1.insert ( Int_Pair ( 3, 30 ) );

   hm1_rIter = hm1.rend( );
   hm1_rIter--;
   cout << "The last element of the reversed hash_map hm1 is "
        << hm1_rIter -> first << "." << endl;

   // begin can be used to start an iteration
   // through a hash_map in a forward order
   cout << "The hash_map is: ";
   for ( hm1_Iter = hm1.begin( ) ; hm1_Iter != hm1.end( );
   hm1_Iter++)
      cout << hm1_Iter -> first << " ";
      cout << "." << endl;

   // rbegin can be used to start an iteration
   // through a hash_map in a reverse order
   cout << "The reversed hash_map is: ";
   for ( hm1_rIter = hm1.rbegin( ) ; hm1_rIter != hm1.rend( );
      hm1_rIter++)
      cout << hm1_rIter -> first << " ";
      cout << "." << endl;

   // A hash_map element can be erased by dereferencing to its key
   hm1_rIter = --hm1.rend( );
   hm1.erase ( hm1_rIter -> first );

   hm1_rIter = hm1.rend( );
   hm1_rIter--;
   cout << "After the erasure, the last element "
        << "in the reversed hash_map is "
        << hm1_rIter -> first << "." << endl;
}
```

```Output
The last element of the reversed hash_map hm1 is 1.
The hash_map is: 1 2 3 .
The reversed hash_map is: 3 2 1 .
After the erasure, the last element in the reversed hash_map is 2.
```

## <a name="hash_mapreverse_iterator"></a><a name="reverse_iterator"></a>hash_map:reverse_iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

Ters hash_map bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleme sağlayan bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::reverse_iterator reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir `reverse_iterator` tür bir öğenin değerini değiştiremez ve hash_map ters olarak yinelemek için kullanılır.

hash_map `reverse_iterator` tarafından tanımlanan value_type nesneleri olan elemanlar [için](#value_type), bu tür **\<çifti const Anahtar, Tip>**, ilk üyesi öğenin anahtarı ve ikinci üyesi eşlenen datum öğe tarafından düzenlenen.

bir hash_map `reverse_iterator` `rIter` bir öğeyi işaret eden bir öğeyi belirtmek için -> işleci kullanın.

Öğe için anahtarın değerine erişmek `rIter`  -> için, **ilk**olarak\* `rIter`( ) değerine eşdeğer olan kullanın. **ilk**. Öğe için eşlenen datum değerine erişmek için, `rIter`  ->  **ikinci**, eşdeğer\* `rIter`( ). **ilk**.

### <a name="example"></a>Örnek

Nasıl bildirilir ve kullanılır. [rbegin](#rbegin) `reverse_iterator`

## <a name="hash_mapsize"></a><a name="size"></a>hash_map::boyut

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

hash_map'daki öğe sayısını verir.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Hash_map geçerli uzunluğu.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

Aşağıdaki örnek, hash_map:boyut üye işlevinin kullanımını göstermektedir.

```cpp
// hash_map_size.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
    using namespace std;
    using namespace stdext;
    hash_map<int, int> hm1, hm2;
    hash_map<int, int>::size_type i;
    typedef pair<int, int> Int_Pair;

    hm1.insert(Int_Pair(1, 1));
    i = hm1.size();
    cout << "The hash_map length is " << i << "." << endl;

    hm1.insert(Int_Pair(2, 4));
    i = hm1.size();
    cout << "The hash_map length is now " << i << "." << endl;
}
```

```Output
The hash_map length is 1.
The hash_map length is now 2.
```

## <a name="hash_mapsize_type"></a><a name="size_type"></a>hash_map:size_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

hash_map'daki öğe sayısını temsil eden imzasız bir tamsayı türü.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::size_type size_type;
```

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

Nasıl beyan edilip kullanılacağına bir örnek için [boyut](#size) örneğine bakın`size_type`

## <a name="hash_mapswap"></a><a name="swap"></a>hash_map::takas

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

İki hash_maps öğelerini değiştirir.

```cpp
void swap(hash_map& right);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Argüman, hedef hash_map değiştirilecek öğelerin sağlanmasını hash_map.

### <a name="remarks"></a>Açıklamalar

Üye işlev, öğeleri değiştirilen iki hash_maps öğeleri belirleyen hiçbir başvuru, işaretçi veya yineleyicigeçersiz olur.

### <a name="example"></a>Örnek

```cpp
// hash_map_swap.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1, hm2, hm3;
   hash_map <int, int>::iterator hm1_Iter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );
   hm1.insert ( Int_Pair ( 3, 30 ) );
   hm2.insert ( Int_Pair ( 10, 100 ) );
   hm2.insert ( Int_Pair ( 20, 200 ) );
   hm3.insert ( Int_Pair ( 30, 300 ) );

   cout << "The original hash_map hm1 is:";
   for ( hm1_Iter = hm1.begin( ); hm1_Iter != hm1.end( ); hm1_Iter++ )
      cout << " " << hm1_Iter -> second;
   cout   << "." << endl;

   // This is the member function version of swap
   // hm2 is said to be the argument hash_map;
   // hm1 is said to be the target hash_map
   hm1.swap( hm2 );

   cout << "After swapping with hm2, hash_map hm1 is:";
   for ( hm1_Iter = hm1.begin( ); hm1_Iter != hm1.end( ); hm1_Iter++ )
      cout << " " << hm1_Iter -> second;
   cout  << "." << endl;

   // This is the specialized template version of swap
   swap( hm1, hm3 );

   cout << "After swapping with hm3, hash_map hm1 is:";
   for ( hm1_Iter = hm1.begin( ); hm1_Iter != hm1.end( ); hm1_Iter++ )
      cout << " " << hm1_Iter -> second;
   cout   << "." << endl;
}
```

```Output
The original hash_map hm1 is: 10 20 30.
After swapping with hm2, hash_map hm1 is: 100 200.
After swapping with hm3, hash_map hm1 is: 300.
```

## <a name="hash_mapupper_bound"></a><a name="upper_bound"></a>hash_map::upper_bound

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

Bir hash_map ilk öğeye bir yineleyici döndürür, bir anahtar belirli bir anahtardan daha büyük bir değere sahip.

```cpp
iterator upper_bound(const Key& key);

const_iterator upper_bound(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*Anahtar*\
Aranın hash_map bir öğenin sıralama anahtar değeriyle karşılaştırılacak bağımsız değişken anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

Bir öğenin konumunu ele alan bir hash_map, bağımsız değişken anahtarından daha büyük bir anahtarla veya anahtar için eşleşme bulunamazsa hash_map'daki son öğeyi başaran konumu gideren bir [const_iterator.](#iterator) [const_iterator](#const_iterator)

İade değeri bir `const_iterator`, hash_map nesnesi değiştirilemez atanır. İade değeri bir `iterator`, hash_map nesnesi değiştirilebilir atanır.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// hash_map_upper_bound.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1;
   hash_map <int, int> :: const_iterator hm1_AcIter, hm1_RcIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );
   hm1.insert ( Int_Pair ( 3, 30 ) );

   hm1_RcIter = hm1.upper_bound( 2 );
   cout << "The first element of hash_map hm1 with a key "
        << "greater than 2 is: "
        << hm1_RcIter -> second << "." << endl;

   // If no match is found for the key, end is returned
   hm1_RcIter = hm1. upper_bound ( 4 );

   if ( hm1_RcIter == hm1.end( ) )
      cout << "The hash_map hm1 doesn't have an element "
           << "with a key greater than 4." << endl;
   else
      cout << "The element of hash_map hm1 with a key > 4 is: "
           << hm1_RcIter -> second << "." << endl;

   // The element at a specific location in the hash_map can be found
   // using a dereferenced iterator addressing the location
   hm1_AcIter = hm1.begin( );
   hm1_RcIter = hm1. upper_bound ( hm1_AcIter -> first );
   cout << "The 1st element of hm1 with a key greater than that\n"
        << "of the initial element of hm1 is: "
        << hm1_RcIter -> second << "." << endl;
}
```

```Output
The first element of hash_map hm1 with a key greater than 2 is: 30.
The hash_map hm1 doesn't have an element with a key greater than 4.
The 1st element of hm1 with a key greater than that
of the initial element of hm1 is: 20.
```

## <a name="hash_mapvalue_comp"></a><a name="value_comp"></a>hash_map:value_comp

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

Anahtar değerlerini karşılaştırarak hash_map öğelerin sırasını belirleyen bir işlev nesnesi döndürür.

```cpp
value_compare value_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir hash_map öğelerini sıralamak için kullandığı karşılaştırma işlevi nesnesini döndürür.

### <a name="remarks"></a>Açıklamalar

Bir hash_map *m*için , eğer iki eleman *e1* (*k1*, *d1*) ve *e2* (*k2*, *d2*) türü [value_type](#value_type)nesneleri, *k1* ve `m.value_comp()(e1, e2)` *k2* tip [key_type](#key_type) ve *d1* ve *d2* [türü](#mapped_type) `m.key_comp()(k1, k2)`mapped_type onların veri vardır . Depolanan nesne üye işlevi tanımlar

`bool operator(value_type& left, value_type& right);`

anahtar **true** değeri `left` önce yse ve sıralama sırasına `right` eşit değilse doğru döndürür.

### <a name="example"></a>Örnek

```cpp
// hash_map_value_comp.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;

   hash_map <int, int, hash_compare<int, less<int> > > hm1;
   hash_map <int, int, hash_compare<int, less<int> > >
   ::value_compare vc1 = hm1.value_comp( );
   pair< hash_map<int,int>::iterator, bool > pr1, pr2;

   pr1= hm1.insert ( hash_map <int, int> :: value_type ( 1, 10 ) );
   pr2= hm1.insert ( hash_map <int, int> :: value_type ( 2, 5 ) );

   if( vc1( *pr1.first, *pr2.first ) == true )
   {
      cout << "The element ( 1,10 ) precedes the element ( 2,5 )."
           << endl;
   }
   else
   {
      cout << "The element ( 1,10 ) does not precede the element ( 2,5 )."
           << endl;
   }

   if( vc1 ( *pr2.first, *pr1.first ) == true )
   {
      cout << "The element ( 2,5 ) precedes the element ( 1,10 )."
           << endl;
   }
   else
   {
      cout << "The element ( 2,5 ) does not precede the element ( 1,10 )."
           << endl;
   }
}
```

## <a name="hash_mapvalue_type"></a><a name="value_type"></a>hash_map:value_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

bir hash_map depolanan nesne türünü temsil eden bir tür.

```cpp
typedef pair<const Key, Type> value_type;
```

### <a name="remarks"></a>Açıklamalar

`value_type`bir bağşlı `pair<key_type, mapped_type>` kapsayıcının anahtarları sabit olmayan bir yineleme veya başvuru kullanılarak değiştirilemeyebileceğinden değil, olduğu bildirilir. `pair<const key_type, mapped_type>`

### <a name="example"></a>Örnek

```cpp
// hash_map_value_type.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   typedef pair <const int, int> cInt2Int;
   hash_map <int, int> hm1;
   hash_map <int, int> :: key_type key1;
   hash_map <int, int> :: mapped_type mapped1;
   hash_map <int, int> :: value_type value1;
   hash_map <int, int> :: iterator pIter;

   // value_type can be used to pass the correct type
   // explicitly to avoid implicit type conversion
   hm1.insert ( hash_map <int, int> :: value_type ( 1, 10 ) );

   // Compare other ways to insert objects into a hash_map
   hm1.insert ( cInt2Int ( 2, 20 ) );
   hm1[ 3 ] = 30;

   // Initializing key1 and mapped1
   key1 = ( hm1.begin( ) -> first );
   mapped1 = ( hm1.begin( ) -> second );

   cout << "The key of first element in the hash_map is "
        << key1 << "." << endl;

   cout << "The data value of first element in the hash_map is "
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
The key of first element in the hash_map is 1.
The data value of first element in the hash_map is 10.
The keys of the mapped elements are: 1 2 3.
The values of the mapped elements are: 10 20 30.
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ Standart Kütüphane Başvurusu](../standard-library/cpp-standard-library-reference.md)
