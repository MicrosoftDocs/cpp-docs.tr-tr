---
title: hash_map sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 08c16cd80828e973e4fff2d1a2c36e211e61f361
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43211598"
---
# <a name="hashmap-class"></a>hash_map Sınıfı

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Depolar ve verileri hızlı bir şekilde her bir öğenin değeri benzersiz olan sıralama anahtarına sahip olduğu bir çift olan bir koleksiyonu ve ilişkili veriler değerini alır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Key,
    class Type,
    class Traits=hash_compare<Key, less<Key>>,
    class Allocator=allocator<pair <const Key, Type>>>
class hash_map
```

### <a name="parameters"></a>Parametreler

*Key*<br/>
 Hash_map içinde depolanacak anahtar veri türü.

*Türü*<br/>
 Hash_map içinde depolanacak öğe veri türü.

*Nitelikler*<br/>
 İki işlev nesneleri içeren türü sınıf karşılaştırma kendi göreli sıralarını ve karma işlevi, belirlemek için sıralama anahtarları iki öğenin değerlerini karşılaştırma mümkün öğelerinin anahtar değerlerini türü işaretsiztamsayılariçineşlemebirlikoşulubiridir`size_t`. Bu bağımsız değişken isteğe bağlıdır ve hash_compare <`Key`, daha az <`Key`>> varsayılan değerdir.

*Ayırıcı*<br/>
 Hash_map'ın ayırma ve bellek ayırmayı kaldırma hakkındaki ayrıntıları içeren saklı ayırıcı nesnesini gösteren tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer allocator < pair < const `Key`, `Type`>>.

## <a name="remarks"></a>Açıklamalar

Hash_map aşağıdaki gibidir:

- İlişkili bir anahtar değerine dayalı öğe değerlerinin verimli alınmasını destekleyen bir değişken boyutu kapsayıcı olan ilişkilendirilebilir bir kapsayıcı.

- Çift yönlüdür, çünkü öğelerine erişmek için çift yönlü bir yineleyici sağlar.

- Karma, çünkü öğelerine demet öğelerinin anahtar değerlere uygulanan bir karma işlevi değere göre gruplanmıştır.

- Benzersizdir, çünkü öğelerinin her birinde benzersiz bir anahtar olması gerekir.

- Bir çift ilişkilendirilebilir kapsayıcıdır, çünkü veri öğelerinin değerleri kendi anahtar değerlerinden farklıdır.

- Bir şablon sınıfıdır, çünkü sağladığı işlevsellik geneldir ve böylece öğeler veya anahtarlar olarak kapsanan belirli veri türünden bağımsızdır. Öğeler ve anahtarlar için kullanılacak veri türleri, karşılaştırma işlevi ve ayırıcı ile birlikte bir sınıf şablonunda parametreler olarak belirtilir.

Sıralama üzerinden karma ana avantajı, daha verimli olur; başarılı bir karma işlevi ekleme, silme gerçekleştirir ve sabit ortalama süre değiştirmeyen bir süre içinde teknikleri sıralama kapsayıcıdaki öğelerin sayısını logaritmasını için orantılı bulur. Bir hash_map içindeki bir öğenin değeri, ancak ilişkili anahtar değeri, doğrudan değiştirilemez. Bunun yerine, eski öğelerle ilişkili anahtar değerleri silinmeli ve eklenen yeni öğelerle ilişkili yeni anahtar değerleri eklenmelidir.

Kapsayıcı türünün seçimi genelde uygulamanın gerektirdiği arama ve ekleme türüne dayalı olmalıdır. Karma ilişkilendirilebilir kapsayıcılar, arama, ekleme ve kaldırma işlemleri için iyileştirilmiştir. Bu işlemleri açıkça destekleyen üye işlevleri, ortalama sabit ve kapsayıcıdaki öğelerin sayısına bağlı olmayan bir zaman gerçekleştirip bir iyi tasarlanmış bir karma işlevi ile kullanıldığında verimlidir. İyi tasarlanmış bir karma işlevi, Tekdüzen karma bir değerler dağıtımı verir ve burada bir çakışma ortaya çıkar farklı anahtar değerlerini aynı karma değer ile eşlenmiş kabul edilir, çakışmaları sayısını en aza indirir. En kötü durumda, en kötü olası karma işlevi ile işlem sayısı dizideki (doğrusal zaman) öğelerin sayısını orantılıdır.

Hash_map, değerleri onların kendi anahtarlarıyla ilişkilendiren koşullar uygulama tarafından karşılandığında seçimin ilişkili kapsayıcısı olmalıdır. Bu tür bir yapı için model sıralı bir listesidir, örneğin tanımları sağlayan dize değerleriyle ilişkili benzersiz oluşan anahtar sözcükler. Ardından, anahtarlar benzersiz değildi. böylece bunun yerine, sözcüklerin birden fazla doğru tanımı varsa, bir hash_multimap kapsayıcı olacaktır. Ardından, diğer taraftan, yalnızca sözcüklerin listesi depolanmaktadır, bir hash_set doğru kapsayıcı olacaktır. Ardından bir hash_multiset sözcüklerin birden çok defa geçmelerine izin verilirse, uygun bir kapsayıcı yapısı olacaktır.

Hash_map depolanan karma çağırarak denetlediği diziyi sıralar *nitelikler* sınıfın nesnesi [value_compare](../standard-library/value-compare-class.md). Üye işlevini çağırarak depolanan bu nesne erişilebilecek [key_comp](#key_comp). Böyle bir işlev nesnesi aynı sınıfın bir nesnesi olarak davranmalıdır [hash_compare](../standard-library/hash-compare-class.md)< daha az anahtar\<anahtarı >>. Tüm değerler için özellikle *anahtarı* türü *anahtarı*, çağrı `Traits`( `Key` ) türünde bir değerler dağıtımı verir `size_t`.

Genelde, bu sıralamayı oluşturmak için öğelerin yalnızca küçüktür biçiminde karşılaştırılabilir olması gerekir; böylece, herhangi iki öğe belirtildiğinde, eşit oldukları (yani birinin diğerinden daha küçük olmadığı anlamında) veya birinin diğerinden küçük olduğu belirlenebilir. Bu, denk olmayan öğeler arasında bir sıralamaya neden olur. Daha teknik bir not üzerinde, karşılaştırma işlevi standart matematiksel anlamda katı bir zayıf sıralama sevk eden ikili bir koşuldur. Bir ikili koşul f(x y) iki bağımsız değişken nesnelere sahip bir işlev nesnesidir `x` ve `y` ve dönüş değeri **true** veya **false**. İkili koşul dönüşsüz, ters ve geçişli ve denklik geçişli ise, burada iki nesne sıralama katı zayıf bir hash_map üzerinde uygulanan sıralama olduğu x ve y f (x, y) hem f (y, x) false olduğunda denk olarak tanımlanır. Anahtarlar arasındaki eşitliğinin daha güçlü koşulu bu denkliğin yerini alırsa, sıralama (içindeki tüm öğelerin birbirine göre sıralanması anlamında) toplam haline gelir ve eşleşen anahtarlar birbirinden ayırt edilemez olacaktır.

Denetlenen dizideki öğelerin gerçek sırası karma işlevi ve sıralama işlevini geçerli boyutu bir kapsayıcı nesnesinde depolanan karma tablo bağlıdır. Denetlenen dizideki öğelerin sırasını genelde tahmin edemezsiniz için karma tablo geçerli boyutu belirlenemiyor. Öğelerin eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; öğelerin kaldırılması yalnızca özellikle kaldırılan öğeleri gösteren yineleyicileri geçersiz kılar.

Hash_map sınıfı tarafından sağlanan yineleyici çift yönlüdür, ancak sınıf üyesi işlevleri olan [Ekle](#insert) ve [hash_map](#hash_map) şablon parametresi olarak daha zayıf bir giriş yineleyicisini alan sürümlere sahip işlevsellik gereksinimleri daha az tarafından çift yönlü Yineleyicilerin sınıfında garanti edilene. Farklı yineleyici kavramları, işlevselliklerindeki iyileştirmelere göre ilgili bir aile biçimlendirir. Her yineleyici kavramının kendi gereksinimler kümesi vardır ve bunlarla çalışan algoritmaların kendi varsayımlarını yineleyici türü tarafından sağlanan gereksinimlerle sınırlaması gerekir. Bir giriş yineleyicinin bazı nesnelere başvurusunun kaldırılacağı ve dizideki sonraki yineleyiciye artırılabileceği varsayılabilir. Bu bir en düşük işlevsellik kümesidir, ancak Yineleyicilerin aralığı hakkında konuşabilmek için yeterlidir `[First, Last)` sınıf üye işlevleri bağlamında.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[hash_map](#hash_map)|Oluşturur bir `hash_map` boş veya diğer bir deyişle bir kopyasını tüm veya diğer bir kısmının parçası `hash_map`.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[allocator_type](#allocator_type)|Temsil eden bir tür `allocator` sınıfının `hash_map` nesne.|
|[const_iterator](#const_iterator)|Çift yönlü bir yineleyici sağlayan tür okuma bir `const` öğesinde `hash_map`.|
|[const_pointer](#const_pointer)|Bir işaretçi sağlayan bir tür bir **const** öğesinde bir `hash_map`.|
|[const_reference](#const_reference)|Bir başvuru sağlayan bir tür bir **const** öğesi içinde depolanan bir `hash_map` okumak ve gerçekleştirmek için **const** operations.|
|[const_reverse_iterator](#const_reverse_iterator)|Çift yönlü bir yineleyici sağlayan tür herhangi okuma **const** öğesinde `hash_map`.|
|[difference_type](#difference_type)|Öğelerin sayısını temsil etmek için kullanılabilen işaretli bir tamsayı türü bir `hash_map` yineleyiciler tarafından gösterilen öğeler arasındaki bir aralıktaki.|
|[Yineleyici](#iterator)|Çift yönlü bir yineleyici sağlayan bir tür okuyabilen veya değiştirebilen herhangi bir öğenin bir `hash_map`.|
|[key_compare](#key_compare)|İki öğenin göreli sırasını belirlemek için iki sıralama anahtarını karşılaştıran işlev nesnesi sağlayan bir tür `hash_map`.|
|[key_type](#key_type)|Her öğesini oluşturan sıralama anahtarını nesnesini tanımlayan bir bir tür `hash_map`.|
|[mapped_type](#mapped_type)|İçinde depolanan veri türünü temsil eden bir tür bir `hash_map`.|
|[İşaretçi](#pointer)|İçindeki bir öğeye işaretçi sağlayan bir tür bir `hash_map`.|
|[Başvuru](#reference)|İçinde depolanan öğeye başvuru sağlayan bir tür bir `hash_map`.|
|[reverse_iterator](#reverse_iterator)|Çift yönlü bir yineleyici sağlayan bir tür okuyabilen veya değiştirebilen ters döndürülmüş bir öğe `hash_map`.|
|[size_type](#size_type)|İçindeki öğelerin sayısını temsil edebilen bir işaretsiz tamsayı türü bir `hash_map`.|
|[value_type](#value_type)|İki öğenin kendi göreli sıralarını belirlemek için sıralama anahtarları olarak karşılaştırabilen bir işlev nesnesi sağlayan bir tür `hash_map`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[konumunda](#at)|Bir öğe bulur bir `hash_map` belirtilen anahtar değere sahip.|
|[başlayın](#begin)|İçindeki ilk öğeyi adresleyen bir yineleyici döndürür `hash_map`.|
|[cbegin](#cbegin)|İçindeki ilk öğeyi adresleyerek bir const yineleyici döndürür `hash_map`.|
|[cend](#cend)|İçindeki son öğeyi takip eden konumu ele alan sabit bir yineleyici döndüren bir `hash_map`.|
|[Temizle](#clear)|Tüm öğelerini siler bir `hash_map`.|
|[Sayısı](#count)|İçindeki öğelerin sayısını döndüren bir `hash_map` anahtarı parametre tarafından belirtilen bir anahtarla eşleşen.|
|[crbegin](#crbegin)|Ters çevrilen içindeki ilk öğeyi adresleyerek bir const yineleyici döndürür `hash_map`.|
|[crend](#crend)|Ters çevrilen içindeki son öğeyi takip eden konumu ele alan sabit bir yineleyici döndürür `hash_map`.|
|[emplace](#emplace)|İçine yerinde oluşturulmuş bir öğe ekler bir `hash_map`.|
|[emplace_hint](#emplace_hint)|İçine yerinde oluşturulmuş bir öğe ekler bir `hash_map`, bir yerleşim ipucuyla birlikte.|
|[boş](#empty)|Testleri bir `hash_map` boştur.|
|[Son](#end)|İçindeki son öğeyi takip eden konumu ele alan bir yineleyici döndüren bir `hash_map`.|
|[equal_range](#equal_range)|Yineleyicilerin bir çiftini, sırasıyla içindeki ilk öğeye döndürür bir `hash_map` içindeki ilk öğeye ve belirtilen anahtardan daha büyük bir anahtarla `hash_map` anahtardan daha büyük veya ona eşit bir anahtara sahip.|
|[silme](#erase)|Bir öğenin veya öğelerin aralığını kaldırır bir `hash_map` belirtilen konumlardan|
|[Bul](#find)|İçindeki bir öğenin konumunu ele alan bir yineleyici döndüren bir `hash_map` belirtilen anahtara denk bir anahtara sahip.|
|[get_allocator](#get_allocator)|Bir kopyasını döndürür `allocator` oluşturmak için kullanılan nesne `hash_map`.|
|[Ekle](#insert)|Bir öğe veya bir dizi öğelerine ekler bir `hash_map`.|
|[key_comp](#key_comp)|İçindeki ilk öğeye bir yineleyici döndüren bir `hash_map` belirtilen anahtardan daha büyük veya ona eşit bir anahtar değere sahip.|
|[lower_bound](#lower_bound)|İçindeki ilk öğeye bir yineleyici döndüren bir `hash_map` belirtilen anahtardan daha büyük veya ona eşit bir anahtar değere sahip.|
|[max_size](#max_size)|Öğesinin maksimum uzunluğunu döndürür `hash_map`.|
|[rbegin](#rbegin)|Ters çevrilen içindeki ilk öğeyi adresleyen bir yineleyici döndürür `hash_map`.|
|[rend](#rend)|Ters çevrilen içindeki son öğeden sonra gelen konumu ele alan bir yineleyici döndürür `hash_map`.|
|[Boyutu](#size)|İçindeki öğelerin sayısını döndürür `hash_map`.|
|[değiştirme](#swap)|İki öğeleri birbiriyle değiştirir `hash_map`s.|
|[upper_bound](#upper_bound)|İçindeki ilk öğeye bir yineleyici döndüren bir `hash_map` belirtilen anahtardan büyük bir anahtarla değer.|
|[value_comp](#value_comp)|İçindeki öğe değerlerini sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır bir `hash_map`.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleci&#91;&#93;](#op_at)|Bir öğe ekler bir `hash_map` belirtilen anahtar değere sahip.|
|[hash_map::operator=](#op_eq)|Öğelerinin yerini alan bir `hash_map` başka bir kopyasına sahip olan `hash_map`.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<hash_map >

**Namespace:** stdext

## <a name="allocator_type"></a>  hash_map::allocator_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Hash_map nesne için ayırıcı sınıf temsil eden tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::allocator_type allocator_type;
```

### <a name="example"></a>Örnek

Örneğin bakın [get_allocator](#get_allocator) bir örnek için `allocator_type`.

## <a name="at"></a>  hash_map::AT

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Belirtilen anahtar değere sahip bir hash_map bir öğe bulur.

```cpp
Type& at(const Key& key);

const Type& at(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Anahtarı*|Bulunacak öğenin anahtar değeri.|

### <a name="return-value"></a>Dönüş Değeri

Bulunan elemanın veri değerine başvuru.

### <a name="remarks"></a>Açıklamalar

Bağımsız değişken anahtarı değeri bulunamazsa sonra işlevin sınıfın bir nesnesi atar [out_of_range sınıfı](../standard-library/out-of-range-class.md).


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

## <a name="begin"></a>  hash_map::Begin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Hash_map içindeki ilk öğeyi ele alan bir yineleyici döndürür.

```cpp
const_iterator begin() const;

iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

Hash_map veya sonra gelen konumu adresleyen bir boş hash_map içindeki ilk öğeyi ele alan bir çift yönlü yineleyici.

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

## <a name="cbegin"></a>  hash_map::cbegin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Hash_map içindeki ilk öğeyi adresleyerek bir const yineleyici döndürür.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

İçindeki ilk öğeyi ele alan sabit bir çift yönlü yineleyici [hash_map](../standard-library/hash-map-class.md) veya sonra gelen konumu adresleyen bir boş `hash_map`.

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

## <a name="cend"></a>  hash_map::cend

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Bir hash_map içindeki son öğeden sonra gelen konumu ele alan bir sabit yineleyici döndürür.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Dönüş Değeri

İçindeki son öğeyi takip eden konumu ele alan sabit bir çift yönlü yineleyici bir [hash_map](../standard-library/hash-map-class.md). Varsa `hash_map` boşsa `hash_map::cend == hash_map::begin`.

### <a name="remarks"></a>Açıklamalar

`cend` sonuna bir yineleyici olup olmadığını test etmek için kullanılan kendi `hash_map`.

Tarafından döndürülen değer `cend` kaldırılmamalıdır.

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

## <a name="clear"></a>  hash_map::Clear

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Bir hash_map tüm öğelerini siler.

```cpp
void clear();
```

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

Aşağıdaki örnek, hash_map::clear üye işlevinin kullanımını gösterir.

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

## <a name="const_iterator"></a>  hash_map::const_iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Çift yönlü bir yineleyici sağlayan tür okuma bir **const** hash_map öğesinde.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_iterator const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_iterator` bir öğenin değerini değiştirmek için kullanılamaz.

`const_iterator` Hash_map noktalarına nesnelerin olan öğeler tarafından tanımlanan [value_type](#value_type), diğer bir deyişle tür `pair< const Key, Type >`olan ilk üye öğe anahtarıdır ve ikinci öğe tarafından tutulan eşlenen datum üyesidir.

Başvurulacak bir `const_iterator` `cIter` bir hash_map içindeki bir öğeyi işaret eden, kullanın `->` işleci.

Öğenin anahtarının değerini erişmek için `cIter->first`, eşdeğer olan `(*cIter).first`. Eşlenmiş veri öğesi için değeri erişmek için `cIter->second`, eşdeğer olan `(*cIter).second`.

### <a name="example"></a>Örnek

Örneğin bakın [başlamak](#begin) bir örnek için `const_iterator`.

## <a name="const_pointer"></a>  hash_map::const_pointer

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Bir işaretçi sağlayan bir tür bir **const** bir hash_map öğesinde.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::const_pointer const_pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_pointer` bir öğenin değerini değiştirmek için kullanılamaz.

Çoğu durumda bir [yineleyici](#iterator) hash_map nesnesindeki öğelere erişmek için kullanılmalıdır.

## <a name="const_reference"></a>  hash_map::const_reference

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Bir başvuru sağlayan bir tür bir **const** okumak ve gerçekleştirmek için bir hash_map içinde depolanan öğenin **const** operations.

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

## <a name="const_reverse_iterator"></a>  hash_map::const_reverse_iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Çift yönlü bir yineleyici sağlayan tür herhangi okuma **const** hash_map öğesinde.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_reverse)iterator const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_reverse_iterator` kullanın tersten hash_map yinelemek için ve bir öğenin değerini değiştiremezsiniz.

`const_reverse_iterator` Hash_map noktalarına nesnelerin olan öğeler tarafından tanımlanan [value_type](#value_type), diğer bir deyişle tür `pair` \< **const Key, türü**>, ilk üye olduğu anahtar öğe tarafından tutulan öğe ve eşlenen datum olan ikinci üyesidir.

Başvurulacak bir `const_reverse_iterator` `crIter` bir hash_map içindeki bir öğeyi işaret eden, kullanın **->** işleci.

Öğenin anahtarının değerini erişmek için `crIter`  ->  **ilk**, eşit olduğu (\* `crIter`) **.first**. Eşlenmiş veri öğesi için değeri erişmek için `crIter`  ->  **ikinci**, eşit olduğu (\* `crIter`). **İlk**.

### <a name="example"></a>Örnek

Örneğin bakın [rend](#rend) bildirme ve kullanma konusunda bir örnek için `const_reverse_iterator`.

## <a name="count"></a>  hash_map::Count

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Anahtarı parametre tarafından belirtilen bir anahtarla eşleşen bir hash_map öğelerin sayısını döndürür.

```cpp
size_type count(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
 Hash_map eşleştirilecek öğelerin anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

hash_map sıralama anahtarı parametresi anahtarla eşleşen bir öğe içeriyorsa 1; 0 hash_map bir öğesi ile eşleşen bir anahtar içermiyor.

### <a name="remarks"></a>Açıklamalar

Üye işlevi öğelerin sayısını döndürür *x* aralığında

[ `lower_bound` (_ *Anahtarı* ), `upper_bound` (\_ *anahtarı* ))

0 veya 1 benzersiz bir ilişkilendirilebilir kapsayıcıdır hash_map, söz konusu olduğunda olduğu.

### <a name="example"></a>Örnek

Aşağıdaki örnek, hash_map::count üye işlevinin kullanımını gösterir.

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

## <a name="crbegin"></a>  hash_map::crbegin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Ters çevrilen hash_map içindeki ilk öğeyi adresleyerek bir const yineleyici döndürür.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir ilk öğeyi ele alan çift yönlü yineleyici bir const [hash_map](../standard-library/hash-map-class.md) veya ne ters çevrilmeyen içindeki son öğeyi adresleyen `hash_map`.

### <a name="remarks"></a>Açıklamalar

`crbegin` ters çevrilen bir hash_map ile kullanılan gibi [başlamak](#begin) ile kullanılan bir `hash_map`.

Dönüş değeri ile `crbegin`, `hash_map` nesnesi değiştirilemez.

`crbegin` yinelemek için kullanılabilecek bir `hash_map` geriye doğru.

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

## <a name="crend"></a>  hash_map::crend

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Ters çevrilen hash_map içindeki son öğeyi takip eden konumu ele alan sabit bir yineleyici döndürür.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir içindeki son öğeden sonra gelen konumu ele çift yönlü yineleyici bir const [hash_map](../standard-library/hash-map-class.md) (ilk öğeyi çevrilmeyen önce gelen konum `hash_map`).

### <a name="remarks"></a>Açıklamalar

`crend` kullanılan bir ters ile `hash_map` gibi [hash_map::end](#end) ile kullanılan bir `hash_map`.

Dönüş değeri ile `crend`, `hash_map` nesnesi değiştirilemez.

`crend` olup ters yineleyici sonuna ulaşıp ulaşmadığını test etmek için kullanılan kendi `hash_map`.

Tarafından döndürülen değer `crend` kaldırılmamalıdır.

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

## <a name="difference_type"></a>  hash_map::difference_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Bir hash_map yineleyiciler tarafından gösterilen öğeler arasındaki bir aralıktaki öğelerin sayısını temsil etmek için kullanılabilen işaretli bir tamsayı türü.

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

## <a name="emplace"></a>  hash_map::emplace

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Bir hash_map yerinde oluşturulmuş bir öğe ekler.

```cpp
template <class ValTy>
pair <iterator, bool>
emplace(
    ValTy&& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*VAL*|Taşıma için kullanılan değer, a eklenmesi için bir öğe oluşturmak [hash_map](../standard-library/hash-map-class.md) sürece `hash_map` zaten o öğenin (veya daha genel anahtarı sıralı eşdeğer bir öğe) içerir.|

### <a name="return-value"></a>Dönüş Değeri

`emplace` Üye işlevi, bool bileşeni ekleme yaptıysanız true değerini döndürür, bayrak yoksa yanlış bir çiftini döndürür `hash_map` anahtarı sıralama, eşdeğer bir değer vardı ve yineleyici bileşeni döndürür bir öğe zaten içeriyordu Burada yeni bir öğe eklendi veya öğenin zaten bulunduğu adres.

Yineleyici bileşen çifti erişmeye `pr` bu üye işlevi tarafından döndürülen, kullanın `pr.first`ve bu başvuru için `*(pr.first)`. Erişim için **bool** bileşen çifti `pr` bu üye işlevi tarafından döndürülen, kullanın `pr.second`ve bu başvuru için `*(pr.second)`.

### <a name="remarks"></a>Açıklamalar

[Hash_map::value_type](#value_type) böylece bir öğenin değerini sıralı bir çift anahtar değerine eşit olan ilk bileşen ve saniye bileşenini öğenin veri değerine eşit olan bir çift öğesidir.

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

## <a name="emplace_hint"></a>  hash_map::emplace_hint

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Bir yerleşim ipucuyla birlikte bir hash_map içine yerinde oluşturulmuş bir öğe ekler.

```cpp
template <class ValTy>
iterator emplace_hint(
    const_iterator _Where,
    ValTy&& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*VAL*|Taşıma için kullanılan değer, a eklenmesi için bir öğe oluşturmak [hash_map](../standard-library/hash-map-class.md) sürece `hash_map` zaten o öğenin (veya daha genel anahtarı sıralı eşdeğer bir öğe) içerir.|
|*_Where*|Doğru ekleme noktasını için aramaya başlamak için yer ile ilgili bir ipucu.|

### <a name="return-value"></a>Dönüş Değeri

[Hash_multimap::emplace](../standard-library/hash-multimap-class.md#emplace) üye işlevi burada yeni bir öğe eklenir içine konumu gösteren bir yineleyici döndürür `hash_map`, ya da eşdeğer sıralamaya sahip var olan öğenin bulunduğu.

### <a name="remarks"></a>Açıklamalar

[Hash_map::value_type](#value_type) böylece bir öğenin değerini sıralı bir çift anahtar değerine eşit olan ilk bileşen ve saniye bileşenini öğenin veri değerine eşit olan bir çift öğesidir.

Ekleme oluşabilir Logaritmik süre yerine amorti edilmiş sabit zaman noktasını hemen izliyorsa *_Where*.

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

## <a name="empty"></a>  hash_map::empty

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Bir hash_map boş olup olmadığını sınar.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** hash_map boşsa; **false** hash_map boş ise.

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

## <a name="end"></a>  hash_map::End

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Bir hash_map içindeki son öğeden sonra gelen konumu ele alan bir yineleyici döndürür.

```cpp
const_iterator end() const;

iterator end();
```

### <a name="return-value"></a>Dönüş Değeri

Bir hash_map içindeki son öğeden sonra gelen konumu ele çift yönlü bir yineleyici. Hash_map boş sonra hash_map::end ise hash_map::begin ==.

### <a name="remarks"></a>Açıklamalar

`end` bir yineleyicinin kendi hash_map sonuna ulaştı olup olmadığını sınamak için kullanılır.

Tarafından döndürülen değer `end` kaldırılmamalıdır.

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

## <a name="equal_range"></a>  hash_map::equal_range

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Yineleyicilerin bir çiftini, sırasıyla belirtilen anahtardan daha büyük bir anahtarla bir hash_map içindeki ilk öğeye ve anahtardan büyük veya ona eşit bir anahtarla hash_map içindeki ilk öğeye döndürür.

```cpp
pair <const_iterator, const_iterator> equal_range (const Key& key) const;

pair <iterator, iterator> equal_range (const Key& key);
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
 Aranan hash_map bir öğeyi sıralama anahtarı ile Karşılaştırılacak bağımsız değişken anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

Yineleyicilerin bir çiftini ilk güvenilecek şekilde [lower_bound](#lower_bound) , anahtar ve ikinci [upper_bound](#upper_bound) anahtarı.

Bir çiftin ilk yineleyicisi erişmeye `pr` üye işlevi tarafından döndürülen, kullanın `pr`. **İlk** ve alt sınır yineleyicinin başvuru kaldırma için \*( `pr`. **İlk**). Bir çiftin ikinci yineleyicisi erişmeye `pr` üye işlevi tarafından döndürülen, kullanın `pr`. **İkinci** ve üst sınır yineleyicinin başvuru kaldırma için \*( `pr`. **İkinci**).

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
        << " matching the 2nd element of the pair"
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

## <a name="erase"></a>  hash_map::ERASE

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Bir öğenin veya öğelerin aralığını belirtilen konumlardan bir hash_map kaldırır veya belirtilen bir anahtarla eşleşen öğeleri kaldırır.

```cpp
iterator erase(iterator _Where);

iterator erase(iterator first, iterator last);

size_type erase(const key_type& key);
```

### <a name="parameters"></a>Parametreler

*_Where*<br/>
 Hash_map kaldırılacak öğenin konumu.

*ilk*<br/>
 Hash_map kaldırılan ilk öğenin konumu.

*Son*<br/>
 Konum yalnızca son öğeden sonra hash_map kaldırıldı.

*Anahtarı*<br/>
 Öğeleri hash_map kaldırılması için anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

İlk iki üye işlevleri için çift yönlü bir yineleyici, böyle bir öğe varsa, kaldırılan tüm öğelerin veya işaretçi hash_map sonuna dışında kalan ilk öğeyi belirtir.

Üye işlevi için üçüncü hash_map kaldırılan öğelerin sayısını döndürür.

### <a name="remarks"></a>Açıklamalar

Üye işlevleri, hiçbir zaman bir özel durum.

### <a name="example"></a>Örnek

Aşağıdaki örnek, hash_map::erase üye işlevinin kullanımını gösterir.

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

## <a name="find"></a>  hash_map::Find

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Belirtilen anahtara denk bir anahtara sahip bir hash_map içindeki bir öğenin konumunu ele alan bir yineleyici döndürür.

```cpp
iterator find(const Key& key);

const_iterator find(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
 Aranan hash_map bir öğeyi sıralama anahtarı tarafından eşleştirilecek anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

Bir öğenin konumunu belirtilen bir anahtar veya anahtar için bir eşleşme varsa hash_map içindeki son öğeyi takip eden konumu ele alan bir yineleyici.

### <a name="remarks"></a>Açıklamalar

`find` comparability ilişkisi küçüktür temel bir sıralama anahtarı, bağımsız değişken anahtarı altındaki bir sıralama sevk eden ikili bir koşula eşdeğerdir hash_map öğeyi adresleyen bir yineleyici döndürür.

Varsa dönüş değerinin `find` atanan bir [const_iterator](#const_iterator), hash_map nesnesi değiştirilemez. Varsa dönüş değerinin `find` atanan bir [yineleyici](#iterator), hash_map nesnesi değiştirilebilir

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

## <a name="get_allocator"></a>  hash_map::get_allocator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Hash_map oluşturmak için kullanılan ayırıcı nesnesinin bir kopyasını döndürür.

```cpp
Allocator get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Hash_map tarafından kullanılan ayırıcı.

### <a name="remarks"></a>Açıklamalar

Hash_map sınıfı için ayırıcılar sınıfı depolama nasıl yönettiğini belirtin. C++ Standart Kitaplığı kapsayıcı sınıfları ile sağlanan varsayılan ayırıcılar çoğu programlama ihtiyaçları için yeterli. Yazma ve kendi allocator sınıfı kullanarak bir Gelişmiş C++ konudur.

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

## <a name="hash_map"></a>  hash_map::hash_map

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Boş olan veya bir kopyası tüm veya bazı diğer hash_map parçası hash_map oluşturur.

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
|*Al*|Varsayılan olarak bu hash_map nesne için kullanılacak depolama ayırıcı sınıf `Allocator`.|
|*Comp*|Karşılaştırma işlevi türü const `Traits` varsayılan olarak hash_map içinde öğeleri sıralamak için kullanılan `hash_compare`.|
|*sağ*|Oluşturulan eşleme kopyası olacak olduğu hash_map.|
|*ilk*|Kopyalanacak öğe aralığındaki ilk öğenin konumu.|
|*Son*|Kopyalanacak öğe aralığının dışındaki ilk öğenin konumu.|
|*IList*|İnitializer_list|

### <a name="remarks"></a>Açıklamalar

Tüm oluşturucular hash_map için bellek depolama yöneten ayırıcı nesnesi türü depolamak ve daha sonra çağırarak döndürülebilir [get_allocator](#get_allocator). Allocator parametresi, sınıf bildirimleri ve diğer ayırıcılar yerine kullanılan ön işleme makroları genellikle atlanır.

Tüm oluşturucular kendi hash_map başlatın.

Tüm oluşturucular türünün işlev nesnesini depolamak `Traits` hash_map anahtarları arasında bir sıralamayı oluşturmak için kullanılan ve, daha sonra döndürülmesi çağırarak [key_comp](#key_comp).

İlk üç Oluşturucu boş bir başlangıç hash_map belirtin, ayrıca, ikinci karşılaştırma işlevi türünü belirtir (*kompozisyonu*) öğeleri ve üçüncüsü sırasını açıkça oluşturmada kullanılacak belirtir ayırıcı türünü (*Al*) kullanılacak. Anahtar sözcüğü **açık** otomatik tür dönüştürme belirli türdeki bastırır.

Dördüncü Oluşturucu hash_map bir kopyasını belirtir *sağ*.

Sonraki üç oluşturucular aralığını kopyalamaktadır `[First, Last)` , sınıfın karşılaştırma işlevinin türü belirtilirken explicitness artan bir hash_map `Traits` ve ayırıcı.

Son Oluşturucu hash_map taşır *sağ*.

## <a name="insert"></a>  hash_map::insert

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Bir öğenin veya öğelerin aralığını bir hash_map ekler.

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
|*VAL*|Hash_map o öğenin (veya daha genel olarak, öğenin anahtarı eşdeğer sıralı) zaten içermiyorsa hash_map eklenecek bir öğenin değeri.|
|*_Where*|Doğru ekleme noktasını için aramaya başlamak için yer ile ilgili bir ipucu.|
|*ilk*|Bir hash_map kopyalanacak ilk öğenin konumu.|
|*Son*|Yalnızca bir hash_map kopyalanacak son öğenin ötesinde konumu.|

### <a name="return-value"></a>Dönüş Değeri

İlk `insert` üye işlevinin döndürdüğü çifti bool bileşeni ekleme yaptıysanız true değerini döndürür ve false hash_map anahtarı sıralama, eşdeğer bir değer vardı ve yineleyici bileşeni döndürür bir öğe içeriyorsa Burada yeni bir öğe eklendi veya öğenin zaten bulunduğu adres.

Yineleyici bileşen çifti erişmeye `pr` bu üye işlevi tarafından döndürülen, kullanın `pr`. **İlk**ve bu başvuru için \*( `pr`. **İlk**). Erişim için **bool** bileşen çifti `pr` bu üye işlevi tarafından döndürülen, kullanın `pr`. **İkinci**ve bu başvuru için \*( `pr`. **İkinci**).

İkinci `insert` üye işlevi, ipucu sürümü yeni bir öğe hash_map eklenir burada konumu gösteren bir yineleyici döndürür.

Son iki `insert` üye işlevleri davrandığını ilk ikisi, aynı oluşturmak eklenen değer taşıma dışında.

### <a name="remarks"></a>Açıklamalar

[Value_type](../standard-library/map-class.md#value_type) böylece bir öğenin değerini sıralı bir çift anahtar değerine eşit olan ilk bileşen ve saniye bileşenini öğenin veri değerine eşit olan bir çift öğesidir.

Ekleme oluşabilir Logaritmik süre yerine INSERT ipucu sürümü için amorti edilmiş sabit zaman noktasını hemen izliyorsa *_Where*.

Üçüncü üye işlevi bir hash_map aralığında bir yineleyici tarafından ele alınan her öğe için karşılık gelen öğe değerleri dizisi ekler *[First, Last)* belirtilen kümenin.

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

    cout<< "The original elements (Key => Value) of hm1 are:";
    for (hm1_pIter = hm1.begin(); hm1_pIter != hm1.end(); hm1_pIter++)
        cout << endl << " " << hm1_pIter -> first << " => "
             << hm1_pIter->second;
    cout << endl;

    pair< hash_map<int,int>::iterator, bool > pr;
    pr = hm1.insert(Int_Pair(1, 10));

    if (pr.second == true)
    {
        cout<< "The element 10 was inserted in hm1 successfully."
            << endl;
    }
    else
    {
        cout<< "The element 10 already exists in hm1\n with a key value of"
            << "((pr.first) -> first)= "<<(pr.first)-> first
            << "."<< endl;
    }

    // The hint version of insert
    hm1.insert(--hm1.end(), Int_Pair(5, 50));

    cout<< "After the insertions, the elements of hm1 are:";
    for (hm1_pIter = hm1.begin(); hm1_pIter != hm1.end(); hm1_pIter++)
        cout << endl << " " << hm1_pIter -> first << " => "
             << hm1_pIter->second;
    cout << endl;

    hm2.insert(Int_Pair(10, 100));

    // The templatized version inserting a range
    hm2.insert( ++hm1.begin(), --hm1.end() );

    cout<< "After the insertions, the elements of hm2 are:";
    for (hm2_pIter = hm2.begin(); hm2_pIter != hm2.end(); hm2_pIter++)
        cout << endl << " " << hm2_pIter -> first << " => "
             << hm2_pIter->second;
    cout << endl;

    // The templatized versions move constructing elements
    hash_map<int, string> hm3, hm4;
    pair<int, string> is1(1, "a"), is2(2, "b");

    hm3.insert(move(is1));
    cout << "After the move insertion, hm3 contains:" << endl
      << " " << hm3.begin()->first
      << " => " << hm3.begin()->second
      << endl;

    hm4.insert(hm4.begin(), move(is2));
    cout << "After the move insertion, hm4 contains:" << endl
      << " " << hm4.begin()->first
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
 with a key value of((pr.first) -> first)= 1.
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

## <a name="iterator"></a>  hash_map::iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Okuyabilen veya değiştirebilen herhangi bir öğenin bir hash_map çift yönlü yineleyiciler sağlayan tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::iterator iterator;
```

### <a name="remarks"></a>Açıklamalar

`iterator` Hash_map noktalarına nesnelerin olan öğeler tarafından tanımlanan [value_type](#value_type), diğer bir deyişle tür **çifti\<const Key, türü >,** olan ilk üye öğe anahtarıdır ve ikinci öğe tarafından tutulan eşlenen datum üyesidir.

Başvurulacak bir **yineleyici** `Iter` öğeye işaret eden bir çoklu eşlemde, kullanın `->` işleci.

Öğenin anahtarının değerini erişmek için `Iter`  ->  **ilk**, eşit olduğu (\* `Iter`). **İlk**. Eşlenmiş veri öğesi için değeri erişmek için `Iter`  ->  **ikinci**, eşit olduğu (\* `Iter`). **İkinci**.

Bir tür `iterator` bir öğenin değerini değiştirmek için kullanılabilir.

### <a name="example"></a>Örnek

Örneğin bakın [başlamak](#begin) bildirme ve kullanma konusunda bir örnek için `iterator`.

## <a name="key_comp"></a>  hash_map::key_comp

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Bir hash_map içindeki anahtarları sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır.

```cpp
key_compare key_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Alt öğeleri düzenlemek amacıyla bir hash_map kullanan bir işlev nesnesi döndürür.

### <a name="remarks"></a>Açıklamalar

Depolanan nesne üyesi işlevini tanımlar.

**bool işleci**( **const anahtar &** `left` **, const anahtar &** `right`);

döndüren **true** varsa `left` önündeki ve eşit değildir `right` sıralama düzeninde.

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

## <a name="key_compare"></a>  hash_map::key_compare

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Eşlem içindeki iki öğenin göreli sırasını belirlemek için iki sıralama anahtarını karşılaştıran işlev nesnesi sağlayan tür.

```cpp
typedef Traits key_compare;
```

### <a name="remarks"></a>Açıklamalar

`key_compare` Şablon parametresi için bir eşanlamlı olduğu `Traits`.

Daha fazla bilgi için `Traits` bkz [hash_map sınıfı](../standard-library/hash-map-class.md) konu.

### <a name="example"></a>Örnek

Örneğin bakın [key_comp](#key_comp) bildirme ve kullanma konusunda bir örnek için `key_compare`.

## <a name="key_type"></a>  hash_map::key_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Hash_map her öğesini oluşturan sıralama anahtarını nesnesini bir türü açıklar.

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Açıklamalar

`key_type` Şablon parametresi için bir eşanlamlı olduğu `Key`.

Daha fazla bilgi için `Key`, Açıklamalar bölümüne bakın [hash_map sınıfı](../standard-library/hash-map-class.md) konu.

### <a name="example"></a>Örnek

Örneğin bakın [value_type](#value_type) bildirme ve kullanma konusunda bir örnek için `key_type`.

## <a name="lower_bound"></a>  hash_map::lower_bound

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Bir yineleyiciyi belirtilen anahtardan daha büyük veya ona eşit bir anahtar değere sahip bir hash_map içindeki ilk öğeye döndürür.

```cpp
iterator lower_bound(const Key& key);

const_iterator lower_bound(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
 Aranan hash_map bir öğeyi sıralama anahtarı ile Karşılaştırılacak bağımsız değişken anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

Bir [yineleyici](#iterator) veya [const_iterator](#const_iterator) bağımsız değişken anahtardan daha büyük veya ona eşit olan veya bu konumu ele alan bir anahtar ile son başarılı bir hash_map içindeki bir öğenin konumunu ele anahtar için bir eşleşme varsa hash_map öğe.

Varsa dönüş değerinin `lower_bound` atanan bir `const_iterator`, hash_map nesnesi değiştirilemez. Varsa dönüş değerinin `lower_bound` atanan bir `iterator`, hash_map nesnesi değiştirilebilir.

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

## <a name="mapped_type"></a>  hash_map::mapped_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Bir hash_map içinde depolanan veri türünü temsil eden tür.

```cpp
typedef Type mapped_type;
```

### <a name="remarks"></a>Açıklamalar

Türü `mapped_type` şablon parametresi için bir eşanlamlı olduğu `Type`.

Daha fazla bilgi için `Type` bkz [hash_map sınıfı](../standard-library/hash-map-class.md) konu.

### <a name="example"></a>Örnek

Örneğin bakın [value_type](#value_type) bildirme ve kullanma konusunda bir örnek için `key_type`.

## <a name="max_size"></a>  hash_map::max_size

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Hash_map maksimum uzunluğunu döndürür.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Hash_map maksimum olası uzunluğu.

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

## <a name="op_at"></a>  hash_map::operator]

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Bir öğe ekler bir `hash_map` belirtilen anahtar değere sahip.

```cpp
Type& operator[](const Key& key);

Type& operator[](Key&& key);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Anahtarı*|Eklenecek öğenin anahtar değeri.|

### <a name="return-value"></a>Dönüş Değeri

Eklenen öğenin veri değerine başvuru.

### <a name="remarks"></a>Açıklamalar

Bağımsız değişken anahtar değeri bulunamazsa, değer veri türünün varsayılan değeriyle birlikte eklenir.

`operator[]` içine bir öğe eklemek için kullanılabilir bir `hash_map m` kullanma

`m[ key] = DataValue`;

değerini olduğu DataValue `mapped_type` öğenin anahtar değeri ile *anahtar*.

Kullanırken `operator[]` öğeleri eklemek için döndürülen başvuru ekleme önceden var olan bir öğeyi veya yeni bir tane oluşturmak anlamına gelmez. Üye işlevleri [Bul](../standard-library/map-class.md#find) ve [Ekle](../standard-library/map-class.md#insert) belirtilen anahtara sahip bir öğe zaten bir ekleme mevcut olup olmadığını belirlemek için kullanılabilir.

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

   // opperator[] will also insert by moving a key
   hash_map <string, int> hm2;
   string str("a");
   hm2[move(str)] = 1;
   cout << "The moved key is " << hm2.begin()->first
      << ", with value " << hm2.begin()->second << endl;
}
```

## <a name="op_eq"></a>  hash_map::operator =

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Hash_map öğelerini başka bir hash_map kopyasıyla değiştirir.

```cpp
hash_map& operator=(const hash_map& right);

hash_map& operator=(hash_map&& right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*sağ*|[Hash_map sınıfı](../standard-library/hash-map-class.md) içine kopyalanan `hash_map`.|

### <a name="remarks"></a>Açıklamalar

Var olan tüm öğeleri silme sonra bir `hash_map`, `operator=` kopyalar veya içeriğini hareket *doğru* içine `hash_map`.

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

## <a name="pointer"></a>  hash_map::pointer

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Bir hash_map öğeye işaretçi sağlayan bir tür.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `pointer` bir öğenin değerini değiştirmek için kullanılabilir.

Çoğu durumda bir [yineleyici](#iterator) hash_map nesnesindeki öğelere erişmek için kullanılmalıdır.

## <a name="rbegin"></a>  hash_map::rbegin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Ters çevrilen hash_map içindeki ilk öğeyi ele alan bir yineleyici döndürür.

```cpp
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen hash_map ilk öğeyi ele alan veya ne ters çevrilmeyen hash_map içindeki son öğeyi adresleyen ters iki yönlü yineleyici.

### <a name="remarks"></a>Açıklamalar

`rbegin` ters çevrilen bir hash_map ile kullanılan gibi [başlamak](#begin) bir hash_map ile kullanılır.

Varsa dönüş değeri `rbegin` atanan bir [const_reverse_iterator](#const_reverse_iterator), sonra da hash_map nesnesi değiştirilemez. Varsa dönüş değeri `rbegin` atanan bir [reverse_iterator](#reverse_iterator), ardından hash_map nesnesi değiştirilebilir.

`rbegin` bir hash_map geriye doğru gezinmek için kullanılabilir.

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

## <a name="reference"></a>  hash_map::Reference

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Bir hash_map içinde depolanan öğeye başvuru sağlayan bir tür.

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

## <a name="rend"></a>  hash_map::rend

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Ters çevrilen hash_map içindeki son öğeden sonra gelen konumu ele alan bir yineleyici döndürür.

```cpp
const_reverse_iterator rend() const;

reverse_iterator rend();
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir hash_map (ters çevrilmeyen hash_map ilk öğeyi önce gelen konum) içindeki son öğeden sonra gelen konumu ele ters iki yönlü yineleyici.

### <a name="remarks"></a>Açıklamalar

`rend` ters çevrilen bir hash_map ile kullanılan gibi [son](#end) bir hash_map ile kullanılır.

Varsa dönüş değeri `rend` atanan bir [const_reverse_iterator](#const_reverse_iterator), sonra da hash_map nesnesi değiştirilemez. Varsa dönüş değeri `rend` atanan bir [reverse_iterator](#reverse_iterator), ardından hash_map nesnesi değiştirilebilir.

`rend` olup ters yineleyici kendi hash_map sonuna ulaşıp ulaşmadığını test etmek için kullanılabilir.

Tarafından döndürülen değer `rend` kaldırılmamalıdır.

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

## <a name="reverse_iterator"></a>  hash_map::reverse_iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Okuyabilen veya değiştirebilen bir ters hash_map içindeki bir öğeyi çift yönlü yineleyiciler sağlayan tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::reverse_iterator reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `reverse_iterator` kullanın tersten hash_map yinelemek için ve bir öğenin değerini değiştiremezsiniz.

`reverse_iterator` Hash_map noktalarına nesnelerin olan öğeler tarafından tanımlanan [value_type](#value_type), diğer bir deyişle tür **çifti\<const Key, türü >**, olan ilk üye öğe anahtarıdır ve ikinci öğe tarafından tutulan eşlenen datum üyesidir.

Başvurulacak bir `reverse_iterator` `rIter` bir hash_map içindeki bir öğeyi işaret eden, kullanın -> işleci.

Öğenin anahtarının değerini erişmek için `rIter`  ->  **ilk**, eşit olduğu (\* `rIter`). **İlk**. Eşlenmiş veri öğesi için değeri erişmek için `rIter`  ->  **ikinci**, eşit olduğu (\* `rIter`). **İlk**.

### <a name="example"></a>Örnek

Örneğin bakın [rbegin](#rbegin) bildirme ve kullanma konusunda bir örnek için `reverse_iterator`.

## <a name="size"></a>  hash_map::size

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Hash_map öğelerin sayısını döndürür.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Hash_map geçerli uzunluğu.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

Aşağıdaki örnek, hash_map::size üye işlevinin kullanımını gösterir.

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

## <a name="size_type"></a>  hash_map::size_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Bir hash_map içindeki öğelerin sayısını temsil edebilen bir işaretsiz tamsayı türü.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::size_type size_type;
```

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

Örneğin bakın [boyutu](#size) bildirme ve kullanma örneği `size_type`

## <a name="swap"></a>  hash_map::Swap

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

İki hash_maps öğelerini birbiriyle değiştirir.

```cpp
void swap(hash_map& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
 Hedef hash_map ile değiştirilecek öğeleri sağlayan bağımsız değişken hash_map.

### <a name="remarks"></a>Açıklamalar

Üye işlev hiçbir başvurular, işaretçiler veya öğeleri değiştirilen iki hash_maps öğelerinde belirlemek yineleyicileri geçersiz kılar.

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

## <a name="upper_bound"></a>  hash_map::upper_bound

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Bir anahtar ile belirtilen anahtardan büyük bir değere sahip bir hash_map içindeki ilk öğeye bir yineleyici döndürür.

```cpp
iterator upper_bound(const Key& key);

const_iterator upper_bound(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
 Aranan hash_map öğeden sıralama anahtar değeri ile Karşılaştırılacak bağımsız değişken anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

Bir [yineleyici](#iterator) veya [const_iterator](#const_iterator) içindeki son öğeden sonra gelen konumu ele, bağımsız değişken anahtarı veya, daha büyük bir anahtarla hash_map içindeki bir öğenin konumunu ele hash_map anahtar için bir eşleşme.

Dönüş değeri atanır, bir `const_iterator`, hash_map nesnesi değiştirilemez. Dönüş değeri atanır, bir `iterator`, hash_map nesnesi değiştirilebilir.

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
   cout << "The 1st element of hm1 with a key greater than "
        << "that\n of the initial element of hm1 is: "
        << hm1_RcIter -> second << "." << endl;
}
```

```Output
The first element of hash_map hm1 with a key greater than 2 is: 30.
The hash_map hm1 doesn't have an element with a key greater than 4.
The 1st element of hm1 with a key greater than that
 of the initial element of hm1 is: 20.
```

## <a name="value_comp"></a>  hash_map::value_comp

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Anahtar değerlerini karşılaştırarak bir hash_map içindeki öğelerin sırasını belirleyen bir işlev nesnesi döndürür.

```cpp
value_compare value_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Alt öğeleri düzenlemek amacıyla bir hash_map kullanan karşılaştırma işlevi nesnesini döndürür.

### <a name="remarks"></a>Açıklamalar

Bir hash_map için *m*, iki öğe *e*1 *(k*1 *, d*1 *)* ve *e*2 *(k*2 *, d*2 *)* türündeki nesneler [value_type](#value_type)burada *k*1 ve *k*2 olan türü, anahtarlarına [key_type](#key_type) ve `d`1 ve `d`2 kendi veri türü olan [mapped_type](#mapped_type), ardından *m.*  `value_comp` *() (e*1 *, e*2 *)* eşdeğerdir *m.* `key_comp` *() (k*1 *, k*2 *)*. Depolanan bir nesne üye işlevini tanımlar.

**bool işleci**( **value_type &** `left`, **value_type &** `right`) **;**

döndüren **true** , anahtar değerini `left` önündeki ve anahtar değerine eşit değil `right` sıralama düzeninde.

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

## <a name="value_type"></a>  hash_map::value_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

İçinde bir hash_map depolanan nesne türünü temsil eden tür.

```cpp
typedef pair<const Key, Type> value_type;
```

### <a name="remarks"></a>Açıklamalar

`value_type` olarak bildirilen `pair<const key_type, mapped_type>` değil `pair<key_type, mapped_type>` nonconstant yineleyici veya başvuru kullanarak ilişkilendirilebilir bir kapsayıcı anahtarları değiştirilemez çünkü.

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
   // explicitely to avoid implicit type conversion
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

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
