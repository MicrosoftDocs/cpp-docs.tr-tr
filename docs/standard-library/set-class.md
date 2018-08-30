---
title: set sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- set/std::set
- set/std::set::allocator_type
- set/std::set::const_iterator
- set/std::set::const_pointer
- set/std::set::const_reference
- set/std::set::const_reverse_iterator
- set/std::set::difference_type
- set/std::set::iterator
- set/std::set::key_compare
- set/std::set::key_type
- set/std::set::pointer
- set/std::set::reference
- set/std::set::reverse_iterator
- set/std::set::size_type
- set/std::set::value_compare
- set/std::set::value_type
- set/std::set::begin
- set/std::set::cbegin
- set/std::set::cend
- set/std::set::clear
- set/std::set::count
- set/std::set::crbegin
- set/std::set::crend
- set/std::set::emplace
- set/std::set::emplace_hint
- set/std::set::empty
- set/std::set::end
- set/std::set::equal_range
- set/std::set::erase
- set/std::set::find
- set/std::set::get_allocator
- set/std::set::insert
- set/std::set::key_comp
- set/std::set::lower_bound
- set/std::set::max_size
- set/std::set::rbegin
- set/std::set::rend
- set/std::set::size
- set/std::set::swap
- set/std::set::upper_bound
- set/std::set::value_comp
dev_langs:
- C++
helpviewer_keywords:
- std::set [C++]
- std::set [C++], allocator_type
- std::set [C++], const_iterator
- std::set [C++], const_pointer
- std::set [C++], const_reference
- std::set [C++], const_reverse_iterator
- std::set [C++], difference_type
- std::set [C++], iterator
- std::set [C++], key_compare
- std::set [C++], key_type
- std::set [C++], pointer
- std::set [C++], reference
- std::set [C++], reverse_iterator
- std::set [C++], size_type
- std::set [C++], value_compare
- std::set [C++], value_type
- std::set [C++], begin
- std::set [C++], cbegin
- std::set [C++], cend
- std::set [C++], clear
- std::set [C++], count
- std::set [C++], crbegin
- std::set [C++], crend
- std::set [C++], emplace
- std::set [C++], emplace_hint
- std::set [C++], empty
- std::set [C++], end
- std::set [C++], equal_range
- std::set [C++], erase
- std::set [C++], find
- std::set [C++], get_allocator
- std::set [C++], insert
- std::set [C++], key_comp
- std::set [C++], lower_bound
- std::set [C++], max_size
- std::set [C++], rbegin
- std::set [C++], rend
- std::set [C++], size
- std::set [C++], swap
- std::set [C++], upper_bound
- std::set [C++], value_comp
ms.assetid: 8991f9aa-5509-4440-adc1-371512d32018
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f7a04710d900aa9eb5889c19fbdc419a3b7f3cbc
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43204616"
---
# <a name="set-class"></a>set Sınıfı

C++ Standart Kitaplığı kapsayıcı sınıfı kümesi, içerdiği öğelerin değerlerinin benzersiz olduğu ve verilerin otomatik sıralamasına göre anahtar değerler olarak hizmet verdikleri bir koleksiyondan verilerin alınmasını ve depolama için kullanılır. Bir kümedeki bir öğenin değeri doğrudan değiştirilemez. Bunun yerine, eski değerleri silmeniz ve yeni değerlere sahip öğeler eklemeniz gerekir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Key,
    class Traits=less<Key>,
    class Allocator=allocator<Key>>
class set
```

### <a name="parameters"></a>Parametreler

*Key*<br/>
 Kümede depolanacak öğe veri türü.

*Nitelikler*<br/>
 İki öğenin değerlerini kümede kendi göreli sıralarını belirlemek için sıralama anahtarları olarak karşılaştırabilen bir işlev nesnesi sağlayan tür. Bu bağımsız değişken isteğe bağlıdır ve ikili koşul **daha az**  *\<anahtarı >* varsayılan değerdir.

C ++ 14'te belirterek heterojen arama etkinleştirebilirsiniz `std::less<>` veya `std::greater<>` hiçbir tür parametreleri olan koşul. Daha fazla bilgi için [, ilişkili kapsayıcılar için heterojen arama](../standard-library/stl-containers.md#sequence_containers)

*Ayırıcı*<br/>
 Kümenin bellek ayırmayı ve ayırmayı kaldırma hakkındaki ayrıntıları içeren saklı ayırıcı nesnesini gösteren tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `allocator<Key>`.

## <a name="remarks"></a>Açıklamalar

C++ Standart Kitaplığı kümesidir:

- İlişkili bir anahtar değerine dayalı öğe değerlerinin verimli alınmasını destekleyen bir değişken boyutu kapsayıcı olan ilişkilendirilebilir bir kapsayıcı. Dahası, basit bir ilişkilendirilebilir kapsayıcıdır, çünkü öğelerinin değerleri kendi anahtar değerleridir.

- Çift yönlüdür, çünkü öğelerine erişmek için çift yönlü bir yineleyici sağlar.

- Sıralıdır, çünkü öğeleri belirtilen karşılaştırma işlevine uygun olarak kapsayıcı içindeki anahtar değerlere göre sıralanır.

- Benzersizdir, çünkü öğelerinin her birinde benzersiz bir anahtar olması gerekir. Ayrıca, küme basit ilişkilendirilebilir bir kapsayıcı olduğundan, onun da öğeleri benzersizdir.

Bir küme aynı zamanda bir şablon sınıfı olarak tanımlanır, çünkü sağladığı işlevsellik geneldir ve böylece öğeler olarak kapsanan belirli veri türünden bağımsızdır. Kullanılacak veri türü, karşılaştırma işlevi ve ayırıcı ile birlikte bir sınıf şablonunda bir parametre olarak belirtilir.

Kapsayıcı türünün seçimi genelde uygulamanın gerektirdiği arama ve ekleme türüne dayalı olmalıdır. İlişkilendirilebilir kapsayıcılar, arama, ekleme ve kaldırma işlemleri için en iyi duruma getirilir. Bu işlemleri açıkça destekleyen üye işlevleri, işlevlerini kapsayıcıdaki öğelerin sayısının logaritmasına ortalama orantılı bir sürede gerçekleştirir ve verimlidir. Öğelerin eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; öğelerin kaldırılması yalnızca özellikle kaldırılan öğeleri gösteren yineleyicileri geçersiz kılar.

Küme, değerleri onların kendi anahtarlarıyla ilişkilendiren koşullar uygulama tarafından karşılandığında seçimin ilişkili kapsayıcısı olmalıdır. Kümenin öğeleri benzersizdir ve kendi sıralama anahtarı olarak hizmet eder. Bu tür bir yapı modeli, sözcüklerin yalnızca bir defa geçebildiği sıralı bir sözcükler listesindedir. Sözcüklerin birden çok defa geçmelerine izin verilirse, bir çoklu küme uygun bir kapsayıcı yapısı olacaktır. Değerlerin benzersiz anahtar sözcükler listesine eklenmesi gerekirse, bir eşlem verileri kapsayacak uygun bir yapı olacaktır. Bunun yerine, anahtarlar benzersiz değilse, seçilecek kapsayıcı bir çoklu eşlem olurdu.

Belirlenen bir türünde depolanmış bir işlev nesnesi çağırarak denetlediği diziyi sıralar [key_compare](#key_compare). Depolanan bu nesne işlevi çağrılarak erişilebilen bir karşılaştırma işlevidir [key_comp](#key_comp). Genelde, bu sıralamayı oluşturmak için öğelerin yalnızca küçüktür biçiminde karşılaştırılabilir olması gerekir; böylece, herhangi iki öğe belirtildiğinde, eşit oldukları (yani birinin diğerinden daha küçük olmadığı anlamında) veya birinin diğerinden küçük olduğu belirlenebilir. Bu, denk olmayan öğeler arasında bir sıralamaya neden olur. Daha teknik bir not üzerinde, karşılaştırma işlevi standart matematiksel anlamda katı bir zayıf sıralama sevk eden ikili bir koşuldur. Bir ikili koşula *f*( *x, y*) iki bağımsız değişken nesnelere sahip bir işlev nesnesidir *x* ve *y* ve dönüş değeri  **doğru** veya **false**. Bir kümesinde ikili koşul dönüşsüz, ters ve geçişli ve denklik geçişli ise, burada iki nesne sıralama katı zayıf sıralamadır *x* ve *y* olarak tanımlanır eşdeğer when hem *f*( *x, y*) ve *f*( *y, x*) false. Anahtarlar arasındaki eşitliğinin daha güçlü koşulu bu denkliğin yerini alırsa, sıralama (içindeki tüm öğelerin birbirine göre sıralanması anlamında) toplam haline gelir ve eşleşen anahtarlar birbirinden ayırt edilemez olacaktır.

C ++ 14'te belirterek heterojen arama etkinleştirebilirsiniz `std::less<>` veya `std::greater<>` hiçbir tür parametreleri olan koşul. Daha fazla bilgi için [, ilişkili kapsayıcılar için heterojen arama](../standard-library/stl-containers.md#sequence_containers)

Küme sınıfı tarafından sağlanan yineleyici çift yönlüdür, ancak sınıf üyesi işlevleri olan [Ekle](#insert) ve [ayarlamak](#set) şablon parametresi olarak daha zayıf bir giriş yineleyicisini alan sürümlere sahip olan işlevsellik gereksinimleri tarafından çift yönlü Yineleyicilerin sınıfında garanti daha düşüktür. Farklı yineleyici kavramları, işlevselliklerindeki iyileştirmelere göre ilgili bir aile biçimlendirir. Her yineleyici kavramının kendi gereksinimler kümesi vardır ve bunlarla çalışan algoritmaların kendi varsayımlarını yineleyici türü tarafından sağlanan gereksinimlerle sınırlaması gerekir. Bir giriş yineleyicinin bazı nesnelere başvurusunun kaldırılacağı ve dizideki sonraki yineleyiciye artırılabileceği varsayılabilir. Bu bir en düşük işlevsellik kümesidir, ancak Yineleyicilerin aralığı hakkında konuşabilmek için yeterlidir [ `First`, `Last`) sınıfın üye işlevleri bağlamında.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[set](#set)|Boş veya küme öğesinin tümünün veya diğer bir kısmının kopyası olan bir küme oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[allocator_type](#allocator_type)|Temsil eden bir tür `allocator` küme nesnesi için sınıf.|
|[const_iterator](#const_iterator)|Çift yönlü bir yineleyici sağlayan tür okuma bir **const** kümedeki öğe.|
|[const_pointer](#const_pointer)|Bir işaretçi sağlayan bir tür bir **const** küme içindeki öğeye.|
|[const_reference](#const_reference)|Bir başvuru sağlayan bir tür bir **const** okumak ve gerçekleştirmek için bir küme içinde depolanan öğenin **const** operations.|
|[const_reverse_iterator](#const_reverse_iterator)|Çift yönlü bir yineleyici sağlayan tür herhangi okuma **const** kümedeki öğe.|
|[difference_type](#difference_type)|Yineleyiciler tarafından gösterilen öğeler arasındaki bir aralıktaki küme öğelerinin sayısını temsil etmek için kullanılabilen işaretli bir tamsayı türü.|
|[Yineleyici](#iterator)|Küme içindeki herhangi bir öğeyi okuyabilen veya değiştirebilen çift yönlü yineleyiciler sağlayan tür.|
|[key_compare](#key_compare)|Küme içindeki iki öğenin göreli sırasını belirlemek için iki sıralama anahtarını karşılaştıran bir işlev nesnesi sağlayan bir tür.|
|[key_type](#key_type)|Bir sıralama anahtarı olarak kapasitesi dahilinde bir küme öğesi olarak depolanan nesneyi tanımlayan bir tür.|
|[İşaretçi](#pointer)|Bir küme içindeki öğeye işaretçi sağlayan bir tür.|
|[Başvuru](#reference)|Küme içinde depolanan öğeye başvuru sağlayan bir tür.|
|[reverse_iterator](#reverse_iterator)|Ters döndürülmüş küme içindeki bir öğeyi okuyabilen veya değiştirebilen çift yönlü yineleyiciler sağlayan tür.|
|[size_type](#size_type)|Küme içindeki öğelerin sayısını temsil edebilen bir işaretsiz tamsayı türü.|
|[value_compare](#value_compare)|Küme içindeki iki öğenin kendi göreli sıralarını belirlemek için iki öğeyi karşılaştıran bir işlev nesnesi sağlayan bir tür.|
|[value_type](#value_type)|Bir değer olarak kapasitesi dahilinde bir küme öğesi şeklinde depolanan nesneyi tanımlayan bir tür.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[başlayın](#begin)|Küme içindeki ilk öğeyi ele alan bir yineleyici döndürür.|
|[cbegin](#cbegin)|Küme içindeki ilk öğeyi ele alan sabit bir yineleyici döndürür.|
|[cend](#cend)|Küme içindeki son öğeyi takip eden konumu ele alan sabit bir yineleyici döndürür.|
|[Temizle](#clear)|Bir kümenin tüm öğelerini siler.|
|[Sayısı](#count)|Anahtarı parametre tarafından belirtilen anahtarla eşleşen küme içindeki öğelerin sayısını döndürür.|
|[crbegin](#rbegin)|Ters çevrilen kümedeki ilk öğeyi ele alan bir sabit yineleyici döndürür.|
|[crend](#rend)|Ters çevrilen kümedeki son öğeden sonra gelen konumu ele alan bir sabit yineleyici döndürür.|
|[emplace](#emplace)|Bir küme içine yerinde oluşturulmuş bir öğe ekler.|
|[emplace_hint](#emplace_hint)|Bir küme içine, bir yerleşim ipucuyla birlikte yerinde oluşturulmuş bir öğe ekler.|
|[boş](#empty)|Kümenin boş olup olmadığını sınar.|
|[Son](#end)|Küme içindeki son öğeyi takip eden konumu ele alan bir yineleyici döndürür.|
|[equal_range](#equal_range)|Yineleyicilerin bir çiftini, sırasıyla belirtilen anahtardan daha büyük olan bir anahtar ile küme içindeki ilk öğeye ve anahtardan büyük veya ona eşit bir anahtar ile kümedeki ilk öğeye döndürür.|
|[silme](#erase)|Küme içindeki bir öğeyi veya öğelerin aralığını belirtilen konumlardan kaldırır veya belirtilen bir anahtarla eşleşen öğeleri kaldırır.|
|[Bul](#find)|Belirtilen anahtara denk bir anahtara sahip bir küme içindeki öğenin konumunu ele alan bir yineleyici döndürür.|
|[get_allocator](#get_allocator)|Bir kopyasını döndürür `allocator` küme oluşturmak için kullanılan nesne.|
|[Ekle](#insert)|Bir küme içine bir öğe veya öğe aralığı ekler.|
|[key_comp](#key_comp)|Bir küme içindeki anahtarları sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır.|
|[lower_bound](#lower_bound)|Bir yineleyiciyi belirtilen anahtardan daha büyük veya ona eşit bir anahtarla küme içindeki ilk öğeye döndürür.|
|[max_size](#max_size)|Küme öğesinin maksimum uzunluğunu döndürür.|
|[rbegin](#rbegin)|Ters çevrilen küme içindeki ilk öğeyi ele alan bir yineleyici döndürür.|
|[rend](#rend)|Ters çevrilen küme içindeki son öğeden sonra gelen konumu ele alan bir yineleyici döndürür.|
|[Boyutu](#size)|Kümedeki öğelerin sayısını döndürür.|
|[değiştirme](#swap)|İki kümenin öğelerini birbiriyle değiştirir.|
|[upper_bound](#upper_bound)|Bir yineleyiciyi belirtilen anahtardan daha büyük bir anahtarla küme içindeki ilk öğeye döndürür.|
|[value_comp](#value_comp)|Küme içindeki öğe değerlerini sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator=](#op_eq)|Bir kümenin öğelerini başka bir küme kopyasıyla değiştirir.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<kümesi >

**Namespace:** std

## <a name="allocator_type"></a>  set::allocator_type

Küme nesnesi için ayırıcı sınıf temsil eden tür.

```cpp
typedef Allocator allocator_type;
```

### <a name="remarks"></a>Açıklamalar

`allocator_type` Şablon parametresi için bir eşanlamlı olduğu [ayırıcı](../standard-library/set-class.md).

Şablon parametresi olan bir çoklu küme, öğeleri düzenlemek amacıyla kullanan işlev nesnesini döndürür `Allocator`.

Daha fazla bilgi için `Allocator`, Açıklamalar bölümüne bakın [set sınıfı](../standard-library/set-class.md) konu.

### <a name="example"></a>Örnek

Örneğin bakın [get_allocator](#get_allocator) kullanan bir örnek için `allocator_type`.

## <a name="begin"></a>  set::Begin

Küme içindeki ilk öğeyi ele alan bir yineleyici döndürür.

```cpp
const_iterator begin() const;

iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

Küme veya sonra gelen konumu adresleyen bir boş küme içindeki ilk öğeyi ele alan bir çift yönlü yineleyici.

### <a name="remarks"></a>Açıklamalar

Varsa dönüş değeri `begin` atanan bir `const_iterator`, öğeleri kümesi nesnesi değiştirilemez. Varsa dönüş değeri `begin` atanan bir `iterator`, Küme nesnesi öğeleri değiştirilebilir.

### <a name="example"></a>Örnek

```cpp
// set_begin.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   set <int> s1;
   set <int>::iterator s1_Iter;
   set <int>::const_iterator s1_cIter;

   s1.insert( 1 );
   s1.insert( 2 );
   s1.insert( 3 );

   s1_Iter = s1.begin( );
   cout << "The first element of s1 is " << *s1_Iter << endl;

   s1_Iter = s1.begin( );
   s1.erase( s1_Iter );

   // The following 2 lines would err because the iterator is const
   // s1_cIter = s1.begin( );
   // s1.erase( s1_cIter );

   s1_cIter = s1.begin( );
   cout << "The first element of s1 is now " << *s1_cIter << endl;
}
```

```Output
The first element of s1 is 1
The first element of s1 is now 2
```

## <a name="cbegin"></a>  set::cbegin

Döndürür bir **const** aralıktaki ilk öğeyi adresleyen bir yineleyici.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

A **const** aralığı veya konuma boş bir aralığın ilk öğesine, çift yönlü erişim yineleyicisi (boş bir aralık için `cbegin() == cend()`).

### <a name="remarks"></a>Açıklamalar

Dönüş değeri ile `cbegin`, aralıktaki öğeler değiştirilemez.

Bu üye işlevi yerine kullanabileceğiniz `begin()` üye işlev dönüş değeri olacağını garanti etmek için `const_iterator`. Genellikle birlikte kullanılır [otomatik](../cpp/auto-cpp.md) kesinti anahtar sözcüğü, aşağıdaki örnekte gösterildiği gibi yazın. Örnekte, göz önünde bulundurun `Container` değiştirilebilir (olmayan **const**) destekleyen herhangi bir türdeki kapsayıcı `begin()` ve `cbegin()`.

```cpp
auto i1 = Container.begin();
// i1 is Container<T>::iterator
auto i2 = Container.cbegin();

// i2 is Container<T>::const_iterator
```

## <a name="cend"></a>  set::cend

Döndürür bir **const** konuma bir aralıktaki son öğeyi ele alan bir yineleyici.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Dönüş Değeri

A **const** aralığın sonunu yalnızca çift yönlü erişim yineleyicisi.

### <a name="remarks"></a>Açıklamalar

`cend` bir yineleyicinin kendi aralığının sonunu geçmediğini sınamak için kullanılır.

Bu üye işlevi yerine kullanabileceğiniz `end()` üye işlev dönüş değeri olacağını garanti etmek için `const_iterator`. Genellikle birlikte kullanılır [otomatik](../cpp/auto-cpp.md) kesinti anahtar sözcüğü, aşağıdaki örnekte gösterildiği gibi yazın. Örnekte, göz önünde bulundurun `Container` değiştirilebilir (olmayan **const**) destekleyen herhangi bir türdeki kapsayıcı `end()` ve `cend()`.

```cpp
auto i1 = Container.end();
// i1 is Container<T>::iterator
auto i2 = Container.cend();

// i2 is Container<T>::const_iterator
```

Tarafından döndürülen değer `cend` kaldırılmamalıdır.

## <a name="clear"></a>  set::Clear

Bir kümenin tüm öğelerini siler.

```cpp
void clear();
```

### <a name="example"></a>Örnek

```cpp
// set_clear.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   set <int> s1;

   s1.insert( 1 );
   s1.insert( 2 );

   cout << "The size of the set is initially " << s1.size( )
        << "." << endl;

   s1.clear( );
   cout << "The size of the set after clearing is "
        << s1.size( ) << "." << endl;
}
```

```Output
The size of the set is initially 2.
The size of the set after clearing is 0.
```

## <a name="const_iterator"></a>  set::const_iterator

Çift yönlü bir yineleyici sağlayan tür okuma bir **const** kümedeki öğe.

```cpp
typedef implementation-defined const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_iterator` bir öğenin değerini değiştirmek için kullanılamaz.

### <a name="example"></a>Örnek

Örneğin bakın [başlamak](#begin) kullanan bir örnek için `const_iterator`.

## <a name="const_pointer"></a>  set::const_pointer

Bir işaretçi sağlayan bir tür bir **const** küme içindeki öğeye.

```cpp
typedef typename allocator_type::const_pointer const_pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_pointer` bir öğenin değerini değiştirmek için kullanılamaz.

Çoğu durumda bir [const_iterator](#const_iterator) const kümesi nesnesindeki öğelere erişmek için kullanılmalıdır.

## <a name="const_reference"></a>  set::const_reference

Bir başvuru sağlayan bir tür bir **const** okumak ve gerçekleştirmek için bir küme içinde depolanan öğenin **const** operations.

```cpp
typedef typename allocator_type::const_reference const_reference;
```

### <a name="example"></a>Örnek

```cpp
// set_const_ref.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   set <int> s1;

   s1.insert( 10 );
   s1.insert( 20 );

   // Declare and initialize a const_reference &Ref1
   // to the 1st element
   const int &Ref1 = *s1.begin( );

   cout << "The first element in the set is "
        << Ref1 << "." << endl;

   // The following line would cause an error because the
   // const_reference cannot be used to modify the set
   // Ref1 = Ref1 + 5;
}
```

```Output
The first element in the set is 10.
```

## <a name="const_reverse_iterator"></a>  set::const_reverse_iterator

Çift yönlü bir yineleyici sağlayan tür herhangi okuma **const** kümedeki öğe.

```cpp
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_reverse_iterator` kullanın ters kümesinde yinelemek için ve bir öğenin değerini değiştiremezsiniz.

### <a name="example"></a>Örnek

Örneğin bakın [rend](#rend) bildirme ve kullanma konusunda bir örnek için `const_reverse_iterator`.

## <a name="count"></a>  set::Count

Anahtarı parametre tarafından belirtilen anahtarla eşleşen küme içindeki öğelerin sayısını döndürür.

```cpp
size_type count(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
 Kümeden eşleştirilecek öğe anahtarı.

### <a name="return-value"></a>Dönüş Değeri

1 küme sıralama anahtarı parametresi anahtarla eşleşen bir öğe içeriyorsa. kümesi ile eşleşen bir anahtarı bir öğe yoksa 0.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, şu aralıktaki öğelerin sayısını döndürür:

[ `lower_bound` (_ *Anahtarı* ), `upper_bound` (\_ *anahtarı* )).

### <a name="example"></a>Örnek

Aşağıdaki örnek, set::count üye işlevinin kullanımını gösterir.

```cpp
// set_count.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main()
{
    using namespace std;
    set<int> s1;
    set<int>::size_type i;

    s1.insert(1);
    s1.insert(1);

    // Keys must be unique in set, so duplicates are ignored
    i = s1.count(1);
    cout << "The number of elements in s1 with a sort key of 1 is: "
         << i << "." << endl;

    i = s1.count(2);
    cout << "The number of elements in s1 with a sort key of 2 is: "
         << i << "." << endl;
}
```

```Output
The number of elements in s1 with a sort key of 1 is: 1.
The number of elements in s1 with a sort key of 2 is: 0.
```

## <a name="crbegin"></a>  set::crbegin

Ters çevrilen kümedeki ilk öğeyi ele alan bir sabit yineleyici döndürür.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir const geriye doğru ne ters çevrilmeyen küme içindeki son öğeyi adresleyen ters çevrilen küme içindeki ilk öğeyi ele alan ya da çift yönlü yineleyici.

### <a name="remarks"></a>Açıklamalar

`crbegin` ters çevrilen küme ile kullanılan gibi [başlamak](#begin) ile bir küme kullanılır.

Dönüş değeri ile `crbegin`, Küme nesnesi değiştirilemez.

### <a name="example"></a>Örnek

```cpp
// set_crbegin.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   set <int> s1;
   set <int>::const_reverse_iterator s1_crIter;

   s1.insert( 10 );
   s1.insert( 20 );
   s1.insert( 30 );

   s1_crIter = s1.crbegin( );
   cout << "The first element in the reversed set is "
        << *s1_crIter << "." << endl;
}
```

```Output
The first element in the reversed set is 30.
```

## <a name="crend"></a>  set::crend

Ters çevrilen kümedeki son öğeden sonra gelen konumu ele alan bir sabit yineleyici döndürür.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir const çift yönlü yineleyici (ters çevrilmeyen kümedeki ilk öğeyi önce gelen konum) ters çevrilen küme içindeki son öğeden sonra gelen konumu ele tersine çevirir.

### <a name="remarks"></a>Açıklamalar

`crend` ters çevrilen küme ile kullanılan gibi [son](#end) ile bir küme kullanılır.

Dönüş değeri ile `crend`, Küme nesnesi değiştirilemez. Tarafından döndürülen değer `crend` kaldırılmamalıdır.

`crend` olup ters yineleyici kendine sonuna ulaşıp ulaşmadığını test etmek için kullanılabilir.

### <a name="example"></a>Örnek

```cpp
// set_crend.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main() {
   using namespace std;
   set <int> s1;
   set <int>::const_reverse_iterator s1_crIter;

   s1.insert( 10 );
   s1.insert( 20 );
   s1.insert( 30 );

   s1_crIter = s1.crend( );
   s1_crIter--;
   cout << "The last element in the reversed set is "
        << *s1_crIter << "." << endl;
}
```

## <a name="difference_type"></a>  set::difference_type

Yineleyiciler tarafından gösterilen öğeler arasındaki bir aralıktaki küme öğelerinin sayısını temsil etmek için kullanılabilen işaretli bir tamsayı türü.

```cpp
typedef typename allocator_type::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

`difference_type` Türü çıkarma veya kapsayıcının yineleyiciler artan döndürülür. `difference_type` Genellikle aralık içindeki öğelerin sayısını temsil etmek için kullanılan *[Soyadı)* yineleyici arasındaki `first` ve `last`, işaret ettiği öğe içeren `first` ve aralığı öğeleri kadar ancak dahil değil, öğe tarafından işaret edilen `last`.

Ancak dikkat `difference_type` kümesi, yineleyici arasındaki çıkarma yalnızca gibi ters çevrilebilir kapsayıcıları tarafından desteklenen çift yönlü Yineleyicilerin sınıfında içeren bir giriş yineleyici gereksinimlerini karşılayan tüm yineleyiciler için kullanılabilir vektör gibi bir rastgele erişim kapsayıcı tarafından sağlanan rasgele erişim yineleyicileri tarafından desteklenmiyor.

### <a name="example"></a>Örnek

```cpp
// set_diff_type.cpp
// compile with: /EHsc
#include <iostream>
#include <set>
#include <algorithm>

int main( )
{
   using namespace std;

   set <int> s1;
   set <int>::iterator s1_Iter, s1_bIter, s1_eIter;

   s1.insert( 20 );
   s1.insert( 10 );
   s1.insert( 20 );   // won't insert as set elements are unique

   s1_bIter = s1.begin( );
   s1_eIter = s1.end( );

   set <int>::difference_type   df_typ5, df_typ10, df_typ20;

   df_typ5 = count( s1_bIter, s1_eIter, 5 );
   df_typ10 = count( s1_bIter, s1_eIter, 10 );
   df_typ20 = count( s1_bIter, s1_eIter, 20 );

   // the keys, and hence the elements of a set are unique,
   // so there is at most one of a given value
   cout << "The number '5' occurs " << df_typ5
        << " times in set s1.\n";
   cout << "The number '10' occurs " << df_typ10
        << " times in set s1.\n";
   cout << "The number '20' occurs " << df_typ20
        << " times in set s1.\n";

   // count the number of elements in a set
   set <int>::difference_type  df_count = 0;
   s1_Iter = s1.begin( );
   while ( s1_Iter != s1_eIter)
   {
      df_count++;
      s1_Iter++;
   }

   cout << "The number of elements in the set s1 is: "
        << df_count << "." << endl;
}
```

```Output
The number '5' occurs 0 times in set s1.
The number '10' occurs 1 times in set s1.
The number '20' occurs 1 times in set s1.
The number of elements in the set s1 is: 2.
```

## <a name="emplace"></a>  set::emplace

(Hiçbir kopyalama veya taşıma işlemleri gerçekleştirilir) yerinde oluşturulmuş bir öğe ekler.

```cpp
template <class... Args>
pair<iterator, bool>
emplace(
    Args&&... args);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*bağımsız değişken*|Bir öğenin değerini eşdeğer sıralı bir öğe içermiyorsa kümesine eklenecek oluşturmak için iletilen bağımsız değişkenler.|

### <a name="return-value"></a>Dönüş Değeri

A [çifti](../standard-library/pair-structure.md) ekleme yapıldıysa, bool bileşen true değerini döndürür ve harita değeri sıralama, eşdeğer bir değer olan bir öğe içeriyorsa false. Dönüş değeri çiftinin yineleyici bileşeni (bool bileşen true ise) burada yeni bir öğe eklendi veya (bool bileşen false ise) öğenin zaten bulunduğu adresini döndürür.

### <a name="remarks"></a>Açıklamalar

Yineleyiciler ya da başvuruları, bu işlev tarafından geçersiz kılınır.

Yerleştirme sırasında bir özel durum oluşturulursa, kapsayıcının durumu değiştirilmez.

### <a name="example"></a>Örnek

```cpp
// set_emplace.cpp
// compile with: /EHsc
#include <set>
#include <string>
#include <iostream>

using namespace std;

template <typename S> void print(const S& s) {
    cout << s.size() << " elements: ";

    for (const auto& p : s) {
        cout << "(" << p << ") ";
    }

    cout << endl;
}

int main()
{
    set<string> s1;

    auto ret = s1.emplace("ten");

    if (!ret.second){
        cout << "Emplace failed, element with value \"ten\" already exists."
            << endl << "  The existing element is (" << *ret.first << ")"
            << endl;
        cout << "set not modified" << endl;
    }
    else{
        cout << "set modified, now contains ";
        print(s1);
    }
    cout << endl;

    ret = s1.emplace("ten");

    if (!ret.second){
        cout << "Emplace failed, element with value \"ten\" already exists."
            << endl << "  The existing element is (" << *ret.first << ")"
            << endl;
    }
    else{
        cout << "set modified, now contains ";
        print(s1);
    }
    cout << endl;
}

```

## <a name="emplace_hint"></a>  set::emplace_hint

(Hiçbir kopyalama veya taşıma işlemleri gerçekleştirilir) bir yerleşim ipucuyla birlikte yerinde oluşturulmuş bir öğe ekler.

```cpp
template <class... Args>
iterator emplace_hint(
    const_iterator where,
    Args&&... args);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*bağımsız değişken*|Belirlenen bu öğeyi zaten içeriyor veya zaten bir öğe değerini içerdiği sürece daha genel olarak, eşdeğer sıralanır sürece kümesine eklenecek bir öğe oluşturmak için iletilen bağımsız değişkenler.|
|*Burada*|Doğru ekleme noktasını için aramaya başlamak için bir yerde. (Bu noktanın hemen önceyse *burada*, ekleme Logaritmik süre yerine amorti edilmiş sabit zaman meydana gelebilir.)|

### <a name="return-value"></a>Dönüş Değeri

Yeni eklenen öğeye bir yineleyici.

Öğe zaten var olduğundan ekleme başarısız olursa var olan öğeye bir yineleyici döndürür.

### <a name="remarks"></a>Açıklamalar

Yineleyiciler ya da başvuruları, bu işlev tarafından geçersiz kılınır.

Yerleştirme sırasında bir özel durum oluşturulursa, kapsayıcının durumu değiştirilmez.

### <a name="example"></a>Örnek

```cpp
// set_emplace.cpp
// compile with: /EHsc
#include <set>
#include <string>
#include <iostream>

using namespace std;

template <typename S> void print(const S& s) {
    cout << s.size() << " elements: " << endl;

    for (const auto& p : s) {
        cout << "(" << p <<  ") ";
    }

    cout << endl;
}

int main()
{
    set<string> s1;

    // Emplace some test data
    s1.emplace("Anna");
    s1.emplace("Bob");
    s1.emplace("Carmine");

    cout << "set starting data: ";
    print(s1);
    cout << endl;

    // Emplace with hint
    // s1.end() should be the "next" element after this emplacement
    s1.emplace_hint(s1.end(), "Doug");

    cout << "set modified, now contains ";
    print(s1);
    cout << endl;
}

```

## <a name="empty"></a>  set::empty

Kümenin boş olup olmadığını sınar.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** kümesi boşsa; **false** kümesi boş ise.

### <a name="example"></a>Örnek

```cpp
// set_empty.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   set <int> s1, s2;
   s1.insert ( 1 );

   if ( s1.empty( ) )
      cout << "The set s1 is empty." << endl;
   else
      cout << "The set s1 is not empty." << endl;

   if ( s2.empty( ) )
      cout << "The set s2 is empty." << endl;
   else
      cout << "The set s2 is not empty." << endl;
}
```

```Output
The set s1 is not empty.
The set s2 is empty.
```

## <a name="end"></a>  set::End

past-the-end yineleyici döndürür.

```cpp
const_iterator end() const;


iterator end();
```

### <a name="return-value"></a>Dönüş Değeri

Past--end yineleyici. Ardından kümesi boşsa, `set::end() == set::begin()`.

### <a name="remarks"></a>Açıklamalar

**Son** kendine sonuna bir yineleyici geçmediğini sınamak için kullanılır.

Tarafından döndürülen değer **son** kaldırılmamalıdır.

Kod örneği için bkz: [set::find](#find).

## <a name="equal_range"></a>  set::equal_range

Yineleyicilerin bir çiftini, sırasıyla bir küme içindeki ilk öğeyi büyüktür veya eşittir belirtilen anahtar ve ilk öğeye anahtardan daha büyük bir anahtarla küme içindeki bir anahtarı ile döndürür.

```cpp
pair <const_iterator, const_iterator> equal_range (const Key& key) const;

pair <iterator, iterator> equal_range (const Key& key);
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
 Aranan kümesinden bir öğenin sıralama anahtarı ile Karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

İlk olduğu Yineleyicilerin bir çiftini [lower_bound](#lower_bound) , anahtar ve ikinci [upper_bound](#upper_bound) anahtarı.

Bir çiftin ilk yineleyicisi erişmeye `pr` üye işlevi tarafından döndürülen, kullanın `pr`. **İlk**ve alt sınır yineleyicinin başvuru kaldırma için \*( `pr`. **İlk**). Bir çiftin ikinci yineleyicisi erişmeye `pr` üye işlevi tarafından döndürülen, kullanın `pr`. **İkinci**ve üst sınır yineleyicinin başvuru kaldırma için \*( `pr`. **İkinci**).

### <a name="example"></a>Örnek

```cpp
// set_equal_range.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   typedef set<int, less< int > > IntSet;
   IntSet s1;
   set <int, less< int > > :: const_iterator s1_RcIter;

   s1.insert( 10 );
   s1.insert( 20 );
   s1.insert( 30 );

   pair <IntSet::const_iterator, IntSet::const_iterator> p1, p2;
   p1 = s1.equal_range( 20 );

   cout << "The upper bound of the element with "
        << "a key of 20 in the set s1 is: "
        << *(p1.second) << "." << endl;

   cout << "The lower bound of the element with "
        << "a key of 20 in the set s1 is: "
        << *(p1.first) << "." << endl;

   // Compare the upper_bound called directly
   s1_RcIter = s1.upper_bound( 20 );
   cout << "A direct call of upper_bound( 20 ) gives "
        << *s1_RcIter << "," << endl
        << "matching the 2nd element of the pair"
        << " returned by equal_range( 20 )." << endl;

   p2 = s1.equal_range( 40 );

   // If no match is found for the key,
   // both elements of the pair return end( )
   if ( ( p2.first == s1.end( ) ) && ( p2.second == s1.end( ) ) )
      cout << "The set s1 doesn't have an element "
           << "with a key less than 40." << endl;
   else
      cout << "The element of set s1 with a key >= 40 is: "
           << *(p1.first) << "." << endl;
}
```

```Output
The upper bound of the element with a key of 20 in the set s1 is: 30.
The lower bound of the element with a key of 20 in the set s1 is: 20.
A direct call of upper_bound( 20 ) gives 30,
matching the 2nd element of the pair returned by equal_range( 20 ).
The set s1 doesn't have an element with a key less than 40.
```

## <a name="erase"></a>  set::ERASE

Küme içindeki bir öğeyi veya öğelerin aralığını belirtilen konumlardan kaldırır veya belirtilen bir anahtarla eşleşen öğeleri kaldırır.

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

*Burada*<br/>
 Kaldırılacak öğenin konumu.

*ilk*<br/>
 Kaldırılacak ilk öğenin konumu.

*Son*<br/>
 Kaldırılacak yalnızca son öğenin ötesinde konumu.

*Key*<br/>
 Kaldırılacak öğe anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

İlk iki üye işlevleri için çift yönlü bir yineleyici, kaldırılan herhangi bir öğe veya böyle bir öğe varsa, küme sonuna bir öğe ilk öğeyi belirtir.

Üye işlevi için üçüncü kümeden kaldırılmış olan öğelerin sayısını döndürür.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

```cpp
// set_erase.cpp
// compile with: /EHsc
#include <set>
#include <string>
#include <iostream>
#include <iterator> // next() and prev() helper functions

using namespace std;

using myset = set<string>;

void printset(const myset& s) {
    for (const auto& iter : s) {
        cout << " [" << iter << "]";
    }
    cout << endl << "size() == " << s.size() << endl << endl;
}

int main()
{
    myset s1;

    // Fill in some data to test with, one at a time
    s1.insert("Bob");
    s1.insert("Robert");
    s1.insert("Bert");
    s1.insert("Rob");
    s1.insert("Bobby");

    cout << "Starting data of set s1 is:" << endl;
    printset(s1);
    // The 1st member function removes an element at a given position
    s1.erase(next(s1.begin()));
    cout << "After the 2nd element is deleted, the set s1 is:" << endl;
    printset(s1);

    // Fill in some data to test with, one at a time, using an intializer list
    myset s2{ "meow", "hiss", "purr", "growl", "yowl" };

    cout << "Starting data of set s2 is:" << endl;
    printset(s2);
    // The 2nd member function removes elements
    // in the range [First, Last)
    s2.erase(next(s2.begin()), prev(s2.end()));
    cout << "After the middle elements are deleted, the set s2 is:" << endl;
    printset(s2);

    myset s3;

    // Fill in some data to test with, one at a time, using emplace
    s3.emplace("C");
    s3.emplace("C#");
    s3.emplace("D");
    s3.emplace("D#");
    s3.emplace("E");
    s3.emplace("E#");
    s3.emplace("F");
    s3.emplace("F#");
    s3.emplace("G");
    s3.emplace("G#");
    s3.emplace("A");
    s3.emplace("A#");
    s3.emplace("B");

    cout << "Starting data of set s3 is:" << endl;
    printset(s3);
    // The 3rd member function removes elements with a given Key
    myset::size_type count = s3.erase("E#");
    // The 3rd member function also returns the number of elements removed
    cout << "The number of elements removed from s3 is: " << count << "." << endl;
    cout << "After the element with a key of \"E#\" is deleted, the set s3 is:" << endl;
    printset(s3);
}

```

## <a name="find"></a>  set::Find

Belirtilen anahtara denk bir anahtara sahip bir kümedeki bir öğenin konumunu gösteren bir yineleyici döndürür.

```cpp
iterator find(const Key& key);


const_iterator find(const Key& key) const;
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
 Aranan kümesinden bir öğenin sıralama anahtarı tarafından eşleştirilecek anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen anahtara sahip bir öğenin konumunu veya konumu küme içindeki son öğeyi adresleyen bir yineleyici (`set::end()`) anahtar için bir eşleşme varsa.

### <a name="remarks"></a>Açıklamalar

Üye işlevi bağımsız değişken eşdeğer anahtarla küme içindeki bir öğeyi başvuran bir yineleyici döndürür *anahtarı* comparability ilişkisi küçüktür göre sıralama sevk eden ikili bir koşul altında.

Varsa dönüş değerinin `find` atanan bir `const_iterator`, Küme nesnesi değiştirilemez. Varsa dönüş değerinin `find` atanan bir `iterator`, Küme nesnesi değiştirilebilir

### <a name="example"></a>Örnek

```cpp
// compile with: /EHsc /W4 /MTd
#include <set>
#include <iostream>
#include <vector>
#include <string>

using namespace std;

template <typename T> void print_elem(const T& t) {
    cout << "(" << t << ") ";
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
    set<int> s1({ 40, 45 });
    cout << "The starting set s1 is: " << endl;
    print_collection(s1);

    vector<int> v;
    v.push_back(43);
    v.push_back(41);
    v.push_back(46);
    v.push_back(42);
    v.push_back(44);
    v.push_back(44); // attempt a duplicate

    cout << "Inserting the following vector data into s1: " << endl;
    print_collection(v);

    s1.insert(v.begin(), v.end());

    cout << "The modified set s1 is: " << endl;
    print_collection(s1);
    cout << endl;
    findit(s1, 45);
    findit(s1, 6);
}

```

## <a name="get_allocator"></a>  set::get_allocator

Küme oluşturmak için kullanılan ayırıcı nesnesinin bir kopyasını döndürür.

```cpp
allocator_type get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şablon parametresi, bellek, yönetilecek kümesi tarafından kullanılan ayırıcı `Allocator`.

Daha fazla bilgi için `Allocator`, Açıklamalar bölümüne bakın [set sınıfı](../standard-library/set-class.md) konu.

### <a name="remarks"></a>Açıklamalar

Ayırıcılar kümesi sınıfı için sınıf depolama nasıl yönettiğini belirtin. C++ Standart Kitaplığı kapsayıcı sınıfları ile sağlanan varsayılan ayırıcılar çoğu programlama ihtiyaçları için yeterli olur. Yazma ve kendi allocator sınıfı kullanarak bir Gelişmiş C++ konudur.

### <a name="example"></a>Örnek

```cpp
// set_get_allocator.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   set <int>::allocator_type s1_Alloc;
   set <int>::allocator_type s2_Alloc;
   set <double>::allocator_type s3_Alloc;
   set <int>::allocator_type s4_Alloc;

   // The following lines declare objects
   // that use the default allocator.
   set <int> s1;
   set <int, allocator<int> > s2;
   set <double, allocator<double> > s3;

   s1_Alloc = s1.get_allocator( );
   s2_Alloc = s2.get_allocator( );
   s3_Alloc = s3.get_allocator( );

   cout << "The number of integers that can be allocated"
        << endl << "before free memory is exhausted: "
        << s2.max_size( ) << "." << endl;

   cout << "\nThe number of doubles that can be allocated"
        << endl << "before free memory is exhausted: "
        << s3.max_size( ) <<  "." << endl;

   // The following line creates a set s4
   // with the allocator of multiset s1.
   set <int> s4( less<int>( ), s1_Alloc );

   s4_Alloc = s4.get_allocator( );

   // Two allocators are interchangeable if
   // storage allocated from each can be
   // deallocated by the other
   if( s1_Alloc == s4_Alloc )
   {
      cout << "\nThe allocators are interchangeable."
           << endl;
   }
   else
   {
      cout << "\nThe allocators are not interchangeable."
           << endl;
   }
}
```

## <a name="insert"></a>  set::insert

Bir küme içine bir öğe veya öğe aralığı ekler.

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
|*VAL*|Değerini eşdeğer sıralı bir öğe içermiyorsa kümesine eklenecek bir öğenin değeri.|
|*Burada*|Doğru ekleme noktasını için aramaya başlamak için bir yerde. (Bu noktanın hemen önceyse *burada*, ekleme Logaritmik süre yerine amorti edilmiş sabit zaman meydana gelebilir.)|
|*ValTy*|Küme öğesi oluşturmak için kullanabileceğiniz bağımsız değişken türü belirten bir şablon parametresi [value_type](../standard-library/map-class.md#value_type)ve mükemmel ileten *Val* bağımsız değişken olarak.|
|*ilk*|Kopyalanacak ilk öğenin konumu.|
|*Son*|Kopyalanacak son öğenin ötesinde konumu.|
|*Inputıterator*|Gereksinimlerini karşılayan şablonu işlev bağımsız değişkeni bir [giriş yineleyici](../standard-library/input-iterator-tag-struct.md) oluşturmak için kullanılan bir tür öğelerine işaret eden [value_type](../standard-library/map-class.md#value_type) nesneleri.|
|*IList*|[İnitializer_list](../standard-library/initializer-list.md) öğeleri kopyalanacak.|

### <a name="return-value"></a>Dönüş Değeri

Tek öğeli üye işlevleri (1) ve (2) iade bir [çifti](../standard-library/pair-structure.md) olan **bool** bileşendir ekleme yaptıysanız true ve false kümesi eşdeğer değerinin bir öğe içeriyorsa sıralama. Yineleyici bileşeni dönüş değeri çiftinin yeni eklenen öğeye işaret ederse **bool** bileşendir true veya var olan öğeye varsa **bool** bileşen değer false.

İpucu ile tek öğe üye işlevleri, (3) ve (4), yeni bir öğe kümesine eklenmiş burada veya eşdeğer bir anahtara sahip bir öğe zaten var olan öğeye varsa konuma gösteren bir yineleyici döndürür.

### <a name="remarks"></a>Açıklamalar

Hiçbir yineleyiciler, işaretçiler veya başvurular, bu işlev tarafından geçersiz kılınır.

Bir özel durum oluşturulursa, yeni bir öğe ekleme sırasında kapsayıcının durumu değiştirilmez. Bir özel durum oluşturulursa, birden çok öğe ekleme sırasında kapsayıcı belirtilmeyen ancak geçerli bir durumda bırakılır.

Yineleyici bileşeni erişmek için bir `pair` `pr` kullanın, tek öğeli üye işlevleri tarafından döndürülen `pr.first`; döndürülen çiftin içinde yineleyicinin başvuru kaldırma, kullanın `*pr.first`, size bir öğe sağlar. Erişim için **bool** bileşeni, kullanım `pr.second`. Bu makaledeki örnek kod örneği için bkz.

[Value_type](../standard-library/map-class.md#value_type) küme ve, kapsayıcıya ait bir tür tanımı, kapsayıcısıdır `set<V>::value_type` türü `const V`.

Aralık üye işlevi (5) aralığında bir yineleyici tarafından ele alınan her öğe için karşılık gelen bir öğe değerleri dizisi ekler `[First, Last)`; bu nedenle `Last` takılı. Kapsayıcı üye işlevi `end()` kapsayıcıdaki son öğeden hemen sonra konuma başvuran — Örneğin, deyim `s.insert(v.begin(), v.end());` tüm öğeleri ekleme girişiminde `v` içine `s`. Yalnızca benzersiz değerler aralığında olan öğeler eklenir; Yinelenen göz ardı edilir. Hangi öğelerin reddedilir gözlemlemek için tek öğeli sürümleri kullanın `insert`.

Başlatıcı listesinde üye işlev (6) kullanan bir [initializer_list](../standard-library/initializer-list.md) öğeleri kümesine kopyalamak için.

Yerinde oluşturulmuş bir öğe ekleme — diğer bir deyişle, hiçbir kopyalama veya taşıma işlemleri gerçekleştirilir — bkz [set::emplace](#emplace) ve [set::emplace_hint](#emplace_hint).

### <a name="example"></a>Örnek

```cpp
// set_insert.cpp
// compile with: /EHsc
#include <set>
#include <iostream>
#include <string>
#include <vector>

using namespace std;

template <typename S> void print(const S& s) {
    cout << s.size() << " elements: ";

    for (const auto& p : s) {
        cout << "(" << p << ") ";
    }

    cout << endl;
}

int main()
{

    // insert single values
    set<int> s1;
    // call insert(const value_type&) version
    s1.insert({ 1, 10 });
    // call insert(ValTy&&) version
    s1.insert(20);

    cout << "The original set values of s1 are:" << endl;
    print(s1);

    // intentionally attempt a duplicate, single element
    auto ret = s1.insert(1);
    if (!ret.second){
        auto elem = *ret.first;
        cout << "Insert failed, element with value 1 already exists."
            << endl << "  The existing element is (" << elem << ")"
            << endl;
    }
    else{
        cout << "The modified set values of s1 are:" << endl;
        print(s1);
    }
    cout << endl;

    // single element, with hint
    s1.insert(s1.end(), 30);
    cout << "The modified set values of s1 are:" << endl;
    print(s1);
    cout << endl;

    // The templatized version inserting a jumbled range
    set<int> s2;
    vector<int> v;
    v.push_back(43);
    v.push_back(294);
    v.push_back(41);
    v.push_back(330);
    v.push_back(42);
    v.push_back(45);

    cout << "Inserting the following vector data into s2:" << endl;
    print(v);

    s2.insert(v.begin(), v.end());

    cout << "The modified set values of s2 are:" << endl;
    print(s2);
    cout << endl;

    // The templatized versions move-constructing elements
    set<string>  s3;
    string str1("blue"), str2("green");

    // single element
    s3.insert(move(str1));
    cout << "After the first move insertion, s3 contains:" << endl;
    print(s3);

    // single element with hint
    s3.insert(s3.end(), move(str2));
    cout << "After the second move insertion, s3 contains:" << endl;
    print(s3);
    cout << endl;

    set<int> s4;
    // Insert the elements from an initializer_list
    s4.insert({ 4, 44, 2, 22, 3, 33, 1, 11, 5, 55 });
    cout << "After initializer_list insertion, s4 contains:" << endl;
    print(s4);
    cout << endl;
}

```

## <a name="iterator"></a>  set::iterator

Bir sabit sağlayan bir tür [çift yönlü yineleyici](../standard-library/bidirectional-iterator-tag-struct.md) kümesindeki herhangi bir öğeyi okuyabilen.

```cpp
typedef implementation-defined iterator;
```

### <a name="example"></a>Örnek

Örneğin bakın [başlamak](#begin) bildirme ve kullanma konusunda bir örnek için bir `iterator`.

## <a name="key_comp"></a>  set::key_comp

Bir küme içindeki anahtarları sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır.

```cpp
key_compare key_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şablon parametresi olan bir alt öğeleri düzenlemek amacıyla kullanan işlev nesnesini döndürür `Traits`.

Daha fazla bilgi için `Traits` bkz [set sınıfı](../standard-library/set-class.md) konu.

### <a name="remarks"></a>Açıklamalar

Depolanan nesne üyesi işlevini tanımlar:

**bool operator()**( **const anahtar &**`_xVal`, **const anahtar &**`_yVal`);

döndüren **true** varsa `_xVal` önündeki ve eşit değildir `_yVal` sıralama düzeninde.

Unutmayın hem [key_compare](#key_compare) ve [value_compare](#value_compare) şablon parametresi için eş anlamlı sözcükler olan `Traits`. Her iki tür kümesi ve farklı olduğu multimap sınıfları ve eşleme ile uyumluluk için aynı oldukları multiset sınıfları için sağlanır.

### <a name="example"></a>Örnek

```cpp
// set_key_comp.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;

   set <int, less<int> > s1;
   set<int, less<int> >::key_compare kc1 = s1.key_comp( ) ;
   bool result1 = kc1( 2, 3 ) ;
   if( result1 == true )
   {
      cout << "kc1( 2,3 ) returns value of true, "
           << "where kc1 is the function object of s1."
           << endl;
   }
   else
   {
      cout << "kc1( 2,3 ) returns value of false "
           << "where kc1 is the function object of s1."
           << endl;
   }

   set <int, greater<int> > s2;
   set<int, greater<int> >::key_compare kc2 = s2.key_comp( ) ;
   bool result2 = kc2( 2, 3 ) ;
   if(result2 == true)
   {
      cout << "kc2( 2,3 ) returns value of true, "
           << "where kc2 is the function object of s2."
           << endl;
   }
   else
   {
      cout << "kc2( 2,3 ) returns value of false, "
           << "where kc2 is the function object of s2."
           << endl;
   }
}
```

```Output
kc1( 2,3 ) returns value of true, where kc1 is the function object of s1.
kc2( 2,3 ) returns value of false, where kc2 is the function object of s2.
```

## <a name="key_compare"></a>  set::key_compare

Küme içindeki iki öğenin göreli sırasını belirlemek için iki sıralama anahtarını karşılaştıran bir işlev nesnesi sağlayan bir tür.

```cpp
typedef Traits key_compare;
```

### <a name="remarks"></a>Açıklamalar

`key_compare` Şablon parametresi için bir eşanlamlı olduğu `Traits`.

Daha fazla bilgi için `Traits` bkz [set sınıfı](../standard-library/set-class.md) konu.

Unutmayın hem `key_compare` ve [value_compare](#value_compare) şablon parametresi için eş anlamlı sözcükler olan `Traits`. Her iki tür kümesi ve farklı olduğu multimap sınıfları ve eşleme ile uyumluluk için aynı oldukları multiset sınıfları için sağlanır.

### <a name="example"></a>Örnek

Örneğin bakın [key_comp](#key_comp) bildirme ve kullanma konusunda bir örnek için `key_compare`.

## <a name="key_type"></a>  set::key_type

Sıralama anahtarı olarak kapasitesi dahilinde bir küme öğesi olarak depolanan nesneyi tanımlayan tür.

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Açıklamalar

`key_type` Şablon parametresi için bir eşanlamlı olduğu `Key`.

Daha fazla bilgi için `Key`, Açıklamalar bölümüne bakın [set sınıfı](../standard-library/set-class.md) konu.

Unutmayın hem `key_type` ve [value_type](#value_type) şablon parametresi için eş anlamlı sözcükler olan `Key`. Her iki tür kümesi ve farklı olduğu multimap sınıfları ve eşleme ile uyumluluk için aynı oldukları multiset sınıfları için sağlanır.

### <a name="example"></a>Örnek

Örneğin bakın [value_type](#value_type) bildirme ve kullanma konusunda bir örnek için `key_type`.

## <a name="lower_bound"></a>  set::lower_bound

Bir yineleyiciyi belirtilen anahtardan daha büyük veya ona eşit bir anahtarla küme içindeki ilk öğeye döndürür.

```cpp
const_iterator lower_bound(const Key& key) const;

iterator lower_bound(const Key& key);
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
 Aranan kümesinden bir öğenin sıralama anahtarı ile Karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Bir yineleyici veya `const_iterator` adresleri anahtar için bağımsız değişken anahtardan daha büyük veya ona eşit olan veya hiçbir küme içindeki son öğeyi takip eden konumu ele bir anahtar ile eşleştiğinden emin bir kümedeki bir öğenin konumunu bulunamadı.

### <a name="example"></a>Örnek

```cpp
// set_lower_bound.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   set <int> s1;
   set <int> :: const_iterator s1_AcIter, s1_RcIter;

   s1.insert( 10 );
   s1.insert( 20 );
   s1.insert( 30 );

   s1_RcIter = s1.lower_bound( 20 );
   cout << "The element of set s1 with a key of 20 is: "
        << *s1_RcIter << "." << endl;

   s1_RcIter = s1.lower_bound( 40 );

   // If no match is found for the key, end( ) is returned
   if ( s1_RcIter == s1.end( ) )
      cout << "The set s1 doesn't have an element "
           << "with a key of 40." << endl;
   else
      cout << "The element of set s1 with a key of 40 is: "
           << *s1_RcIter << "." << endl;

   // The element at a specific location in the set can be found
   // by using a dereferenced iterator that addresses the location
   s1_AcIter = s1.end( );
   s1_AcIter--;
   s1_RcIter = s1.lower_bound( *s1_AcIter );
   cout << "The element of s1 with a key matching "
        << "that of the last element is: "
        << *s1_RcIter << "." << endl;
}
```

```Output
The element of set s1 with a key of 20 is: 20.
The set s1 doesn't have an element with a key of 40.
The element of s1 with a key matching that of the last element is: 30.
```

## <a name="max_size"></a>  set::max_size

Küme öğesinin maksimum uzunluğunu döndürür.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kümesinin maksimum olası uzunluğu.

### <a name="example"></a>Örnek

```cpp
// set_max_size.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   set <int> s1;
   set <int>::size_type i;

   i = s1.max_size( );
   cout << "The maximum possible length "
        << "of the set is " << i << "." << endl;
}
```

## <a name="op_eq"></a>  set::operator =

Bu öğelerini değiştirir `set` öğeleri başka bir kullanılarak `set`.

```cpp
set& operator=(const set& right);

set& operator=(set&& right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*sağ*|`set` İçin atanacak yeni öğeleri sağlayan `set`.|

### <a name="remarks"></a>Açıklamalar

Ürününün ilk sürümünü `operator=` kullanan bir [lvalue başvuru](../cpp/lvalue-reference-declarator-amp.md) için *doğru*öğelerden kopyalamak için *doğru* bu `set`.

Dosyanın ikinci sürümü kullanan bir [rvalue başvuru](../cpp/rvalue-reference-declarator-amp-amp.md) yönelik hakkı. Öğelerden taşır *doğru* bu `set`.

Bu öğeleri `set` işleç işlev yürütülmeden önce atılır.

### <a name="example"></a>Örnek

```cpp
// set_operator_as.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
   {
   using namespace std;
   set<int> v1, v2, v3;
   set<int>::iterator iter;

   v1.insert(10);

   cout << "v1 = " ;
   for (iter = v1.begin(); iter != v1.end(); iter++)
      cout << *iter << " ";
   cout << endl;

   v2 = v1;
   cout << "v2 = ";
   for (iter = v2.begin(); iter != v2.end(); iter++)
      cout << *iter << " ";
   cout << endl;

// move v1 into v2
   v2.clear();
   v2 = move(v1);
   cout << "v2 = ";
   for (iter = v2.begin(); iter != v2.end(); iter++)
      cout << *iter << " ";
   cout << endl;
   }
```

## <a name="pointer"></a>  set::pointer

Bir küme içindeki öğeye işaretçi sağlayan bir tür.

```cpp
typedef typename allocator_type::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir tür **işaretçi** bir öğenin değerini değiştirmek için kullanılabilir.

Çoğu durumda bir [yineleyici](#iterator) kümesi nesnesindeki öğelere erişmek için kullanılmalıdır.

## <a name="rbegin"></a>  set::rbegin

Ters çevrilen küme içindeki ilk öğeyi ele alan bir yineleyici döndürür.

```cpp
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen küme içindeki ilk öğeyi ele alan veya ne ters çevrilmeyen küme içindeki son öğeyi adresleyen ters iki yönlü yineleyici.

### <a name="remarks"></a>Açıklamalar

`rbegin` ters çevrilen küme ile kullanılan gibi [başlamak](#begin) ile bir küme kullanılır.

Varsa dönüş değeri `rbegin` atanan bir `const_reverse_iterator`, ardından küme nesnesi değiştirilemez. Varsa dönüş değeri `rbegin` atanan bir `reverse_iterator`, ardından küme nesnesi değiştirilebilir.

`rbegin` Geriye dönük olarak aracılığıyla yineleme yapmak için kullanılabilir.

### <a name="example"></a>Örnek

```cpp
// set_rbegin.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   set <int> s1;
   set <int>::iterator s1_Iter;
   set <int>::reverse_iterator s1_rIter;

   s1.insert( 10 );
   s1.insert( 20 );
   s1.insert( 30 );

   s1_rIter = s1.rbegin( );
   cout << "The first element in the reversed set is "
        << *s1_rIter << "." << endl;

   // begin can be used to start an iteration
   // throught a set in a forward order
   cout << "The set is:";
   for ( s1_Iter = s1.begin( ) ; s1_Iter != s1.end( ); s1_Iter++ )
      cout << " " << *s1_Iter;
   cout << endl;

   // rbegin can be used to start an iteration
   // throught a set in a reverse order
   cout << "The reversed set is:";
   for ( s1_rIter = s1.rbegin( ) ; s1_rIter != s1.rend( ); s1_rIter++ )
      cout << " " << *s1_rIter;
   cout << endl;

   // A set element can be erased by dereferencing to its key
   s1_rIter = s1.rbegin( );
   s1.erase ( *s1_rIter );

   s1_rIter = s1.rbegin( );
   cout << "After the erasure, the first element "
        << "in the reversed set is "<< *s1_rIter << "." << endl;
}
```

```Output
The first element in the reversed set is 30.
The set is: 10 20 30
The reversed set is: 30 20 10
After the erasure, the first element in the reversed set is 20.
```

## <a name="reference"></a>  set::Reference

Küme içinde depolanan öğeye başvuru sağlayan bir tür.

```cpp
typedef typename allocator_type::reference reference;
```

### <a name="example"></a>Örnek

```cpp
// set_reference.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   set <int> s1;

   s1.insert( 10 );
   s1.insert( 20 );

   // Declare and initialize a reference &Ref1 to the 1st element
   const int &Ref1 = *s1.begin( );

   cout << "The first element in the set is "
        << Ref1 << "." << endl;
}
```

```Output
The first element in the set is 10.
```

## <a name="rend"></a>  set::rend

Ters çevrilen küme içindeki son öğeden sonra gelen konumu ele alan bir yineleyici döndürür.

```cpp
const_reverse_iterator rend() const;

reverse_iterator rend();
```

### <a name="return-value"></a>Dönüş Değeri

Konumu (ters çevrilmeyen kümedeki ilk öğeyi önce gelen konum) ters çevrilen küme içindeki son öğeyi adresleyen ters iki yönlü yineleyici.

### <a name="remarks"></a>Açıklamalar

`rend` ters çevrilen küme ile kullanılan gibi [son](#end) ile bir küme kullanılır.

Varsa dönüş değeri `rend` atanan bir `const_reverse_iterator`, ardından küme nesnesi değiştirilemez. Varsa dönüş değeri `rend` atanan bir `reverse_iterator`, ardından küme nesnesi değiştirilebilir. Tarafından döndürülen değer `rend` kaldırılmamalıdır.

`rend` olup ters yineleyici kendine sonuna ulaşıp ulaşmadığını test etmek için kullanılabilir.

### <a name="example"></a>Örnek

```cpp
// set_rend.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main() {
   using namespace std;
   set <int> s1;
   set <int>::iterator s1_Iter;
   set <int>::reverse_iterator s1_rIter;
   set <int>::const_reverse_iterator s1_crIter;

   s1.insert( 10 );
   s1.insert( 20 );
   s1.insert( 30 );

   s1_rIter = s1.rend( );
   s1_rIter--;
   cout << "The last element in the reversed set is "
        << *s1_rIter << "." << endl;

   // end can be used to terminate an iteration
   // throught a set in a forward order
   cout << "The set is: ";
   for ( s1_Iter = s1.begin( ) ; s1_Iter != s1.end( ); s1_Iter++ )
      cout << *s1_Iter << " ";
   cout << "." << endl;

   // rend can be used to terminate an iteration
   // throught a set in a reverse order
   cout << "The reversed set is: ";
   for ( s1_rIter = s1.rbegin( ) ; s1_rIter != s1.rend( ); s1_rIter++ )
      cout << *s1_rIter << " ";
   cout << "." << endl;

   s1_rIter = s1.rend( );
   s1_rIter--;
   s1.erase ( *s1_rIter );

   s1_rIter = s1.rend( );
   --s1_rIter;
   cout << "After the erasure, the last element in the "
        << "reversed set is " << *s1_rIter << "." << endl;
}
```

## <a name="reverse_iterator"></a>  set::reverse_iterator

Ters döndürülmüş küme içindeki bir öğeyi okuyabilen veya değiştirebilen çift yönlü yineleyiciler sağlayan tür.

```cpp
typedef std::reverse_iterator<iterator> reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `reverse_iterator` kullanın ters kümesinde yinelemek için.

### <a name="example"></a>Örnek

Örneğin bakın [rbegin](#rbegin) bildirme ve kullanma konusunda bir örnek için `reverse_iterator`.

## <a name="set"></a>  set::set

Boş veya küme öğesinin tümünün veya diğer bir kısmının kopyası olan bir küme oluşturur.

```cpp
set();

explicit set(
    const Traits& Comp);

set(
    const Traits& Comp,
    const Allocator& Al);

set(
    const set& Right);

set(
    set&& Right);

set(
    initializer_list<Type> IList);

set(
    initializer_list<Type> IList,
    const Compare& Comp);

set(
    initializer_list<Type> IList,
    const Compare& Comp,
    const Allocator& Al);


template <class InputIterator>
set(
 InputIterator First,
    InputIterator Last);

template <class InputIterator>
set(
 InputIterator First,
    InputIterator Last,
    const Traits& Comp);

template <class InputIterator>
set(
 InputIterator First,
    InputIterator Last,
    const Traits& Comp,
    const Allocator& Al);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Al*|Varsayılan olarak bu küme nesnesi için kullanılacak depolama ayırıcı sınıf `Allocator`.|
|*Comp*|Karşılaştırma işlevi türü `const Traits` öğeler kümesinde varsayılan olarak sıralamak için kullanılan `Compare`.|
|*Rght*|Oluşturulan kümesi kopyası olacak olduğu kümesi.|
|*ilk*|Kopyalanacak öğe aralığındaki ilk öğenin konumu.|
|*Son*|Kopyalanacak öğe aralığının dışındaki ilk öğenin konumu.|
|*IList*|Öğelerin kopyalanacağı initializer_list.|

### <a name="remarks"></a>Açıklamalar

Tüm Oluşturucular, bellek depolama kümesi için yönetir ve bu daha sonra döndürülmesi çağırarak ayırıcı nesnesi türü depolamak [get_allocator](#get_allocator). Allocator parametresi, sınıf bildirimleri ve diğer ayırıcılar yerine kullanılan ön işleme makroları genellikle atlanır.

Tüm Oluşturucular, Ayarlar'ı başlatın.

Tüm oluşturucular türünün işlev nesnesini depolamak `Traits` anahtarları kümesi arasında bir sıralamayı oluşturmak için kullanılan ve, daha sonra döndürülmesi çağırarak [key_comp](#key_comp).

İlk üç Oluşturucular, bir boş ilk kümesi, ikinci belirtin karşılaştırma işlevinin türü belirtme (`comp`) öğeleri ve üçüncüsü sırasını oluşturmada kullanılacak ayırıcı açıkça belirtilmesi yazın (`al`) olması kullanılır. Anahtar sözcüğü **açık** otomatik tür dönüştürme belirli türdeki bastırır.

Dördüncü Oluşturucu kümesinin bir kopyasını belirtir `right`.

Sonraki üç oluşturucular bir initializer_list öğeleri belirtmek için kullanın.

Sonraki üç oluşturucular aralığını kopyalamaktadır [ `first`, `last`) sınıfın karşılaştırma işlevinin türü belirtilirken explicitness artan kümesinin `Traits` ve **ayırıcı**.

Sekizinci Oluşturucusu taşıyarak kümesinin bir kopyasını belirtir. `right`.

### <a name="example"></a>Örnek

```cpp
// set_set.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main()
{
    using namespace std;

    // Create an empty set s0 of key type integer
    set <int> s0;

    // Create an empty set s1 with the key comparison
    // function of less than, then insert 4 elements
    set <int, less<int> > s1;
    s1.insert(10);
    s1.insert(20);
    s1.insert(30);
    s1.insert(40);

    // Create an empty set s2 with the key comparison
    // function of less than, then insert 2 elements
    set <int, less<int> > s2;
    s2.insert(10);
    s2.insert(20);

    // Create a set s3 with the
    // allocator of set s1
    set <int>::allocator_type s1_Alloc;
    s1_Alloc = s1.get_allocator();
    set <int> s3(less<int>(), s1_Alloc);
    s3.insert(30);

    // Create a copy, set s4, of set s1
    set <int> s4(s1);

    // Create a set s5 by copying the range s1[ first,  last)
    set <int>::const_iterator s1_bcIter, s1_ecIter;
    s1_bcIter = s1.begin();
    s1_ecIter = s1.begin();
    s1_ecIter++;
    s1_ecIter++;
    set <int> s5(s1_bcIter, s1_ecIter);

    // Create a set s6 by copying the range s4[ first,  last)
    // and with the allocator of set s2
    set <int>::allocator_type s2_Alloc;
    s2_Alloc = s2.get_allocator();
    set <int> s6(s4.begin(), ++s4.begin(), less<int>(), s2_Alloc);

    cout << "s1 =";
    for (auto i : s1)
        cout << " " << i;
    cout << endl;

    cout << "s2 = " << *s2.begin() << " " << *++s2.begin() << endl;

    cout << "s3 =";
    for (auto i : s3)
        cout << " " << i;
    cout << endl;

    cout << "s4 =";
    for (auto i : s4)
        cout << " " << i;
    cout << endl;

    cout << "s5 =";
    for (auto i : s5)
        cout << " " << i;
    cout << endl;

    cout << "s6 =";
    for (auto i : s6)
        cout << " " << i;
    cout << endl;

    // Create a set by moving s5
    set<int> s7(move(s5));
    cout << "s7 =";
    for (auto i : s7)
        cout << " " << i;
    cout << endl;

    // Create a set with an initializer_list
    cout << "s8 =";
    set<int> s8{ { 1, 2, 3, 4 } };
    for (auto i : s8)
        cout << " " << i;
    cout << endl;

    cout << "s9 =";
    set<int> s9{ { 5, 6, 7, 8 }, less<int>() };
    for (auto i : s9)
        cout << " " << i;
    cout << endl;

    cout << "s10 =";
    set<int> s10{ { 10, 20, 30, 40 }, less<int>(), s9.get_allocator() };
    for (auto i : s10)
        cout << " " << i;
    cout << endl;
}

```

```Output
s1 = 10 20 30 40s2 = 10 20s3 = 30s4 = 10 20 30 40s5 = 10 20s6 = 10s7 = 10 20s8 = 1 2 3 4s9 = 5 6 7 8s10 = 10 20 30 40
```

## <a name="size"></a>  set::size

Kümedeki öğelerin sayısını döndürür.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ayarlama geçerli uzunluğu.

### <a name="example"></a>Örnek

```cpp
// set_size.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   set <int> s1;
   set <int> :: size_type i;

   s1.insert( 1 );
   i = s1.size( );
   cout << "The set length is " << i << "." << endl;

   s1.insert( 2 );
   i = s1.size( );
   cout << "The set length is now " << i << "." << endl;
}
```

```Output
The set length is 1.
The set length is now 2.
```

## <a name="size_type"></a>  set::size_type

Küme içindeki öğelerin sayısını temsil edebilen bir işaretsiz tamsayı türü.

```cpp
typedef typename allocator_type::size_type size_type;
```

### <a name="example"></a>Örnek

Örneğin bakın [boyutu](#size) bildirme ve kullanma örneği `size_type`

## <a name="swap"></a>  set::Swap

İki kümenin öğelerini birbiriyle değiştirir.

```cpp
void swap(
    set<Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
 Hedef ile değiştirilecek öğeleri sağlayan kümesi bağımsız değişkeni ayarlayın.

### <a name="remarks"></a>Açıklamalar

Üye işlev hiçbir başvurular, işaretçiler veya öğeleri değiştirilen iki kümenin öğelerini belirlemek yineleyicileri geçersiz kılar.

### <a name="example"></a>Örnek

```cpp
// set_swap.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   set <int> s1, s2, s3;
   set <int>::iterator s1_Iter;

   s1.insert( 10 );
   s1.insert( 20 );
   s1.insert( 30 );
   s2.insert( 100 );
   s2.insert( 200 );
   s3.insert( 300 );

   cout << "The original set s1 is:";
   for ( s1_Iter = s1.begin( ); s1_Iter != s1.end( ); s1_Iter++ )
      cout << " " << *s1_Iter;
   cout   << "." << endl;

   // This is the member function version of swap
   s1.swap( s2 );

   cout << "After swapping with s2, list s1 is:";
   for ( s1_Iter = s1.begin( ); s1_Iter != s1.end( ); s1_Iter++ )
      cout << " " << *s1_Iter;
   cout  << "." << endl;

   // This is the specialized template version of swap
   swap( s1, s3 );

   cout << "After swapping with s3, list s1 is:";
   for ( s1_Iter = s1.begin( ); s1_Iter != s1.end( ); s1_Iter++ )
      cout << " " << *s1_Iter;
   cout   << "." << endl;
}
```

```Output
The original set s1 is: 10 20 30.
After swapping with s2, list s1 is: 100 200.
After swapping with s3, list s1 is: 300.
```

## <a name="upper_bound"></a>  set::upper_bound

Bir yineleyici ilk öğeye bir kümesi, belirtilen anahtardan daha büyük bir anahtarla döndürür.

```cpp
const_iterator upper_bound(const Key& key) const;

iterator upper_bound(const Key& key);
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
 Aranan kümesinden bir öğenin sıralama anahtarı ile Karşılaştırılacak bağımsız değişken anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Bir `iterator` veya `const_iterator` adresleri anahtar için bağımsız değişken anahtardan daha büyük ya da hiçbir küme içindeki son öğeyi takip eden konumu ele bir anahtar ile eşleştiğinden emin küme içindeki bir öğenin konumunu bulunamadı.

### <a name="example"></a>Örnek

```cpp
// set_upper_bound.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   set <int> s1;
   set <int> :: const_iterator s1_AcIter, s1_RcIter;

   s1.insert( 10 );
   s1.insert( 20 );
   s1.insert( 30 );

   s1_RcIter = s1.upper_bound( 20 );
   cout << "The first element of set s1 with a key greater "
        << "than 20 is: " << *s1_RcIter << "." << endl;

   s1_RcIter = s1.upper_bound( 30 );

   // If no match is found for the key, end( ) is returned
   if ( s1_RcIter == s1.end( ) )
      cout << "The set s1 doesn't have an element "
           << "with a key greater than 30." << endl;
   else
      cout << "The element of set s1 with a key > 40 is: "
           << *s1_RcIter << "." << endl;

   // The element at a specific location in the set can be found
   // by using a dereferenced iterator addressing the location
   s1_AcIter = s1.begin( );
   s1_RcIter = s1.upper_bound( *s1_AcIter );
   cout << "The first element of s1 with a key greater than"
        << endl << "that of the initial element of s1 is: "
        << *s1_RcIter << "." << endl;
}
```

```Output
The first element of set s1 with a key greater than 20 is: 30.
The set s1 doesn't have an element with a key greater than 30.
The first element of s1 with a key greater than
that of the initial element of s1 is: 20.
```

## <a name="value_comp"></a>  set::value_comp

Küme içindeki öğe değerlerini sıralamak için kullanılan karşılaştırma nesnesinin bir kopyasını alır.

```cpp
value_compare value_comp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şablon parametresi olan bir alt öğeleri düzenlemek amacıyla kullanan işlev nesnesini döndürür `Traits`.

Daha fazla bilgi için `Traits` bkz [set sınıfı](../standard-library/set-class.md) konu.

### <a name="remarks"></a>Açıklamalar

Depolanan nesne üyesi işlevini tanımlar:

**bool işleci**( **const anahtar &**`_xVal`, **const anahtar &**`_yVal`);

döndüren **true** varsa `_xVal` önündeki ve eşit değildir `_yVal` sıralama düzeninde.

Unutmayın hem [value_compare](#value_compare) ve [key_compare](#key_compare) şablon parametresi için eş anlamlı sözcükler olan `Traits`. Her iki tür kümesi ve farklı olduğu multimap sınıfları ve eşleme ile uyumluluk için aynı oldukları multiset sınıfları için sağlanır.

### <a name="example"></a>Örnek

```cpp
// set_value_comp.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;

   set <int, less<int> > s1;
   set <int, less<int> >::value_compare vc1 = s1.value_comp( );
   bool result1 = vc1( 2, 3 );
   if( result1 == true )
   {
      cout << "vc1( 2,3 ) returns value of true, "
           << "where vc1 is the function object of s1."
           << endl;
   }
   else
   {
      cout << "vc1( 2,3 ) returns value of false, "
           << "where vc1 is the function object of s1."
           << endl;
   }

   set <int, greater<int> > s2;
   set<int, greater<int> >::value_compare vc2 = s2.value_comp( );
   bool result2 = vc2( 2, 3 );
   if( result2 == true )
   {
      cout << "vc2( 2,3 ) returns value of true, "
           << "where vc2 is the function object of s2."
           << endl;
   }
   else
   {
      cout << "vc2( 2,3 ) returns value of false, "
           << "where vc2 is the function object of s2."
           << endl;
   }
}
```

```Output
vc1( 2,3 ) returns value of true, where vc1 is the function object of s1.
vc2( 2,3 ) returns value of false, where vc2 is the function object of s2.
```

## <a name="value_compare"></a>  set::value_compare

Kümedeki kendi göreli sıralarını belirlemek için iki öğenin değerlerini karşılaştırabilen bir işlev nesnesi sağlayan tür.

```cpp
typedef key_compare value_compare;
```

### <a name="remarks"></a>Açıklamalar

`value_compare` Şablon parametresi için bir eşanlamlı olduğu `Traits`.

Daha fazla bilgi için `Traits` bkz [set sınıfı](../standard-library/set-class.md) konu.

Unutmayın hem [key_compare](#key_compare) ve `value_compare` şablon parametresi için eş anlamlı sözcükler olan `Traits`. Her iki tür kümesi ve farklı olduğu multimap sınıfları ve eşleme ile uyumluluk için aynı oldukları multiset sınıfları için sağlanır.

### <a name="example"></a>Örnek

Örneğin bakın [value_comp](#value_comp) bildirme ve kullanma konusunda bir örnek için `value_compare`.

## <a name="value_type"></a>  set::value_type

Bir değer olarak kapasitesi dahilinde bir küme öğesi olarak depolanan nesneyi tanımlayan tür.

```cpp
typedef Key value_type;
```

### <a name="remarks"></a>Açıklamalar

`value_type` Şablon parametresi için bir eşanlamlı olduğu `Key`.

Daha fazla bilgi için `Key`, Açıklamalar bölümüne bakın [set sınıfı](../standard-library/set-class.md) konu.

Unutmayın hem [key_type](#key_type) ve `value_type` şablon parametresi için eş anlamlı sözcükler olan `Key`. Her iki tür kümesi ve farklı olduğu multimap sınıfları ve eşleme ile uyumluluk için aynı oldukları multiset sınıfları için sağlanır.

### <a name="example"></a>Örnek

```cpp
// set_value_type.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   set <int> s1;
   set <int>::iterator s1_Iter;

   set <int>::value_type svt_Int;   // Declare value_type
   svt_Int = 10;            // Initialize value_type

   set <int> :: key_type skt_Int;   // Declare key_type
   skt_Int = 20;             // Initialize key_type

   s1.insert( svt_Int );         // Insert value into s1
   s1.insert( skt_Int );         // Insert key into s1

   // A set accepts key_types or value_types as elements
   cout << "The set has elements:";
   for ( s1_Iter = s1.begin( ) ; s1_Iter != s1.end( ); s1_Iter++)
      cout << " " << *s1_Iter;
   cout << "." << endl;
}
```

```Output
The set has elements: 10 20.
```

## <a name="see-also"></a>Ayrıca bkz.

[\<kümesi >](../standard-library/set.md)<br/>
[Kapsayıcılar](../cpp/containers-modern-cpp.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
