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
ms.openlocfilehash: 67f891ae7e0b9eab10b1cceda8736661a24641bb
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88560655"
---
# <a name="hash_map-class"></a>hash_map Sınıfı

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

Her öğenin değeri benzersiz olan ve ilişkili bir veri değeri olan bir sıralama anahtarına sahip bir çiftin bulunduğu bir koleksiyondan verileri hızlı bir şekilde depolar ve alır.

## <a name="syntax"></a>Söz dizimi

```cpp
template <class Key,
    class Type,
    class Traits=hash_compare<Key, less<Key>>,
    class Allocator=allocator<pair <const Key, Type>>>
class hash_map
```

### <a name="parameters"></a>Parametreler

*Anahtar*\
Hash_map depolanacak anahtar veri türü.

*Türüyle*\
Hash_map depolanacak öğe veri türü.

*Lerdir*\
İki işlev nesnesi içeren tür, bir sınıftan biri, kendi göreli sıralarını ve öğelerin birli koşul eşleme anahtarı değerleri olan bir karma işlevi, türün işaretsiz tamsayılar olarak belirleyen bir karma işlevi bir sıralama anahtarı olarak karşılaştıramayacak şekilde karşılaştırılmaktadır `size_t` . Bu bağımsız değişken isteğe bağlıdır ve hash_compare<`Key` , daha az<`Key`> > varsayılan değerdir.

*Öğe*\
Hash_map, bellek ayırma ve ayırmayı kaldırma hakkındaki ayrıntıları kapsülleyen saklı ayırıcı nesnesini temsil eden tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer ayırıcı \<pair <const `Key`, `Type`>>.

## <a name="remarks"></a>Açıklamalar

Hash_map:

- İlişkili bir anahtar değerine dayalı öğe değerlerinin verimli alınmasını destekleyen bir değişken boyutu kapsayıcı olan ilişkilendirilebilir bir kapsayıcı.

- Çift yönlüdür, çünkü öğelerine erişmek için çift yönlü bir yineleyici sağlar.

- Karma değeri, öğelerinin anahtar değerlerine uygulanan bir karma işlevin değerine bağlı olarak demet halinde gruplandığından karma hale getirilir.

- Benzersizdir, çünkü öğelerinin her birinde benzersiz bir anahtar olması gerekir.

- Bir çift ilişkilendirilebilir kapsayıcıdır, çünkü veri öğelerinin değerleri kendi anahtar değerlerinden farklıdır.

- Sınıf şablonu, sağladığı işlevsellik geneldir ve bu nedenle öğe veya anahtar olarak içerilen belirli veri türünden bağımsızdır. Öğeler ve anahtarlar için kullanılacak veri türleri, karşılaştırma işlevi ve ayırıcı ile birlikte bir sınıf şablonunda parametreler olarak belirtilir.

Sıralama üzerinden karmalamanın başlıca avantajı daha fazla verimlilik; başarılı bir karma değer ekleme, silme işlemleri gerçekleştirir ve sabit ortalama süre içinde, sıralama teknikleri için kapsayıcıdaki öğelerin sayısının logaritmasına kıyasla bir zaman orantılı olarak bulur. Bir hash_map öğenin değeri, ancak ilişkili anahtar değerini değil doğrudan değiştirilebilir. Bunun yerine, eski öğelerle ilişkili anahtar değerleri silinmeli ve eklenen yeni öğelerle ilişkili yeni anahtar değerleri eklenmelidir.

Kapsayıcı türünün seçimi genelde uygulamanın gerektirdiği arama ve ekleme türüne dayalı olmalıdır. Karma olarak ilişkilendirilebilir kapsayıcılar, arama, ekleme ve kaldırma işlemleri için iyileştirilmiştir. Bu işlemleri açıkça destekleyen üye işlevleri, iyi tasarlanmış bir karma işlevi ile kullanıldığında etkili olur ve bunları ortalama Sabitte olan ve kapsayıcıdaki öğelerin sayısına bağımlı olmayan bir zaman içinde gerçekleştiriyor. İyi tasarlanmış bir karma işlevi, karma değerler için Tekdüzen bir dağıtım üretir ve ayrı anahtar değerleri aynı karma değere eşlendiğinde bir çarpışmanın oluşmasına neden olan çakışmaların sayısını en aza indirir. En kötü durumda, mümkün olan en kötü karma işlevi olan işlem sayısı, dizideki öğelerin sayısıyla orantılıdır (doğrusal saat).

Değerleri, anahtar ile ilişkilendirirken, uygulama tarafından karşılandıkları durumlarda seçeneğin ilişkilendirilebilir kapsayıcısı olmalıdır. hash_map Bu tür bir yapı modeli, ilgili dize değerleri, deyin, tanımlar,,, ve tanımları sağlayan, benzersiz olarak oluşan anahtar sözcüklerin sıralı bir listesidir. Bunun yerine, sözcüklerin birden fazla doğru tanımı vardı, bu nedenle anahtarlar benzersiz değil, bir hash_multimap seçim kapsayıcısı olur. Diğer taraftan, yalnızca sözcüklerin listesi depolanmakta olduğundan, doğru kapsayıcı hash_set. Sözcüklerin birden çok örneğine izin veriliyorsa, hash_multiset uygun kapsayıcı yapısı olur.

Hash_map, [value_compare](../standard-library/value-compare-class.md)sınıfının saklı bir karma *nitelikleri* nesnesini çağırarak denetlediği diziyi sıralar. Bu saklı nesneye [key_comp](#key_comp)üye işlevi çağırarak erişilebilir. Böyle bir işlev nesnesi, [hash_compare](../standard-library/hash-compare-class.md)<anahtarı, daha az> olan bir nesne ile aynı şekilde davranmalıdır \<Key> . Özellikle, *anahtar*türündeki tüm *değerler için* , Call `Traits` (), `Key` türündeki değerlerin bir dağılımını verir `size_t` .

Genelde, bu sıralamayı oluşturmak için öğelerin yalnızca küçüktür biçiminde karşılaştırılabilir olması gerekir; böylece, herhangi iki öğe belirtildiğinde, eşit oldukları (yani birinin diğerinden daha küçük olmadığı anlamında) veya birinin diğerinden küçük olduğu belirlenebilir. Bu, denk olmayan öğeler arasında bir sıralamaya neden olur. Daha teknik bir not üzerinde, karşılaştırma işlevi standart matematiksel anlamda katı bir zayıf sıralama sevk eden ikili bir koşuldur. Bir ikili koşul f (x y), iki bağımsız değişken nesnesine `x` ve `y` veya dönüş değerine sahip bir işlev nesnesidir **`true`** **`false`** . İkili koşul geri dönüşsüz, antisimetrik ve geçişli ve denklik geçişli ise, hash_map uygulanan bir sıralama katı zayıf bir sıradır, burada iki nesne x ve y, her ikisi de f (x, y) ve f (y, x) false olduğunda denk olarak tanımlanır. Anahtarlar arasındaki eşitliğinin daha güçlü koşulu bu denkliğin yerini alırsa, sıralama (içindeki tüm öğelerin birbirine göre sıralanması anlamında) toplam haline gelir ve eşleşen anahtarlar birbirinden ayırt edilemez olacaktır.

Denetlenen dizideki öğelerin gerçek sırası, karma işleve, sıralama işlevine ve kapsayıcı nesnesinde depolanan karma tablonun geçerli boyutuna bağlıdır. Karma tablonun geçerli boyutunu belirleyemez, bu nedenle denetimli dizideki öğelerin sırasını genel olarak tahmin edemezsiniz. Öğelerin eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; öğelerin kaldırılması yalnızca özellikle kaldırılan öğeleri gösteren yineleyicileri geçersiz kılar.

Hash_map Sınıfı tarafından verilen yineleyici çift yönlü bir yineleyicidir, ancak [Insert](#insert) ve [hash_map](#hash_map) sınıf üyesi işlevleri, şablon parametresi olarak daha zayıf bir giriş yineleyicisini alan, işlevsellik gereksinimleri çift yönlü yineleyicilerin sınıfına göre garantiden daha düşük olan sürümlere sahiptir. Farklı yineleyici kavramları, işlevselliklerindeki iyileştirmelere göre ilgili bir aile biçimlendirir. Her yineleyici kavramının kendi gereksinimler kümesi vardır ve bunlarla çalışan algoritmaların kendi varsayımlarını yineleyici türü tarafından sağlanan gereksinimlerle sınırlaması gerekir. Bir giriş yineleyicinin bazı nesnelere başvurusunun kaldırılacağı ve dizideki sonraki yineleyiciye artırılabileceği varsayılabilir. Bu en düşük işlevsellik kümesidir, ancak `[First, Last)` sınıf üye işlevleri bağlamında bir dizi yineleyiciler hakkında anlamlı bir şekilde konuşabilmek yeterlidir.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[hash_map](#hash_map)|`hash_map`Boş olan veya bir kısmının tümünün veya bir kısmının kopyası olan oluşturur `hash_map` .|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[allocator_type](#allocator_type)|Nesnenin sınıfını temsil eden bir tür `allocator` `hash_map` .|
|[const_iterator](#const_iterator)|İçindeki bir öğeyi okuyabilen çift yönlü bir yineleyici sağlayan bir tür **`const`** `hash_map` .|
|[const_pointer](#const_pointer)|İçindeki bir öğeye işaretçi sağlayan bir tür **`const`** `hash_map` .|
|[const_reference](#const_reference)|**`const`** `hash_map` İşlem okumak ve gerçekleştirmek için içinde depolanan bir öğeye başvuru sağlayan bir tür **`const`** .|
|[const_reverse_iterator](#const_reverse_iterator)|İçindeki herhangi bir öğeyi okuyabilen çift yönlü bir yineleyici sağlayan bir tür **`const`** `hash_map` .|
|[difference_type](#difference_type)|Yineleyiciler tarafından gösterilen öğeler arasındaki bir aralıktaki öğelerinin sayısını temsil etmek için kullanılabilen işaretli bir tamsayı türü `hash_map` .|
|[iden](#iterator)|İçindeki herhangi bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleyici sağlayan bir tür `hash_map` .|
|[key_compare](#key_compare)|İçindeki iki öğenin göreli sırasını belirleyebilmek için iki sıralama anahtarını karşılaştırabilen bir işlev nesnesi sağlayan bir tür `hash_map` .|
|[key_type](#key_type)|Bir tür, öğesinin her öğesini oluşturan sıralama anahtarı nesnesini açıklar `hash_map` .|
|[mapped_type](#mapped_type)|İçinde depolanan veri türünü temsil eden bir tür `hash_map` .|
|[pointer](#pointer)|İçindeki bir öğeye işaretçi sağlayan bir tür `hash_map` .|
|[başvurunun](#reference)|İçinde depolanan bir öğeye başvuru sağlayan bir tür `hash_map` .|
|[reverse_iterator](#reverse_iterator)|Ters çevrilen bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleyici sağlayan bir tür `hash_map` .|
|[size_type](#size_type)|İçindeki öğe sayısını temsil eden işaretsiz bir tamsayı türü `hash_map` .|
|[value_type](#value_type)|İçinde göreli sıralarını belirlemede iki öğeyi sıralama anahtarları olarak karşılaştırabilen bir işlev nesnesi sağlayan bir tür `hash_map` .|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[hızı](#at)|İçinde `hash_map` belirtilen anahtar değeri ile bir öğesi bulur.|
|[başladı](#begin)|İçindeki ilk öğeyi adresleyen bir yineleyici döndürür `hash_map` .|
|[cbegin](#cbegin)|İçindeki ilk öğeyi adresleyen bir const yineleyici döndürür `hash_map` .|
|[cend](#cend)|İçindeki son öğeden sonraki konumu ele alan bir const yineleyici döndürür `hash_map` .|
|[lediğiniz](#clear)|Tüm öğelerini siler `hash_map` .|
|[biriktirme](#count)|Bir `hash_map` anahtarı parametre belirtilen anahtarla eşleşen bir öğe sayısını döndürür.|
|[crbegin](#crbegin)|Ters çevrilen ilk öğeyi adresleyen bir const yineleyici döndürür `hash_map` .|
|[crend](#crend)|Ters çevrilen son öğeden sonraki konumu ele alan bir const yineleyici döndürür `hash_map` .|
|[Emplace](#emplace)|İçinde oluşturulan bir öğesi ekler `hash_map` .|
|[emplace_hint](#emplace_hint)|Bir yerleştirme ipucuyla birlikte, içine oluşturulmuş bir öğe ekler `hash_map` .|
|[empty](#empty)|`hash_map`Boşsa, sınar.|
|[erer](#end)|İçindeki son öğeden sonra gelen konumu ele alan bir yineleyici döndürür `hash_map` .|
|[equal_range](#equal_range)|`hash_map`Belirtilen anahtardan daha büyük bir anahtarla ve bir anahtarla `hash_map` eşit veya ondan daha büyük olan bir anahtarla, içindeki ilk öğeye, sırasıyla bir çift yineleyiciler döndürür.|
|[silme](#erase)|Belirtilen konumlardan bir öğeyi veya öğe aralığını kaldırır `hash_map`|
|[find](#find)|İçindeki bir öğenin `hash_map` belirtilen anahtara denk eşdeğeri olan konumunu ele alan bir yineleyici döndürür.|
|[get_allocator](#get_allocator)|`allocator`Oluşturmak için kullanılan nesnenin bir kopyasını döndürür `hash_map` .|
|[ekleyin](#insert)|İçine bir öğe veya öğe aralığı ekler `hash_map` .|
|[key_comp](#key_comp)|Bir yineleyiciyi `hash_map` , belirtilen anahtardan daha büyük veya ona eşit olan bir anahtar değeri ile birlikte ilk öğesine döndürür.|
|[lower_bound](#lower_bound)|Bir yineleyiciyi `hash_map` , belirtilen anahtardan daha büyük veya ona eşit olan bir anahtar değeri ile birlikte ilk öğesine döndürür.|
|[max_size](#max_size)|Maksimum uzunluğunu döndürür `hash_map` .|
|[rbegin](#rbegin)|Ters çevrilen ilk öğeyi adresleyen bir yineleyici döndürür `hash_map` .|
|[rend](#rend)|Ters çevrilen son öğeden sonraki konumu ele alan bir yineleyici döndürür `hash_map` .|
|[boyutla](#size)|İçindeki öğelerin sayısını döndürür `hash_map` .|
|[Kur](#swap)|İki öğenin öğelerini değiş tokuş eder `hash_map` .|
|[upper_bound](#upper_bound)|Bir yineleyiciyi `hash_map` belirtilen anahtardan daha büyük bir anahtar değeri olan ilk öğesine döndürür.|
|[value_comp](#value_comp)|İçindeki öğe değerlerini sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır `hash_map` .|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç&#91;&#93;](#op_at)|`hash_map`Belirtilen anahtar değeri ile öğesine bir öğesi ekler.|
|[hash_map:: operator =](#op_eq)|Öğesinin öğelerini `hash_map` başka bir kopyasıyla değiştirir `hash_map` .|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<hash_map>

**Ad alanı:** stdext

## <a name="hash_mapallocator_type"></a><a name="allocator_type"></a> hash_map:: allocator_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

Hash_map nesnesinin ayırıcı sınıfını temsil eden bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::allocator_type allocator_type;
```

### <a name="example"></a>Örnek

Bir örnek için bkz. [get_allocator](#get_allocator) örneği `allocator_type` .

## <a name="hash_mapat"></a><a name="at"></a> hash_map:: at

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

Hash_map, belirtilen anahtar değeri olan bir öğe bulur.

```cpp
Type& at(const Key& key);

const Type& at(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*anahtar*\
Bulunan öğenin anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

Bulunan öğenin veri değerine başvuru.

### <a name="remarks"></a>Açıklamalar

Bağımsız değişken anahtar değeri bulunamazsa, işlev sınıf [Out_of_range sınıfından](../standard-library/out-of-range-class.md)bir nesne oluşturur.

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

## <a name="hash_mapbegin"></a><a name="begin"></a> hash_map:: Begin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

Hash_map ilk öğeyi adresleyen bir yineleyici döndürür.

```cpp
const_iterator begin() const;

iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

Hash_map ilk öğeyi adresleyen çift yönlü yineleyici veya konum boş bir hash_map başarılı oluyor.

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

## <a name="hash_mapcbegin"></a><a name="cbegin"></a> hash_map:: cbegin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

Hash_map ilk öğeyi adresleyen bir const yineleyici döndürür.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

[Hash_map](../standard-library/hash-map-class.md) ilk öğeyi adresleyen bir const çift yönlü yineleyici veya bir boş olan konum `hash_map` .

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

## <a name="hash_mapcend"></a><a name="cend"></a> hash_map:: cend

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

Hash_map son öğeden sonraki konumu ele alan bir const yineleyici döndürür.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir [hash_map](../standard-library/hash-map-class.md)son öğeden sonraki konumu ele alan bir const çift yönlü Yineleyici. `hash_map`Boşsa, `hash_map::cend == hash_map::begin` .

### <a name="remarks"></a>Açıklamalar

`cend` , bir yineleyicinin sonuna kadar ulaşılmadığını test etmek için kullanılır `hash_map` .

Tarafından döndürülen değer `cend` başvurulmamalıdır.

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

## <a name="hash_mapclear"></a><a name="clear"></a> hash_map:: Clear

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

Hash_map tüm öğelerini siler.

```cpp
void clear();
```

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

Aşağıdaki örnek hash_map:: Clear üye işlevinin kullanımını gösterir.

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

## <a name="hash_mapconst_iterator"></a><a name="const_iterator"></a> hash_map:: const_iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

Hash_map bir öğeyi okuyabilen çift yönlü bir yineleyici sağlayan bir tür **`const`** .

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_iterator const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_iterator` , bir öğenin değerini değiştirmek için kullanılamaz.

`const_iterator`Tarafından tanımlanan hash_map, [value_type](#value_type) `pair< const Key, Type >` ilk üyesi öğe için anahtar olan ve ikinci üye öğesi tarafından tutulan eşlenmiş veri olan value_type nesneleri olan öğeleri gösterir.

Bir hash_map bir `const_iterator` `cIter` öğeyi işaret etmek için `->` işlecini kullanın.

Öğesinin anahtar değerine erişmek için, `cIter->first` ile eşdeğer olan öğesini kullanın `(*cIter).first` . Öğesi için eşlenen veri değerine erişmek için, `cIter->second` ile eşdeğer olan öğesini kullanın `(*cIter).second` .

### <a name="example"></a>Örnek

Bir [örnek için bkz](#begin) . using örneği `const_iterator` .

## <a name="hash_mapconst_pointer"></a><a name="const_pointer"></a> hash_map:: const_pointer

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

Hash_map bir öğeye işaretçi sağlayan bir tür **`const`** .

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::const_pointer const_pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_pointer` , bir öğenin değerini değiştirmek için kullanılamaz.

Çoğu durumda, bir [yineleyici](#iterator) hash_map nesnesindeki öğelere erişmek için kullanılmalıdır.

## <a name="hash_mapconst_reference"></a><a name="const_reference"></a> hash_map:: const_reference

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

**`const`** İşlemleri okumak ve gerçekleştirmek için bir hash_map depolanan öğeye başvuru sağlayan bir tür **`const`** .

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

## <a name="hash_mapconst_reverse_iterator"></a><a name="const_reverse_iterator"></a> hash_map:: const_reverse_iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

Hash_map herhangi bir öğeyi okuyabilen çift yönlü bir yineleyici sağlayan bir tür **`const`** .

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_reverse)iterator const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür, `const_reverse_iterator` bir öğenin değerini değiştiremez ve hash_map ters bir şekilde yinelemek için kullanılır.

`const_reverse_iterator`Tarafından tanımlanan hash_map, [value_type](#value_type) `pair` \< **const Key, Type**> ilk üyesi öğe için anahtar olan ve ikinci üye öğesi tarafından tutulan eşlenmiş veri olan value_type nesneleri olan öğeleri gösterir.

Bir hash_map bir `const_reverse_iterator` `crIter` öğeyi işaret etmek için **->** işlecini kullanın.

Öğesi için anahtar değerine erişmek üzere, `crIter`  ->  **ilk**olarak ( \* `crIter` ) **. önce**kullanın. Öğesi için eşlenen veri değerine erişmek için, `crIter`  ->  () eşdeğeri olan **ikincisini**kullanın \* `crIter` . **ilk**olarak.

### <a name="example"></a>Örnek

' In nasıl bildirilemeyeceğini ve kullanılacağına ilişkin bir örnek için bkz. [rend](#rend) için örneğe bakın `const_reverse_iterator` .

## <a name="hash_mapcount"></a><a name="count"></a> hash_map:: Count

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

Anahtarı parametre tarafından belirtilen anahtarla eşleşen bir hash_map öğe sayısını döndürür.

```cpp
size_type count(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*anahtar*\
Hash_map eşleştirilecek öğelerin anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

hash_map sıralama anahtarı parametre anahtarıyla eşleşen bir öğe içeriyorsa, 1. hash_map eşleşen bir anahtara sahip bir öğe içermiyorsa 0.

### <a name="remarks"></a>Açıklamalar

Üye işlevi aralıktaki *x* öğelerinin sayısını döndürür

\[ lower_bound (*anahtar*), upper_bound (*anahtar*))

benzersiz bir ilişkilendirilebilir kapsayıcı olan hash_map durumunda 0 veya 1 ' dir.

### <a name="example"></a>Örnek

Aşağıdaki örnek hash_map:: Count üye işlevinin kullanımını gösterir.

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

## <a name="hash_mapcrbegin"></a><a name="crbegin"></a> hash_map:: crbegin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

Ters çevrilen hash_map ilk öğeyi adresleyen bir const yineleyici döndürür.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir [hash_map](../standard-library/hash-map-class.md) ilk öğeyi ele almak veya geri çevrilmede son öğenin ne olduğunu ele almak için bir const ters çift yönlü Yineleyici `hash_map` .

### <a name="remarks"></a>Açıklamalar

`crbegin` , [BEGIN](#begin) ile birlikte kullanılan bir ters hash_map ile kullanılır `hash_map` .

Dönüş değeri ile `crbegin` `hash_map` nesne değiştirilemez.

`crbegin` , geriye doğru yinelemek için kullanılabilir `hash_map` .

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

## <a name="hash_mapcrend"></a><a name="crend"></a> hash_map:: crend

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

Ters çevrilen hash_map son öğeden sonraki konumu ele alan bir const yineleyici döndürür.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir [hash_map](../standard-library/hash-map-class.md) (geri çevrilme içindeki ilk öğeden önce gelen konum) izleyen konumu ele alan bir sabit ters çift yönlü Yineleyici `hash_map` .

### <a name="remarks"></a>Açıklamalar

`crend` , bir ters ile birlikte kullanıldığında `hash_map` [hash_map:: End](#end) ile birlikte kullanılır `hash_map` .

Dönüş değeri ile `crend` `hash_map` nesne değiştirilemez.

`crend` , geriye doğru bir yineleyicinin sonuna ulaşılıp ulaşılmadığını test etmek için kullanılabilir `hash_map` .

Tarafından döndürülen değer `crend` başvurulmamalıdır.

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

## <a name="hash_mapdifference_type"></a><a name="difference_type"></a> hash_map::d ifference_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

Yineleyiciler tarafından gösterilen öğeler arasındaki bir aralıktaki hash_map öğelerinin sayısını temsil etmek için kullanılabilen işaretli bir tamsayı türü.

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

## <a name="hash_mapemplace"></a><a name="emplace"></a> hash_map:: emplace

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

Bir hash_map içinde oluşturulmuş bir öğe ekler.

```cpp
template <class ValTy>
pair <iterator, bool>
emplace(
    ValTy&& val);
```

### <a name="parameters"></a>Parametreler

*Acil*\
[hash_map](../standard-library/hash-map-class.md) `hash_map` Zaten bu öğeyi (ya da daha genel olarak, anahtarı equivalently sıralı bir öğe) içermiyorsa, bir öğeyi hash_map içine eklenecek şekilde taşımak için kullanılan değer.

### <a name="return-value"></a>Dönüş Değeri

`emplace`Üye işlevi, bir ekleme yapılırsa bool bileşeni true değeri döndüren bir çift döndürür ve `hash_map` zaten anahtarı sıralamada denk bir değere sahip olan bir öğe içeriyorsa ve yineleyici bileşeni, yeni bir öğenin eklendiği veya öğenin zaten bulunduğu yere bir adresi döndürürse.

Bu üye işlevi tarafından döndürülen bir çiftin Yineleyici bileşenine erişmek için, `pr` kullanın ve öğesini kullanın `pr.first` `*(pr.first)` . **`bool`** `pr` Bu üye işlevi tarafından döndürülen bir çiftin bileşenine erişmek için, kullanın ve öğesini kullanın `pr.second` `*(pr.second)` .

### <a name="remarks"></a>Açıklamalar

Bir öğenin [hash_map:: value_type](#value_type) bir çifttir, böylece bir öğe değeri, ilk bileşeni anahtar değerine eşit olan ve ikinci bileşen öğenin veri değerine eşit olan bir sıralı çift olacaktır.

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

## <a name="hash_mapemplace_hint"></a><a name="emplace_hint"></a> hash_map:: emplace_hint

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

Yerleştirme ipucuyla birlikte hash_map oluşturulan bir öğe ekler.

```cpp
template <class ValTy>
iterator emplace_hint(
    const_iterator _Where,
    ValTy&& val);
```

### <a name="parameters"></a>Parametreler

*Acil*\
[hash_map](../standard-library/hash-map-class.md) `hash_map` Zaten bu öğeyi (ya da daha genel olarak, anahtarı equivalently sıralı bir öğe) içermiyorsa, bir öğeyi hash_map içine eklenecek şekilde taşımak için kullanılan değer.

*_Where*\
Doğru ekleme noktasını aramaya başlamak için yer hakkında bir ipucu.

### <a name="return-value"></a>Dönüş Değeri

[Hash_multimap:: emplace](../standard-library/hash-multimap-class.md#emplace) üye işlevi, yeni öğenin içine eklendiği konuma `hash_map` veya eşdeğer sıralamaya sahip olan öğenin bulunduğu konuma işaret eden bir yineleyici döndürür.

### <a name="remarks"></a>Açıklamalar

Bir öğenin [hash_map:: value_type](#value_type) bir çifttir, böylece bir öğe değeri, ilk bileşeni anahtar değerine eşit olan ve ikinci bileşen öğenin veri değerine eşit olan bir sıralı çift olacaktır.

Ekleme noktası *_Where*hemen ardından, ekleme noktası, logaritmik bir süre yerine, sabit zamanlı olarak meydana gelebilir.

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

## <a name="hash_mapempty"></a><a name="empty"></a> hash_map:: boş

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

Hash_map boş ise sınar.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** hash_map boşsa; **`false`** hash_map boş değilse.

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

## <a name="hash_mapend"></a><a name="end"></a> hash_map:: End

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

Hash_map son öğeden sonraki konumu ele alan bir yineleyici döndürür.

```cpp
const_iterator end() const;

iterator end();
```

### <a name="return-value"></a>Dönüş Değeri

Bir hash_map son öğeden sonraki konumu ele alan çift yönlü bir yineleyici. Hash_map boşsa, hash_map:: End = = hash_map:: BEGIN.

### <a name="remarks"></a>Açıklamalar

`end` , bir yineleyicinin hash_map sonuna kadar ulaşılıp ulaşmadığını test etmek için kullanılır.

Tarafından döndürülen değer `end` başvurulmamalıdır.

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

## <a name="hash_mapequal_range"></a><a name="equal_range"></a> hash_map:: equal_range

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

Belirtilen anahtardan daha büyük bir anahtarla ve anahtardan daha büyük veya ona eşit olan bir anahtarla hash_map ilk öğe olan bir hash_map yineleyicilerin bir çiftini döndürür.

```cpp
pair <const_iterator, const_iterator> equal_range (const Key& key) const;

pair <iterator, iterator> equal_range (const Key& key);
```

### <a name="parameters"></a>Parametreler

*anahtar*\
Aranan hash_map öğenin sıralama anahtarıyla Karşılaştırılacak bağımsız değişken anahtarı değeri.

### <a name="return-value"></a>Dönüş Değeri

Birincisi anahtarın [lower_bound](#lower_bound) , ikincisi ise anahtarın [upper_bound](#upper_bound) olan yinelemelerin bir çiftinden biridir.

Üye işlevi tarafından döndürülen bir çiftin ilk Yineleyici öğesine erişmek için `pr` kullanın `pr` . **ilk** olarak, alt sınır Yineleyici için başvuru yapmak üzere \* ( `pr` . **ilk**). Üye işlevi tarafından döndürülen bir çiftin ikinci Yineleyici öğesine erişmek için `pr` kullanın `pr` . **ikincisi** ve üst sınır yineleyicisini başvuru yapmak için \* ( `pr` . **ikinci**).

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

## <a name="hash_maperase"></a><a name="erase"></a> hash_map:: Erase

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

Belirtilen konumlardan bir hash_map öğeyi veya öğe aralığını kaldırır veya belirtilen bir anahtarla eşleşen öğeleri kaldırır.

```cpp
iterator erase(iterator _Where);

iterator erase(iterator first, iterator last);

size_type erase(const key_type& key);
```

### <a name="parameters"></a>Parametreler

*_Where*\
Hash_map kaldırılacak öğenin konumu.

*adı*\
Hash_map kaldırılan ilk öğenin konumu.

*soyadına*\
Hash_map kaldırılan son öğenin hemen ötesinde konumlandır.

*anahtar*\
Hash_map kaldırılacak öğelerin anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

İlk iki üye işlevi için, kaldırılan öğelerin dışında kalan ilk öğeyi veya böyle bir öğe yoksa hash_map sonuna işaretçiyi atayan çift yönlü bir yineleyici.

Üçüncü üye işlevi için, hash_map kaldırılan öğelerin sayısını döndürür.

### <a name="remarks"></a>Açıklamalar

Üye işlevleri hiçbir şekilde özel durum oluşturmaz.

### <a name="example"></a>Örnek

Aşağıdaki örnek hash_map:: Erase üye işlevinin kullanımını gösterir.

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

## <a name="hash_mapfind"></a><a name="find"></a> hash_map:: Find

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

Belirtilen anahtara eşdeğer bir anahtara sahip bir hash_map öğenin konumunu ele alan bir yineleyici döndürür.

```cpp
iterator find(const Key& key);

const_iterator find(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*anahtar*\
Aranmakta olan hash_map öğenin sıralama anahtarıyla eşleştirilecek anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen bir anahtarla bir öğenin konumunu ele alan veya anahtar için eşleşme bulunmazsa hash_map son öğeden geçen konumda bulunan bir yineleyici.

### <a name="remarks"></a>Açıklamalar

`find` sıralama anahtarı, karşılaştırıdan daha az bir ilişkiye göre sıralama yapan bir ikili koşulda bağımsız değişken anahtarına denk gelen hash_map bir öğeyi ele alan bir yineleyici döndürür.

Dönüş değeri `find` bir [const_iterator](#const_iterator)atanmışsa, hash_map nesnesi değiştirilemez. Dönüş değeri `find` bir [Yineleyici](#iterator)öğesine atanırsa, hash_map nesnesi değiştirilebilir

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

## <a name="hash_mapget_allocator"></a><a name="get_allocator"></a> hash_map:: get_allocator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

Hash_map oluşturmak için kullanılan ayırıcı nesnesinin bir kopyasını döndürür.

```cpp
Allocator get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Hash_map tarafından kullanılan ayırıcı.

### <a name="remarks"></a>Açıklamalar

Hash_map Sınıfı için ayrıcılar, sınıfın depolamayı nasıl yönettiğini belirtir. C++ standart kitaplığı kapsayıcı sınıflarıyla birlikte sağlanan varsayılan ayrıcılar çoğu programlama ihtiyacı için yeterlidir. Kendi ayırıcı sınıfınızı yazmak ve kullanmak, gelişmiş bir C++ konudur.

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

## <a name="hash_maphash_map"></a><a name="hash_map"></a> hash_map:: hash_map

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

Boş bir hash_map oluşturur veya diğer bir hash_map tümünün veya bir kısmının kopyasıdır.

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

*Eşkenar*\
Varsayılan olan bu hash_map nesnesi için kullanılacak depolama ayırıcı sınıfı `Allocator` .

*İnin*\
`Traits`Varsayılan olarak, hash_map öğeleri sıralamak için kullanılan const türünde karşılaştırma işlevi `hash_compare` .

*Right*\
Oluşturulan haritanın bir kopya olduğu hash_map.

*Adı*\
Kopyalanacak öğe aralığındaki ilk öğenin konumu.

*Soyadına*\
Kopyalanacak öğe aralığının ötesinde ilk öğenin konumu.

*IList*\
İnitializer_list

### <a name="remarks"></a>Açıklamalar

Tüm oluşturucular, hash_map bellek depolamayı yöneten bir tür ayırıcı nesnesi depolar ve daha sonra [get_allocator](#get_allocator)çağırarak döndürülür. Ayırıcı parametresi, genellikle sınıf bildirimlerinde atlanır ve alternatif ayırıcıları değiştirmek için kullanılan ön işleme makrolarıyla sonuçlanır.

Tüm oluşturucular hash_map başlatır.

Tüm oluşturucular, `Traits` hash_map anahtarları arasında bir sıra oluşturmak için kullanılan ve daha sonra [key_comp](#key_comp)çağırarak geri döndürülebilecek bir işlev nesnesini depolar.

İlk üç Oluşturucu boş bir ilk hash_map belirtiyor, ek olarak ikinci olarak, öğelerin sırasını oluşturmak için kullanılacak karşılaştırma işlevi (*comp*) türünü ve üçüncü olarak açıkça kullanılacak ayırıcı türünü (*Al*) belirtir. Anahtar sözcüğü **`explicit`** bazı otomatik tür dönüştürme türlerini bastırır.

Dördüncü Oluşturucu hash_map *sağ*bir kopyasını belirtir.

Sonraki üç Oluşturucu, `[First, Last)` bir hash_map aralığını, sınıfın ve ayırıcının karşılaştırma işlevinin türünü belirtirken açıkça artarak kopyalar `Traits` .

Son Oluşturucu hash_map *sağa*taşımaktır.

## <a name="hash_mapinsert"></a><a name="insert"></a> hash_map:: INSERT

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

Bir hash_map öğe veya öğe aralığı ekler.

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

*Acil*\
Hash_map zaten bu öğeyi (veya daha genel olarak, anahtarı equivalently sıralı bir öğe) içermiyorsa, hash_map eklenecek öğenin değeri.

*_Where*\
Doğru ekleme noktasını aramaya başlamak için yer hakkında bir ipucu.

*adı*\
Hash_map kopyalanacak ilk öğenin konumu.

*soyadına*\
Hash_map kopyalanacak son öğenin hemen ötesinde konum.

### <a name="return-value"></a>Dönüş Değeri

İlk `insert` üye işlevi, bir ekleme yapılırsa bool bileşeni true döndüren bir çift döndürür ve hash_map zaten anahtarı sıralamada denk bir değere sahip olan bir öğe içeriyorsa ve yineleyici bileşeni, yeni bir öğenin eklendiği veya öğenin zaten bulunduğu adresi döndüren bir öğe içeriyorsa.

Bu üye işlevi tarafından döndürülen bir çiftin Yineleyici bileşenine erişmek için `pr` kullanın `pr` . **ilk**olarak, başvuru için \* ( `pr` . **ilk**). **`bool`** `pr` Bu üye işlevi tarafından döndürülen bir çiftin bileşenine erişmek için kullanın `pr` . **ikincisi**ve başvuru yapmak için \* ( `pr` . **ikinci**).

İkinci `insert` üye işlevi olan ipucu sürümü, yeni öğenin hash_map eklendiği konuma işaret eden bir yineleyici döndürür.

Son iki `insert` üye işlevi ilk ikisi ile aynı şekilde davranır, ancak eklenen değeri oluşturur.

### <a name="remarks"></a>Açıklamalar

Bir öğe [value_type](../standard-library/map-class.md#value_type) bir çifdir, böylece bir öğe değeri, ilk bileşeni anahtar değerine eşit olan ve ikinci bileşen öğenin veri değerine eşit olan bir sıralı çift olacaktır.

Ekleme noktasının hemen ardından *_Where*, ekleme noktası yerine ekleme işleminin ipucu sürümü için sabit zamanlı olarak ekleme yapılabilir.

Üçüncü üye işlevi, belirtilen bir küme içindeki *[First, Last)* aralığında bir yineleyici tarafından bahsedilen her öğeye karşılık gelen bir hash_map öğe değerleri dizisini ekler.

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

## <a name="hash_mapiterator"></a><a name="iterator"></a> hash_map:: Yineleyici

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

Bir hash_map herhangi bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleyici sağlayan bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::iterator iterator;
```

### <a name="remarks"></a>Açıklamalar

`iterator`Tarafından tanımlanan hash_map, [value_type](#value_type) `pair<const Key, Type>` ilk üyesi öğe için anahtar olan ve ikinci üye öğesi tarafından tutulan eşlenmiş veri olan value_type nesneleri olan öğeleri gösterir.

`Iter`Birden çok haritadaki bir öğeye işaret eden bir yineleyici başvurusu için `->` işlecini kullanın.

Öğesinin anahtar değerine erişmek için, `Iter->first` ile eşdeğer olan öğesini kullanın `(*Iter).first` . Öğesi için eşlenen veri değerine erişmek için, `Iter->second` ile eşdeğer olan öğesini kullanın `(*Iter).second` .

Bir türü `iterator` , bir öğenin değerini değiştirmek için kullanılabilir.

### <a name="example"></a>Örnek

' In nasıl bildirilemeyeceğini ve [kullanılacağına ilişkin bir örnek için bkz](#begin) `iterator` ..

## <a name="hash_mapkey_comp"></a><a name="key_comp"></a> hash_map:: key_comp

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

Hash_map anahtarları sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır.

```cpp
key_compare key_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Hash_map öğelerini sıralamak için kullandığı işlev nesnesini döndürür.

### <a name="remarks"></a>Açıklamalar

Saklı nesne, üye işlevini tanımlar

`bool operator( const Key& left, const Key&right );`

Bu, **`true`** `left` önce olursa ve sıralama düzeninde eşit değilse döndürür `right` .

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

## <a name="hash_mapkey_compare"></a><a name="key_compare"></a> hash_map:: key_compare

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

Haritadaki iki öğenin göreli sırasını belirleyebilmek için iki sıralama anahtarını karşılaştırabilen bir işlev nesnesi sağlayan bir tür.

```cpp
typedef Traits key_compare;
```

### <a name="remarks"></a>Açıklamalar

`key_compare` , şablon parametresinin eşanlamlısıdır `Traits` .

Hakkında daha fazla bilgi için `Traits` [hash_map Sınıfı](../standard-library/hash-map-class.md) konusuna bakın.

### <a name="example"></a>Örnek

Bildirme ve kullanma hakkında bir örnek için bkz. [key_comp](#key_comp) örneği `key_compare` .

## <a name="hash_mapkey_type"></a><a name="key_type"></a> hash_map:: key_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

Bir tür, hash_map her bir öğesini oluşturan sıralama anahtarı nesnesini açıklar.

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Açıklamalar

`key_type` , şablon parametresinin eşanlamlısıdır `Key` .

Hakkında daha fazla bilgi için `Key` [hash_map Sınıfı](../standard-library/hash-map-class.md) konusunun açıklamalar bölümüne bakın.

### <a name="example"></a>Örnek

Bildirme ve kullanma hakkında bir örnek için bkz. [value_type](#value_type) örneği `key_type` .

## <a name="hash_maplower_bound"></a><a name="lower_bound"></a> hash_map:: lower_bound

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

Bir yineleyiciyi belirtilen anahtardan daha büyük veya ona eşit bir anahtar değeri olan bir hash_map ilk öğeye döndürür.

```cpp
iterator lower_bound(const Key& key);

const_iterator lower_bound(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*anahtar*\
Aranan hash_map öğenin sıralama anahtarıyla Karşılaştırılacak bağımsız değişken anahtarı değeri.

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişken anahtarına eşit veya ondan daha büyük bir anahtara sahip bir hash_map içindeki bir öğenin konumunu adresleyen veya anahtar için eşleşme bulunmazsa hash_map son öğeden sonraki konumu ele alan bir [Yineleyici](#iterator) veya [const_iterator](#const_iterator) .

Dönüş değeri `lower_bound` bir öğesine atanırsa `const_iterator` , hash_map nesnesi değiştirilemez. Dönüş değeri `lower_bound` bir öğesine atanırsa `iterator` , hash_map nesnesi değiştirilebilir.

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

## <a name="hash_mapmapped_type"></a><a name="mapped_type"></a> hash_map:: mapped_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

Hash_map depolanan veri türünü temsil eden bir tür.

```cpp
typedef Type mapped_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, `mapped_type` şablon parametresi için bir eş anlamlı `Type` .

Hakkında daha fazla bilgi için `Type` [hash_map Sınıfı](../standard-library/hash-map-class.md) konusuna bakın.

### <a name="example"></a>Örnek

Bildirme ve kullanma hakkında bir örnek için bkz. [value_type](#value_type) örneği `key_type` .

## <a name="hash_mapmax_size"></a><a name="max_size"></a> hash_map:: max_size

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

Hash_map maksimum uzunluğunu döndürür.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Hash_map olabilecek en uzun uzunluk.

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

## <a name="hash_mapoperator"></a><a name="op_at"></a> hash_map:: operator []

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

`hash_map`Belirtilen anahtar değeri ile öğesine bir öğesi ekler.

```cpp
Type& operator[](const Key& key);

Type& operator[](Key&& key);
```

### <a name="parameters"></a>Parametreler

*anahtar*\
Eklenecek öğenin anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

Eklenen öğenin veri değerine başvuru.

### <a name="remarks"></a>Açıklamalar

Bağımsız değişken anahtar değeri bulunamazsa, değer veri türünün varsayılan değeriyle birlikte eklenir.

`operator[]`, bir using öğesine öğe eklemek için kullanılabilir `hash_map m`

`m[ key] = DataValue`;

Burada DataValue, anahtar `mapped_type` değeri olan öğesinin değerinin değeridir. *key*

`operator[]`Öğeleri eklemek için kullanırken, döndürülen başvuru, bir ekleme işlemi önceden varolan bir öğeyi değiştirip değiştirmediğini veya yeni bir tane oluşturmayı göstermez. [Bul](../standard-library/map-class.md#find) ve [Ekle](../standard-library/map-class.md#insert) üye işlevleri, bir ekleme işleminden önce belirtilen anahtara sahip bir öğenin zaten mevcut olup olmadığını anlamak için kullanılabilir.

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

## <a name="hash_mapoperator"></a><a name="op_eq"></a> hash_map:: operator =

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

Hash_map öğelerini başka bir hash_map kopyasıyla değiştirir.

```cpp
hash_map& operator=(const hash_map& right);

hash_map& operator=(hash_map&& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
İçine kopyalandığı [hash_map Sınıfı](../standard-library/hash-map-class.md) `hash_map` .

### <a name="remarks"></a>Açıklamalar

İçindeki varolan öğeleri sildikten sonra `hash_map` , ' `operator=` nin içeriğini kopyalar ya da içine *taşısa* `hash_map` .

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

## <a name="hash_mappointer"></a><a name="pointer"></a> hash_map::p oınter

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

Hash_map bir öğeye işaretçi sağlayan bir tür.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir türü `pointer` , bir öğenin değerini değiştirmek için kullanılabilir.

Çoğu durumda, bir [yineleyici](#iterator) hash_map nesnesindeki öğelere erişmek için kullanılmalıdır.

## <a name="hash_maprbegin"></a><a name="rbegin"></a> hash_map:: rbegin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

Ters çevrilen hash_map ilk öğeyi adresleyen bir yineleyici döndürür.

```cpp
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir hash_map ilk öğeyi ele almak veya geri alınamaz hash_map son öğe olduğunu ele almak için ters çift yönlü Yineleyici.

### <a name="remarks"></a>Açıklamalar

`rbegin` , [Başlangıç](#begin) olarak bir hash_map ile birlikte kullanılan bir ters hash_map ile kullanılır.

Dönüş değeri `rbegin` bir [const_reverse_iterator](#const_reverse_iterator)atanmışsa, hash_map nesnesi değiştirilemez. Dönüş değeri `rbegin` bir [reverse_iterator](#reverse_iterator)atanmışsa, hash_map nesnesi değiştirilebilir.

`rbegin` , bir hash_map geriye doğru yinelemek için kullanılabilir.

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

## <a name="hash_mapreference"></a><a name="reference"></a> hash_map:: Reference

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

Hash_map depolanan bir öğeye başvuru sağlayan bir tür.

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

## <a name="hash_maprend"></a><a name="rend"></a> hash_map:: rend

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

Ters çevrilen hash_map son öğeden sonraki konumu ele alan bir yineleyici döndürür.

```cpp
const_reverse_iterator rend() const;

reverse_iterator rend();
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir hash_map en son öğeden sonra gelen konumu ele alan ters çift yönlü yineleyici (geri alınamaz hash_map ilk öğeden önce gelen konum).

### <a name="remarks"></a>Açıklamalar

`rend` , [End](#end) bir hash_map ile kullanıldığı gibi ters bir hash_map kullanılır.

Dönüş değeri `rend` bir [const_reverse_iterator](#const_reverse_iterator)atanmışsa, hash_map nesnesi değiştirilemez. Dönüş değeri `rend` bir [reverse_iterator](#reverse_iterator)atanmışsa, hash_map nesnesi değiştirilebilir.

`rend` ters bir yineleyicinin hash_map sonuna kadar ulaştığı konusunda test etmek için kullanılabilir.

Tarafından döndürülen değer `rend` başvurulmamalıdır.

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

## <a name="hash_mapreverse_iterator"></a><a name="reverse_iterator"></a> hash_map:: reverse_iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

Ters çevrilen bir hash_map bir öğeyi okuyabilen veya değiştirebilen çift yönlü bir yineleyici sağlayan bir tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::reverse_iterator reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür, `reverse_iterator` bir öğenin değerini değiştiremez ve hash_map ters bir şekilde yinelemek için kullanılır.

`reverse_iterator`Tarafından tanımlanan hash_map,, ilk üyesi öğe için anahtar olan ve ikinci üye öğesi tarafından tutulan eşlenmiş veri olan tür **çiftinin \<const Key, Type> ** [value_type](#value_type)nesneleri olan öğeleri gösterir.

Bir hash_map bir `reverse_iterator` `rIter` öğeyi işaret etmek için-> işlecini kullanın.

Öğesinin anahtar değerine erişmek için, `rIter`  ->  () ile eşdeğer olan **ilk**öğesini kullanın \* `rIter` . **ilk**olarak. Öğesi için eşlenen veri değerine erişmek için, `rIter`  ->  () eşdeğeri olan **ikincisini**kullanın \* `rIter` . **ilk**olarak.

### <a name="example"></a>Örnek

Bildirme ve kullanma hakkında bir örnek için bkz. [rbegin](#rbegin) örneği `reverse_iterator` .

## <a name="hash_mapsize"></a><a name="size"></a> hash_map:: size

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

Hash_map öğe sayısını döndürür.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Hash_map geçerli uzunluğu.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

Aşağıdaki örnek hash_map:: size üye işlevinin kullanımını gösterir.

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

## <a name="hash_mapsize_type"></a><a name="size_type"></a> hash_map:: size_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

Bir hash_map öğe sayısını temsil eden işaretsiz bir tamsayı türü.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::size_type size_type;
```

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

Bildirme ve kullanma hakkında bir [örnek için bkz](#size) . örnek `size_type`

## <a name="hash_mapswap"></a><a name="swap"></a> hash_map:: swap

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

İki hash_maps öğelerini değiş tokuş eder.

```cpp
void swap(hash_map& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Bağımsız değişkeni, hedef hash_map birlikte takas edilecek öğeleri sağlayan hash_map.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, öğeleri takas edilmekte olan iki hash_maps öğeleri belirten başvuruları, işaretçileri veya yineleyicileri geçersiz kılar.

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

## <a name="hash_mapupper_bound"></a><a name="upper_bound"></a> hash_map:: upper_bound

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

Bir yineleyiciyi belirtilen anahtardan daha büyük bir değere sahip olan bir hash_map içindeki ilk öğeye döndürür.

```cpp
iterator upper_bound(const Key& key);

const_iterator upper_bound(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*anahtar*\
Aranan hash_map öğenin sıralama anahtarı değeriyle Karşılaştırılacak bağımsız değişken anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişken anahtarından daha büyük bir anahtara sahip bir hash_map içindeki bir öğenin konumunu adresleyen veya anahtar için eşleşme bulunmazsa hash_map son öğeden sonraki konumu ele alan bir [Yineleyici](#iterator) veya [const_iterator](#const_iterator) .

Dönüş değeri bir öğesine atanırsa `const_iterator` , hash_map nesnesi değiştirilemez. Dönüş değeri bir öğesine atanırsa `iterator` , hash_map nesnesi değiştirilebilir.

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

## <a name="hash_mapvalue_comp"></a><a name="value_comp"></a> hash_map:: value_comp

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

Anahtar değerlerini karşılaştırarak bir hash_map öğelerin sırasını belirleyen bir işlev nesnesi döndürür.

```cpp
value_compare value_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Hash_map öğelerini sıralamak için kullandığı karşılaştırma işlevi nesnesini döndürür.

### <a name="remarks"></a>Açıklamalar

Bir hash_map n için, iki öğe *E1* (*K1*, *D1*) ve *e2* (*K2*, *D2*), [value_type](#value_type)türündeki nesnelerdir; burada *K1* ve *K2* [key_type](#key_type) , *D1* ve *D2* [mapped_type](#mapped_type)türünde olan ve bu durumda ile *m* `m.value_comp()(e1, e2)` eşdeğerdir `m.key_comp()(k1, k2)` . Saklı nesne üye işlevini tanımlar

`bool operator(value_type& left, value_type& right);`

Bu **`true`** , anahtar değerinin `left` önce ve ' nin sıralama düzeninde anahtar değerine eşit olmaması halinde döndürür `right` .

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

## <a name="hash_mapvalue_type"></a><a name="value_type"></a> hash_map:: value_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

Hash_map depolanan nesne türünü temsil eden bir tür.

```cpp
typedef pair<const Key, Type> value_type;
```

### <a name="remarks"></a>Açıklamalar

`value_type` , `pair<const key_type, mapped_type>` `pair<key_type, mapped_type>` bir ilişkilendirilebilir kapsayıcının anahtarlarının sabit olmayan bir yineleyici veya başvuru kullanılarak değiştirilemediği için olduğu şekilde bildirilmiştir.

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

[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ standart kitaplığı başvurusu](../standard-library/cpp-standard-library-reference.md)
