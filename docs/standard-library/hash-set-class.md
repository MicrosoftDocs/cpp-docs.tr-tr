---
title: hash_set sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8e2a6dc618795872e3587c1872c4fb020872861f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="hashset-class"></a>hash_set Sınıfı

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Kapsayıcı sınıfı hash_set C++ Standart Kitaplığı, bir uzantısıdır ve hızlı alınması bulunan öğeleri değerlerini benzersiz ve anahtar değerleri olarak hizmet veren bir koleksiyon verileri ve depolama için kullanılır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Key,
    class Traits=hash_compare<Key, less<Key>>,
    class Allocator=allocator<Key>>
class hash_set
```

### <a name="parameters"></a>Parametreler

`Key` Hash_set depolanması için öğe veri türü.

`Traits` İki işlev nesneleri içeren, bir sınıfın karşılaştırma türü olan tekli bir koşul eşlemesi anahtar değerleri işaretsiz öğelere, bir karma işlevi ve göreli sıralarına belirlemek için sıralama anahtarları olarak iki öğenin değerleri karşılaştırmak için bir ikili karşılaştırma Tamsayı türünde **size_t**. Bu bağımsız değişken isteğe bağlıdır ve `hash_compare` *< anahtar* **daha az ***\<anahtar >>* varsayılan değerdir.

`Allocator` Hash_set's ayırma ve bellek ayırmayı kaldırma hakkında ayrıntılar yalıtan saklı ayırıcısı nesneyi temsil eden tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer **ayırıcısı ***\<anahtar >.*

## <a name="remarks"></a>Açıklamalar

Hash_set aşağıdaki gibidir:

- İlişkili bir anahtar değerine dayalı öğe değerlerinin verimli alınmasını destekleyen bir değişken boyutu kapsayıcı olan ilişkilendirilebilir bir kapsayıcı. Dahası, basit bir ilişkilendirilebilir kapsayıcıdır, çünkü öğelerinin değerleri kendi anahtar değerleridir.

- Çift yönlüdür, çünkü öğelerine erişmek için çift yönlü bir yineleyici sağlar.

- Karma, öğelerin anahtar değerleri için uygulanan bir karma işlevine değere göre demet içine öğeleri gruplandırıldığından.

- Benzersizdir, çünkü öğelerinin her birinde benzersiz bir anahtar olması gerekir. Hash_set da basit bir ilişkilendirilebilir kapsayıcı olduğundan, öğeleri de benzersizdir.

- İşlevselliği sağladığından genel ve bu nedenle bağımsız öğeleri veya anahtarları olarak bulunan verileri, belirli türde bir şablon sınıfı. Öğeler ve anahtarlar için kullanılacak veri türleri, karşılaştırma işlevi ve ayırıcı ile birlikte bir sınıf şablonunda parametreler olarak belirtilir.

Sıralama üzerinden karma ana avantajı, verimliliği olmasıdır; başarılı bir karma eklemeler, silmeler gerçekleştirir ve sabit ortalama süresi bir saat ile karşılaştırıldığında teknikleri sıralamak için kapsayıcısında öğe sayısını logaritmasını orantılı bulur. Bir kümedeki bir öğenin değeri doğrudan değiştirilemez. Bunun yerine, eski değerleri silmeniz ve yeni değerlere sahip öğeler eklemeniz gerekir.

Kapsayıcı türünün seçimi genelde uygulamanın gerektirdiği arama ve ekleme türüne dayalı olmalıdır. Karma ilişkilendirilebilir kapsayıcıları, arama, ekleme ve kaldırma işlemleri için en iyi duruma getirilir. Açıkça işlemlerini destekleyen üye işlevleri, bunları ortalama sabit ve kapsayıcı öğe sayısı bağımlı bir süre içinde gerçekleştirdiğiniz bir iyi tasarlanmış karma işlevi ile kullanıldığında verimlidir. İyi tasarlanmış karma işlevi karma değerleri Tekdüzen dağıtımını oluşturur ve çakışma, burada bir çakışma DISTINCT anahtar değerleri aynı karma değer eşlenir ortaya söylenir sayısını en aza indirir. En kötü durumda, en kötü olası karma işlevi ile işlemlerinin sayısı (doğrusal saati) dizisindeki öğelerin sayısı orantılıdır.

Uygulama tarafından değerleri kendi anahtarlarla ilişkilendirme koşulları sağlandığında hash_set tercih ilişkilendirilebilir kapsayıcı olmalıdır. Bir hash_set öğelerinin benzersiz ve kendi sıralama anahtarı olarak hizmet. Bu tür bir yapı modeli, sözcüklerin yalnızca bir defa geçebildiği sıralı bir sözcükler listesindedir. Birden çok tekrarı sözcükleri izin verilmekteydi, bir hash_multiset uygun bir kapsayıcı yapısı olacaktır. Değerler benzersiz anahtar sözcükleri listesine eklenmesi gerekiyorsa, bir hash_map bu verileri içerecek şekilde uygun bir yapı olacaktır. Bunun yerine anahtarları benzersiz değilse, bir hash_multimap tercih kapsayıcı olacaktır.

Hash_set denetimleri depolanan karma çağırarak dizisi siparişleri **nitelikler** nesne türü [value_compare](#value_compare). Üye işlevini çağırarak bu saklı nesne erişilebileceği [key_comp](#key_comp). Bu tür bir işlev nesnesi sınıfın bir nesnesi olarak aynı şekilde davranır gerekir *hash_compare < daha az anahtar\<anahtar >>.* Özellikle, tüm değerler için `key` türü anahtarı, çağrı ayırdedici nitelik ( `key` ) bir dağıtım türü size_t değerlerinin verir.

Genelde, bu sıralamayı oluşturmak için öğelerin yalnızca küçüktür biçiminde karşılaştırılabilir olması gerekir; böylece, herhangi iki öğe belirtildiğinde, eşit oldukları (yani birinin diğerinden daha küçük olmadığı anlamında) veya birinin diğerinden küçük olduğu belirlenebilir. Bu, bir eşdeğer olmayan öğeler arasında sıralamada sonuçlanır. Daha teknik bir not üzerinde, karşılaştırma işlevi standart matematiksel anlamda katı bir zayıf sıralama sevk eden ikili bir koşuldur. İkili karşılaştırma *f*( *x*, *y*) iki bağımsız değişken nesnelere sahip bir işlev nesnesidir x ve y ve true veya false dönüş değeri. İkili karşılaştırma dönüşsüz, ters ve geçişli ve burada iki nesneleri eşdeğer geçişli ise, sıralama katı bir zayıf olduğu bir hash_set üzerinde uygulanan sıralama *x* ve *y* tanımlanır ne zaman eşdeğer olarak her ikisi de *f*( *x*, *y*) ve *f*( *y*, *x*) false ' tur. Anahtarlar arasındaki eşitliğinin daha güçlü koşulu bu denkliğin yerini alırsa, sıralama (içindeki tüm öğelerin birbirine göre sıralanması anlamında) toplam haline gelir ve eşleşen anahtarlar birbirinden ayırt edilemez olacaktır.

Denetlenen sıradaki öğelerin gerçek sırası karma işlevi, sıralama işlevi ve kapsayıcı nesnesinde depolanan karma tablosu boyutunu bağlıdır. Denetlenen sıradaki öğelerin sırasını genel tahmin edilemez şekilde karma tablo geçerli boyutu saptanamaz. Öğelerin eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; öğelerin kaldırılması yalnızca özellikle kaldırılan öğeleri gösteren yineleyicileri geçersiz kılar.

Hash_set sınıfı tarafından sağlanan yineleyici sınıf üyesi işlevleri ancak bir çift yönlü yineleyici olan [Ekle](#insert) ve [hash_set](#hash_set) daha zayıf bir giriş yineleyici şablonu parametreleri olarak ele sürümlerde çift yönlü yineleyiciler sınıfı tarafından garanti olandan daha az olan işlevselliği gereksinimleridir. Farklı yineleyici kavramları, işlevselliklerindeki iyileştirmelere göre ilgili bir aile biçimlendirir. Her yineleyici kavramının kendi gereksinimler kümesi vardır ve bunlarla çalışan algoritmaların kendi varsayımlarını yineleyici türü tarafından sağlanan gereksinimlerle sınırlaması gerekir. Bir giriş yineleyicinin bazı nesnelere başvurusunun kaldırılacağı ve dizideki sonraki yineleyiciye artırılabileceği varsayılabilir. Bu en az işlevselliği kümesidir, ancak anlamlı yineleyiciler çeşitli hakkında iletişim kurabilmesi için yeterlidir [ `first`, `last`) sınıf üyesi işlevleri bağlamında.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[hash_set](#hash_set)|Oluşturan bir `hash_set` diğer bir deyişle boş veya diğer bir deyişle tüm kopyasını veya başka bir parçası `hash_set`.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[allocator_type](#allocator_type)|Temsil eden bir tür `allocator` için sınıf `hash_set` nesnesi.|
|[const_iterator](#const_iterator)|Çift yönlü yineleyici bu can sağlayan bir türü okuma bir `const` öğesinde `hash_set`.|
|[const_pointer](#const_pointer)|Bir işaretçi sağlayan bir türü bir `const` öğesinde bir `hash_set`.|
|[const_reference](#const_reference)|Bir başvuru sağlayan bir türü bir `const` öğesi saklanan bir `hash_set` okumak ve gerçekleştirmek için `const` işlemleri.|
|[const_reverse_iterator](#const_reverse_iterator)|Herhangi bir çift yönlü yineleyici bu can sağlayan bir türü okuma `const` öğesinde `hash_set`.|
|[difference_type](#difference_type)|Öğelerinin sayısı temsil etmek için kullanılan bir imzalı tamsayı türü bir `hash_set` yineleyiciler tarafından işaret öğeler arasındaki bir aralıkta.|
|[Yineleyici](#iterator)|Çift yönlü yineleyici sağlayan bir tür okuma veya herhangi bir öğe değiştirme bir `hash_set`.|
|[key_compare](#key_compare)|Göreli içinde iki öğe sırasını belirlemek için iki sıralama anahtarları karşılaştırabilirsiniz bir işlev nesnesi sağlayan bir türü `hash_set`.|
|[key_type](#key_type)|Bir öğe depolanan bir nesne açıklayan türü bir `hash_set` kapasitesi sıralama anahtarı olarak içinde.|
|[İşaretçi](#pointer)|Bir öğe için bir işaretçi sağlayan bir türü bir `hash_set`.|
|[Başvuru](#reference)|Depolanmış bir öğe için bir başvuru sağlayan bir türü bir `hash_set`.|
|[reverse_iterator](#reverse_iterator)|Çift yönlü yineleyici sağlayan bir tür okuma veya bir öğedeki bir ters değiştirme `hash_set`.|
|[size_type](#size_type)|Öğe sayısı gösterebilir bir işaretsiz tamsayı türü bir `hash_set`.|
|[value_compare](#value_compare)|İki işlev nesneleri, iki öğenin değerleri karşılaştırabilirsiniz sınıfı karşılaştırma, ikili koşulu sağlayan bir türü bir `hash_set` göreli belirlemek için sırası ve bir birli öğeleri karmaları koşul.|
|[value_type](#value_type)|Bir öğe depolanan bir nesne açıklayan türü bir `hash_set` kapasitesi değeri olarak içinde.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[Başlangıç](#begin)|İlk öğe adresleri yineleyici döndürür `hash_set`.|
|[cbegin](#cbegin)|İlk öğe adresleme const yineleyici döndürür `hash_set`.|
|[cend](#cend)|Son öğesi başarılı konumu adresleri const bir yineleyici döndüren bir `hash_set`.|
|[Temizle](#clear)|Tüm öğeleri sildiği bir `hash_set`.|
|[Sayısı](#count)|Öğelerin sayısını döndürür bir `hash_set` parametresi belirtilen bir anahtarı olan anahtar eşleşir.|
|[crbegin](#crbegin)|İlk öğe bir ters adresleme const yineleyici döndürür `hash_set`.|
|[crend](#crend)|Son öğesi bir ters başarılı konumu adresleri const bir yineleyici döndürür `hash_set`.|
|[emplace](#emplace)|Yerinde oluşturulan bir öğe ekler bir `hash_set`.|
|[emplace_hint](#emplace_hint)|Yerinde oluşturulan bir öğe ekler bir `hash_set`, yerleştirme İpucu ile.|
|[boş](#empty)|Testleri bir `hash_set` boş.|
|[Bitiş](#end)|Son öğesi başarılı konumu adresleri yineleyici döndüren bir `hash_set`.|
|[equal_range](#equal_range)|Yineleyiciler çifti sırasıyla ilk öğe döndürür bir `hash_set` ilk öğe için ve belirtilen anahtar daha büyük bir anahtarla `hash_set` eşit veya bundan büyük anahtarı bir anahtara sahip.|
|[silme](#erase)|Bir öğenin veya bir dizi öğeleri kaldırır bir `hash_set` belirtilen konumları veya belirtilen anahtar eşleşen kaldırır öğeleri.|
|[Bul](#find)|Bir öğedeki konumunu adresleme yineleyici döndüren bir `hash_set` , belirtilen anahtar için eşdeğer bir anahtara sahip.|
|[get_allocator](#get_allocator)|Bir kopyasını döndürür `allocator` oluşturmak için kullanılan nesne `hash_set`.|
|[Ekle](#insert)|Bir öğenin veya bir dizi elemanlara ekler bir `hash_set`.|
|[key_comp](#key_comp)|Sipariş anahtarlarında kullanılacak karşılaştırma nesnesinin bir kopyasını alır bir `hash_set`.|
|[lower_bound](#lower_bound)|Yineleyici ilk öğe döndürür bir `hash_set` eşit veya bundan büyük belirtilen anahtar bir anahtara sahip.|
|[max_size](#max_size)|En büyük uzunluğunu döndürür `hash_set`.|
|[rbegin](#rbegin)|İlk öğe bir ters adresleme yineleyici döndürür `hash_set`.|
|[rend](#rend)|Son öğesi bir ters başarılı konumu adresleri yineleyici döndürür `hash_set`.|
|[Boyutu](#size)|Öğelerin sayısını döndürür `hash_set`.|
|[Değiştirme](#swap)|İki öğelerini alış verişleri `hash_set`s.|
|[upper_bound](#upper_bound)|Yineleyici ilk öğe döndürür bir `hash_set` eşit veya belirtilen anahtar daha büyük bir anahtar ile.|
|[value_comp](#value_comp)|Karma ve öğe anahtarı değerleri sıralamak için kullanılan karma nitelikler nesnesinin bir kopyasını alır bir `hash_set`.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[hash_set::operator=](#op_eq)|Öğeleri değiştirir bir `hash_set` başka bir kopyasına sahip `hash_set`.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<hash_set >

**Namespace:** stdext

## <a name="allocator_type"></a>  hash_set::allocator_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Allocator sınıfı hash_set nesnesinin temsil eden tür.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::allocator_type allocator_type;
```

### <a name="remarks"></a>Açıklamalar

**allocator_type** şablon parametresi için bir eş anlamlı olduğundan `Allocator`.

Daha fazla bilgi için `Allocator`, Açıklamalar bölümüne bakın [hash_set sınıfı](../standard-library/hash-set-class.md) konu.

### <a name="example"></a>Örnek

Örneğin bkz [get_allocator](#get_allocator) kullanan bir örnek `allocator_type`.

## <a name="begin"></a>  hash_set::Begin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Hash_set ilk öğe adresleri yineleyici döndürür.

```cpp
const_iterator begin() const;

iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

Hash_set ya da boş bir hash_set başarılı konumu ilk öğe adresleme çift yönlü yineleyici.

### <a name="remarks"></a>Açıklamalar

Varsa dönüş değerini **başlamak** atanmış bir `const_iterator`, hash_set nesnesindeki öğelerin değiştirilemez. Varsa dönüş değerini **başlamak** atanmış bir **yineleyici**, hash_set nesnesindeki öğelerin değiştirilebilir.

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

Hash_set ilk öğe adresleri const bir yineleyici döndürür.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

İlk öğe adresleme const bir çift yönlü yineleyici [hash_set](../standard-library/hash-set-class.md) ya da boş bir başarılı konumu `hash_set`.

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

Bir hash_set son öğesi başarılı konumu adresleri const bir yineleyici döndürür.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Son öğesi başarılı konumu adresleri const bir çift yönlü yineleyici bir [hash_set](../standard-library/hash-set-class.md). Varsa `hash_set` boş olduğundan `hash_set::cend == hash_set::begin`.

### <a name="remarks"></a>Açıklamalar

`cend` Yineleyici sonuna ulaştı olup olmadığını sınamak için kullanılan kendi `hash_set`. Tarafından döndürülen değer `cend` değil başvuru yapıldı.

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

Bir hash_set tüm öğeleri siler.

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

Çift yönlü yineleyici bu can sağlayan bir türü okuma bir **const** hash_set öğesinde.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_iterator const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_iterator` bir öğenin değerini değiştirmek için kullanılamaz.

### <a name="example"></a>Örnek

Örneğin bkz [başlamak](#begin) kullanan bir örnek `const_iterator`.

## <a name="const_pointer"></a>  hash_set::const_pointer

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Bir işaretçi sağlayan bir türü bir **const** bir hash_set öğesinde.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_pointer const_pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_pointer` bir öğenin değerini değiştirmek için kullanılamaz.

Çoğu durumda, bir [const_iterator](#const_iterator) öğeleri erişmek üzere kullanılması bir **const** hash_set nesnesi.

## <a name="const_reference"></a>  hash_set::const_reference

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Bir başvuru sağlayan bir türü bir **const** okumak ve gerçekleştirmek için bir hash_set depolanan öğesi **const** işlemleri.

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

Herhangi bir çift yönlü yineleyici bu can sağlayan bir türü okuma **const** hash_set öğesinde.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_reverse_iterator const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_reverse_iterator` bir öğenin değerini değiştiremez ve kullanın ters hash_set yinelemek için.

### <a name="example"></a>Örnek

Örneğin bkz [rend](#rend) bildirme ve kullanma örneği `const_reverse_iterator`

## <a name="count"></a>  hash_set::Count

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Parametresi belirtilen bir anahtarı olan anahtarla eşleşen bir hash_set öğe sayısını döndürür.

```cpp
size_type count(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

`key` Hash_set eşleştirilmesini öğeleri anahtarı.

### <a name="return-value"></a>Dönüş Değeri

hash_set olan sıralama anahtarı parametre anahtarıyla eşleşen bir öğe içeriyorsa 1.

hash_set eşleşen bir anahtara bir öğe içermiyorsa 0.

### <a name="remarks"></a>Açıklamalar

Üye işlevi aşağıdaki aralıkta öğe sayısını döndürür:

[ **lower_bound** (_ *anahtar* ), **upper_bound** (\_ *anahtar* )).

### <a name="example"></a>Örnek

Aşağıdaki örnek hash_set::count üye fonksiyonu kullanımını göstermektedir.

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

Ters hash_set ilk öğe adresleme const yineleyici döndürür.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir const ters ilk öğe bir ters adresleme çift yönlü yineleyici [hash_set](../standard-library/hash-set-class.md) veya ne son öğesi unreversed olsaydı adresleme `hash_set`.

### <a name="remarks"></a>Açıklamalar

`crbegin` Ters hash_set ile kullanılan gibi [hash_set::begin](#begin) hash_set ile kullanılır.

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

Ters hash_set son öğesi başarılı konumu adresleri const bir yineleyici döndürür.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir const ters son öğesi bir ters başarılı konumu adresleri çift yönlü yineleyici [hash_set](../standard-library/hash-set-class.md) (ilk öğe unreversed öncesinde konumu `hash_set`).

### <a name="remarks"></a>Açıklamalar

`crend` kullanılan bir ters ile `hash_set` gibi [hash_set::end](#end) ile kullanılan bir `hash_set`.

Dönüş değeri ile `crend`, `hash_set` nesnesi değiştirilemez.

`crend` Ters yineleyici sonuna olup ulaştı için test etmek için kullanılan kendi `hash_set`.

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

Hash_set yineleyiciler tarafından işaret öğeler arasındaki bir aralıkta öğe sayısını temsil etmek için kullanılan bir imzalı tamsayı türü.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

`difference_type` Türü çıkarılmasıyla veya kapsayıcı yineleyiciler artırma döndürülür. `difference_type` Genellikle aralığında öğe sayısını temsil etmek için kullanılan [ `first`, `last`) yineleyiciler arasında `first` ve `last`, gösterdiği öğesi içerir `first` ve öğeleri kadar aralığı , ancak değil de dahil olmak üzere, gösterdiği öğesi `last`.

Ancak unutmayın `difference_type` kümesi, çıkarma yineleyiciler arasında yalnızca gibi ters çevrilebilir kapsayıcıları tarafından desteklenen çift yönlü yineleyiciler sınıfı içeren bir giriş yineleyici gereksinimlerini karşılayan tüm yineleyiciler için kullanılabilir rasgele erişim yineleyiciler vektör veya deque gibi bir rastgele erişim kapsayıcı tarafından sağlanan tarafından desteklenir.

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

Hash_set yerinde oluşturulan bir öğe ekler.

```cpp
template <class ValTy>
pair <iterator, bool>
emplace(
    ValTy&& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|`val`|İçine Eklenecek öğenin değerini [hash_set](../standard-library/hash-set-class.md) sürece `hash_set` o öğeye veya daha genel anahtar eşdeğer sıralanmış bir öğe zaten içeriyor.|

### <a name="return-value"></a>Dönüş Değeri

`emplace` Üye işlevi bir çift döndürür, `bool` bileşenini döndürür `true` ekleme yapma ise ve `false` varsa `hash_set` anahtar sıralama ve özelliği eşdeğer bir değeri olan bir öğeyi zaten içeriyor Yineleyici bileşen burada yeni bir öğe eklendi veya öğe zaten bulunduğu konumun adresini döndürür.

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

Hash_set yerinde oluşturulan bir öğe ekler.

```cpp
template <class ValTy>
iterator emplace(
    const_iterator _Where,
    ValTy&& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|`val`|İçine Eklenecek öğenin değerini [hash_set](../standard-library/hash-set-class.md) sürece `hash_set` o öğeye veya daha genel anahtar eşdeğer sıralanmış bir öğe zaten içeriyor.|
|`_Where`|Ekleme için doğru noktası aramaya başlamak için koyun. (Ekleme gerçekleşebilir Logaritmik zaman yerine amortized sabit zaman ekleme noktasını hemen izleyen `_Where`.)|

### <a name="return-value"></a>Dönüş Değeri

[Hash_set::emplace](#emplace) üye işlevinin döndürdüğü burada yeni öğe eklenir içine konumuna işaret eden bir yineleyici `hash_set`, ya da eşdeğer sıralama ile varolan öğeyi bulunduğu.

### <a name="remarks"></a>Açıklamalar

Ekleme gerçekleşebilir Logaritmik zaman yerine amortized sabit zaman ekleme noktasını hemen izleyen `_Where`.

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

Bir hash_set boşsa, testleri.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** hash_set boşsa; **false** hash_set boş olmayan ise.

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

Bir hash_set son öğesi başarılı konumu adresleri yineleyici döndürür.

```cpp
const_iterator end() const;

iterator end();
```

### <a name="return-value"></a>Dönüş Değeri

Bir hash_set son öğesi başarılı konumu adresleri çift yönlü yineleyici. Hash_set boş, hash_set::end ise hash_set::begin ==.

### <a name="remarks"></a>Açıklamalar

**Son** yineleyici kendi hash_set sonuna ulaştı olup olmadığını test etmek için kullanılır. Tarafından döndürülen değer **son** değil başvuru yapıldı.

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

Yineleyiciler çifti sırasıyla belirtilen anahtar ve ilk öğe için anahtar daha büyük bir anahtar kümesi karma eşittir bir anahtar kümesi karma ilk öğe döndürür.

```cpp
pair <const_iterator, const_iterator> equal_range (const Key& key) const;

pair <iterator, iterator> equal_range (const Key& key);
```

### <a name="parameters"></a>Parametreler

`key` Aranmakta hash_set öğeden sıralama anahtarı ile Karşılaştırılacak bağımsız değişkeni anahtarı.

### <a name="return-value"></a>Dönüş Değeri

İlk olduğu yineleyiciler çifti [lower_bound](../standard-library/set-class.md#lower_bound) anahtarı ve ikincisi [upper_bound](../standard-library/set-class.md#upper_bound) anahtarı.

Üye işlevi tarafından döndürülen çifti kolaylaştırılmıştır ilk yineleyici erişmek için `pr`. **İlk**ve alt sınır yineleyici başvurulacak kullanmak \*( `pr`. **İlk**). İkinci yineleyici çiftinin erişmek için `pr` üye işlevi tarafından döndürülen, kullanmak `pr`. **İkinci**ve üst sınır yineleyici başvurulacak kullanmak \*( `pr`. **İkinci**).

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

Bir öğenin veya bir dizi öğeleri hash_set belirtilen konumlardan kaldırır veya belirtilen anahtar eşleşen öğeleri kaldırır.

```cpp
iterator erase(iterator _Where);

iterator erase(iterator first, iterator last);

size_type erase(const key_type& key);
```

### <a name="parameters"></a>Parametreler

`_Where` Hash_set kaldırılacak öğe konumu.

`first` İlk öğenin konumunu hash_set kaldırıldı.

`last` Yalnızca son öğenin ötesinde konumu hash_set kaldırıldı.

`key` Hash_set kaldırılacak öğe anahtarı.

### <a name="return-value"></a>Dönüş Değeri

İlk iki üye işlevleri için çift yönlü Yineleyici, böyle bir öğe varsa, kaldırılan öğelerin ya da bir işaretçi hash_set sonuna dışında kalan ilk öğe belirler. Üçüncü üye fonksiyonu için hash_set kaldırılan öğelerin sayısı.

### <a name="remarks"></a>Açıklamalar

Üye işlevleri hiçbir zaman bir özel durum.

### <a name="example"></a>Örnek

Aşağıdaki örnek hash_set::erase üye fonksiyonu kullanımını göstermektedir.

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

Belirtilen anahtar için eşdeğer bir anahtara sahip bir hash_set bir öğedeki konumunu adresleme yineleyici döndürür.

```cpp
iterator find(const Key& key);

const_iterator find(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

`key` Aranmakta hash_set öğeden sıralama anahtarı tarafından eşleştirilmesini bağımsız değişkeni anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Bir **yineleyici** veya `const_iterator` belirtilen anahtar için eşdeğer bir öğe konumu adresleri veya anahtar için bir eşleşme varsa hash_set son öğesi başarılı konumu giderir.

### <a name="remarks"></a>Açıklamalar

Üye işlevi olan sıralama anahtarı hash_set bir öğedeki adresleri yineleyici döndürür **eşdeğer** bağımsız değişkeni üzerinde daha az bir sıralama uygulanmasını ikili bir koşul altında anahtar temel-comparability ilişkisi daha.

Varsa dönüş değerini **Bul** atanmış bir `const_iterator`, hash_set nesnesi değiştirilemez. Varsa dönüş değerini **Bul** atanmış bir **yineleyici**, hash_set nesne değiştirilebilir.

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

Hash_set oluşturmak için kullanılan ayırıcısı nesnesinin bir kopyasını döndürür.

```cpp
Allocator get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şablon parametresi bellek yönetmek için hash_set tarafından kullanılan ayırıcısı `Allocator`.

Daha fazla bilgi için `Allocator`, Açıklamalar bölümüne bakın [hash_set sınıfı](../standard-library/hash-set-class.md) konu.

### <a name="remarks"></a>Açıklamalar

Allocators hash_set sınıfı için sınıf depolama nasıl yönettiğini belirtin. C++ Standart Kitaplığı kapsayıcı sınıfları ile sağlanan varsayılan allocators çoğu programlama ihtiyaçları için yeterli. Yazma ve kendi allocator sınıfı kullanarak ileri düzeyde C++ bir konudur.

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

Oluşturan bir `hash_set` diğer bir deyişle boş veya diğer bir deyişle tüm kopyasını veya başka bir parçası `hash_set`.

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
|`Al`|Bunun için kullanılacak depolama allocator sınıfı `hash_set` varsayılan olarak nesne `Allocator`.|
|`Comp`|Türü karşılaştırma işlevinden `const Traits` öğeleri sıralamak için kullanılan `hash_set`, varsayılan olarak `hash_compare`.|
|`Right`|`hash_set` Biri oluşturulan `hash_set` kopyasını olacak.|
|`First`|Kopyalanacak öğe aralığını ilk öğe konumu.|
|`Last`|Kopyalanacak öğeleri aralık ötesinde ilk öğe konumu.|

### <a name="remarks"></a>Açıklamalar

Tüm oluşturucular depolamak için bellek depolama yönetir ayırıcısı nesne türünü `hash_set` ve, daha sonra döndürülüp döndürülmediğini çağırarak [hash_set::get_allocator](#get_allocator). Allocator parametresi, sınıf bildirimleri ve diğer allocators yerine kullanılacak önişlem makroları genellikle atlanır.

Tüm oluşturucular kendi hash_sets başlatır.

İşlev nesnesi türündeki tüm oluşturucular depolamak `Traits` bir sipariş anahtarlar oluşturmak için kullanılan `hash_set` ve, daha sonra döndürülüp döndürülmediğini çağırarak [hash_set::key_comp](#key_comp). Daha fazla bilgi için `Traits` bkz [hash_set sınıfı](../standard-library/hash-set-class.md) konu.

Boş bir ilk ilk Oluşturucusu oluşturur `hash_set` ikinci karşılaştırma işlevi türünü belirtir ( `Comp`) öğeleri ve üçüncü sırasını açıkça oluşturmada kullanılacak ayırıcı türünü belirtir ( `Al`) olmalıdır kullanılır. Anahtar sözcük `explicit` otomatik tür dönüştürme belirli türdeki gizler.

Dördüncü ve beşinci oluşturucular bir kopyasını belirtin `hash_set` `Right`.

Son altıncı, yedinci ve sekizinci oluşturucular öğeleri için bir initializer_list kullanın.

Aralığın son oluşturucuları kopyalama [ `First`, `Last`), bir `hash_set` karşılaştırma işlevinden sınıfı nitelikler ve ayırıcısı türünü belirleyen içinde explicitness artan.

Sekizinci Oluşturucusu taşır `hash_set` `Right`.

Öğelerin gerçek sırasını bir `hash_set` kapsayıcısı üzerinde karma işlevi bağlıdır, sıralama işlevi ve karma geçerli boyutu tablo ve burada belirlenmiştir sıralama kümesi kapsayıcısı ile verebilir gibi genel olarak, tahmin edilemez tek başına işlevi.

## <a name="insert"></a>  hash_set::insert

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Bir öğenin veya bir dizi elemanlara ekler bir `hash_set`.

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
|`Val`|İçine Eklenecek öğenin değerini `hash_set` sürece `hash_set` o öğeye veya daha genel anahtar eşdeğer sıralanmış bir öğe zaten içeriyor.|
|`Where`|Ekleme için doğru noktası aramaya başlamak için koyun. (Ekleme gerçekleşebilir Logaritmik zaman yerine amortized sabit zaman ekleme noktasını hemen izleyen `_Where`.)|
|`First`|Kopyalanacak ilk öğenin konumunu bir `hash_set`.|
|`Last`|Kopyalanacak yalnızca son öğenin ötesinde konumu bir `hash_set`.|
|`IList`|Öğelerin kopyalanacağı initializer_list.|

### <a name="return-value"></a>Dönüş Değeri

İlk `insert` üye işlevi bir çift döndürür, `bool` bileşenini döndürür `true` ekleme yapma ise ve `false` varsa `hash_set` anahtar sıralama içinde karşılık gelen bir değer olan bir öğe zaten bulunan ve Yineleyici bileşeni, burada yeni bir öğe eklendi veya öğe zaten bulunduğu konumun adresini döndürür.

Bir çift yineleyici bileşeninin erişmek için `pr` bu üye işlevi tarafından döndürülen, kullanın `pr.first` ve başvurabilir için `*(pr.first)`. Erişim için `bool` çiftinin bileşen `pr` bu üye işlevi tarafından döndürülen, kullanın `pr.second`ve başvurabilir, `*(pr.second)`.

İkinci `insert` üye işlevinin döndürdüğü burada yeni öğe eklenir içine konumuna işaret eden bir yineleyici `hash_set`.

### <a name="remarks"></a>Açıklamalar

Üçüncü üye işlevi bir initializer_list öğeleri ekler.

Üçüncü üye işlevi bir dizi öğesi değerlerini ekler bir `hash_set` yineleyici aralığında tarafından ele her öğesine karşılık gelen [ `First`, `Last`) bir belirtilen `hash_set`.

## <a name="iterator"></a>  hash_set::iterator

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Okuma veya herhangi bir hash_set öğesinde değiştirmek için bir çift yönlü yineleyici sağlayan türü.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::iterator iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür **yineleyici** bir öğenin değerini değiştirmek için kullanılabilir.

### <a name="example"></a>Örnek

Örneğin bkz [başlamak](#begin) bildirme ve kullanma konusunda bir örnek için **yineleyici**.

## <a name="key_comp"></a>  hash_set::key_comp

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Karma ve öğe bir hash_set anahtar değerleri sıralamak için kullanılan karma nitelikler nesnesinin bir kopyasını alır.

```cpp
key_compare key_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şablon parametresi olan bir hash_set öğeleri, sipariş için kullandığı işlevi nesnesi döndüren `Traits`.

Daha fazla bilgi için `Traits` bkz [hash_set sınıfı](../standard-library/hash-set-class.md) konu.

### <a name="remarks"></a>Açıklamalar

Saklanan nesne üye işlevini tanımlar:

**bool işleci**( **const anahtar &** _ *xVal*, **const anahtar &** \_ `yVal`);

döndüren **true** varsa `_xVal` önündeki ve eşit değil `_yVal` sıralama düzeninde.

Unutmayın her ikisi de [key_compare](#key_compare) ve [value_compare](#value_compare) şablon parametresi için eş anlamlı sözcükleri olan **nitelikler**. Her iki tür ayrı nerede hash_map ve hash_multimap sınıfları ile uyumluluk için aynı oldukları hash_set ve hash_multiset sınıfları için sağlanır.

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

İşlev nesnesi sağlayan bir türü göreli hash_set içinde iki öğe sırasını belirlemek için iki sıralama anahtarları karşılaştırabilirsiniz.

```cpp
typedef Traits key_compare;
```

### <a name="remarks"></a>Açıklamalar

`key_compare` Şablon parametresi için bir eş anlamlı olduğundan `Traits`.

Daha fazla bilgi için `Traits` bkz [hash_set sınıfı](../standard-library/hash-set-class.md) konu.

Unutmayın her ikisi de `key_compare` ve [value_compare](#value_compare) şablon parametresi için eş anlamlı sözcükleri olan **nitelikler**. Her iki tür kümesi ve burada ayrı multimap sınıfların ve eşleme ile uyumluluk için aynı oldukları çok kümeli sınıfları için sağlanır.

### <a name="example"></a>Örnek

Örneğin bkz [key_comp](#key_comp) bildirme ve kullanma konusunda bir örnek için `key_compare`.

## <a name="key_type"></a>  hash_set::key_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Hash_set kapasitesi sıralama anahtarı olarak içinde bir öğe olarak saklanan bir nesneyi tanımlayan bir türü.

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Açıklamalar

**key_type** şablon parametresi için bir eş anlamlı olduğundan `Key`.

Daha fazla bilgi için `Key`, Açıklamalar bölümüne bakın [hash_set sınıfı](../standard-library/hash-set-class.md) konu.

Unutmayın her ikisi de `key_type` ve [value_type](#value_type) şablon parametresi için eş anlamlı sözcükleri olan **anahtar**. Her iki tür ayrı nerede hash_map ve hash_multimap sınıfları ile uyumluluk için aynı oldukları hash_set ve hash_multiset sınıfları için sağlanır.

### <a name="example"></a>Örnek

Örneğin bkz [value_type](#value_type) bildirme ve kullanma konusunda bir örnek için `key_type`.

## <a name="lower_bound"></a>  hash_set::lower_bound

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Yineleyici eşit veya bundan büyük belirtilen anahtar bir anahtarı olan bir hash_set ilk öğe döndürür.

```cpp
const_iterator lower_bound(const Key& key) const;

iterator lower_bound(const Key& key);
```

### <a name="parameters"></a>Parametreler

`key` Aranmakta hash_set öğeden sıralama anahtarı ile Karşılaştırılacak bağımsız değişkeni anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Bir **yineleyici** veya `const_iterator` eşit veya bundan büyük bağımsız değişkeni anahtar veya yoksa hash_set son öğesi başarılı konumu adresleri anahtarı ile eşleşmesini hash_set bir öğedeki konumunu adresleri için anahtar bulunamadı.

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

Hash_set en büyük uzunluğunu döndürür.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Hash_set en fazla olası uzunluğu.

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

Hash_set öğelerini başka bir hash_set bir kopyası ile değiştirir.

```cpp
hash_set& operator=(const hash_set& right);

hash_set& operator=(hash_set&& right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|`right`|[Hash_set](../standard-library/hash-set-class.md) içine kopyalanmasını `hash_set`.|

### <a name="remarks"></a>Açıklamalar

Var olan öğeleri silindikten sonra bir `hash_set`, `operator=` kopyalar ya da içeriğini taşır `right` içine `hash_set`.

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

Bir hash_set bir öğe için bir işaretçi sağlayan türü.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir tür **işaretçi** bir öğenin değerini değiştirmek için kullanılabilir.

Çoğu durumda, bir [yineleyici](#iterator) hash_set nesnesindeki öğelerin erişmek için kullanılmalıdır.

## <a name="rbegin"></a>  hash_set::rbegin

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Yineleyici ters hash_set ilk öğe adresleme döndürür.

```cpp
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```

### <a name="return-value"></a>Dönüş Değeri

Ters hash_set ilk öğe adresleme veya ne adresleme ters çift yönlü yineleyici unreversed hash_set son öğesi eklenmiştir.

### <a name="remarks"></a>Açıklamalar

`rbegin` Ters hash_set ile kullanılan gibi [başlamak](#begin) hash_set ile kullanılır.

Varsa dönüş değerini `rbegin` atanmış bir `const_reverse_iterator`, sonra da hash_set nesnesi değiştirilemez. Varsa dönüş değerini `rbegin` atandığı bir `reverse_iterator`, sonra hash_set nesne değiştirilebilir.

`rbegin` hash_set geriye doğru yinelemek için kullanılabilir.

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
   // throught a hash_set in a forward order
   cout << "The hash_set is: ";
   for ( hs1_Iter = hs1.begin( ) ; hs1_Iter != hs1.end( );
         hs1_Iter++ )
      cout << *hs1_Iter << " ";
   cout << endl;

   // rbegin can be used to start an iteration
   // throught a hash_set in a reverse order
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

Hash_set içinde depolanan bir öğe için bir başvuru sağlar türü.

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

Ters hash_set son öğesi başarılı konumu adresleri yineleyici döndürür.

```cpp
const_reverse_iterator rend() const;

reverse_iterator rend();
```

### <a name="return-value"></a>Dönüş Değeri

Ters hash_set (ilk öğe unreversed hash_set öncesinde konum) son öğesi başarılı konumu adresleri ters çift yönlü yineleyici.

### <a name="remarks"></a>Açıklamalar

`rend` Ters hash_set ile kullanılan gibi [son](#end) hash_set ile kullanılır.

Varsa dönüş değerini `rend` atanmış bir `const_reverse_iterator`, sonra da hash_set nesnesi değiştirilemez. Varsa dönüş değerini `rend` atandığı bir `reverse_iterator`, sonra hash_set nesne değiştirilebilir. Tarafından döndürülen değer `rend` değil başvuru yapıldı.

`rend` Ters yineleyici kendi hash_set sonuna olup ulaştı için test etmek için kullanılabilir.

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
   // throught a hash_set in a forward order
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

Okuma veya ters hash_set bir öğedeki değiştirmek için bir çift yönlü yineleyici sağlayan türü.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::reverse_iterator reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `reverse_iterator` kullanın ters hash_set yinelemek için.

### <a name="example"></a>Örnek

Örneğin bkz [rbegin](#rbegin) bildirme ve kullanma konusunda bir örnek için `reverse_iterator`.

## <a name="size"></a>  hash_set::size

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Hash_set öğe sayısını döndürür.

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

Bir hash_set öğe sayısı gösterebilir bir işaretsiz tamsayı türü.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::size_type size_type;
```

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

Örneğin bkz [boyutu](#size) bildirme ve kullanma örneği `size_type`

## <a name="swap"></a>  hash_set::Swap

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

İki hash_sets öğelerini değiş tokuş eder.

```cpp
void swap(hash_set& right);
```

### <a name="parameters"></a>Parametreler

`right` Bağımsız değişken hash_set öğeleri ile hedef hash_set takas için sağlama.

### <a name="remarks"></a>Açıklamalar

Üye işlevini hiçbir başvuruları, işaretçileri veya öğeleri arasında alınıp verilen iki hash_sets öğelerinde tanımladığınız yineleyiciler geçersiz kılar.

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

Yineleyici ilk öğeye bir hash_set, belirtilen anahtar daha büyük bir anahtarla döndürür.

```cpp
const_iterator upper_bound(const Key& key) const;

iterator upper_bound(const Key& key);
```

### <a name="parameters"></a>Parametreler

`key` Aranmakta hash_set öğeden sıralama anahtarı ile Karşılaştırılacak bağımsız değişkeni anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Bir **yineleyici** veya `const_iterator` eşit veya bundan büyük bağımsız değişkeni anahtar veya yoksa hash_set son öğesi başarılı konumu adresleri anahtarı ile eşleşmesini hash_set bir öğedeki konumunu adresleri için anahtar bulunamadı.

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

Bir hash_set sipariş öğesi değerleri için kullanılan karşılaştırma nesnesinin bir kopyasını alır.

```cpp
value_compare value_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şablon parametresi olan bir hash_set öğeleri, sipariş için kullandığı işlevi nesnesi döndüren `Compare`.

Daha fazla bilgi için `Compare`, Açıklamalar bölümüne bakın [hash_set sınıfı](../standard-library/hash-set-class.md) konu.

### <a name="remarks"></a>Açıklamalar

Saklanan nesne üye işlevini tanımlar:

**bool işleci**( **const anahtar &** _ *xVal*, **const anahtar &** \_ `yVal`);

döndüren **true** varsa `_xVal` önündeki ve eşit değil `_yVal` sıralama düzeninde.

Unutmayın her ikisi de [value_compare](../standard-library/set-class.md#value_compare) ve [key_compare](../standard-library/set-class.md#key_compare) şablon parametresi için eş anlamlı sözcükleri olan `Compare`. Her iki tür ayrı nerede hash_map ve hash_multimap sınıfları ile uyumluluk için aynı oldukları hash_set ve hash_multiset sınıfları için sağlanır.

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

İki işlev nesneleri sağlayan bir türü göreli sıralarına belirlemek için bir hash_set iki öğenin değerleri karşılaştırabilirsiniz sınıfı karşılaştırma, ikili bir koşul ve öğeleri karmaları birli koşul.

```cpp
typedef key_compare value_compare;
```

### <a name="remarks"></a>Açıklamalar

**value_compare** şablon parametresi için bir eş anlamlı olduğundan `Traits`.

Daha fazla bilgi için `Traits` bkz [hash_set sınıfı](../standard-library/hash-set-class.md) konu.

Unutmayın her ikisi de [key_compare](#key_compare) ve **value_compare** şablon parametresi için eş anlamlı sözcükleri olan **nitelikler**. Her iki tür ayrı nerede hash_map ve hash_multimap sınıfları ile uyumluluk için aynı oldukları hash_set ve hash_multiset sınıfları için sağlanır.

### <a name="example"></a>Örnek

Örneğin bkz [value_comp](#value_comp) bildirme ve kullanma konusunda bir örnek için `value_compare`.

## <a name="value_type"></a>  hash_set::value_type

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Hash_set kapasitesi değer olarak, bir öğe olarak saklanan bir nesneyi tanımlayan bir türü.

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
