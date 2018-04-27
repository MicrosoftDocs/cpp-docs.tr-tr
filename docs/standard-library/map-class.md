---
title: map sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- map/std::map
- map/std::map::allocator_type
- map/std::map::const_iterator
- map/std::map::const_pointer
- map/std::map::const_reference
- map/std::map::const_reverse_iterator
- map/std::map::difference_type
- map/std::map::iterator
- map/std::map::key_compare
- map/std::map::key_type
- map/std::map::mapped_type
- map/std::map::pointer
- map/std::map::reference
- map/std::map::reverse_iterator
- map/std::map::size_type
- map/std::map::value_type
- map/std::map::at
- map/std::map::begin
- map/std::map::cbegin
- map/std::map::cend
- map/std::map::clear
- map/std::map::count
- map/std::map::crbegin
- map/std::map::crend
- map/std::map::emplace
- map/std::map::emplace_hint
- map/std::map::empty
- map/std::map::end
- map/std::map::equal_range
- map/std::map::erase
- map/std::map::find
- map/std::map::get_allocator
- map/std::map::insert
- map/std::map::key_comp
- map/std::map::lower_bound
- map/std::map::max_size
- map/std::map::rbegin
- map/std::map::rend
- map/std::map::size
- map/std::map::swap
- map/std::map::upper_bound
- map/std::map::value_comp
dev_langs:
- C++
helpviewer_keywords:
- std::map [C++]
- std::map [C++], allocator_type
- std::map [C++], const_iterator
- std::map [C++], const_pointer
- std::map [C++], const_reference
- std::map [C++], const_reverse_iterator
- std::map [C++], difference_type
- std::map [C++], iterator
- std::map [C++], key_compare
- std::map [C++], key_type
- std::map [C++], mapped_type
- std::map [C++], pointer
- std::map [C++], reference
- std::map [C++], reverse_iterator
- std::map [C++], size_type
- std::map [C++], value_type
- std::map [C++], at
- std::map [C++], begin
- std::map [C++], cbegin
- std::map [C++], cend
- std::map [C++], clear
- std::map [C++], count
- std::map [C++], crbegin
- std::map [C++], crend
- std::map [C++], emplace
- std::map [C++], emplace_hint
- std::map [C++], empty
- std::map [C++], end
- std::map [C++], equal_range
- std::map [C++], erase
- std::map [C++], find
- std::map [C++], get_allocator
- std::map [C++], insert
- std::map [C++], key_comp
- std::map [C++], lower_bound
- std::map [C++], max_size
- std::map [C++], rbegin
- std::map [C++], rend
- std::map [C++], size
- std::map [C++], swap
- std::map [C++], upper_bound
- std::map [C++], value_comp
ms.assetid: 7876f4c9-ebb4-4878-af1e-09364c43af0a
caps.latest.revision: 27
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 58c4353f36ceab0171b2cd928e8fa53a079f960b
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="map-class"></a>map Sınıfı

Her bir öğenin hem veri değerine hem de sıralama anahtarına sahip olduğu bir çift olan bir koleksiyondaki verileri alma ve depolama için kullanılır. Anahtarın değeri benzersizdir ve verileri otomatik olarak sıralamak için kullanılır.

Bir eşlemdeki bir öğenin değeri doğrudan değiştirilemez. Anahtar değeri sabittir ve değiştirilemez. Bunun yerine, eski öğelerle ilişkili anahtar değerleri silinmeli ve yeni öğeler için yeni anahtar değerleri eklenmelidir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Key,
    class Type,
    class Traits = less<Key>,
    class Allocator=allocator<pair <const Key, Type>>>
class map;
```

### <a name="parameters"></a>Parametreler

`Key` Haritada depolanması için anahtar veri türü.

`Type` Haritada depolanması için öğe veri türü.

`Traits` İşlev nesnesi sağlayan türü göreli sıralarına eşlemesindeki belirlemek için sıralama anahtarları olarak iki öğenin değerleri karşılaştırabilirsiniz. Bu bağımsız değişken isteğe bağlıdır ve ikili karşılaştırma `less<Key>` varsayılan değerdir.

C ++ 14'te tür parametresi yok std::less <> koşulu belirterek heterojen arama etkinleştirebilirsiniz. Daha fazla bilgi için bkz: [ilişkilendirilebilir kapsayıcılarında heterojen arama](../standard-library/stl-containers.md#sequence_containers)

`Allocator` Haritanın ayırma ve bellek ayırmayı kaldırma hakkında ayrıntılar yalıtan saklı ayırıcısı nesneyi temsil eden tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `allocator<pair<const Key, Type> >`.

## <a name="remarks"></a>Açıklamalar

C++ Standart Kitaplığı harita sınıfıdır:

- Öğe değerlerini etkin olarak alan değişken boyutunun bir kapsayıcısı ilişkili anahtar değerlerine dayalıdır.

- Çift yönlüdür, çünkü öğelerine erişmek için çift yönlü yineleyiciler sağlar.

- Sıralıdır, çünkü öğeleri belirtilen karşılaştırma işlevine uygun olarak anahtar değerlere göre sıralanır.

- Benzersiz. alt öğelerin her biri benzersiz bir anahtar olması gerektiğinden.

- Bir çift ilişkilendirilebilir kapsayıcıdır, çünkü veri öğelerinin değerleri kendi anahtar değerlerinden farklıdır.

- Bir şablon sınıfıdır, çünkü sağladığı işlevsellik geneldir ve öğe ve anahtar türünden bağımsızdır. Öğeler ve anahtarlar için kullanılan veri türleri, karşılaştırma işlevi ve ayırıcı ile birlikte bir sınıf şablonunda parametreler olarak belirtilir.

Map sınıfı tarafından sağlanan yineleyici çift yönlü yineleyici olan ancak [Ekle](#insert) ve [harita](#map) sınıf üyesi işlevleri daha zayıf bir giriş yineleyici şablonu parametreleri olarak ele sürümleri sahip olan işlevselliği çift yönlü yineleyiciler sınıfı tarafından garanti olandan daha az gereksinimleridir. Farklı yineleyici kavramları, işlevselliklerindeki iyileştirmelerle ilgilidir. Her yineleyici kavramı kendi gereksinimler kümesine sahiptir ve onunla çalışan algoritmalar bu gereksinimler ile sınırlı olmalıdır. Bir giriş yineleyicinin bazı nesnelere başvurusu kaldırılabilir ve dizideki sonraki yineleyiciye artırılabilir.

Kapsayıcı türünün seçimini uygulamanın gerektirdiği arama ve ekleme türüne dayalı yapmanız önerilir. İlişkilendirilebilir kapsayıcılar, arama, ekleme ve kaldırma işlemleri için en iyi duruma getirilir. Bu işlemleri açıkça destekleyen üye işlevleri, işlevlerini kapsayıcıdaki öğelerin sayısının logaritmasına ortalama orantılı en kötü sürede gerçekleştirir. Öğelerin eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; öğelerin kaldırılması yalnızca özellikle kaldırılan öğeleri gösteren yineleyicileri geçersiz kılar.

Eşlemi, değerleri anahtarlarıyla ilişkilendiren koşullar uygulama tarafından karşılandığında seçimin ilişkili kapsayıcısı yapmanız önerilir. Bu tür bir yapı modeli, tanımlar sağlayan ilişkilendirmiş dize değerlerine sahip benzersiz oluşan anahtar sözcüklerin sıralı bir listesidir. Bir sözcüğün birden fazla doğru tanımı varsa, anahtar benzersiz olmadığından, çoklu eşlem kapsayıcı seçimi olacaktır. Yalnızca sözcüklerin listesi depolanmaktaysa, uygun kapsayıcı bir küme olacaktır. Sözcüklerin birden çok defa geçmelerine izin verilirse, bir çoklu küme uygun olacaktır.

Harita denetleyen bir saklı işlevi nesne türü çağırarak öğeleri siparişleri [key_compare](#key_compare). Çağıran erişilebilen bir karşılaştırma işlevi bu saklı nesnesidir [key_comp](#key_comp) yöntemi. Genelde, verilen herhangi iki öğe, birinin diğerinden daha küçük olup olmadığının veya denk olup olmadıklarının belirlenmesi için karşılaştırılır. Tüm öğeler karşılaştırıldığında, denk olmayan öğelerin sıralı bir dizisi oluşturulur.

> [!NOTE]
> Karşılaştırma işlevi standart matematiksel anlamda katı bir zayıf sıralama sevk eden ikili bir koşuldur. İkili karşılaştırma f(x,y) iki bağımsız değişken nesnelere sahip bir işlev nesnesidir x ve y ve dönüş değeri `true` veya `false`. İkili karşılaştırma dönüşsüz, ters ve geçişli ve burada iki nesneleri eşdeğer geçişli ise, sıralama katı bir zayıf bir kümesi üzerinde uygulanan sıralama olduğu x ve y ne zaman eşdeğer olarak tanımlanan her ikisi                     f (x, y) ve f(y,x) `false`. Anahtarlar arasındaki eşitliğinin daha güçlü koşulu bu denkliğin yerini alırsa, sıralama (içindeki tüm öğelerin birbirine göre sıralanması anlamında) toplam haline gelir ve eşleşen anahtarlar birbirinden ayırt edilemez olacaktır.
>
> C ++ 14'te belirterek heterojen arama etkinleştirebilirsiniz `std::less<>` veya `std::greater<>` tür parametresi yok koşulu. Daha fazla bilgi için bkz: [ilişkilendirilebilir kapsayıcılarında heterojen arama](../standard-library/stl-containers.md#sequence_containers)

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[eşleme](#map)|Belirli bir boyutta veya belirli bir değere öğelerini veya belirli bir liste oluşturur `allocator` veya başka bir harita kopyası olarak.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[allocator_type](#allocator_type)|Typedef için `allocator` harita nesnesi için sınıf.|
|[const_iterator](#const_iterator)|Typedef okuyabilir çift yönlü yineleyici için bir `const` harita öğesi.|
|[const_pointer](#const_pointer)|Typedef için bir işaretçi bir `const` bir harita öğesi.|
|[const_reference](#const_reference)|Typedef başvuru için bir `const` okumak ve gerçekleştirmek için bir harita depolanan öğesi `const` işlemleri.|
|[const_reverse_iterator](#const_reverse_iterator)|Herhangi bir çift yönlü yineleyici bu can sağlayan bir türü okuma `const` harita öğesi.|
|[difference_type](#difference_type)|Yineleyiciler tarafından gösterilen öğeler arasındaki bir aralıktaki eşlemin öğelerinin işaretli bir tamsayı typedef'i.|
|[Yineleyici](#iterator)|Eşlem içindeki herhangi bir öğeyi okuyabilen veya değiştirebilen çift yönlü yineleyiciler için typedef.|
|[key_compare](#key_compare)|Eşlem içindeki iki öğenin göreli sırasını belirlemek için iki sıralama anahtarını karşılaştıran işlev nesnesi için bir typedef.|
|[key_type](#key_type)|Eşlemin her öğesinde depolanan sıralama anahtarı için bir typedef.|
|[mapped_type](#mapped_type)|Bir eşlemin her öğesinde depolanan veriler için bir typedef.|
|[İşaretçi](#pointer)|Typedef için bir işaretçi bir `const` bir harita öğesi.|
|[Başvuru](#reference)|Bir eşlem içinde depolan bir öğeye başvuru için bir typedef.|
|[reverse_iterator](#reverse_iterator)|Ters döndürülmüş eşlem içindeki bir öğeyi okuyabilen veya değiştirebilen çift yönlü yineleyiciler için typedef.|
|[size_type](#size_type)|Bir eşlemdeki öğe sayısı için işaretsiz tamsayı typedef'i.|
|[value_type](#value_type)|Bir eşlem içinde bir öğe olarak depolanan nesne türü için bir typedef.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[konumundaki](#at)|Belirtilen anahtar değere sahip bir öğe bulur.|
|[Başlangıç](#begin)|Eşlem içindeki ilk öğeyi gösteren bir yineleyici döndürür.|
|[cbegin](#cbegin)|Eşlem içindeki ilk öğeyi gösteren sabit bir yineleyici döndürür.|
|[cend](#cend)|Bir sabit past-the-end yineleyici döndürür.|
|[Temizle](#clear)|Eşlemin tüm öğelerini siler.|
|[Sayısı](#count)|Anahtarı bir parametre içinde belirtilen anahtarla eşleşen eşlem içindeki öğelerin sayısını döndürür.|
|[crbegin](#crbegin)|Ters döndürülmüş bir eşlem içindeki ilk öğeyi gösteren sabit bir yineleyici döndürür.|
|[crend](#crend)|Ters döndürülmüş bir eşlem içindeki son öğenin ardındaki konumu gösteren sabit bir yineleyici döndürür.|
|[emplace](#emplace)|Eşlem içine yerinde oluşturulmuş bir öğe ekler.|
|[emplace_hint](#emplace_hint)|Eşlem içine, bir yerleşim ipucuyla birlikte yerinde oluşturulmuş bir öğe ekler.|
|[boş](#empty)|Döndürür `true` bir harita boşsa.|
|[Bitiş](#end)|past-the-end yineleyici döndürür.|
|[equal_range](#equal_range)|Yineleyicilerin bir çiftini döndürür. İlk öğe çifti işaret ilk yineleyici bir `map` belirtilen anahtar daha büyük bir anahtar. İlk öğe çifti işaret ikinci yineleyici `map` eşit veya bundan büyük anahtarı bir anahtara sahip.|
|[silme](#erase)|Bir eşlemdeki bir öğe veya öğe aralığını belirtilen konumdan kaldırır.|
|[Bul](#find)|Belirtilen anahtara eşit bir anahtara sahip bir eşlem içindeki bir öğenin konumunu gösteren bir yineleyici döndürür.|
|[get_allocator](#get_allocator)|Bir kopyasını döndürür `allocator` harita oluşturmak için kullanılan nesne.|
|[Ekle](#insert)|Bir eşlemdeki bir öğeyi veya öğe aralığını belirtilen konumda ekler.|
|[key_comp](#key_comp)|Bir eşlem içindeki anahtarları sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını döndürür.|
|[lower_bound](#lower_bound)|Bir yineleyiciyi belirtilen anahtardan daha büyük veya ona eşit bir anahtar değere sahip bir eşlem içindeki ilk öğeye döndürür.|
|[max_size](#max_size)|Eşlem öğesinin maksimum uzunluğunu döndürür.|
|[rbegin](#rbegin)|Ters döndürülmüş eşlem içindeki ilk öğeyi gösteren bir yineleyici döndürür.|
|[rend](#rend)|Ters döndürülmüş bir eşlem içindeki son öğenin ardındaki konumu gösteren bir yineleyici döndürür.|
|[Boyutu](#size)|Eşlem içindeki öğelerin sayısını döndürür.|
|[Değiştirme](#swap)|İki eşlemin öğelerini birbiriyle değiştirir.|
|[upper_bound](#upper_bound)|Bir yineleyiciyi belirtilen anahtardan daha büyükse bir anahtar değere sahip bir eşlem içindeki ilk öğeye döndürür.|
|[value_comp](#value_comp)|Bir eşlem içindeki öğe değerlerini sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleci&#91;&#93;](#op_at)|Belirtilen bir anahtar değere sahip bir eşleme bir öğe ekler.|
|[operator=](#op_eq)|Bir eşlemin öğelerini başka bir eşlem kopyasıyla değiştirir.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<harita >

**Namespace:** std

## <a name="allocator_type"></a>  Map::allocator_type

Allocator sınıfı eşleme nesnesinin temsil eden tür.

```cpp
typedef Allocator allocator_type;
```

### <a name="example"></a>Örnek

Örneğin bkz [get_allocator](#get_allocator) kullanan bir örnek `allocator_type`.

## <a name="at"></a>  Map::AT

Belirtilen anahtar değere sahip bir öğe bulur.

```cpp
Type& at(const Key& key);

const Type& at(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|Parametre|Açıklama|
|`key`|Bulunacak anahtar değeri.|

### <a name="return-value"></a>Dönüş Değeri

Öğe bulundu veri değerinin bir başvuru.

### <a name="remarks"></a>Açıklamalar

Bağımsız değişken anahtar değeri bulunamadı sonra işlevi sınıfın bir nesnesi oluşturur [out_of_range sınıfı](../standard-library/out-of-range-class.md).

### <a name="example"></a>Örnek

```cpp
// map_at.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

typedef std::map<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// find and show elements
    std::cout << "c1.at('a') == " << c1.at('a') << std::endl;
    std::cout << "c1.at('b') == " << c1.at('b') << std::endl;
    std::cout << "c1.at('c') == " << c1.at('c') << std::endl;

    return (0);
    }
```

## <a name="begin"></a>  Map::Begin

Harita ilk öğe adresleme yineleyici döndürür.

```cpp
const_iterator begin() const;

iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

Harita ya da boş bir harita başarılı konumu ilk öğe adresleme çift yönlü yineleyici.

### <a name="example"></a>Örnek

```cpp
// map_begin.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int> m1;

   map <int, int> :: iterator m1_Iter;
   map <int, int> :: const_iterator m1_cIter;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 0, 0 ) );
   m1.insert ( Int_Pair ( 1, 1 ) );
   m1.insert ( Int_Pair ( 2, 4 ) );

   m1_cIter = m1.begin ( );
   cout << "The first element of m1 is " << m1_cIter -> first << endl;

   m1_Iter = m1.begin ( );
   m1.erase ( m1_Iter );

   // The following 2 lines would err because the iterator is const
   // m1_cIter = m1.begin ( );
   // m1.erase ( m1_cIter );

   m1_cIter = m1.begin( );
   cout << "The first element of m1 is now " << m1_cIter -> first << endl;
}
```

```Output
The first element of m1 is 0
The first element of m1 is now 1
```

## <a name="cbegin"></a>  Map::cbegin

Döndürür bir `const` konumun yalnızca bir aralıkta son öğenin ötesinde adresleri yineleyici.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

A `const` aralık veya yalnızca boş bir aralığın ötesinde konumu ilk öğe adresleme çift yönlü yineleyici (boş bir aralığın için `cbegin() == cend()`).

### <a name="remarks"></a>Açıklamalar

Dönüş değeri ile `cbegin`, öğeleri aralığında değiştirilemez.

Bu üye işlevi yerine kullanabileceğiniz `begin()` üye işlevi dönüş değeri garanti `const_iterator`. Genellikle, ile birlikte kullanılır [otomatik](../cpp/auto-cpp.md) kesintisi anahtar sözcüğü, aşağıdaki örnekte gösterildiği gibi yazın. Örnekte, göz önünde bulundurun `Container` bir değiştirilebilir için (olmayan `const`) destekleyen herhangi bir türde kapsayıcı `begin()` ve `cbegin()`.

```cpp
auto i1 = Container.begin();
// i1 is Container<T>::iterator
auto i2 = Container.cbegin();

// i2 is Container<T>::const_iterator
```

## <a name="cend"></a>  Map::cend

Döndürür bir `const` konumun yalnızca bir aralıkta son öğenin ötesinde adresleri yineleyici.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Dönüş Değeri

A `const` yalnızca aralığın sonunu aşan işaret çift yönlü erişim yineleyici.

### <a name="remarks"></a>Açıklamalar

`cend` Yineleyici kendi aralığının sonunu geçti olup olmadığını test etmek için kullanılır.

Bu üye işlevi yerine kullanabileceğiniz `end()` üye işlevi dönüş değeri garanti `const_iterator`. Genellikle, ile birlikte kullanılır [otomatik](../cpp/auto-cpp.md) kesintisi anahtar sözcüğü, aşağıdaki örnekte gösterildiği gibi yazın. Örnekte, göz önünde bulundurun `Container` bir değiştirilebilir için (olmayan `const`) destekleyen herhangi bir türde kapsayıcı `end()` ve `cend()`.

```cpp
auto i1 = Container.end();
// i1 is Container<T>::iterator
auto i2 = Container.cend();

// i2 is Container<T>::const_iterator
```

Tarafından döndürülen değer `cend` değil başvuru yapıldı.

## <a name="clear"></a>  Map::Clear

Eşlemin tüm öğelerini siler.

```cpp
void clear();
```

### <a name="example"></a>Örnek

Aşağıdaki örnek map::clear üye fonksiyonu kullanımını göstermektedir.

```cpp
// map_clear.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main()
{
    using namespace std;
    map<int, int> m1;
    map<int, int>::size_type i;
    typedef pair<int, int> Int_Pair;

    m1.insert(Int_Pair(1, 1));
    m1.insert(Int_Pair(2, 4));

    i = m1.size();
    cout << "The size of the map is initially "
         << i << "." << endl;

    m1.clear();
    i = m1.size();
    cout << "The size of the map after clearing is "
         << i << "." << endl;
}
```

```Output
The size of the map is initially 2.
The size of the map after clearing is 0.
```

## <a name="const_iterator"></a>  Map::const_iterator

Çift yönlü yineleyici bu can sağlayan bir türü okuma bir **const** harita öğesi.

```cpp
typedef implementation-defined const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_iterator` bir öğenin değerini değiştirmek için kullanılamaz.

`const_iterator` Nesnelerin öğesine eşleme noktaları tarafından tanımlanan [value_type](#value_type), yani türü `pair` \< **constKey**, **türü**> , olan ilk üye öğesi anahtarıdır ve ikinci öğe tarafından tutulan eşlenen datum üyesidir.

Başvuru için bir `const_iterator` `cIter` bir harita öğesi işaret eden, kullanın **->** işleci.

Öğe için anahtar değerini erişmek için `cIter`  ->  **ilk**, eşit olduğu (\* `cIter`). **İlk**.

Eşlenen veri öğesinin değeri erişmek için `cIter`  ->  **ikinci**, eşit olduğu (\* `cIter`). **İkinci**.

### <a name="example"></a>Örnek

Örneğin bkz [başlamak](#begin) kullanan bir örnek `const_iterator`.

## <a name="const_pointer"></a>  Map::const_pointer

Bir işaretçi sağlayan bir türü bir **const** bir harita öğesi.

```cpp
typedef typename allocator_type::const_pointer const_pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_pointer` bir öğenin değerini değiştirmek için kullanılamaz.

Çoğu durumda, bir [yineleyici](#iterator) bir harita nesnesi öğelerinde erişmek için kullanılmalıdır.

## <a name="const_reference"></a>  Map::const_reference

Bir başvuru sağlayan bir türü bir **const** okumak ve gerçekleştirmek için bir harita depolanan öğesi **const** işlemleri.

```cpp
typedef typename allocator_type::const_reference const_reference;
```

### <a name="example"></a>Örnek

```cpp
// map_const_ref.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int> m1;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );

   // Declare and initialize a const_reference &Ref1
   // to the key of the first element
   const int &Ref1 = ( m1.begin( ) -> first );

   // The following line would cause an error as the
   // non-const_reference cannot be used to access the key
   // int &Ref1 = ( m1.begin( ) -> first );

   cout << "The key of first element in the map is "
        << Ref1 << "." << endl;

   // Declare and initialize a reference &Ref2
   // to the data value of the first element
   int &Ref2 = ( m1.begin( ) -> second );

   cout << "The data value of first element in the map is "
        << Ref2 << "." << endl;
}
```

```Output
The key of first element in the map is 1.
The data value of first element in the map is 10.
```

## <a name="const_reverse_iterator"></a>  Map::const_reverse_iterator

Herhangi bir çift yönlü yineleyici bu can sağlayan bir türü okuma **const** harita öğesi.

```cpp
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_reverse_iterator` bir öğenin değerini değiştiremez ve kullanın ters eşlemesinde yinelemek için.

`const_reverse_iterator` Nesnelerin öğesine eşleme noktaları tarafından tanımlanan [value_type](#value_type), yani türü `pair<const Key, Type>`, ilk üye öğesi anahtarıdır ve ikinci öğe tarafından tutulan eşlenen datum üyesidir.

Başvuru için bir `const_reverse_iterator crIter` bir harita öğesi işaret eden, kullanın **->** işleci.

Öğe için anahtar değerini erişmek için `crIter`  ->  **ilk**, eşit olduğu (\* `crIter`). **İlk**.

Eşlenen veri öğesinin değeri erişmek için `crIter`  ->  **ikinci**, eşit olduğu (\* `crIter`). **İlk**.

### <a name="example"></a>Örnek

Örneğin bkz [rend](#rend) bildirme ve kullanma konusunda bir örnek için `const_reverse_iterator`.

## <a name="count"></a>  Map::Count

Parametresi belirtilen bir anahtarı olan anahtarla eşleşen bir eşleminde öğe sayısını döndürür.

```cpp
size_type count(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

`key` Öğeleri eşlemesinden eşleştirilmesi için anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

Harita olan sıralama anahtarı parametre anahtarıyla eşleşen bir öğe içeriyorsa 1; 0 harita eşleşen bir anahtara bir öğe içermiyor.

### <a name="remarks"></a>Açıklamalar

Üye işlevini öğe sayısını döndürür *x* aralığında

[ `lower_bound` (_ *Anahtar* ), `upper_bound` (\_ *anahtar* ))

0 veya 1 benzersiz bir ilişkilendirilebilir kapsayıcıdır harita durumunda olduğu.

### <a name="example"></a>Örnek

Aşağıdaki örnek map::count üye fonksiyonu kullanımını göstermektedir.

```cpp
// map_count.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main()
{
    using namespace std;
    map<int, int> m1;
    map<int, int>::size_type i;
    typedef pair<int, int> Int_Pair;

    m1.insert(Int_Pair(1, 1));
    m1.insert(Int_Pair(2, 1));
    m1.insert(Int_Pair(1, 4));
    m1.insert(Int_Pair(2, 1));

    // Keys must be unique in map, so duplicates are ignored
    i = m1.count(1);
    cout << "The number of elements in m1 with a sort key of 1 is: "
         << i << "." << endl;

    i = m1.count(2);
    cout << "The number of elements in m1 with a sort key of 2 is: "
         << i << "." << endl;

    i = m1.count(3);
    cout << "The number of elements in m1 with a sort key of 3 is: "
         << i << "." << endl;
}
```

```Output
The number of elements in m1 with a sort key of 1 is: 1.
The number of elements in m1 with a sort key of 2 is: 1.
The number of elements in m1 with a sort key of 3 is: 0.
```

## <a name="crbegin"></a>  Map::crbegin

Ters harita ilk öğe adresleme const yineleyici döndürür.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir const ters ilk öğe bir ters adresleme çift yönlü yineleyici [harita](../standard-library/map-class.md) veya ne son öğesi unreversed olsaydı adresleme `map`.

### <a name="remarks"></a>Açıklamalar

`crbegin` kullanılan bir ters ile `map` gibi [başlamak](#begin) ile kullanılan bir `map`.

Dönüş değeri ile `crbegin`, `map` nesnesi değiştirilemez

`crbegin` yinelemek için kullanılabilecek bir `map` geriye doğru.

### <a name="example"></a>Örnek

```cpp
// map_crbegin.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int> m1;

   map <int, int> :: const_reverse_iterator m1_crIter;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );
   m1.insert ( Int_Pair ( 3, 30 ) );

   m1_crIter = m1.crbegin( );
   cout << "The first element of the reversed map m1 is "
        << m1_crIter -> first << "." << endl;
}
```

```Output
The first element of the reversed map m1 is 3.
```

## <a name="crend"></a>  Map::crend

Ters harita son öğesi başarılı konumu adresleri const bir yineleyici döndürür.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir const ters son öğesi bir ters başarılı konumu adresleri çift yönlü yineleyici [harita](../standard-library/map-class.md) (ilk öğe unreversed öncesinde konumu `map`).

### <a name="remarks"></a>Açıklamalar

`crend` bir ters Haritası kullanılan gibi [son](#end) ile kullanılan bir `map`.

Dönüş değeri ile `crend`, `map` nesnesi değiştirilemez.

`crend` Ters yineleyici sonuna olup ulaştı için test etmek için kullanılan kendi `map`.

Tarafından döndürülen değer `crend` değil başvuru yapıldı.

### <a name="example"></a>Örnek

```cpp
// map_crend.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int> m1;

   map <int, int> :: const_reverse_iterator m1_crIter;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );
   m1.insert ( Int_Pair ( 3, 30 ) );

   m1_crIter = m1.crend( );
   m1_crIter--;
   cout << "The last element of the reversed map m1 is "
        << m1_crIter -> first << "." << endl;
}
```

```Output
The last element of the reversed map m1 is 1.
```

## <a name="difference_type"></a>  Map::difference_type

Yineleyiciler tarafından işaret öğeler arasındaki bir aralıkta bir harita öğelerinin sayısı temsil etmek için kullanılan bir imzalı tamsayı türü.

```cpp
typedef allocator_type::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

`difference_type` Türü çıkarılmasıyla veya kapsayıcı yineleyiciler artırma döndürülür. `difference_type` Genellikle aralığında öğe sayısını temsil etmek için kullanılan *[Soyadı)* yineleyiciler arasında `first` ve `last`, gösterdiği öğesini içeren `first` ve aralığı öğeleri kadar ancak dahil değil, öğe işaret için tarafından `last`.

Ancak unutmayın `difference_type` kümesi, çıkarma yineleyiciler arasında yalnızca gibi ters çevrilebilir kapsayıcıları tarafından desteklenen çift yönlü yineleyiciler sınıfı içeren bir giriş yineleyici gereksinimlerini karşılayan tüm yineleyiciler için kullanılabilir rasgele erişim kapsayıcı vektör gibi tarafından sağlanan rasgele erişim yineleyiciler tarafından desteklenir.

### <a name="example"></a>Örnek

```cpp
// map_diff_type.cpp
// compile with: /EHsc
#include <iostream>
#include <map>
#include <algorithm>

int main( )
{
   using namespace std;
   map <int, int> m1;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 2, 20 ) );
   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 3, 20 ) );
   m1.insert ( Int_Pair ( 2, 30 ) );

   map <int, int>::iterator m1_Iter, m1_bIter, m1_eIter;
   m1_bIter = m1.begin( );
   m1_eIter = m1.end( );

   // Count the number of elements in a map
   map <int, int>::difference_type  df_count = 1;
   m1_Iter = m1.begin( );
   while ( m1_Iter != m1_eIter)
   {
      df_count++;
      m1_Iter++;
   }

   cout << "The number of elements in the map m1 is: "
        << df_count << "." << endl;
}
```

```Output
The number of elements in the map m1 is: 4.
```

## <a name="emplace"></a>  Map::emplace

(Hiçbir kopyalama veya taşıma işlemler gerçekleştirilir) yerinde bir eşlemeye oluşturulan bir öğe ekler.

```cpp
template <class... Args>
pair<iterator, bool>
emplace(
    Args&&... args);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|Parametre|Açıklama|
|`args`|Öğenin değeri eşdeğer sıralı içermedikçe eşlemeye eklenecek bir öğe oluşturmak için iletilen bağımsız değişkenler.|

### <a name="return-value"></a>Dönüş Değeri

A [çifti](../standard-library/pair-structure.md) , `bool` bileşenidir ekleme yaptıysanız true ve false harita sıralama içinde eşdeğer değerinin bir öğe içeriyorsa. Dönüş değeri çifti yineleyici bileşeninin varsa yeni eklenen öğesine işaret eden `bool` bileşenidir true veya varolan öğesine durumunda `bool` bileşen değer false.

Yineleyici bileşeninin erişmek için bir `pair` `pr`, kullanın `pr.first`; başvurabilir, kullanmak için `*pr.first`. Erişim için `bool` bileşen, kullanım `pr.second`. Bu makaledeki örnek kod bir örnek için bkz.

### <a name="remarks"></a>Açıklamalar

Yineleyiciler veya başvuruları olmadığından bu işlev tarafından geçersiz kılınır.

Bir özel durum, emplacement sırasında kapsayıcının durumu değiştirilemez.

[Value_type](#value_type) böylece bir öğe değerini bir sıralı çifti anahtar değerine eşit ilk bileşeni ve öğenin veri değerine eşit ikinci bileşeni ile bir çift öğesidir.

### <a name="example"></a>Örnek

```cpp
// map_emplace.cpp
// compile with: /EHsc
#include <map>
#include <string>
#include <iostream>

using namespace std;

template <typename M> void print(const M& m) {
    cout << m.size() << " elements: ";

    for (const auto& p : m) {
        cout << "(" << p.first << ", " << p.second << ") ";
    }

    cout << endl;
}

int main()
{
    map<int, string> m1;

    auto ret = m1.emplace(10, "ten");

    if (!ret.second){
        auto pr = *ret.first;
        cout << "Emplace failed, element with key 10 already exists."
            << endl << "  The existing element is (" << pr.first << ", " << pr.second << ")"
            << endl;
        cout << "map not modified" << endl;
    }
    else{
        cout << "map modified, now contains ";
        print(m1);
    }
    cout << endl;

    ret = m1.emplace(10, "one zero");

    if (!ret.second){
        auto pr = *ret.first;
        cout << "Emplace failed, element with key 10 already exists."
            << endl << "  The existing element is (" << pr.first << ", " << pr.second << ")"
            << endl;
    }
    else{
        cout << "map modified, now contains ";
        print(m1);
    }
    cout << endl;
}

```

## <a name="emplace_hint"></a>  Map::emplace_hint

Yerinde (hiçbir kopyalama veya taşıma işlemler gerçekleştirilir), yerleştirme İpucu ile oluşturulan bir öğe ekler.

```cpp
template <class... Args>
iterator emplace_hint(
    const_iterator where,
    Args&&... args);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|Parametre|Açıklama|
|`args`|Harita bu öğe zaten içeriyor veya zaten bir öğe olan anahtar içerdiği sürece daha genel olarak, eşdeğer sıralanır sürece eşlemeye eklenecek bir öğe oluşturmak için iletilen bağımsız değişkenler.|
|`where`|Ekleme için doğru noktası aramaya başlamak için koyun. (O noktadan hemen önceyse `where`, ekleme Logaritmik zaman yerine amortized sabit zaman meydana gelebilir.)|

### <a name="return-value"></a>Dönüş Değeri

Yineleyici yeni eklenen öğesi.

Öğe zaten var olduğundan ekleme başarısız olursa, yineleyici kendisine anahtarıyla varolan öğeyi döndürür.

### <a name="remarks"></a>Açıklamalar

Yineleyiciler veya başvuruları olmadığından bu işlev tarafından geçersiz kılınır.

Bir özel durum, emplacement sırasında kapsayıcının durumu değiştirilemez.

[Value_type](#value_type) böylece bir öğe değerini bir sıralı çifti anahtar değerine eşit ilk bileşeni ve öğenin veri değerine eşit ikinci bileşeni ile bir çift öğesidir.

### <a name="example"></a>Örnek

```cpp
// map_emplace.cpp
// compile with: /EHsc
#include <map>
#include <string>
#include <iostream>

using namespace std;

template <typename M> void print(const M& m) {
    cout << m.size() << " elements: " << endl;

    for (const auto& p : m) {
        cout << "(" << p.first <<  "," << p.second << ") ";
    }

    cout << endl;
}

int main()
{
    map<string, string> m1;

    // Emplace some test data
    m1.emplace("Anna", "Accounting");
    m1.emplace("Bob", "Accounting");
    m1.emplace("Carmine", "Engineering");

    cout << "map starting data: ";
    print(m1);
    cout << endl;

    // Emplace with hint
    // m1.end() should be the "next" element after this emplacement
    m1.emplace_hint(m1.end(), "Doug", "Engineering");

    cout << "map modified, now contains ";
    print(m1);
    cout << endl;
}

```

## <a name="empty"></a>  Map::empty

Bir harita boşsa, testleri.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** harita boşsa; **false** harita boş olmayan ise.

### <a name="example"></a>Örnek

```cpp
// map_empty.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int> m1, m2;

   typedef pair <int, int> Int_Pair;
   m1.insert ( Int_Pair ( 1, 1 ) );

   if ( m1.empty( ) )
      cout << "The map m1 is empty." << endl;
   else
      cout << "The map m1 is not empty." << endl;

   if ( m2.empty( ) )
      cout << "The map m2 is empty." << endl;
   else
      cout << "The map m2 is not empty." << endl;
}
```

```Output
The map m1 is not empty.
The map m2 is empty.
```

## <a name="end"></a>  Map::End

past-the-end yineleyici döndürür.

```cpp
const_iterator end() const;


iterator end();
```

### <a name="return-value"></a>Dönüş Değeri

Geçmiş--end yineleyici. Harita boş ise, `map::end() == map::begin()`.

### <a name="remarks"></a>Açıklamalar

**Son** yineleyici kendi harita sonunu geçti olup olmadığını test etmek için kullanılır.

Tarafından döndürülen değer **son** değil başvuru yapıldı.

Kod örneği için bkz: [map::find](#find).

## <a name="equal_range"></a>  Map::equal_range

Yineleyiciler çifti temsil eden döndürür [lower_bound](#lower_bound) anahtarının ve [upper_bound](#upper_bound) anahtarı.

```cpp
pair <const_iterator, const_iterator> equal_range (const Key& key) const;

pair <iterator, iterator> equal_range (const Key& key);
```

### <a name="parameters"></a>Parametreler

`key` Bir öğenin Aranmakta eşlemesinden sıralama anahtarı ile Karşılaştırılacak bağımsız değişkeni anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

İlk yineleyici çiftinin erişmek için `pr` üye işlevi tarafından döndürülen, kullanmak `pr`. **İlk**ve alt sınır yineleyici başvurulacak kullanmak \*( `pr`. **İlk**). İkinci yineleyici çiftinin erişmek için `pr` üye işlevi tarafından döndürülen, kullanmak `pr`. **İkinci**ve üst sınır yineleyici başvurulacak kullanmak \*( `pr`. **İkinci**).

### <a name="example"></a>Örnek

```cpp
// map_equal_range.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   typedef map <int, int, less<int> > IntMap;
   IntMap m1;
   map <int, int> :: const_iterator m1_RcIter;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );
   m1.insert ( Int_Pair ( 3, 30 ) );

   pair <IntMap::const_iterator, IntMap::const_iterator> p1, p2;
   p1 = m1.equal_range( 2 );

   cout << "The lower bound of the element with "
        << "a key of 2 in the map m1 is: "
        << p1.first -> second << "." << endl;

   cout << "The upper bound of the element with "
        << "a key of 2 in the map m1 is: "
        << p1.second -> second << "." << endl;

   // Compare the upper_bound called directly
   m1_RcIter = m1.upper_bound( 2 );

   cout << "A direct call of upper_bound( 2 ) gives "
        << m1_RcIter -> second << "," << endl
        << " matching the 2nd element of the pair"
        << " returned by equal_range( 2 )." << endl;

   p2 = m1.equal_range( 4 );

   // If no match is found for the key,
   // both elements of the pair return end( )
   if ( ( p2.first == m1.end( ) ) && ( p2.second == m1.end( ) ) )
      cout << "The map m1 doesn't have an element "
           << "with a key less than 40." << endl;
   else
      cout << "The element of map m1 with a key >= 40 is: "
           << p2.first -> first << "." << endl;
}
```

```Output
The lower bound of the element with a key of 2 in the map m1 is: 20.
The upper bound of the element with a key of 2 in the map m1 is: 30.
A direct call of upper_bound( 2 ) gives 30,
 matching the 2nd element of the pair returned by equal_range( 2 ).
The map m1 doesn't have an element with a key less than 40.
```

## <a name="erase"></a>  Map::ERASE

Belirtilen konumlardan eşlemesindeki bir öğe veya öğe aralığını kaldırır veya belirtilen anahtar eşleşen öğeleri kaldırır.

```cpp
iterator erase(
    const_iterator Where);


iterator erase(
    const_iterator First,
    const_iterator Last);


size_type erase(
    const key_type& Key);
```

### <a name="parameters"></a>Parametreler

`Where` Kaldırılacak öğe konumu.

`First` Kaldırılacak ilk öğe konumu.

`Last` Kaldırılacak yalnızca son öğenin ötesinde konumu.

`Key` Kaldırılacak öğe anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

İlk iki üye işlevleri için çift yönlü Yineleyici, kaldırılan öğelerin ya da böyle bir öğe varsa harita sonuna olan bir öğeyi dışında kalan ilk öğe belirler.

Üye işlevi için üçüncü eşlemesinden kaldırılan öğe sayısını döndürür.

### <a name="example"></a>Örnek

```cpp
// map_erase.cpp
// compile with: /EHsc
#include <map>
#include <string>
#include <iostream>
#include <iterator> // next() and prev() helper functions
#include <utility>  // make_pair()

using namespace std;

using mymap = map<int, string>;

void printmap(const mymap& m) {
    for (const auto& elem : m) {
        cout << " [" << elem.first << ", " << elem.second << "]";
    }
    cout << endl << "size() == " << m.size() << endl << endl;
}

int main()
{
    mymap m1;

    // Fill in some data to test with, one at a time
    m1.insert(make_pair(1, "A"));
    m1.insert(make_pair(2, "B"));
    m1.insert(make_pair(3, "C"));
    m1.insert(make_pair(4, "D"));
    m1.insert(make_pair(5, "E"));

    cout << "Starting data of map m1 is:" << endl;
    printmap(m1);
    // The 1st member function removes an element at a given position
    m1.erase(next(m1.begin()));
    cout << "After the 2nd element is deleted, the map m1 is:" << endl;
    printmap(m1);

    // Fill in some data to test with, one at a time, using an intializer list
    mymap m2
    {
        { 10, "Bob" },
        { 11, "Rob" },
        { 12, "Robert" },
        { 13, "Bert" },
        { 14, "Bobby" }
    };

    cout << "Starting data of map m2 is:" << endl;
    printmap(m2);
    // The 2nd member function removes elements
    // in the range [First, Last)
    m2.erase(next(m2.begin()), prev(m2.end()));
    cout << "After the middle elements are deleted, the map m2 is:" << endl;
    printmap(m2);

    mymap m3;

    // Fill in some data to test with, one at a time, using emplace
    m3.emplace(1, "red");
    m3.emplace(2, "yellow");
    m3.emplace(3, "blue");
    m3.emplace(4, "green");
    m3.emplace(5, "orange");
    m3.emplace(6, "purple");
    m3.emplace(7, "pink");

    cout << "Starting data of map m3 is:" << endl;
    printmap(m3);
    // The 3rd member function removes elements with a given Key
    mymap::size_type count = m3.erase(2);
    // The 3rd member function also returns the number of elements removed
    cout << "The number of elements removed from m3 is: " << count << "." << endl;
    cout << "After the element with a key of 2 is deleted, the map m3 is:" << endl;
    printmap(m3);
}

```

## <a name="find"></a>  Map::Find

Belirtilen anahtar için eşdeğer bir anahtara sahip bir harita öğesi konumunu başvurduğu yineleyici döndürür.

```cpp
iterator find(const Key& key);


const_iterator find(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

`key` Bir öğenin Aranmakta eşlemesinden sıralama anahtarı tarafından eşleştirilmesini anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen bir anahtarı olan bir öğe konumu veya harita son öğesi başarılı konuma başvuruyor yineleyici ( `map::end()`) anahtar için bir eşleşme varsa.

### <a name="remarks"></a>Açıklamalar

Üye işlevi bağımsız değişken anahtarı bir comparability ilişkisi küçüktür göre sıralama uygulanmasını ikili bir koşul altında olan sıralama anahtarı harita öğesi başvurduğu yineleyici eşdeğerdir döndürür.

Varsa dönüş değerini **Bul** atanmış bir **const_iterator**, harita nesnesi değiştirilemez. Varsa dönüş değerini **Bul** atanmış bir **yineleyici**, harita nesnesi değiştirilebilir

### <a name="example"></a>Örnek

```cpp
// compile with: /EHsc /W4 /MTd
#include <map>
#include <iostream>
#include <vector>
#include <string>
#include <utility>  // make_pair()

using namespace std;

template <typename A, typename B> void print_elem(const pair<A, B>& p) {
    cout << "(" << p.first << ", " << p.second << ") ";
}

template <typename T> void print_collection(const T& t) {
    cout << t.size() << " elements: ";

    for (const auto& p : t) {
        print_elem(p);
    }
    cout << endl;
}

template <typename C, class T> void findit(const C& c, T val) {
    cout << "Trying find() on value " << val << endl;
    auto result = c.find(val);
    if (result != c.end()) {
        cout << "Element found: "; print_elem(*result); cout << endl;
    } else {
        cout << "Element not found." << endl;
    }
}

int main()
{
    map<int, string> m1({ { 40, "Zr" }, { 45, "Rh" } });
    cout << "The starting map m1 is (key, value):" << endl;
    print_collection(m1);

    vector<pair<int, string>> v;
    v.push_back(make_pair(43, "Tc"));
    v.push_back(make_pair(41, "Nb"));
    v.push_back(make_pair(46, "Pd"));
    v.push_back(make_pair(42, "Mo"));
    v.push_back(make_pair(44, "Ru"));
    v.push_back(make_pair(44, "Ru")); // attempt a duplicate

    cout << "Inserting the following vector data into m1:" << endl;
    print_collection(v);

    m1.insert(v.begin(), v.end());

    cout << "The modified map m1 is (key, value):" << endl;
    print_collection(m1);
    cout << endl;
    findit(m1, 45);
    findit(m1, 6);
}

```

## <a name="get_allocator"></a>  Map::get_allocator

Harita oluşturmak için kullanılan ayırıcısı nesnesinin bir kopyasını döndürür.

```cpp
allocator_type get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Eşleme tarafından kullanılan ayırıcısı.

### <a name="remarks"></a>Açıklamalar

Allocators harita sınıfı için sınıf depolama nasıl yönettiğini belirtin. C++ Standart Kitaplığı kapsayıcı sınıfları ile sağlanan varsayılan allocators çoğu programlama ihtiyaçları için yeterli. Yazma ve kendi allocator sınıfı kullanarak ileri düzeyde C++ bir konudur.

### <a name="example"></a>Örnek

```cpp
// map_get_allocator.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int>::allocator_type m1_Alloc;
   map <int, int>::allocator_type m2_Alloc;
   map <int, double>::allocator_type m3_Alloc;
   map <int, int>::allocator_type m4_Alloc;

   // The following lines declare objects
   // that use the default allocator.
   map <int, int> m1;
   map <int, int, allocator<int> > m2;
   map <int, double, allocator<double> > m3;

   m1_Alloc = m1.get_allocator( );
   m2_Alloc = m2.get_allocator( );
   m3_Alloc = m3.get_allocator( );

   cout << "The number of integers that can be allocated\n"
        << "before free memory is exhausted: "
        << m2.max_size( ) << ".\n" << endl;

   cout << "The number of doubles that can be allocated\n"
        << "before free memory is exhausted: "
        << m3.max_size( ) <<  ".\n" << endl;

   // The following line creates a map m4
   // with the allocator of map m1.
   map <int, int> m4( less<int>( ), m1_Alloc );

   m4_Alloc = m4.get_allocator( );

   // Two allocators are interchangeable if
   // storage allocated from each can be
   // deallocated with the other
   if( m1_Alloc == m4_Alloc )
   {
      cout << "The allocators are interchangeable." << endl;
   }
   else
   {
      cout << "The allocators are not interchangeable." << endl;
   }
}
```

## <a name="insert"></a>  Map::insert

Bir öğenin veya bir dizi öğeleri bir eşlemeye ekler.

```cpp
// (1) single element
pair<iterator, bool> insert(
    const value_type& Val);


// (2) single element, perfect forwarded
template <class ValTy>
pair<iterator, bool>
insert(
    ValTy&& Val);


// (3) single element with hint
iterator insert(
    const_iterator Where,
    const value_type& Val);


// (4) single element, perfect forwarded, with hint
template <class ValTy>
iterator insert(
    const_iterator Where,
    ValTy&& Val);


// (5) range
template <class InputIterator>
void insert(
    InputIterator First,
    InputIterator Last);


// (6) initializer list
void insert(
    initializer_list<value_type>
IList);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|Parametre|Açıklama|
|`Val`|Anahtar eşdeğer sıralanmış bir öğe içermiyorsa eşlemeye Eklenecek öğenin değeri.|
|`Where`|Ekleme için doğru noktası aramaya başlamak için koyun. (O noktadan hemen önceyse `Where`, ekleme Logaritmik zaman yerine amortized sabit zaman meydana gelebilir.)|
|`ValTy`|Harita öğesi oluşturmak için kullanabileceğiniz bağımsız değişken türünü belirten bir şablon parametresi [value_type](#value_type)ve mükemmel ileten `Val` bağımsız değişken olarak.|
|`First`|Kopyalanacak ilk öğe konumu.|
|`Last`|Kopyalanacak yalnızca son öğenin ötesinde konumu.|
|`InputIterator`|Gereksinimlerini karşılayan şablon işlevi bağımsız değişken bir [giriş yineleyici](../standard-library/input-iterator-tag-struct.md) oluşturmak için kullanılan bir türü öğelerine işaret [value_type](#value_type) nesneleri.|
|`IList`|[İnitializer_list](../standard-library/initializer-list.md) öğeleri kopyalanacak.|

### <a name="return-value"></a>Dönüş Değeri

Tek öğe üye işlevleri (1) ve (2), dönüş bir [çifti](../standard-library/pair-structure.md) , `bool` bileşenidir ekleme yaptıysanız true ve false harita anahtar sıralama içinde karşılık gelen bir değer olan bir öğe içeriyorsa. Dönüş değeri çifti yineleyici bileşeninin varsa yeni eklenen öğesine işaret eden `bool` bileşenidir true veya varolan öğesine durumunda `bool` bileşen değer false.

İpucu ile tek öğe üye işlevleri (3) ve (4), yeni öğe eşlemeye eklenen burada veya eşdeğer bir anahtarı olan bir öğe zaten var olan öğe varsa konumuna işaret eden bir yineleyici döndürür.

### <a name="remarks"></a>Açıklamalar

Hiçbir yineleyiciler, işaretçileri veya başvuruları bu işlev tarafından geçersiz kılınır.

Bir özel durum, yalnızca bir öğe ekleme sırasında kapsayıcının durumu değiştirilemez. Bir özel durum, birden çok öğe ekleme sırasında kapsayıcı belirtilmeyen ancak geçerli bir durumda bırakılır.

Yineleyici bileşeninin erişmek için bir `pair` `pr` tek öğe üye işlevleri tarafından döndürülen, kullanın `pr.first`; döndürülen çifti içinde yineleyici dereference kullanmak için `*pr.first`, bir öğenin vermiş. Erişim için `bool` bileşen, kullanım `pr.second`. Bu makaledeki örnek kod bir örnek için bkz.

[Value_type](#value_type) kapsayıcısı ve harita Yakınlaştırmasını ait bir typedef, kapsayıcısıdır `map<K, V>::value_type` olan `pair<const K, V>`. Bir öğenin ilk bileşen anahtar değerine eşit olan ve ikinci bileşen öğesi veri değerine eşit olan bir sıralı çifti değerdir.

Aralık üye işlevi (5) aralığında bir yineleyici tarafından ele her öğesine karşılık gelen bir harita bir dizi öğesi değerlerini ekler `[First, Last)`; bu nedenle, `Last` takılı. Kapsayıcı üye fonksiyonu `end()` kapsayıcı son öğesi hemen sonra konuma başvuruyor — Örneğin, deyim `m.insert(v.begin(), v.end());` tüm öğeleri ekleme girişiminde `v` içine `m`. Yalnızca benzersiz değerler aralığında olan öğenin eklenir; Yinelenen değer yok sayılır. Hangi öğelerin reddedilir izlemek için tek öğe sürümlerini kullanan `insert`.

Başlatıcı listesi üye işlevi (6) kullanan bir [initializer_list](../standard-library/initializer-list.md) öğeleri eşlemeye kopyalamak.

Yerinde oluşturulan bir öğe eklemeye — diğer bir deyişle, kopyalama veya taşıma işlemi yok gerçekleştirilen — bkz [map::emplace](#emplace) ve [map::emplace_hint](#emplace_hint).

### <a name="example"></a>Örnek

```cpp
// map_insert.cpp
// compile with: /EHsc
#include <map>
#include <iostream>
#include <string>
#include <vector>
#include <utility>  // make_pair()

using namespace std;

template <typename M> void print(const M& m) {
    cout << m.size() << " elements: ";

    for (const auto& p : m) {
        cout << "(" << p.first << ", " << p.second << ") ";
    }

    cout << endl;
}

int main()
{

    // insert single values
    map<int, int> m1;
    // call insert(const value_type&) version
    m1.insert({ 1, 10 });
    // call insert(ValTy&&) version
    m1.insert(make_pair(2, 20));

    cout << "The original key and mapped values of m1 are:" << endl;
    print(m1);

    // intentionally attempt a duplicate, single element
    auto ret = m1.insert(make_pair(1, 111));
    if (!ret.second){
        auto pr = *ret.first;
        cout << "Insert failed, element with key value 1 already exists."
            << endl << "  The existing element is (" << pr.first << ", " << pr.second << ")"
            << endl;
    }
    else{
        cout << "The modified key and mapped values of m1 are:" << endl;
        print(m1);
    }
    cout << endl;

    // single element, with hint
    m1.insert(m1.end(), make_pair(3, 30));
    cout << "The modified key and mapped values of m1 are:" << endl;
    print(m1);
    cout << endl;

    // The templatized version inserting a jumbled range
    map<int, int> m2;
    vector<pair<int, int>> v;
    v.push_back(make_pair(43, 294));
    v.push_back(make_pair(41, 262));
    v.push_back(make_pair(45, 330));
    v.push_back(make_pair(42, 277));
    v.push_back(make_pair(44, 311));

    cout << "Inserting the following vector data into m2:" << endl;
    print(v);

    m2.insert(v.begin(), v.end());

    cout << "The modified key and mapped values of m2 are:" << endl;
    print(m2);
    cout << endl;

    // The templatized versions move-constructing elements
    map<int, string>  m3;
    pair<int, string> ip1(475, "blue"), ip2(510, "green");

    // single element
    m3.insert(move(ip1));
    cout << "After the first move insertion, m3 contains:" << endl;
    print(m3);

    // single element with hint
    m3.insert(m3.end(), move(ip2));
    cout << "After the second move insertion, m3 contains:" << endl;
    print(m3);
    cout << endl;

    map<int, int> m4;
    // Insert the elements from an initializer_list
    m4.insert({ { 4, 44 }, { 2, 22 }, { 3, 33 }, { 1, 11 }, { 5, 55 } });
    cout << "After initializer_list insertion, m4 contains:" << endl;
    print(m4);
    cout << endl;
}

```

## <a name="iterator"></a>  Map::iterator

Okuma veya herhangi bir harita öğesinde değiştirmek için bir çift yönlü yineleyici sağlayan türü.

```cpp
typedef implementation-defined iterator;
```

### <a name="remarks"></a>Açıklamalar

**Yineleyici** nesnelerin öğesine eşleme noktaları tarafından tanımlanan [value_type](#value_type), yani türü `pair` * \< * **constKey** , **Türü *** >*, ilk üye öğesi anahtarıdır ve ikinci öğe tarafından tutulan eşlenen datum üyesidir.

Başvuru için bir **yineleyici** `Iter` bir harita öğesi işaret eden, kullanın **->** işleci.

Öğe için anahtar değerini erişmek için `Iter`  ->  **ilk**, eşit olduğu (\* `Iter`). **İlk**. Eşlenen veri öğesinin değeri erişmek için `Iter`  ->  **ikinci**, eşit olduğu (\* `Iter`). **İkinci**.

### <a name="example"></a>Örnek

Örneğin bkz [başlamak](#begin) bildirme ve kullanma konusunda bir örnek için **yineleyici**.

## <a name="key_comp"></a>  Map::key_comp

Bir harita sipariş anahtarlarında kullanılacak karşılaştırma nesnesinin bir kopyasını alır.

```cpp
key_compare key_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Öğeleri sıralamak için bir harita kullanan işlevi nesnesini döndürür.

### <a name="remarks"></a>Açıklamalar

Üye işlevini saklanan nesne tanımlar

**bool işleci**( **constKey &**`left`, **const anahtar &**`right`);

döndüren **true** varsa `left` önündeki ve eşit değil `right` sıralama düzeninde.

### <a name="example"></a>Örnek

```cpp
// map_key_comp.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;

   map <int, int, less<int> > m1;
   map <int, int, less<int> >::key_compare kc1 = m1.key_comp( ) ;
   bool result1 = kc1( 2, 3 ) ;
   if( result1 == true )
   {
      cout << "kc1( 2,3 ) returns value of true, "
           << "where kc1 is the function object of m1."
           << endl;
   }
   else
   {
      cout << "kc1( 2,3 ) returns value of false "
           << "where kc1 is the function object of m1."
           << endl;
   }

   map <int, int, greater<int> > m2;
   map <int, int, greater<int> >::key_compare kc2 = m2.key_comp( );
   bool result2 = kc2( 2, 3 ) ;
   if( result2 == true )
   {
      cout << "kc2( 2,3 ) returns value of true, "
           << "where kc2 is the function object of m2."
           << endl;
   }
   else
   {
      cout << "kc2( 2,3 ) returns value of false, "
           << "where kc2 is the function object of m2."
           << endl;
   }
}
```

```Output
kc1( 2,3 ) returns value of true, where kc1 is the function object of m1.
kc2( 2,3 ) returns value of false, where kc2 is the function object of m2.
```

## <a name="key_compare"></a>  Map::key_compare

İşlev nesnesi sağlayan bir türü göreli eşlemesindeki iki öğe sırasını belirlemek için iki sıralama anahtarları karşılaştırabilirsiniz.

```cpp
typedef Traits key_compare;
```

### <a name="remarks"></a>Açıklamalar

`key_compare` Şablon parametresi için bir eş anlamlı olduğundan `Traits`.

Daha fazla bilgi için `Traits` bkz [map sınıfı](../standard-library/map-class.md) konu.

### <a name="example"></a>Örnek

Örneğin bkz [key_comp](#key_comp) bildirme ve kullanma konusunda bir örnek için `key_compare`.

## <a name="key_type"></a>  Map::key_type

Her bir harita öğesinde depolanan sıralama anahtarı açıklayan türü.

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Açıklamalar

`key_type` Şablon parametresi için bir eş anlamlı olduğundan `Key`.

Daha fazla bilgi için `Key`, Açıklamalar bölümüne bakın [map sınıfı](../standard-library/map-class.md) konu.

### <a name="example"></a>Örnek

Örneğin bkz [value_type](#value_type) bildirme ve kullanma konusunda bir örnek için `key_type`.

## <a name="lower_bound"></a>  Map::lower_bound

Yineleyici eşit veya belirtilen anahtar daha büyük bir anahtar değeri ile bir eşleme ilk öğe döndürür.

```cpp
iterator lower_bound(const Key& key);

const_iterator lower_bound(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

`key` Bir öğenin Aranmakta eşlemesinden sıralama anahtarı ile Karşılaştırılacak bağımsız değişkeni anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

Bir **yineleyici** veya `const_iterator` adresleri için eşit veya bundan büyük bağımsız değişkeni anahtar veya yoksa harita son öğesi başarılı konumu adreslerini bir anahtarla eşleşen harita öğesi konumu bulunamadı anahtar.

Varsa dönüş değerini `lower_bound` atanmış bir `const_iterator`, harita nesnesi değiştirilemez. Varsa dönüş değerini `lower_bound` atanmış bir **yineleyici**, harita nesnesi değiştirilebilir.

### <a name="example"></a>Örnek

```cpp
// map_lower_bound.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int> m1;
   map <int, int> :: const_iterator m1_AcIter, m1_RcIter;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );
   m1.insert ( Int_Pair ( 3, 30 ) );

   m1_RcIter = m1.lower_bound( 2 );
   cout << "The first element of map m1 with a key of 2 is: "
        << m1_RcIter -> second << "." << endl;

   // If no match is found for this key, end( ) is returned
   m1_RcIter = m1. lower_bound ( 4 );

   if ( m1_RcIter == m1.end( ) )
      cout << "The map m1 doesn't have an element "
           << "with a key of 4." << endl;
   else
      cout << "The element of map m1 with a key of 4 is: "
           << m1_RcIter -> second << "." << endl;

   // The element at a specific location in the map can be found
   // using a dereferenced iterator addressing the location
   m1_AcIter = m1.end( );
   m1_AcIter--;
   m1_RcIter = m1. lower_bound ( m1_AcIter -> first );
   cout << "The element of m1 with a key matching "
        << "that of the last element is: "
        << m1_RcIter -> second << "." << endl;
}
```

```Output
The first element of map m1 with a key of 2 is: 20.
The map m1 doesn't have an element with a key of 4.
The element of m1 with a key matching that of the last element is: 30.
```

## <a name="map"></a>  Map::Map

Boş veya tüm kopyalama veya başka bir eşleme parçası olan bir harita oluşturur.

```cpp
map();

explicit map(
    const Traits& Comp);

map(
    const Traits& Comp,
    const Allocator& Al);

map(
    const map& Right);

map(
    map&& Right);

map(
    initializer_list<value_type> IList);

map(
    initializer_list<value_type> IList,
    const Traits& Comp);

map(
    initializer_list<value_type> IList,
    const Traits& Comp,
    const Allocator& Allocator);

template <class InputIterator>
map(
 InputIterator First,
    InputIterator Last);

template <class InputIterator>
map(
 InputIterator First,
    InputIterator Last,
    const Traits& Comp);

template <class InputIterator>
map(
 InputIterator First,
    InputIterator Last,
    const Traits& Comp,
    const Allocator& Al);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|Parametre|Açıklama|
|`Al`|Varsayılan olarak bu harita nesnesi için kullanılacak depolama allocator sınıfı `Allocator`.|
|`Comp`|Türü karşılaştırma işlevinden `const Traits` varsayılan olarak eşlemesindeki öğeleri sıralamak için kullanılan `hash_compare`.|
|`Right`|Oluşturulan kümesi bir kopya olarak olduğu eşleme.|
|`First`|Kopyalanacak öğe aralığını ilk öğe konumu.|
|`Last`|Kopyalanacak öğeleri aralık ötesinde ilk öğe konumu.|
|`IList`|İçinden öğeleri kopyalanacağını initializer_list.|

### <a name="remarks"></a>Açıklamalar

Tüm oluşturucular bellek depolama harita yönetir ve, daha sonra döndürülüp döndürülmediğini çağırarak ayırıcısı nesne türünü depolamak [get_allocator](#get_allocator). Allocator parametresi, sınıf bildirimleri ve diğer allocators yerine kullanılacak önişlem makroları genellikle atlanır.

Tüm oluşturucular kendi harita başlatır.

Tüm oluşturucular işlevi türünde bir nesne bir sipariş harita anahtarlar oluşturmak için kullanılan ve, daha sonra döndürülüp döndürülmediğini çağırarak nitelikler depolamak [key_comp](#key_comp).

İlk üç oluşturucular belirtin boş ilk eşleme, ikinci karşılaştırma işlev türünü belirtme ( `Comp`) öğeleri ve üçüncü sırasını oluşturmada kullanılacak ayırıcı açıkça belirtilmesi yazın ( `Al`) olmalıdır kullanılır. Anahtar sözcük `explicit` otomatik tür dönüştürme belirli türdeki gizler.

Harita kopyasını dördüncü Oluşturucusu belirtir `Right`.

Beşinci Oluşturucusu taşıyarak harita kopyasını belirtir `Right`.

Altıncı, yedinci ve sekizinci oluşturucular üyeleri kopyalanacak bir initializer_list kullanın.

Sonraki üç oluşturucular aralığı kopyalayın `[First, Last)` sınıfının karşılaştırma işlevini türünü belirleyen içinde explicitness artan eşleme `Traits` ve ayırıcı.

### <a name="example"></a>Örnek

```cpp
// map_map.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main()
{
    using namespace std;
    typedef pair <int, int> Int_Pair;
    map <int, int>::iterator m1_Iter, m3_Iter, m4_Iter, m5_Iter, m6_Iter, m7_Iter;
    map <int, int, less<int> >::iterator m2_Iter;

    // Create an empty map m0 of key type integer
    map <int, int> m0;

    // Create an empty map m1 with the key comparison
    // function of less than, then insert 4 elements
    map <int, int, less<int> > m1;
    m1.insert(Int_Pair(1, 10));
    m1.insert(Int_Pair(2, 20));
    m1.insert(Int_Pair(3, 30));
    m1.insert(Int_Pair(4, 40));

    // Create an empty map m2 with the key comparison
    // function of geater than, then insert 2 elements
    map <int, int, less<int> > m2;
    m2.insert(Int_Pair(1, 10));
    m2.insert(Int_Pair(2, 20));

    // Create a map m3 with the
    // allocator of map m1
    map <int, int>::allocator_type m1_Alloc;
    m1_Alloc = m1.get_allocator();
    map <int, int> m3(less<int>(), m1_Alloc);
    m3.insert(Int_Pair(3, 30));

    // Create a copy, map m4, of map m1
    map <int, int> m4(m1);

    // Create a map m5 by copying the range m1[ first,  last)
    map <int, int>::const_iterator m1_bcIter, m1_ecIter;
    m1_bcIter = m1.begin();
    m1_ecIter = m1.begin();
    m1_ecIter++;
    m1_ecIter++;
    map <int, int> m5(m1_bcIter, m1_ecIter);

    // Create a map m6 by copying the range m4[ first,  last)
    // and with the allocator of map m2
    map <int, int>::allocator_type m2_Alloc;
    m2_Alloc = m2.get_allocator();
    map <int, int> m6(m4.begin(), ++m4.begin(), less<int>(), m2_Alloc);

    cout << "m1 =";
    for (auto i : m1)
        cout << i.first << " " << i.second << ", ";
    cout << endl;

    cout << "m2 =";
    for(auto i : m2)
        cout << i.first << " " << i.second << ", ";
    cout << endl;

    cout << "m3 =";
    for (auto i : m3)
        cout << i.first << " " << i.second << ", ";
    cout << endl;

    cout << "m4 =";
    for (auto i : m4)
        cout << i.first << " " << i.second << ", ";
    cout << endl;

    cout << "m5 =";
    for (auto i : m5)
        cout << i.first << " " << i.second << ", ";
    cout << endl;

    cout << "m6 =";
    for (auto i : m6)
        cout << i.first << " " << i.second << ", ";
    cout << endl;

    // Create a map m7 by moving m5
    cout << "m7 =";
    map<int, int> m7(move(m5));
    for (auto i : m7)
        cout << i.first << " " << i.second << ", ";
    cout << endl;

    // Create a map m8 by copying in an initializer_list
    map<int, int> m8{ { { 1, 1 }, { 2, 2 }, { 3, 3 }, { 4, 4 } } };
    cout << "m8: = ";
    for (auto i : m8)
        cout << i.first << " " << i.second << ", ";
    cout << endl;

    // Create a map m9 with an initializer_list and a comparator
    map<int, int> m9({ { 5, 5 }, { 6, 6 }, { 7, 7 }, { 8, 8 } }, less<int>());
    cout << "m9: = ";
    for (auto i : m9)
        cout << i.first << " " << i.second << ", ";
    cout << endl;

    // Create a map m10 with an initializer_list, a comparator, and an allocator
    map<int, int> m10({ { 9, 9 }, { 10, 10 }, { 11, 11 }, { 12, 12 } }, less<int>(), m9.get_allocator());
    cout << "m10: = ";
    for (auto i : m10)
        cout << i.first << " " << i.second << ", ";
    cout << endl;
}

```

## <a name="mapped_type"></a>  Map::mapped_type

Bir eşlemesinde depolanan verileri temsil eden tür.

```cpp
typedef Type mapped_type;
```

### <a name="remarks"></a>Açıklamalar

Türü `mapped_type` sınıfının eşanlamlısı olduğu `Type` şablon parametresi.

Daha fazla bilgi için `Type` bkz [map sınıfı](../standard-library/map-class.md) konu.

### <a name="example"></a>Örnek

Örneğin bkz [value_type](#value_type) bildirme ve kullanma konusunda bir örnek için `mapped_type`.

## <a name="max_size"></a>  Map::max_size

Eşlem öğesinin maksimum uzunluğunu döndürür.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Haritanın maksimum olası uzunluğu.

### <a name="example"></a>Örnek

```cpp
// map_max_size.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int> m1;
   map <int, int> :: size_type i;

   i = m1.max_size( );
   cout << "The maximum possible length "
        << "of the map is " << i << "."
        << endl << "(Magnitude is machine specific.)";
}
```

## <a name="op_at"></a>  Map::operator]

Belirtilen bir anahtar değere sahip bir eşleme bir öğe ekler.

```cpp
Type& operator[](const Key& key);

Type& operator[](Key&& key);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|Parametre|Açıklama|
|`key`|Eklenecek öğenin anahtar değeri.|

### <a name="return-value"></a>Dönüş Değeri

Eklenen öğenin veri değerine başvuru.

### <a name="remarks"></a>Açıklamalar

Bağımsız değişken anahtar değeri bulunamazsa, değer veri türünün varsayılan değeriyle birlikte eklenir.

`operator[]` bir eşlemeye öğe eklemek için kullanılabilir `m` kullanarak `m[ key] = DataValue;` nerede `DataValue` değeri `mapped_type` öğenin anahtar değerini `key`.

Kullanırken `operator[]` öğe eklemek için döndürülen başvuru ekleme önceden var olan bir öğe değiştirme veya yeni bir tane oluşturmak anlamına gelmez. Üye işlevleri [Bul](#find) ve [Ekle](#insert) belirtilen anahtara sahip bir öğe zaten bir ekleme önce mevcut olup olmadığını belirlemek için kullanılabilir.

### <a name="example"></a>Örnek

```cpp
// map_op_insert.cpp
// compile with: /EHsc
#include <map>
#include <iostream>
#include <string>

int main( )
{
   using namespace std;
   typedef pair <const int, int> cInt2Int;
   map <int, int> m1;
   map <int, int> :: iterator pIter;

   // Insert a data value of 10 with a key of 1
   // into a map using the operator[] member function
   m1[ 1 ] = 10;

   // Compare other ways to insert objects into a map
   m1.insert ( map <int, int> :: value_type ( 2, 20 ) );
   m1.insert ( cInt2Int ( 3, 30 ) );

   cout  << "The keys of the mapped elements are:";
   for ( pIter = m1.begin( ) ; pIter != m1.end( ) ; pIter++ )
      cout << " " << pIter -> first;
   cout << "." << endl;

   cout  << "The values of the mapped elements are:";
   for ( pIter = m1.begin( ) ; pIter != m1.end( ) ; pIter++ )
      cout << " " << pIter -> second;
   cout << "." << endl;

   // If the key already exists, operator[]
   // changes the value of the datum in the element
   m1[ 2 ] = 40;

   // operator[] will also insert the value of the data
   // type's default constructor if the value is unspecified
   m1[5];

   cout  << "The keys of the mapped elements are now:";
   for ( pIter = m1.begin( ) ; pIter != m1.end( ) ; pIter++ )
      cout << " " << pIter -> first;
   cout << "." << endl;

   cout  << "The values of the mapped elements are now:";
   for ( pIter = m1.begin( ) ; pIter != m1.end( ) ; pIter++ )
      cout << " " << pIter -> second;
   cout << "." << endl;

// insert by moving key
    map<string, int> c2;
    string str("abc");
    cout << "c2[move(str)] == " << c2[move(str)] << endl;
    cout << "c2["abc"] == " << c2["abc"] << endl;

    return (0);
}
```

```Output
The keys of the mapped elements are: 1 2 3.
The values of the mapped elements are: 10 20 30.
The keys of the mapped elements are now: 1 2 3 5.
The values of the mapped elements are now: 10 40 30 0.
c2[move(str)] == 0
c2["abc"] == 1
```

## <a name="op_eq"></a>  Map::operator =

Bir eşlemin öğelerini başka bir eşlem kopyasıyla değiştirir.

```cpp
map& operator=(const map& right);

map& operator=(map&& right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|Parametre|Açıklama|
|`right`|[Harita](../standard-library/map-class.md) içine kopyalanmasını `map`.|

### <a name="remarks"></a>Açıklamalar

Var olan öğeleri silindikten sonra bir `map`, `operator=` kopyalar ya da içeriğini taşır `right` harita içine.

### <a name="example"></a>Örnek

```cpp
// map_operator_as.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
   {
   using namespace std;
   map<int, int> v1, v2, v3;
   map<int, int>::iterator iter;

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

## <a name="pointer"></a>  Map::pointer

Bir harita öğesi için bir işaretçi sağlayan türü.

```cpp
typedef typename allocator_type::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir tür **işaretçi** bir öğenin değerini değiştirmek için kullanılabilir.

Çoğu durumda, bir [yineleyici](#iterator) bir harita nesnesi öğelerinde erişmek için kullanılmalıdır.

## <a name="rbegin"></a>  Map::rbegin

Yineleyici ters harita ilk öğe adresleme döndürür.

```cpp
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```

### <a name="return-value"></a>Dönüş Değeri

Ters harita ilk öğe adresleme veya ne adresleme ters çift yönlü yineleyici unreversed harita son öğesi eklenmiştir.

### <a name="remarks"></a>Açıklamalar

`rbegin` bir ters Haritası kullanılan gibi [başlamak](#begin) eşleme ile kullanılır.

Varsa dönüş değerini `rbegin` atanan bir `const_reverse_iterator`, sonra da harita nesnesi değiştirilemez. Varsa dönüş değerini `rbegin` atandığı bir `reverse_iterator`, sonra harita nesnesi değiştirilebilir.

`rbegin` bir eşleme geriye doğru yinelemek için kullanılabilir.

### <a name="example"></a>Örnek

```cpp
// map_rbegin.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int> m1;

   map <int, int> :: iterator m1_Iter;
   map <int, int> :: reverse_iterator m1_rIter;
   map <int, int> :: const_reverse_iterator m1_crIter;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );
   m1.insert ( Int_Pair ( 3, 30 ) );

   m1_rIter = m1.rbegin( );
   cout << "The first element of the reversed map m1 is "
        << m1_rIter -> first << "." << endl;

   // begin can be used to start an iteration
   // through a map in a forward order
   cout << "The map is: ";
   for ( m1_Iter = m1.begin( ) ; m1_Iter != m1.end( ); m1_Iter++)
      cout << m1_Iter -> first << " ";
      cout << "." << endl;

   // rbegin can be used to start an iteration
   // through a map in a reverse order
   cout << "The reversed map is: ";
   for ( m1_rIter = m1.rbegin( ) ; m1_rIter != m1.rend( ); m1_rIter++)
      cout << m1_rIter -> first << " ";
      cout << "." << endl;

   // A map element can be erased by dereferencing to its key
   m1_rIter = m1.rbegin( );
   m1.erase ( m1_rIter -> first );

   m1_rIter = m1.rbegin( );
   cout << "After the erasure, the first element "
        << "in the reversed map is "
        << m1_rIter -> first << "." << endl;
}
```

```Output
The first element of the reversed map m1 is 3.
The map is: 1 2 3 .
The reversed map is: 3 2 1 .
After the erasure, the first element in the reversed map is 2.
```

## <a name="reference"></a>  Map::Reference

Bir eşlemesinde depolanan bir öğe için bir başvuru sağlar türü.

```cpp
typedef typename allocator_type::reference reference;
```

### <a name="example"></a>Örnek

```cpp
// map_reference.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int> m1;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );

   // Declare and initialize a const_reference &Ref1
   // to the key of the first element
   const int &Ref1 = ( m1.begin( ) -> first );

   // The following line would cause an error because the
   // non-const_reference cannot be used to access the key
   // int &Ref1 = ( m1.begin( ) -> first );

   cout << "The key of first element in the map is "
        << Ref1 << "." << endl;

   // Declare and initialize a reference &Ref2
   // to the data value of the first element
   int &Ref2 = ( m1.begin( ) -> second );

   cout << "The data value of first element in the map is "
        << Ref2 << "." << endl;

   //The non-const_reference can be used to modify the
   //data value of the first element
   Ref2 = Ref2 + 5;
   cout << "The modified data value of first element is "
        << Ref2 << "." << endl;
}
```

```Output
The key of first element in the map is 1.
The data value of first element in the map is 10.
The modified data value of first element is 15.
```

## <a name="rend"></a>  Map::rend

Ters harita son öğesi başarılı konumu adresleri yineleyici döndürür.

```cpp
const_reverse_iterator rend() const;

reverse_iterator rend();
```

### <a name="return-value"></a>Dönüş Değeri

Ters eşleme (ilk öğe unreversed eşlemesinde öncesinde konum) son öğesi başarılı konumu adresleri ters çift yönlü yineleyici.

### <a name="remarks"></a>Açıklamalar

`rend` bir ters Haritası kullanılan gibi [son](#end) eşleme ile kullanılır.

Varsa dönüş değerini `rend` atanan bir `const_reverse_iterator`, sonra da harita nesnesi değiştirilemez. Varsa dönüş değerini `rend` atandığı bir `reverse_iterator`, sonra harita nesnesi değiştirilebilir.

`rend` Ters yineleyici kendi harita sonuna olup ulaştı için test etmek için kullanılabilir.

Tarafından döndürülen değer `rend` değil başvuru yapıldı.

### <a name="example"></a>Örnek

```cpp
// map_rend.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int> m1;

   map <int, int> :: iterator m1_Iter;
   map <int, int> :: reverse_iterator m1_rIter;
   map <int, int> :: const_reverse_iterator m1_crIter;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );
   m1.insert ( Int_Pair ( 3, 30 ) );

   m1_rIter = m1.rend( );
   m1_rIter--;
   cout << "The last element of the reversed map m1 is "
        << m1_rIter -> first << "." << endl;

   // begin can be used to start an iteration
   // through a map in a forward order
   cout << "The map is: ";
   for ( m1_Iter = m1.begin( ) ; m1_Iter != m1.end( ); m1_Iter++)
      cout << m1_Iter -> first << " ";
      cout << "." << endl;

   // rbegin can be used to start an iteration
   // through a map in a reverse order
   cout << "The reversed map is: ";
   for ( m1_rIter = m1.rbegin( ) ; m1_rIter != m1.rend( ); m1_rIter++)
      cout << m1_rIter -> first << " ";
      cout << "." << endl;

   // A map element can be erased by dereferencing to its key
   m1_rIter = --m1.rend( );
   m1.erase ( m1_rIter -> first );

   m1_rIter = m1.rend( );
   m1_rIter--;
   cout << "After the erasure, the last element "
        << "in the reversed map is "
        << m1_rIter -> first << "." << endl;
}
```

```Output
The last element of the reversed map m1 is 1.
The map is: 1 2 3 .
The reversed map is: 3 2 1 .
After the erasure, the last element in the reversed map is 2.
```

## <a name="reverse_iterator"></a>  Map::reverse_iterator

Okuma veya ters harita öğesi değiştirmek için bir çift yönlü yineleyici sağlayan türü.

```cpp
typedef std::reverse_iterator<iterator> reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `reverse_iterator` bir öğenin değerini değiştiremez ve kullanın ters eşlemesinde yinelemek için.

`reverse_iterator` Nesnelerin öğesine eşleme noktaları tarafından tanımlanan [value_type](#value_type), yani türü `pair` * \< * **constKey**, * *Türü *** >*, ilk üye öğesi anahtarıdır ve ikinci öğe tarafından tutulan eşlenen datum üyesidir.

Başvuru için bir `reverse_iterator` `rIter` bir harita öğesi işaret eden, kullanın **->** işleci.

Öğe için anahtar değerini erişmek için `rIter`  ->  **ilk**, eşit olduğu (\* `rIter`). **İlk**. Eşlenen veri öğesinin değeri erişmek için `rIter`  ->  **ikinci**, eşit olduğu (\* `rIter`). **İlk**.

### <a name="example"></a>Örnek

Örneğin bkz [rbegin](#rbegin) bildirme ve kullanma konusunda bir örnek için `reverse_iterator`.

## <a name="size"></a>  Map::size

Eşlem içindeki öğelerin sayısını döndürür.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Harita geçerli uzunluğu.

### <a name="example"></a>Örnek

Aşağıdaki örnek map::size üye fonksiyonu kullanımını göstermektedir.

```cpp
// map_size.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main()
{
    using namespace std;
    map<int, int> m1, m2;
    map<int, int>::size_type i;
    typedef pair<int, int> Int_Pair;

    m1.insert(Int_Pair(1, 1));
    i = m1.size();
    cout << "The map length is " << i << "." << endl;

    m1.insert(Int_Pair(2, 4));
    i = m1.size();
    cout << "The map length is now " << i << "." << endl;
}
```

```Output
The map length is 1.
The map length is now 2.
```

## <a name="size_type"></a>  Map::size_type

Bir harita öğe sayısı gösterebilir bir işaretsiz tamsayı türü.

```cpp
typedef typename allocator_type::size_type size_type;
```

### <a name="example"></a>Örnek

Örneğin bkz [boyutu](#size) bildirme ve kullanma konusunda bir örnek için `size_type`.

## <a name="swap"></a>  Map::Swap

İki eşlemin öğelerini birbiriyle değiştirir.

```cpp
void swap(
    map<Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`right` Bağımsız değişken eşleme öğeleri hedef Haritası takas için sağlama.

### <a name="remarks"></a>Açıklamalar

Üye işlevini hiçbir başvuruları, işaretçileri veya öğeleri arasında alınıp verilen iki Maps öğeleri belirleme yineleyiciler geçersiz kılar.

### <a name="example"></a>Örnek

```cpp
// map_swap.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int> m1, m2, m3;
   map <int, int>::iterator m1_Iter;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );
   m1.insert ( Int_Pair ( 3, 30 ) );
   m2.insert ( Int_Pair ( 10, 100 ) );
   m2.insert ( Int_Pair ( 20, 200 ) );
   m3.insert ( Int_Pair ( 30, 300 ) );

   cout << "The original map m1 is:";
   for ( m1_Iter = m1.begin( ); m1_Iter != m1.end( ); m1_Iter++ )
      cout << " " << m1_Iter -> second;
   cout   << "." << endl;

   // This is the member function version of swap
   //m2 is said to be the argument map; m1 the target map
   m1.swap( m2 );

   cout << "After swapping with m2, map m1 is:";
   for ( m1_Iter = m1.begin( ); m1_Iter != m1.end( ); m1_Iter++ )
      cout << " " << m1_Iter -> second;
   cout  << "." << endl;

   // This is the specialized template version of swap
   swap( m1, m3 );

   cout << "After swapping with m3, map m1 is:";
   for ( m1_Iter = m1.begin( ); m1_Iter != m1.end( ); m1_Iter++ )
      cout << " " << m1_Iter -> second;
   cout   << "." << endl;
}
```

```Output
The original map m1 is: 10 20 30.
After swapping with m2, map m1 is: 100 200.
After swapping with m3, map m1 is: 300.
```

## <a name="upper_bound"></a>  Map::upper_bound

Bir harita ilk öğe anahtarı ile belirtilen anahtar büyük bir değere sahip bir yineleyici döndürür.

```cpp
iterator upper_bound(const Key& key);

const_iterator upper_bound(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

`key` Bir öğenin Aranmakta eşlemesinden sıralama anahtar değeri ile Karşılaştırılacak bağımsız değişkeni anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

Bir **yineleyici** veya `const_iterator` adresleri anahtar için bağımsız değişken anahtarından daha büyük ya da son öğe yoksa başarılı konumu adresleri bir anahtarla eşleşen harita öğesi konumu bulunamadı.

Dönüş değeri atanırsa bir `const_iterator`, harita nesnesi değiştirilemez. Dönüş değeri atanırsa bir **yineleyici**, harita nesnesi değiştirilebilir.

### <a name="example"></a>Örnek

```cpp
// map_upper_bound.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int> m1;
   map <int, int> :: const_iterator m1_AcIter, m1_RcIter;
   typedef pair <int, int> Int_Pair;

   m1.insert ( Int_Pair ( 1, 10 ) );
   m1.insert ( Int_Pair ( 2, 20 ) );
   m1.insert ( Int_Pair ( 3, 30 ) );

   m1_RcIter = m1.upper_bound( 2 );
   cout << "The first element of map m1 with a key "
        << "greater than 2 is: "
        << m1_RcIter -> second << "." << endl;

   // If no match is found for the key, end is returned
   m1_RcIter = m1. upper_bound ( 4 );

   if ( m1_RcIter == m1.end( ) )
      cout << "The map m1 doesn't have an element "
           << "with a key greater than 4." << endl;
   else
      cout << "The element of map m1 with a key > 4 is: "
           << m1_RcIter -> second << "." << endl;

   // The element at a specific location in the map can be found
   // using a dereferenced iterator addressing the location
   m1_AcIter = m1.begin( );
   m1_RcIter = m1. upper_bound ( m1_AcIter -> first );
   cout << "The 1st element of m1 with a key greater than\n"
        << "that of the initial element of m1 is: "
        << m1_RcIter -> second << "." << endl;
}
```

```Output
The first element of map m1 with a key greater than 2 is: 30.
The map m1 doesn't have an element with a key greater than 4.
The 1st element of m1 with a key greater than
that of the initial element of m1 is: 20.
```

## <a name="value_comp"></a>  Map::value_comp

Üye işlevi anahtar değerlerine karşılaştırarak bir harita öğelerin sırasını belirleyen bir işlev nesnesi döndürür.

```cpp
value_compare value_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Öğeleri sıralamak için bir harita kullanan karşılaştırma işlevi nesnesini döndürür.

### <a name="remarks"></a>Açıklamalar

Bir harita *m*, iki öğe *e*1 ( *k*1, *d*1) ve *e*2 ( *k*2, `d`2) türündeki nesneler `value_type`, burada *k*1 ve *k*2 olan kendi anahtarları türü `key_type` ve `d`1 ve `d`2 kendi veri türü `mapped_type`, ardından *m.*`value_comp`( *e*1, *e*olan 2) eşdeğer *m.* `key_comp` *(k*1, *k*2). Üye işlevini saklanan bir nesne tanımlar

**bool işleci**( **value_type &**`left`, **value_type &**`right`);

döndüren **true** , anahtar değeri `left` önündeki ve anahtar değerine eşit değil `right` sıralama düzeninde.

### <a name="example"></a>Örnek

```cpp
// map_value_comp.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;

   map <int, int, less<int> > m1;
   map <int, int, less<int> >::value_compare vc1 = m1.value_comp( );
   pair< map<int,int>::iterator, bool > pr1, pr2;

   pr1= m1.insert ( map <int, int> :: value_type ( 1, 10 ) );
   pr2= m1.insert ( map <int, int> :: value_type ( 2, 5 ) );

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

   if(vc1( *pr2.first, *pr1.first ) == true )
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

```Output
The element ( 1,10 ) precedes the element ( 2,5 ).
The element ( 2,5 ) does not precede the element ( 1,10 ).
```

## <a name="value_type"></a>  Map::value_type

Bir eşleme öğesi olarak depolanan nesnenin türü.

```cpp
typedef pair<const Key, Type> value_type;
```

### <a name="example"></a>Örnek

```cpp
// map_value_type.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   typedef pair <const int, int> cInt2Int;
   map <int, int> m1;
   map <int, int> :: key_type key1;
   map <int, int> :: mapped_type mapped1;
   map <int, int> :: value_type value1;
   map <int, int> :: iterator pIter;

   // value_type can be used to pass the correct type
   // explicitly to avoid implicit type conversion
   m1.insert ( map <int, int> :: value_type ( 1, 10 ) );

   // Compare other ways to insert objects into a map
   m1.insert ( cInt2Int ( 2, 20 ) );
   m1[ 3 ] = 30;

   // Initializing key1 and mapped1
   key1 = ( m1.begin( ) -> first );
   mapped1 = ( m1.begin( ) -> second );

   cout << "The key of first element in the map is "
        << key1 << "." << endl;

   cout << "The data value of first element in the map is "
        << mapped1 << "." << endl;

   // The following line would cause an error because
   // the value_type is not assignable
   // value1 = cInt2Int ( 4, 40 );

   cout  << "The keys of the mapped elements are:";
   for ( pIter = m1.begin( ) ; pIter != m1.end( ) ; pIter++ )
      cout << " " << pIter -> first;
   cout << "." << endl;

   cout  << "The values of the mapped elements are:";
   for ( pIter = m1.begin( ) ; pIter != m1.end( ) ; pIter++ )
      cout << " " << pIter -> second;
   cout << "." << endl;
}
```

## <a name="see-also"></a>Ayrıca bkz.

[\<Harita > üyeleri](http://msdn.microsoft.com/en-us/7e8f0bc2-6034-40f6-9d14-76d4cef86308)<br/>
[Kapsayıcılar](../cpp/containers-modern-cpp.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
