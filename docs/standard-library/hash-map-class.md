---
title: hash_map sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
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
caps.latest.revision: 25
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bd22e193b1223ef3cef473463cc91f5bea0173b9
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="hashmap-class"></a>hash_map Sınıfı

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Depolar ve verileri hızlı bir şekilde her öğenin değeri benzersiz olan sıralama anahtarı olan bir çift olduğu bir koleksiyon ve ilişkili veriler bir değer alır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Key,
    class Type,
    class Traits=hash_compare<Key, less<Key>>,
    class Allocator=allocator<pair <const Key, Type>>>
class hash_map
```

### <a name="parameters"></a>Parametreler

`Key` Hash_map depolanması için anahtar veri türü.

`Type` Hash_map depolanması için öğe veri türü.

`Traits` İki işlev nesneleri içeren türü göreli sıralarına ve karma işlevini, belirlemek için sıralama anahtarları iki öğenin değerleri karşılaştırmak için sınıf karşılaştırma türü İmzasıztamsayılaraöğelerininanahtardeğerlerinieşlemebirlikoşulbiri`size_t`. Bu bağımsız değişken isteğe bağlıdır ve hash_compare < `Key`, daha az < `Key`>> varsayılan değerdir.

`Allocator` Hash_map's ayırma ve bellek ayırmayı kaldırma hakkında ayrıntılar yalıtan saklı ayırıcısı nesneyi temsil eden tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer ayırıcısı < pair < const `Key`, `Type`>>.

## <a name="remarks"></a>Açıklamalar

Hash_map aşağıdaki gibidir:

- İlişkili bir anahtar değerine dayalı öğe değerlerinin verimli alınmasını destekleyen bir değişken boyutu kapsayıcı olan ilişkilendirilebilir bir kapsayıcı.

- Çift yönlüdür, çünkü öğelerine erişmek için çift yönlü bir yineleyici sağlar.

- Karma, öğelerin anahtar değerleri için uygulanan bir karma işlevine değere göre demet içine öğeleri gruplandırıldığından.

- Benzersizdir, çünkü öğelerinin her birinde benzersiz bir anahtar olması gerekir.

- Bir çift ilişkilendirilebilir kapsayıcıdır, çünkü veri öğelerinin değerleri kendi anahtar değerlerinden farklıdır.

- Bir şablon sınıfıdır, çünkü sağladığı işlevsellik geneldir ve böylece öğeler veya anahtarlar olarak kapsanan belirli veri türünden bağımsızdır. Öğeler ve anahtarlar için kullanılacak veri türleri, karşılaştırma işlevi ve ayırıcı ile birlikte bir sınıf şablonunda parametreler olarak belirtilir.

Sıralama üzerinden karma ana avantajı, verimliliği olmasıdır; başarılı bir karma eklemeler, silmeler gerçekleştirir ve sabit ortalama süresi bir saat ile karşılaştırıldığında teknikleri sıralamak için kapsayıcısında öğe sayısını logaritmasını orantılı bulur. Bir hash_map bir öğe değerini ancak değil ilişkili anahtar değerini, doğrudan değiştirilebilir. Bunun yerine, eski öğelerle ilişkili anahtar değerleri silinmeli ve eklenen yeni öğelerle ilişkili yeni anahtar değerleri eklenmelidir.

Kapsayıcı türünün seçimi genelde uygulamanın gerektirdiği arama ve ekleme türüne dayalı olmalıdır. Karma ilişkilendirilebilir kapsayıcıları, arama, ekleme ve kaldırma işlemleri için en iyi duruma getirilir. Açıkça işlemlerini destekleyen üye işlevleri, bunları ortalama sabit ve kapsayıcı öğe sayısı bağımlı bir süre içinde gerçekleştirdiğiniz bir iyi tasarlanmış karma işlevi ile kullanıldığında verimlidir. İyi tasarlanmış karma işlevi karma değerleri Tekdüzen dağıtımını oluşturur ve çakışma, burada bir çakışma DISTINCT anahtar değerleri aynı karma değer eşlenir ortaya söylenir sayısını en aza indirir. En kötü durumda, en kötü olası karma işlevi ile işlemlerinin sayısı (doğrusal saati) dizisindeki öğelerin sayısı orantılıdır.

Uygulama tarafından değerleri kendi anahtarlarla ilişkilendirme koşulları sağlandığında hash_map tercih ilişkilendirilebilir kapsayıcı olmalıdır. Sıralı bir listesi modeldir yapısı bu tür için ilişkili dize değerleri, söyleyin, tanımları sağlama ile benzersiz olarak tekrarlanan anahtar sözcükler. Bunun yerine, böylece anahtarları benzersiz değil sözcükleri birden fazla doğru tanımı sahipse, bir hash_multimap tercih kapsayıcı olacaktır. Diğer taraftan, yalnızca sözcükleri listesini depolanmakta varsa, bir hash_set doğru kapsayıcı olacaktır. Birden çok tekrarı sözcükleri izin verilmekteydi, bir hash_multiset uygun bir kapsayıcı yapısı olacaktır.

Hash_map denetimleri depolanan karma çağırarak dizisi siparişleri `Traits` sınıfın nesnesi [value_compare](../standard-library/value-compare-class.md). Üye işlevini çağırarak bu saklı nesne erişilebileceği [key_comp](#key_comp). Bu tür bir işlev nesnesi sınıfın bir nesnesi olarak aynı şekilde davranır gerekir [hash_compare](../standard-library/hash-compare-class.md)< daha az anahtar\<anahtar >>. Özellikle, tüm değerler için `Key` türü `Key`, çağrı `Traits`( `Key` ) bir dağıtım türündeki değerlerin verir `size_t`.

Genelde, bu sıralamayı oluşturmak için öğelerin yalnızca küçüktür biçiminde karşılaştırılabilir olması gerekir; böylece, herhangi iki öğe belirtildiğinde, eşit oldukları (yani birinin diğerinden daha küçük olmadığı anlamında) veya birinin diğerinden küçük olduğu belirlenebilir. Bu, denk olmayan öğeler arasında bir sıralamaya neden olur. Daha teknik bir not üzerinde, karşılaştırma işlevi standart matematiksel anlamda katı bir zayıf sıralama sevk eden ikili bir koşuldur. İkili karşılaştırma f(x y) iki bağımsız değişken nesnelere sahip bir işlev nesnesidir `x` ve `y` ve dönüş değeri `true` veya `false`. İkili karşılaştırma dönüşsüz, ters ve geçişli ve burada iki nesneleri eşdeğer geçişli ise, sıralama katı bir zayıf bir hash_map üzerinde uygulanan sıralama olduğu x ve y f (x, y) ve f (y, x) false olduğunda eşdeğer olarak tanımlanır. Anahtarlar arasındaki eşitliğinin daha güçlü koşulu bu denkliğin yerini alırsa, sıralama (içindeki tüm öğelerin birbirine göre sıralanması anlamında) toplam haline gelir ve eşleşen anahtarlar birbirinden ayırt edilemez olacaktır.

Denetlenen sıradaki öğelerin gerçek sırası karma işlevi, sıralama işlevi ve kapsayıcı nesnesinde depolanan karma tablosu boyutunu bağlıdır. Denetlenen sıradaki öğelerin sırasını genel tahmin edilemez şekilde karma tablo geçerli boyutu saptanamaz. Öğelerin eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; öğelerin kaldırılması yalnızca özellikle kaldırılan öğeleri gösteren yineleyicileri geçersiz kılar.

Hash_map sınıfı tarafından sağlanan yineleyici sınıf üyesi işlevleri ancak bir çift yönlü yineleyici olan [Ekle](#insert) ve [hash_map](#hash_map) daha zayıf bir giriş yineleyici şablonu parametreleri olarak ele sürümlerde çift yönlü yineleyiciler sınıfı tarafından garanti olandan daha az olan işlevselliği gereksinimleridir. Farklı yineleyici kavramları, işlevselliklerindeki iyileştirmelere göre ilgili bir aile biçimlendirir. Her yineleyici kavramının kendi gereksinimler kümesi vardır ve bunlarla çalışan algoritmaların kendi varsayımlarını yineleyici türü tarafından sağlanan gereksinimlerle sınırlaması gerekir. Bir giriş yineleyicinin bazı nesnelere başvurusunun kaldırılacağı ve dizideki sonraki yineleyiciye artırılabileceği varsayılabilir. Bu en az işlevselliği kümesidir, ancak anlamlı yineleyiciler çeşitli hakkında iletişim kurabilmesi için yeterlidir `[First, Last)` sınıf üyesi işlevleri bağlamında.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[hash_map](#hash_map)|Oluşturan bir `hash_map` diğer bir deyişle boş veya diğer bir deyişle tüm kopyasını veya başka bir parçası `hash_map`.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[allocator_type](#allocator_type)|Temsil eden bir tür `allocator` için sınıf `hash_map` nesnesi.|
|[const_iterator](#const_iterator)|Çift yönlü yineleyici bu can sağlayan bir türü okuma bir `const` öğesinde `hash_map`.|
|[const_pointer](#const_pointer)|Bir işaretçi sağlayan bir türü bir `const` öğesinde bir `hash_map`.|
|[const_reference](#const_reference)|Bir başvuru sağlayan bir türü bir `const` öğesi saklanan bir `hash_map` okumak ve gerçekleştirmek için `const` işlemleri.|
|[const_reverse_iterator](#const_reverse_iterator)|Herhangi bir çift yönlü yineleyici bu can sağlayan bir türü okuma `const` öğesinde `hash_map`.|
|[difference_type](#difference_type)|Öğelerinin sayısı temsil etmek için kullanılan bir imzalı tamsayı türü bir `hash_map` yineleyiciler tarafından işaret öğeler arasındaki bir aralıkta.|
|[Yineleyici](#iterator)|Çift yönlü yineleyici sağlayan bir tür okuma veya herhangi bir öğe değiştirme bir `hash_map`.|
|[key_compare](#key_compare)|Göreli içinde iki öğe sırasını belirlemek için iki sıralama anahtarları karşılaştırabilirsiniz bir işlev nesnesi sağlayan bir türü `hash_map`.|
|[key_type](#key_type)|Her öğeye oluşturduğunu sıralama anahtar nesne türü açıklanır `hash_map`.|
|[mapped_type](#mapped_type)|İçinde depolanan veri türünü temsil eden bir tür bir `hash_map`.|
|[İşaretçi](#pointer)|Bir öğe için bir işaretçi sağlayan bir türü bir `hash_map`.|
|[Başvuru](#reference)|Depolanmış bir öğe için bir başvuru sağlayan bir türü bir `hash_map`.|
|[reverse_iterator](#reverse_iterator)|Çift yönlü yineleyici sağlayan bir tür okuma veya bir öğedeki bir ters değiştirme `hash_map`.|
|[size_type](#size_type)|Öğe sayısı gösterebilir bir işaretsiz tamsayı türü bir `hash_map`.|
|[value_type](#value_type)|İki öğe içindeki göreli sıralarına belirlemek için sıralama anahtarları olarak karşılaştırabilirsiniz bir işlev nesnesi sağlayan bir türü `hash_map`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[konumundaki](#at)|Bir öğedeki bulur bir `hash_map` belirtilen anahtar değerine sahip.|
|[Başlangıç](#begin)|İlk öğe adresleme yineleyici döndürür `hash_map`.|
|[cbegin](#cbegin)|İlk öğe adresleme const yineleyici döndürür `hash_map`.|
|[cend](#cend)|Son öğesi başarılı konumu adresleri const bir yineleyici döndüren bir `hash_map`.|
|[Temizle](#clear)|Tüm öğeleri sildiği bir `hash_map`.|
|[Sayısı](#count)|Öğelerin sayısını döndürür bir `hash_map` parametresi belirtilen bir anahtarı olan anahtar eşleşir.|
|[crbegin](#crbegin)|İlk öğe bir ters adresleme const yineleyici döndürür `hash_map`.|
|[crend](#crend)|Son öğesi bir ters başarılı konumu adresleri const bir yineleyici döndürür `hash_map`.|
|[emplace](#emplace)|Yerinde oluşturulan bir öğe ekler bir `hash_map`.|
|[emplace_hint](#emplace_hint)|Yerinde oluşturulan bir öğe ekler bir `hash_map`, yerleştirme İpucu ile.|
|[boş](#empty)|Testleri bir `hash_map` boş.|
|[Bitiş](#end)|Son öğesi başarılı konumu adresleri yineleyici döndüren bir `hash_map`.|
|[equal_range](#equal_range)|Bir çift yineleyiciler, sırasıyla ilk öğe döndürür bir `hash_map` ilk öğe için ve belirtilen anahtar daha büyük bir anahtarla `hash_map` eşit veya bundan büyük anahtarı bir anahtara sahip.|
|[silme](#erase)|Bir öğenin veya bir dizi öğeleri kaldırır bir `hash_map` belirtilen konumlardan|
|[Bul](#find)|Bir öğedeki konumunu adresleme yineleyici döndüren bir `hash_map` , belirtilen anahtar için eşdeğer bir anahtara sahip.|
|[get_allocator](#get_allocator)|Bir kopyasını döndürür `allocator` oluşturmak için kullanılan nesne `hash_map`.|
|[Ekle](#insert)|Bir öğenin veya bir dizi elemanlara ekler bir `hash_map`.|
|[key_comp](#key_comp)|Yineleyici ilk öğe döndürür bir `hash_map` eşit veya bundan büyük belirtilen anahtar, anahtar değerine sahip.|
|[lower_bound](#lower_bound)|Yineleyici ilk öğe döndürür bir `hash_map` eşit veya bundan büyük belirtilen anahtar, anahtar değerine sahip.|
|[max_size](#max_size)|En büyük uzunluğunu döndürür `hash_map`.|
|[rbegin](#rbegin)|İlk öğe bir ters adresleme yineleyici döndürür `hash_map`.|
|[rend](#rend)|Son öğesi bir ters başarılı konumu adresleri yineleyici döndürür `hash_map`.|
|[Boyutu](#size)|Öğelerin sayısını döndürür `hash_map`.|
|[Değiştirme](#swap)|İki öğelerini alış verişleri `hash_map`s.|
|[upper_bound](#upper_bound)|Yineleyici ilk öğe döndürür bir `hash_map` bir anahtarla değeri, belirtilen anahtar daha büyük.|
|[value_comp](#value_comp)|Sipariş öğesi değerleri için kullanılan karşılaştırma nesnesinin bir kopyasını alır bir `hash_map`.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleci&#91;&#93;](#op_at)|Bir öğeye ekler bir `hash_map` belirtilen anahtar değerine sahip.|
|[hash_map::operator=](#op_eq)|Öğeleri değiştirir bir `hash_map` başka bir kopyasına sahip `hash_map`.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<hash_map >

**Namespace:** stdext

## <a name="allocator_type"></a>  hash_map::allocator_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Allocator sınıfı hash_map nesnesinin temsil eden tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::allocator_type allocator_type;
```

### <a name="example"></a>Örnek

Örneğin bkz [get_allocator](#get_allocator) kullanarak bir örnek için `allocator_type`.

## <a name="at"></a>  hash_map::AT

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Hash_map belirtilen anahtar değerine sahip bir öğe bulur.

```cpp
Type& at(const Key& key);

const Type& at(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|`key`|Bulunacak öğe anahtarı değeri.|

### <a name="return-value"></a>Dönüş Değeri

Öğe bulundu veri değerinin bir başvuru.

### <a name="remarks"></a>Açıklamalar

Bağımsız değişken anahtar değeri bulunamadı sonra işlevi sınıfın bir nesnesi oluşturur [out_of_range sınıfı](../standard-library/out-of-range-class.md).


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

Hash_map ilk öğe adresleme yineleyici döndürür.

```cpp
const_iterator begin() const;

iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

Hash_map ya da boş bir hash_map başarılı konumu ilk öğe adresleme çift yönlü yineleyici.

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

Hash_map ilk öğe adresleme const yineleyici döndürür.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

İlk öğe adresleme const bir çift yönlü yineleyici [hash_map](../standard-library/hash-map-class.md) ya da boş bir başarılı konumu `hash_map`.

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

Bir hash_map son öğesi başarılı konumu adresleri const bir yineleyici döndürür.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Son öğesi başarılı konumu adresleri const bir çift yönlü yineleyici bir [hash_map](../standard-library/hash-map-class.md). Varsa `hash_map` boş olduğundan `hash_map::cend == hash_map::begin`.

### <a name="remarks"></a>Açıklamalar

`cend` Yineleyici sonuna ulaştı olup olmadığını sınamak için kullanılan kendi `hash_map`.

Tarafından döndürülen değer `cend` değil başvuru yapıldı.

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

Bir hash_map tüm öğeleri siler.

```cpp
void clear();
```

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

Aşağıdaki örnek hash_map::clear üye fonksiyonu kullanımını göstermektedir.

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

Çift yönlü yineleyici bu can sağlayan bir türü okuma bir **const** hash_map öğesinde.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_iterator const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_iterator` bir öğenin değerini değiştirmek için kullanılamaz.

`const_iterator` Nesnelerin öğesine hash_map noktaları tarafından tanımlanan [value_type](#value_type), yani türü `pair` *\< ***const anahtar, türü*** >*, ilk üye öğesi anahtarıdır ve ikinci öğe tarafından tutulan eşlenen datum üyesidir.

Başvuru için bir `const_iterator` `cIter` bir hash_map bir öğesine işaret eden, kullanın **->** işleci.

Öğe için anahtar değerini erişmek için `cIter` **ilk ->**, eşit olduğu (\* `cIter`) **.first**. Eşlenen veri öğesinin değeri erişmek için `cIter` **ikinci ->**, eşit olduğu (\* `cIter`) **.second**.

### <a name="example"></a>Örnek

Örneğin bkz [başlamak](#begin) kullanarak bir örnek için `const_iterator`.

## <a name="const_pointer"></a>  hash_map::const_pointer

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Bir işaretçi sağlayan bir türü bir **const** bir hash_map öğesinde.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::const_pointer const_pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_pointer` bir öğenin değerini değiştirmek için kullanılamaz.

Çoğu durumda, bir [yineleyici](#iterator) hash_map nesnesindeki öğelerin erişmek için kullanılmalıdır.

## <a name="const_reference"></a>  hash_map::const_reference

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Bir başvuru sağlayan bir türü bir **const** okumak ve gerçekleştirmek için bir hash_map depolanan öğesi **const** işlemleri.

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

Herhangi bir çift yönlü yineleyici bu can sağlayan bir türü okuma **const** hash_map öğesinde.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_reverse)iterator const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_reverse_iterator` bir öğenin değerini değiştiremez ve kullanın ters hash_map yinelemek için.

`const_reverse_iterator` Nesnelerin öğesine hash_map noktaları tarafından tanımlanan [value_type](#value_type), yani türü `pair` \< **const anahtar, türü**>, olan ilk üye olduğu anahtarı öğe ve eşlenen datum, ikinci üye olan öğe tarafından tutulan.

Başvuru için bir `const_reverse_iterator` `crIter` bir hash_map bir öğesine işaret eden, kullanın **->** işleci.

Öğe için anahtar değerini erişmek için `crIter`  ->  **ilk**, eşit olduğu (\* `crIter`) **.first**. Eşlenen veri öğesinin değeri erişmek için `crIter`  ->  **ikinci**, eşit olduğu (\* `crIter`). **İlk**.

### <a name="example"></a>Örnek

Örneğin bkz [rend](#rend) bildirme ve kullanma konusunda bir örnek için `const_reverse_iterator`.

## <a name="count"></a>  hash_map::Count

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Parametresi belirtilen bir anahtarı olan anahtarla eşleşen bir hash_map öğe sayısını döndürür.

```cpp
size_type count(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

`key` Öğeleri hash_map eşleştirilmesi için anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

hash_map olan sıralama anahtarı parametre anahtarıyla eşleşen bir öğe içeriyorsa 1; 0 hash_map bir öğesi ile eşleşen bir anahtarı içermiyor.

### <a name="remarks"></a>Açıklamalar

Üye işlevini öğe sayısını döndürür *x* aralığında

[ `lower_bound` (_ *Anahtar* ), `upper_bound` (\_ *anahtar* ))

0 veya 1 benzersiz bir ilişkilendirilebilir kapsayıcıdır hash_map durumunda olduğu.

### <a name="example"></a>Örnek

Aşağıdaki örnek hash_map::count üye fonksiyonu kullanımını göstermektedir.

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

Ters hash_map ilk öğe adresleme const yineleyici döndürür.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir const ters ilk öğe bir ters adresleme çift yönlü yineleyici [hash_map](../standard-library/hash-map-class.md) veya ne son öğesi unreversed olsaydı adresleme `hash_map`.

### <a name="remarks"></a>Açıklamalar

`crbegin` Ters hash_map ile kullanılan gibi [başlamak](#begin) ile kullanılan bir `hash_map`.

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

Ters hash_map son öğesi başarılı konumu adresleri const bir yineleyici döndürür.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir const ters son öğesi bir ters başarılı konumu adresleri çift yönlü yineleyici [hash_map](../standard-library/hash-map-class.md) (ilk öğe unreversed öncesinde konumu `hash_map`).

### <a name="remarks"></a>Açıklamalar

`crend` kullanılan bir ters ile `hash_map` gibi [hash_map::end](#end) ile kullanılan bir `hash_map`.

Dönüş değeri ile `crend`, `hash_map` nesnesi değiştirilemez.

`crend` Ters yineleyici sonuna olup ulaştı için test etmek için kullanılan kendi `hash_map`.

Tarafından döndürülen değer `crend` değil başvuru yapıldı.

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

Hash_map yineleyiciler tarafından işaret öğeler arasındaki bir aralıkta öğe sayısını temsil etmek için kullanılan bir imzalı tamsayı türü.

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

Hash_map yerinde oluşturulan bir öğe ekler.

```cpp
template <class ValTy>
pair <iterator, bool>
emplace(
    ValTy&& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|`val`|Taşıma için kullanılan değer oluşturmak içine Eklenecek öğenin [hash_map](../standard-library/hash-map-class.md) sürece `hash_map` zaten o öğenin (veya daha genel olarak, anahtar eşdeğer sıralanmış bir öğe) içerir.|

### <a name="return-value"></a>Dönüş Değeri

`emplace` Üye işlevinin döndürdüğü çifti bool bileşeni ekleme yaptıysanız true değerini döndürür ve false ise `hash_map` anahtar sıralama içinde karşılık gelen bir değer var ve bu, yineleyici bileşenini döndürür bir öğe içinde zaten yer Burada yeni bir öğe eklendi veya öğe zaten bulunduğu adres.

Bir çift yineleyici bileşeninin erişmek için `pr` bu üye işlevi tarafından döndürülen, kullanın `pr.first`ve başvurabilir için `*(pr.first)`. Erişim için `bool` çiftinin bileşen `pr` bu üye işlevi tarafından döndürülen, kullanın `pr.second`ve başvurabilir, `*(pr.second)`.

### <a name="remarks"></a>Açıklamalar

[Hash_map::value_type](#value_type) böylece bir öğe değerini bir sıralı çifti anahtar değerine eşit ilk bileşeni ve öğenin veri değerine eşit ikinci bileşeni ile bir çift öğesidir.

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

Yerleştirme İpucu ile bir hash_map içine yerinde oluşturulan bir öğe ekler.

```cpp
template <class ValTy>
iterator emplace_hint(
    const_iterator _Where,
    ValTy&& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|`val`|Taşıma için kullanılan değer oluşturmak içine Eklenecek öğenin [hash_map](../standard-library/hash-map-class.md) sürece `hash_map` zaten o öğenin (veya daha genel olarak, anahtar eşdeğer sıralanmış bir öğe) içerir.|
|`_Where`|Ekleme için doğru noktası aramaya başlamak için yer ile ilgili bir ipucu.|

### <a name="return-value"></a>Dönüş Değeri

[Hash_multimap::emplace](../standard-library/hash-multimap-class.md#emplace) üye işlevinin döndürdüğü burada yeni öğe eklenir içine konumuna işaret eden bir yineleyici `hash_map`, ya da eşdeğer sıralama ile varolan öğeyi bulunduğu.

### <a name="remarks"></a>Açıklamalar

[Hash_map::value_type](#value_type) böylece bir öğe değerini bir sıralı çifti anahtar değerine eşit ilk bileşeni ve öğenin veri değerine eşit ikinci bileşeni ile bir çift öğesidir.

Ekleme gerçekleşebilir Logaritmik zaman yerine amortized sabit zaman ekleme noktasını hemen izleyen `_Where`.

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

Bir hash_map boşsa, testleri.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** hash_map boşsa; **false** hash_map boş olmayan ise.

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

Bir hash_map son öğesi başarılı konumu adresleri yineleyici döndürür.

```cpp
const_iterator end() const;

iterator end();
```

### <a name="return-value"></a>Dönüş Değeri

Bir hash_map son öğesi başarılı konumu adresleri çift yönlü yineleyici. Hash_map boş, hash_map::end ise hash_map::begin ==.

### <a name="remarks"></a>Açıklamalar

**Son** yineleyici kendi hash_map sonuna ulaştı olup olmadığını test etmek için kullanılır.

Tarafından döndürülen değer **son** değil başvuru yapıldı.

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

Yineleyiciler çifti sırasıyla hash_map belirtilen anahtar daha büyük bir anahtarla ilk öğe ve eşit veya bundan büyük anahtarı bir anahtarla hash_map ilk öğe döndürür.

```cpp
pair <const_iterator, const_iterator> equal_range (const Key& key) const;

pair <iterator, iterator> equal_range (const Key& key);
```

### <a name="parameters"></a>Parametreler

`key` Aranmakta hash_map öğeden sıralama anahtarı ile Karşılaştırılacak bağımsız değişkeni anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

Yineleyiciler çifti ilk olacak şekilde, [lower_bound](#lower_bound) anahtarı ve ikincisi [upper_bound](#upper_bound) anahtarı.

İlk yineleyici çiftinin erişmek için `pr` üye işlevi tarafından döndürülen, kullanmak `pr`. **İlk** ve alt sınır yineleyici başvurulacak kullanmak \*( `pr`. **İlk**). İkinci yineleyici çiftinin erişmek için `pr` üye işlevi tarafından döndürülen, kullanmak `pr`. **İkinci** ve üst sınır yineleyici başvurulacak kullanmak \*( `pr`. **İkinci**).

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

Bir öğenin veya bir dizi öğeleri hash_map belirtilen konumlardan kaldırır veya belirtilen anahtar eşleşen öğeleri kaldırır.

```cpp
iterator erase(iterator _Where);

iterator erase(iterator first, iterator last);

size_type erase(const key_type& key);
```

### <a name="parameters"></a>Parametreler

`_Where` Hash_map kaldırılacak öğe konumu.

`first` İlk öğenin konumunu hash_map kaldırıldı.

`last` Yalnızca son öğenin ötesinde konumu hash_map kaldırıldı.

`key` Hash_map kaldırılacak öğe anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

İlk iki üye işlevleri için çift yönlü Yineleyici, böyle bir öğe varsa, kaldırılan öğelerin ya da bir işaretçi hash_map sonuna dışında kalan ilk öğe belirler.

Üye işlevi için üçüncü hash_map kaldırılmış olan öğe sayısını döndürür.

### <a name="remarks"></a>Açıklamalar

Üye işlevleri hiçbir zaman bir özel durum.

### <a name="example"></a>Örnek

Aşağıdaki örnek hash_map::erase üye fonksiyonu kullanımını göstermektedir.

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

Belirtilen anahtar için eşdeğer bir anahtara sahip bir hash_map bir öğedeki konumunu adresleme yineleyici döndürür.

```cpp
iterator find(const Key& key);

const_iterator find(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

`key` Aranmakta hash_map öğeden sıralama anahtarı tarafından eşleştirilmesini anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen bir anahtar veya anahtar için bir eşleşme varsa hash_map son öğesi başarılı konumu ile öğenin konumunu adresleri yineleyici.

### <a name="remarks"></a>Açıklamalar

**Bul** comparability ilişkisi küçüktür temel bir öğe olan sıralama anahtarı, bağımsız değişken anahtarı bir sıralama uygulanmasını ikili bir koşul altında eşdeğerdir hash_map adresleri yineleyici döndürür.

Varsa dönüş değerini **Bul** atanmış bir [const_iterator](#const_iterator), hash_map nesnesi değiştirilemez. Varsa dönüş değerini **Bul** atanmış bir [yineleyici](#iterator), hash_map nesne değiştirilebilir

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

Hash_map oluşturmak için kullanılan ayırıcısı nesnesinin bir kopyasını döndürür.

```cpp
Allocator get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Hash_map tarafından kullanılan ayırıcısı.

### <a name="remarks"></a>Açıklamalar

Allocators hash_map sınıfı için sınıf depolama nasıl yönettiğini belirtin. C++ Standart Kitaplığı kapsayıcı sınıfları ile sağlanan varsayılan allocators çoğu programlama ihtiyaçları için yeterli. Yazma ve kendi allocator sınıfı kullanarak ileri düzeyde C++ bir konudur.

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

Boş veya tüm kopyalama veya başka bir hash_map parçası olan bir hash_map oluşturur.

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
|`Al`|Varsayılan olarak bu hash_map nesne için kullanılacak depolama allocator sınıfı **ayırıcısı**.|
|`Comp`|Türü karşılaştırma işlevinden const `Traits` öğeler için varsayılanları hash_map içinde sıralamak için kullanılan `hash_compare`.|
|`Right`|Oluşturulan eşleme kopyasını olmasını olduğu hash_map.|
|`First`|Kopyalanacak öğe aralığını ilk öğe konumu.|
|`Last`|Kopyalanacak öğeleri aralık ötesinde ilk öğe konumu.|
|`IList`|İnitializer_list|

### <a name="remarks"></a>Açıklamalar

Tüm oluşturucular hash_map için bellek depolama yönetir ayırıcısı nesne türünü depolamak ve daha sonra çağırarak döndürülebilecek [get_allocator](#get_allocator). Allocator parametresi, sınıf bildirimleri ve diğer allocators yerine kullanılacak önişlem makroları genellikle atlanır.

Tüm oluşturucular kendi hash_map başlatır.

İşlev nesnesi türündeki tüm oluşturucular depolamak `Traits` sipariş hash_map anahtarlar oluşturmak için kullanılan ve, daha sonra döndürülüp döndürülmediğini çağırarak [key_comp](#key_comp).

Boş bir ilk hash_map ilk üç oluşturucular belirtin, ayrıca, ikinci karşılaştırma işlevi türünü belirtir ( `Comp`) öğeleri ve üçüncü sırasını açıkça oluşturmada kullanılacak ayırıcı türü ( belirtir.`Al`) kullanılacak. Anahtar sözcüğü `explicit` otomatik tür dönüştürme belirli türdeki gizler.

Hash_map bir kopyasını dördüncü Oluşturucusu belirtir `Right`.

Sonraki üç oluşturucular aralığı kopyalayın `[First, Last)` sınıfının karşılaştırma işlevini türünü belirleyen içinde explicitness artan hash_map, `Traits` ve ayırıcı.

Hash_map son Oluşturucusu taşır `Right`.

## <a name="insert"></a>  hash_map::insert

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Bir öğenin veya bir dizi öğeleri hash_map ekler.

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
|`val`|Hash_map o öğenin (veya daha genel olarak, anahtar eşdeğer sıralanmış bir öğe) zaten içermedikçe hash_map Eklenecek öğenin değeri.|
|`_Where`|Ekleme için doğru noktası aramaya başlamak için yer ile ilgili bir ipucu.|
|`first`|Hash_map kopyalanacak ilk öğe konumu.|
|`last`|Hash_map kopyalanmasını yalnızca son öğenin ötesinde konumu.|

### <a name="return-value"></a>Dönüş Değeri

İlk **Ekle** üye işlevi bool bileşeni ekleme yapılmış ve hash_map anahtar sıralama içinde karşılık gelen bir değer olan bir öğe içeriyorsa false, true değerini döndürür ve, yineleyici çifti döndürür bileşen burada yeni bir öğe eklendi veya öğe zaten bulunduğu konumun adresini döndürür.

Bir çift yineleyici bileşeninin erişmek için `pr` bu üye işlevi tarafından döndürülen, kullanmak `pr`. **İlk**ve başvurabilir için \*( `pr`. **İlk**). Erişim için `bool` çiftinin bileşen `pr` bu üye işlevi tarafından döndürülen, kullanmak `pr`. **İkinci**ve başvurabilir için \*( `pr`. **İkinci**).

İkinci **Ekle** üye işlevi, ipucu sürüm yeni öğe hash_map eklenir burada konumuna işaret eden bir yineleyici döndürür.

Son iki **Ekle** üye işlevleri davrandığını ilk iki aynı oluşturmak eklenen değer taşıma dışında.

### <a name="remarks"></a>Açıklamalar

[Value_type](../standard-library/map-class.md#value_type) böylece bir öğe değerini bir sıralı çifti anahtar değerine eşit ilk bileşeni ve öğenin veri değerine eşit ikinci bileşeni ile bir çift öğesidir.

Ekleme gerçekleşebilir Logaritmik zaman yerine INSERT ipucu sürümü amortized sabit zamanında ekleme noktasını hemen izleyen `_Where`.

Üçüncü üye işlevi bir dizi öğesi değerlerini yineleyici aralığında tarafından ele her öğesine karşılık gelen bir hash_map ekler *[First, Last)* belirtilen kümenin.

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

Okuma veya herhangi bir hash_map öğesinde değiştirmek için bir çift yönlü yineleyici sağlayan türü.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::iterator iterator;
```

### <a name="remarks"></a>Açıklamalar

**Yineleyici** nesnelerin öğesine hash_map noktaları tarafından tanımlanan [value_type](#value_type), yani türü **çifti\<const anahtar, türü >,** , ilk üye öğe ve eşlenen datum, ikinci üye olduğundan anahtarına öğe tarafından tutulur.

Başvuru için bir **yineleyici** `Iter` bir öğe olarak işaret eden bir multimap, kullanın **->** işleci.

Öğe için anahtar değerini erişmek için `Iter`  ->  **ilk**, eşit olduğu (\* `Iter`). **İlk**. Eşlenen veri öğesinin değeri erişmek için `Iter`  ->  **ikinci**, eşit olduğu (\* `Iter`). **İkinci**.

Bir tür **yineleyici** bir öğenin değerini değiştirmek için kullanılabilir.

### <a name="example"></a>Örnek

Örneğin bkz [başlamak](#begin) bildirme ve kullanma konusunda bir örnek için **yineleyici**.

## <a name="key_comp"></a>  hash_map::key_comp

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Bir hash_map sipariş anahtarlarında kullanılacak karşılaştırma nesnesinin bir kopyasını alır.

```cpp
key_compare key_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Öğeleri sıralamak için bir hash_map kullanan işlevi nesnesini döndürür.

### <a name="remarks"></a>Açıklamalar

Üye işlevini saklanan nesne tanımlar

**bool işleci**( **const anahtar &** `left` **, const anahtar &** `right`);

döndüren **true** varsa `left` önündeki ve eşit değil `right` sıralama düzeninde.

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

İşlev nesnesi sağlayan bir türü göreli eşlemesindeki iki öğe sırasını belirlemek için iki sıralama anahtarları karşılaştırabilirsiniz.

```cpp
typedef Traits key_compare;
```

### <a name="remarks"></a>Açıklamalar

`key_compare` Şablon parametresi için bir eş anlamlı olduğundan `Traits`.

Daha fazla bilgi için `Traits` bkz [hash_map sınıfı](../standard-library/hash-map-class.md) konu.

### <a name="example"></a>Örnek

Örneğin bkz [key_comp](#key_comp) bildirme ve kullanma konusunda bir örnek için `key_compare`.

## <a name="key_type"></a>  hash_map::key_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Hash_map her öğeye oluşturduğunu sıralama anahtar nesne türü açıklar.

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Açıklamalar

`key_type` Şablon parametresi için bir eş anlamlı olduğundan `Key`.

Daha fazla bilgi için `Key`, Açıklamalar bölümüne bakın [hash_map sınıfı](../standard-library/hash-map-class.md) konu.

### <a name="example"></a>Örnek

Örneğin bkz [value_type](#value_type) bildirme ve kullanma konusunda bir örnek için `key_type`.

## <a name="lower_bound"></a>  hash_map::lower_bound

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Yineleyici hash_map eşit veya belirtilen anahtar daha büyük bir anahtar değeri ile ilk öğe döndürür.

```cpp
iterator lower_bound(const Key& key);

const_iterator lower_bound(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

`key` Aranmakta hash_map öğeden sıralama anahtarı ile Karşılaştırılacak bağımsız değişkeni anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

Bir [yineleyici](#iterator) veya [const_iterator](#const_iterator) eşit veya bundan büyük bağımsız değişkeni anahtar veya konumu adresleri anahtarı ile son başarılı bir hash_map bir öğedeki konumunu adresleri anahtar için bir eşleşme varsa hash_map öğe.

Varsa dönüş değerini `lower_bound` atanmış bir `const_iterator`, hash_map nesnesi değiştirilemez. Varsa dönüş değerini `lower_bound` atanmış bir **yineleyici**, hash_map nesne değiştirilebilir.

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

Hash_map içinde depolanan veri türünü temsil eden tür.

```cpp
typedef Type mapped_type;
```

### <a name="remarks"></a>Açıklamalar

Türü `mapped_type` şablon parametresi için bir eş anlamlı olduğundan `Type`.

Daha fazla bilgi için `Type` bkz [hash_map sınıfı](../standard-library/hash-map-class.md) konu.

### <a name="example"></a>Örnek

Örneğin bkz [value_type](#value_type) bildirme ve kullanma konusunda bir örnek için `key_type`.

## <a name="max_size"></a>  hash_map::max_size

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Hash_map en büyük uzunluğunu döndürür.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Hash_map en fazla olası uzunluğu.

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

Bir öğeye ekler bir `hash_map` belirtilen anahtar değerine sahip.

```cpp
Type& operator[](const Key& key);

Type& operator[](Key&& key);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|`key`|Eklenecek öğenin anahtar değeri.|

### <a name="return-value"></a>Dönüş Değeri

Eklenen öğenin veri değerine başvuru.

### <a name="remarks"></a>Açıklamalar

Bağımsız değişken anahtar değeri bulunamazsa, değer veri türünün varsayılan değeriyle birlikte eklenir.

`operator[]` elemanlara eklemek için kullanılabilir bir `hash_map m` kullanma

`m[ key] = DataValue`;

veri değeri değeri olduğu `mapped_type` öğenin anahtar değerini `key`.

Kullanırken `operator[]` öğe eklemek için döndürülen başvuru ekleme önceden var olan bir öğe değiştirme veya yeni bir tane oluşturmak anlamına gelmez. Üye işlevleri [Bul](../standard-library/map-class.md#find) ve [Ekle](../standard-library/map-class.md#insert) belirtilen anahtara sahip bir öğe zaten bir ekleme önce mevcut olup olmadığını belirlemek için kullanılabilir.

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

Hash_map öğelerini başka bir hash_map bir kopyası ile değiştirir.

```cpp
hash_map& operator=(const hash_map& right);

hash_map& operator=(hash_map&& right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|`right`|[Hash_map sınıfı](../standard-library/hash-map-class.md) içine kopyalanmasını `hash_map`.|

### <a name="remarks"></a>Açıklamalar

Var olan öğeleri silindikten sonra bir `hash_map`, `operator=` kopyalar ya da içeriğini taşır `right` içine `hash_map`.

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

Bir hash_map bir öğe için bir işaretçi sağlayan türü.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir tür **işaretçi** bir öğenin değerini değiştirmek için kullanılabilir.

Çoğu durumda, bir [yineleyici](#iterator) hash_map nesnesindeki öğelerin erişmek için kullanılmalıdır.

## <a name="rbegin"></a>  hash_map::rbegin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Yineleyici ters hash_map ilk öğe adresleme döndürür.

```cpp
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```

### <a name="return-value"></a>Dönüş Değeri

Ters hash_map ilk öğe adresleme veya ne adresleme ters çift yönlü yineleyici unreversed hash_map son öğesi eklenmiştir.

### <a name="remarks"></a>Açıklamalar

`rbegin` Ters hash_map ile kullanılan gibi [başlamak](#begin) hash_map ile kullanılır.

Varsa dönüş değerini `rbegin` atanmış bir [const_reverse_iterator](#const_reverse_iterator), sonra da hash_map nesnesi değiştirilemez. Varsa dönüş değerini `rbegin` atandığı bir [reverse_iterator](#reverse_iterator), sonra hash_map nesne değiştirilebilir.

`rbegin` hash_map geriye doğru yinelemek için kullanılabilir.

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

Hash_map içinde depolanan bir öğe için bir başvuru sağlar türü.

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

Ters hash_map son öğesi başarılı konumu adresleri yineleyici döndürür.

```cpp
const_reverse_iterator rend() const;

reverse_iterator rend();
```

### <a name="return-value"></a>Dönüş Değeri

Ters hash_map (ilk öğe unreversed hash_map öncesinde konum) son öğesi başarılı konumu adresleri ters çift yönlü yineleyici.

### <a name="remarks"></a>Açıklamalar

`rend` Ters hash_map ile kullanılan gibi [son](#end) hash_map ile kullanılır.

Varsa dönüş değerini `rend` atanmış bir [const_reverse_iterator](#const_reverse_iterator), sonra da hash_map nesnesi değiştirilemez. Varsa dönüş değerini `rend` atandığı bir [reverse_iterator](#reverse_iterator), sonra hash_map nesne değiştirilebilir.

`rend` Ters yineleyici kendi hash_map sonuna olup ulaştı için test etmek için kullanılabilir.

Tarafından döndürülen değer `rend` değil başvuru yapıldı.

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

Okuma veya ters hash_map bir öğedeki değiştirmek için bir çift yönlü yineleyici sağlayan türü.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::reverse_iterator reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `reverse_iterator` bir öğenin değerini değiştiremez ve kullanın ters hash_map yinelemek için.

`reverse_iterator` Nesnelerin öğesine hash_map noktaları tarafından tanımlanan [value_type](#value_type), yani türü **çifti\<const anahtar, türü >**, yalnızca ilk üye öğesi anahtarıdır ve ikinci öğe tarafından tutulan eşlenen datum üyesidir.

Başvuru için bir `reverse_iterator` `rIter` bir hash_map bir öğesine işaret eden, kullanın -> işleci.

Öğe için anahtar değerini erişmek için `rIter`  ->  **ilk**, eşit olduğu (\* `rIter`). **İlk**. Eşlenen veri öğesinin değeri erişmek için `rIter`  ->  **ikinci**, eşit olduğu (\* `rIter`). **İlk**.

### <a name="example"></a>Örnek

Örneğin bkz [rbegin](#rbegin) bildirme ve kullanma konusunda bir örnek için `reverse_iterator`.

## <a name="size"></a>  hash_map::size

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

Hash_map öğe sayısını döndürür.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Hash_map geçerli uzunluğu.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

Aşağıdaki örnek hash_map::size üye fonksiyonu kullanımını göstermektedir.

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

Bir hash_map öğe sayısı gösterebilir bir işaretsiz tamsayı türü.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::size_type size_type;
```

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

Örneğin bkz [boyutu](#size) bildirme ve kullanma örneği `size_type`

## <a name="swap"></a>  hash_map::Swap

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

İki hash_maps öğelerini değiş tokuş eder.

```cpp
void swap(hash_map& right);
```

### <a name="parameters"></a>Parametreler

`right` Bağımsız değişken hash_map öğeleri ile hedef hash_map takas için sağlama.

### <a name="remarks"></a>Açıklamalar

Üye işlevini hiçbir başvuruları, işaretçileri veya öğeleri arasında alınıp verilen iki hash_maps öğelerinde tanımladığınız yineleyiciler geçersiz kılar.

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

Bir anahtar ile belirtilen anahtar büyük bir değere sahip bir hash_map ilk öğe için bir yineleyici döndürür.

```cpp
iterator upper_bound(const Key& key);

const_iterator upper_bound(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

`key` Aranmakta hash_map öğeden sıralama anahtar değeri ile Karşılaştırılacak bağımsız değişkeni anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

Bir [yineleyici](#iterator) veya [const_iterator](#const_iterator) gideren bağımsız değişkeni anahtar ya da büyük bir anahtarla konumun son öğesi başarılı bir hash_map bir öğedeki konumunu adresleri hash_map anahtar için bir eşleşme.

Dönüş değeri atanırsa bir `const_iterator`, hash_map nesnesi değiştirilemez. Dönüş değeri atanırsa bir **yineleyici**, hash_map nesne değiştirilebilir.

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

Anahtar değerlerine karşılaştırarak bir hash_map öğelerin sırasını belirleyen bir işlev nesnesi döndürür.

```cpp
value_compare value_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Öğeleri sıralamak için bir hash_map kullanan karşılaştırma işlevi nesnesini döndürür.

### <a name="remarks"></a>Açıklamalar

Bir hash_map için *m*, iki öğe *e*1 *(k*1 *, d*1 *)* ve *e*2 *(k*2 *, d*2 *)* türündeki nesneler [value_type](#value_type), burada *k*1 ve *k*2 olan kendi anahtarları türü [key_type](#key_type) ve `d`1 ve `d`2 kendi veri türü olan [mapped_type](#mapped_type), ardından *m.*  `value_comp` *() (e*1 *, e*2 *)* eşdeğerdir *m.* `key_comp` *() (k*1 *, k*2 *)*. Üye işlevini saklanan bir nesne tanımlar

**bool işleci**( **value_type &** `left`, **value_type &** `right`) **;**

döndüren **true** , anahtar değeri `left` önündeki ve anahtar değerine eşit değil `right` sıralama düzeninde.

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

Hash_map içinde depolanan nesne türünü temsil eden tür.

```cpp
typedef pair<const Key, Type> value_type;
```

### <a name="remarks"></a>Açıklamalar

`value_type` olarak bildirilen `pair`  *\< * **const**[key_type](#key_type), [mapped_type](#mapped_type)*> * değil `pair`  **\<key_type, mapped_type >** nonconstant yineleyici veya reference kullanarak bir ilişkilendirilebilir kapsayıcısı anahtarları değiştirilemez çünkü.

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
