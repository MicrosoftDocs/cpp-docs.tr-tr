---
title: deque sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- deque/std::deque
- deque/std::deque::allocator_type
- deque/std::deque::const_iterator
- deque/std::deque::const_pointer
- deque/std::deque::const_reference
- deque/std::deque::const_reverse_iterator
- deque/std::deque::difference_type
- deque/std::deque::iterator
- deque/std::deque::pointer
- deque/std::deque::reference
- deque/std::deque::reverse_iterator
- deque/std::deque::size_type
- deque/std::deque::value_type
- deque/std::deque::assign
- deque/std::deque::at
- deque/std::deque::back
- deque/std::deque::begin
- deque/std::deque::cbegin
- deque/std::deque::cend
- deque/std::deque::clear
- deque/std::deque::crbegin
- deque/std::deque::crend
- deque/std::deque::emplace
- deque/std::deque::emplace_back
- deque/std::deque::emplace_front
- deque/std::deque::empty
- deque/std::deque::end
- deque/std::deque::erase
- deque/std::deque::front
- deque/std::deque::get_allocator
- deque/std::deque::insert
- deque/std::deque::max_size
- deque/std::deque::pop_back
- deque/std::deque::pop_front
- deque/std::deque::push_back
- deque/std::deque::push_front
- deque/std::deque::rbegin
- deque/std::deque::rend
- deque/std::deque::resize
- deque/std::deque::shrink_to_fit
- deque/std::deque::size
- deque/std::deque::swap
dev_langs:
- C++
helpviewer_keywords:
- std::deque [C++]
- std::deque [C++], allocator_type
- std::deque [C++], const_iterator
- std::deque [C++], const_pointer
- std::deque [C++], const_reference
- std::deque [C++], const_reverse_iterator
- std::deque [C++], difference_type
- std::deque [C++], iterator
- std::deque [C++], pointer
- std::deque [C++], reference
- std::deque [C++], reverse_iterator
- std::deque [C++], size_type
- std::deque [C++], value_type
- std::deque [C++], assign
- std::deque [C++], at
- std::deque [C++], back
- std::deque [C++], begin
- std::deque [C++], cbegin
- std::deque [C++], cend
- std::deque [C++], clear
- std::deque [C++], crbegin
- std::deque [C++], crend
- std::deque [C++], emplace
- std::deque [C++], emplace_back
- std::deque [C++], emplace_front
- std::deque [C++], empty
- std::deque [C++], end
- std::deque [C++], erase
- std::deque [C++], front
- std::deque [C++], get_allocator
- std::deque [C++], insert
- std::deque [C++], max_size
- std::deque [C++], pop_back
- std::deque [C++], pop_front
- std::deque [C++], push_back
- std::deque [C++], push_front
- std::deque [C++], rbegin
- std::deque [C++], rend
- std::deque [C++], resize
- std::deque [C++], shrink_to_fit
- std::deque [C++], size
- std::deque [C++], swap
ms.assetid: 64842ee5-057a-4063-8c16-4267a0332584
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d0ed609de9d36b602bf525a9643534cf5d1d55a8
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38963040"
---
# <a name="deque-class"></a>deque Sınıfı

Öğeleri belirli bir türden doğrusal bir düzende yerleştirir ve bir vektör gibi herhangi bir öğe ve verimli ekleme ve silme kapsayıcı arkasına hızlı rastgele erişim sağlar. Ancak, bir vektör aksine `deque` sınıfı da verimli ekleme ve silme kapsayıcının önünde destekler.

## <a name="syntax"></a>Sözdizimi

```unstlib
template <class Type, class Allocator =allocator<Type>>
class deque
```

### <a name="parameters"></a>Parametreler

*Tür* deque içinde depolanacak öğe veri türü.

*Allocator* deque'nın ayırma ve bellek ayırmayı kaldırma hakkındaki ayrıntıları içeren saklı ayırıcı nesnesini gösteren tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer: **ayırıcı\<türü > ***.*

## <a name="remarks"></a>Açıklamalar

Kapsayıcı türünün seçimi genelde uygulamanın gerektirdiği arama ve ekleme türüne dayalı olmalıdır. [Vektör](../standard-library/vector-class.md) herhangi bir öğeye rastgele erişim, bir premium olduğunda ve eklemeler ve silmeleri öğelerin, yalnızca bir sıralı yönetmek için tercih edilen kapsayıcı olmalıdır sıralamadaki sonunda gereklidir. Kapsayıcı listeleme performansını etkin olduğunda üstün eklemeler ve silmeler (sabit zaman içinde) dizisi içindeki herhangi bir konumda bir premium. Bu işlemlerin ortasındaysa dizisi öğesi kopyalar ve atamaları sayısı dizideki (doğrusal zaman) öğelerin orantılı gerektirir.

Deque reallocation bir üye işlevi ekleme veya dizi öğelerini silmek oluşur:

- Öğenin boş bir dizi eklenir ya da boş bir dizi bırakmak için bir öğe silinmesi, ardından yineleyiciler önceki tarafından döndürülen [başlamak](#begin) ve [son](#end) geçersiz hale gelir.

- Deque sonra tüm yineleyiciler, ancak başvuru ilk konumunda bir öğe eklediyseniz, var olan öğe geçersiz hale belirleyin.

- Bir öğe deque sonunda ardından eklenir, [son](#end) ve tüm yineleyiciler ancak varolan öğeleri geçersiz hale atadığınız hiçbir başvuru.

- Deque önündeki öğeyi silinir, yalnızca bu Yineleyici ve Silinen öğe başvuruları geçersiz duruma gelir.

- Son öğeyi deque sonundan silinir, son öğe için yalnızca bu Yineleyici ve Silinen öğe başvuruları geçersiz olur.

Aksi takdirde, ekleme veya bir öğeyi silme tüm yineleyiciler ve başvuruları geçersiz kılar.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[deque](#deque)|Oluşturur bir `deque`. Birçok oluşturucuya yeni içerikleri ayarlamak için sağlanan `deque` farklı şekillerde: boş; boş öğelerin belirtilen sayıyla yüklendi; taşınan veya başka bir kopyalanan içeriği `deque`; kopyaladığınız veya taşıdığınız bir yineleyici; kullanarak içeriği ve bir öğe kopyalanmasını `deque` `count` kez. Bazı oluşturucular kullanarak özel bir etkinleştirme `allocator` öğeleri oluşturmak için.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[allocator_type](#allocator_type)|Temsil eden bir tür `allocator` sınıfının `deque` nesne.|
|[const_iterator](#const_iterator)|Bir rastgele erişim yineleyicisi sağlayan bir tür erişebilir ve öğeleri okuma `deque` olarak `const`|
|[const_pointer](#const_pointer)|İçindeki bir öğeye işaretçi sağlayan bir tür bir `deque` gibi bir `const.`|
|[const_reference](#const_reference)|İçinde bir öğeye başvuru sağlayan bir tür bir `deque` okumak ve başka bir işlem olarak bir `const.`|
|[const_reverse_iterator](#const_reverse_iterator)|Bir rastgele erişim yineleyicisi sağlayan bir tür erişebilir ve öğeleri okuma `deque` olarak **const**. Deque tersten görüntülenir. Daha fazla bilgi için [reverse_iterator sınıfı](../standard-library/reverse-iterator-class.md)|
|[difference_type](#difference_type)|Aynı öğelere başvuran iki rastgele erişim yineleyici arasındaki farkı sağlayan bir tür `deque`.|
|[Yineleyici](#iterator)|Bir rastgele erişim yineleyicisi sağlayan bir tür okuyabilen veya değiştirebilen herhangi bir öğenin bir `deque`.|
|[İşaretçi](#pointer)|İçindeki bir öğeye işaretçi sağlayan bir tür bir `deque`.|
|[Başvuru](#reference)|İçinde depolanan öğeye başvuru sağlayan bir tür bir `deque`.|
|[reverse_iterator](#reverse_iterator)|Bir rastgele erişim yineleyicisi sağlayan bir tür okuyabilen veya değiştirebilen bir öğedeki bir `deque`. Deque ters sırada görüntülenir.|
|[size_type](#size_type)|İçindeki öğelerin sayısını sayar bir tür bir `deque`.|
|[value_type](#value_type)|İçinde depolanan veri türünü temsil eden bir tür bir `deque`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[Ata](#assign)|Öğelerden silen bir `deque` ve yeni bir öğe dizisi hedefe kopyalar `deque`.|
|[konumunda](#at)|Belirtilen bir konumda öğeye bir başvuru döndürür `deque`.|
|[Geri](#back)|Öğesinin son öğesinin bir başvuru döndürür `deque`.|
|[başlayın](#begin)|İçindeki ilk öğeyi ele alan bir rastgele erişim yineleyici döndüren `deque`.|
|[cbegin](#cbegin)|İlk öğe için sabit bir yineleyici döndürür `deque`.|
|[cend](#cend)|Bir rastgele erişim verir **const** hemen sonunu gösteren yineleyici `deque`.|
|[Temizle](#clear)|Tüm öğelerini siler bir `deque`.|
|[crbegin](#crbegin)|İçindeki ilk öğeye sabit bir rastgele erişim yineleyici döndüren bir `deque` ters sırada görüntülenebilir.|
|[crend](#crend)|İçindeki ilk öğeye sabit bir rastgele erişim yineleyici döndüren bir `deque` ters sırada görüntülenebilir.|
|[emplace](#emplace)|İçine yerinde oluşturulmuş bir öğe ekler `deque` belirtilen konumda.|
|[emplace_back](#emplace_back)|Sonuna yerinde oluşturulmuş bir öğe ekler `deque`.|
|[emplace_front](#emplace_front)|Başlatma yerinde oluşturulmuş bir öğe ekler `deque`.|
|[boş](#empty)|Döndürür **true** varsa `deque` sıfır öğe içeren ve **false** bir veya daha fazla öğe içeriyorsa.|
|[Son](#end)|Sonuna hemen ötesine işaret eden bir rasgele erişim yineleyicisi döndürür `deque`.|
|[silme](#erase)|Bir öğenin veya öğelerin aralığını kaldırır bir `deque` belirtilen konumlardan.|
|[Ön](#front)|İçindeki ilk öğeye bir başvuru döndürür bir `deque`.|
|[get_allocator](#get_allocator)|Bir kopyasını döndürür `allocator` oluşturmak için kullanılan nesne `deque`.|
|[Ekle](#insert)|Bir öğe, birkaç öğe veya bir dizi öğelerine ekler `deque` belirtilen konumda.|
|[max_size](#max_size)|Olası en büyük uzunluğunu döndürür `deque`.|
|[pop_back](#pop_back)|Sonundaki öğeyi siler `deque`.|
|[pop_front](#pop_front)|Başındaki öğeyi siler `deque`.|
|[push_back](#push_back)|Sonuna bir öğe ekler `deque`.|
|[push_front](#push_front)|Bir öğe ekler başlangıcına kadar `deque`.|
|[rbegin](#rbegin)|Ters çevrilen içindeki ilk öğeye bir rasgele erişim yineleyicisi döndürür `deque`.|
|[rend](#rend)|Bir rastgele erişim yineleyicisini son öğenin hemen ötesine işaret eden bir ters döndürür `deque`.|
|[yeniden boyutlandırma](#resize)|İçin yeni bir boyut belirtir bir `deque`.|
|[shrink_to_fit](#shrink_to_fit)|Aşırı kapasitesini atar.|
|[Boyutu](#size)|İçindeki öğelerin sayısını döndürür `deque`.|
|[değiştirme](#swap)|İki öğeleri birbiriyle değiştirir `deque`s.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleci&#91;&#93;](#op_at)|Bir başvuru döndürür `deque` öğesine belirtilen konumda.|
|[operator=](#op_eq)|Öğelerini değiştirir `deque` başka bir kopyasına sahip olan `deque`.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi**: \<deque >

## <a name="allocator_type"></a>  deque::allocator_type

Deque nesne için ayırıcı sınıf temsil eden tür.

```cpp
typedef Allocator allocator_type;
```

### <a name="remarks"></a>Açıklamalar

`allocator_type` Şablon parametresi için bir eşanlamlı olduğu `Allocator`.

### <a name="example"></a>Örnek

Örneğin bakın [get_allocator](#get_allocator).

## <a name="assign"></a>  deque::Assign

İki uçlu kuyruktaki öğeleri siler ve yeni bir öğe kümesini için hedef deque kopyalar.

```cpp
template <class InputIterator>
void assign(
    InputIterator First,
    InputIterator Last);

void assign(
    size_type Count,
    const Type& Val);

void assign(initializer_list<Type> IList);
```

### <a name="parameters"></a>Parametreler

*İlk* bağımsız değişken deque kopyalanacak ilk öğenin aralığındaki öğelerin konumu.

*Son* bağımsız değişken deque kopyalanacak öğe aralığının dışındaki ilk öğenin konumu.

*Sayısı* kopyası deque eklenen öğe sayısı.

*VAL* deque eklenen öğe değeri.

*IList* deque eklenen initializer_list.

### <a name="remarks"></a>Açıklamalar

Var olan öğeleri hedef deque içinde silinir sonra `assign` hedef deque içinde belirtilen bir aralıktaki öğelerin özgün deque ya da diğer bazı deque ekler veya hedef deque kopyalarını bir belirtilen değerin yeni bir öğe ekler.

### <a name="example"></a>Örnek

```cpp
// deque_assign.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>
#include <initializer_list>

int main()
{
    using namespace std;
    deque <int> c1, c2;
    deque <int>::const_iterator cIter;

    c1.push_back(10);
    c1.push_back(20);
    c1.push_back(30);
    c2.push_back(40);
    c2.push_back(50);
    c2.push_back(60);

    deque<int> d1{ 1, 2, 3, 4 };
    initializer_list<int> iList{ 5, 6, 7, 8 };
    d1.assign(iList);

    cout << "d1 = ";
    for (int i : d1)
        cout << i;
    cout << endl;

    cout << "c1 =";
    for (int i : c1)
        cout << i;
    cout << endl;

    c1.assign(++c2.begin(), c2.end());
    cout << "c1 =";
    for (int i : c1)
        cout << i;
    cout << endl;

    c1.assign(7, 4);
    cout << "c1 =";
    for (int i : c1)
        cout << i;
    cout << endl;

}

```

```Output
d1 = 5678c1 =102030c1 =5060c1 =4444444
```

## <a name="at"></a>  deque::AT

Deque içinde belirtilen konumdaki bir öğeye bir başvuru döndürür.

```cpp
reference at(size_type pos);

const_reference at(size_type pos) const;
```

### <a name="parameters"></a>Parametreler

*POS* öğe alt simge (veya konum numarası) içinde deque başvurmak için.

### <a name="return-value"></a>Dönüş Değeri

Varsa *pos* deque boyutundan büyükse `at` bir özel durum oluşturur.

### <a name="return-value"></a>Dönüş Değeri

Varsa dönüş değerinin `at` atanan bir `const_reference`, deque nesnesi değiştirilemez. Varsa dönüş değerinin `at` atanan bir `reference`, deque nesnesi değiştirilebilir.

### <a name="example"></a>Örnek

```cpp
// deque_at.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_back( 10 );
   c1.push_back( 20 );

   const int& i = c1.at( 0 );
   int& j = c1.at( 1 );
   cout << "The first element is " << i << endl;
   cout << "The second element is " << j << endl;
}
```

```Output
The first element is 10
The second element is 20
```

## <a name="back"></a>  deque::Back

Deque öğesinin son öğesinin bir başvuru döndürür.

```cpp
reference back();
const_reference back() const;
```

### <a name="return-value"></a>Dönüş Değeri

Deque son öğesi. Deque boş ise, dönüş değeri tanımsızdır.

### <a name="remarks"></a>Açıklamalar

Varsa dönüş değerinin `back` atanan bir `const_reference`, deque nesnesi değiştirilemez. Varsa dönüş değerinin `back` atanan bir `reference`, deque nesnesi değiştirilebilir.

Kullanılarak derlendiğinde [_ıterator_debug_level](../standard-library/iterator-debug-level.md) 1 veya 2 ' tanımlı, boş bir deque içinde bir öğeye erişmeyi denerseniz bir çalışma zamanı hatası oluşur.  Bkz: [Checked Iterators](../standard-library/checked-iterators.md) daha fazla bilgi için.

### <a name="example"></a>Örnek

```cpp
// deque_back.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_back( 10 );
   c1.push_back( 11 );

   int& i = c1.back( );
   const int& ii = c1.front( );

   cout << "The last integer of c1 is " << i << endl;
   i--;
   cout << "The next-to-last integer of c1 is " << ii << endl;
}
```

```Output
The last integer of c1 is 11
The next-to-last integer of c1 is 10
```

## <a name="begin"></a>  deque::Begin

Deque içindeki ilk öğeyi ele alan bir yineleyici döndürür.

```cpp
const_iterator begin() const;
iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

Deque veya sonra gelen konumu adresleyen bir boş deque ilk öğeyi ele alan bir rastgele erişim yineleyicisi.

### <a name="remarks"></a>Açıklamalar

Varsa dönüş değerinin `begin` atanan bir `const_iterator`, deque nesnesi değiştirilemez. Varsa dönüş değerinin `begin` atanan bir `iterator`, deque nesnesi değiştirilebilir.

### <a name="example"></a>Örnek

```cpp
// deque_begin.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;
   deque <int>::iterator c1_Iter;
   deque <int>::const_iterator c1_cIter;

   c1.push_back( 1 );
   c1.push_back( 2 );

   c1_Iter = c1.begin( );
   cout << "The first element of c1 is " << *c1_Iter << endl;

*c1_Iter = 20;
   c1_Iter = c1.begin( );
   cout << "The first element of c1 is now " << *c1_Iter << endl;

   // The following line would be an error because iterator is const
   // *c1_cIter = 200;
}
```

```Output
The first element of c1 is 1
The first element of c1 is now 20
```

## <a name="cbegin"></a>  deque::cbegin

Döndürür bir **const** aralıktaki ilk öğeyi adresleyen bir yineleyici.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

A **const** aralığı veya konuma boş bir aralığın ilk öğesine, rasgele erişim yineleyicisi (boş bir aralık için `cbegin() == cend()`).

### <a name="remarks"></a>Açıklamalar

Dönüş değeri ile `cbegin`, aralıktaki öğeler değiştirilemez.

Bu üye işlevi yerine kullanabileceğiniz `begin()` üye işlev dönüş değeri olacağını garanti etmek için `const_iterator`. Genellikle birlikte kullanılır [otomatik](../cpp/auto-cpp.md) kesinti anahtar sözcüğü, aşağıdaki örnekte gösterildiği gibi yazın. Örnekte, göz önünde bulundurun `Container` değiştirilebilir (olmayan `const`) destekleyen herhangi bir türdeki kapsayıcı `begin()` ve `cbegin()`.

```cpp
auto i1 = Container.begin();
// i1 is Container<T>::iterator
auto i2 = Container.cbegin();

// i2 is Container<T>::const_iterator
```

## <a name="cend"></a>  deque::cend

Döndürür bir **const** konuma bir aralıktaki son öğeyi ele alan bir yineleyici.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Aralığın hemen sonunu gösteren bir rastgele erişim yineleyicisi.

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

## <a name="clear"></a>  deque::Clear

İki uçlu kuyruktaki tüm öğelerini siler.

```cpp
void clear();
```

### <a name="example"></a>Örnek

```cpp
// deque_clear.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_back( 10 );
   c1.push_back( 20 );
   c1.push_back( 30 );

   cout << "The size of the deque is initially " << c1.size( ) << endl;
   c1.clear( );
   cout << "The size of the deque after clearing is " << c1.size( ) << endl;
}
```

```Output
The size of the deque is initially 3
The size of the deque after clearing is 0
```

## <a name="const_iterator"></a>  deque::const_iterator

Bir rastgele erişim yineleyicisi sağlayan bir tür erişebileceğiniz ve okuma bir **const** deque öğesinde.

```cpp
typedef implementation-defined const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_iterator` bir öğenin değerini değiştirmek için kullanılamaz.

### <a name="example"></a>Örnek

Örneğin bakın [geri](#back).

## <a name="const_pointer"></a>  deque::const_pointer

İşaretçi sağlayan bir **const** iki uçlu kuyruktaki öğesi.

```cpp
typedef typename Allocator::const_pointer const_pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_pointer` bir öğenin değerini değiştirmek için kullanılamaz. Bir [yineleyici](#iterator) genellikle sıradan çıkan bir öğeye erişmek için kullanılır.

## <a name="const_reference"></a>  deque::const_reference

Bir başvuru sağlayan bir tür bir **const** okumak ve gerçekleştirmek için iki uçlu kuyruktaki içinde depolanan öğenin **const** operations.

```cpp
typedef typename Allocator::const_reference const_reference;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_reference` bir öğenin değerini değiştirmek için kullanılamaz.

### <a name="example"></a>Örnek

```cpp
// deque_const_ref.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_back( 10 );
   c1.push_back( 20 );

   const deque <int> c2 = c1;
   const int &i = c2.front( );
   const int &j = c2.back( );
   cout << "The first element is " << i << endl;
   cout << "The second element is " << j << endl;

   // The following line would cause an error as c2 is const
   // c2.push_back( 30 );
}
```

```Output
The first element is 10
The second element is 20
```

## <a name="const_reverse_iterator"></a>  deque::const_reverse_iterator

Herhangi bir rastgele erişim yineleyicisi sağlayan bir tür okuma **const** deque öğesinde.

```cpp
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_reverse_iterator` bir öğenin değerini değiştiremez ve ters deque yinelemek için kullanılır.

### <a name="example"></a>Örnek

Örneğin bakın [rbegin](#rbegin) bildirme ve bir yineleyici kullanma konusunda bir örnek.

## <a name="crbegin"></a>  deque::crbegin

Ters çevrilen deque içindeki ilk öğeye sabit bir yineleyici döndürür.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir ilk öğeyi ele alan bir rastgele erişim yineleyicisini bir const [deque](../standard-library/deque-class.md) veya ne ters çevrilmeyen içindeki son öğeyi adresleyen `deque`.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri ile `crbegin`, `deque` nesnesi değiştirilemez.

### <a name="example"></a>Örnek

```cpp
// deque_crbegin.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> v1;
   deque <int>::iterator v1_Iter;
   deque <int>::const_reverse_iterator v1_rIter;

   v1.push_back( 1 );
   v1.push_back( 2 );

   v1_Iter = v1.begin( );
   cout << "The first element of deque is "
        << *v1_Iter << "." << endl;

   v1_rIter = v1.crbegin( );
   cout << "The first element of the reversed deque is "
        << *v1_rIter << "." << endl;
}
```

```Output
The first element of deque is 1.
The first element of the reversed deque is 2.
```

## <a name="crend"></a>  deque::crend

Sonra gelen konumu adresleyen ters iki uçlu kuyruktaki son öğeyi ele alan sabit bir yineleyici döndürür.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir const ters döndürülmüş bir içindeki son öğeden sonra gelen konumu ele rastgele erişim yineleyicisini [deque](../standard-library/deque-class.md) (ters çevrilmeyen deque ilk öğeyi önce gelen konum).

### <a name="remarks"></a>Açıklamalar

`crend` kullanılan bir ters ile `deque` gibi [array::cend](../standard-library/array-class-stl.md#cend) ile kullanılan bir `deque`.

Dönüş değeri ile `crend` (uygun şekilde indirildiği), `deque` nesnesi değiştirilemez.

`crend` olup ters Yineleyici, deque sonuna ulaşıp ulaşmadığını test etmek için kullanılabilir.

Tarafından döndürülen değer `crend` kaldırılmamalıdır.

### <a name="example"></a>Örnek

```cpp
// deque_crend.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> v1;
   deque <int>::const_reverse_iterator v1_rIter;

   v1.push_back( 1 );
   v1.push_back( 2 );

   for ( v1_rIter = v1.rbegin( ) ; v1_rIter != v1.rend( ) ; v1_rIter++ )
      cout << *v1_rIter << endl;
}
```

```Output
2
1
```

## <a name="deque"></a>  deque::deque

İki uçlu kuyruktaki belirli bir boyut veya öğeleri belirli bir değer veya belirli bir ayırıcı ile veya bir kopyası tüm veya bazı diğer deque bir parçası olarak oluşturur.

```cpp
deque();

explicit deque(const Allocator& Al);
explicit deque(size_type Count);
deque(size_type Count, const Type& Val);

deque(
    size_type Count,
    const Type& Val,
    const Allocator& Al);

deque(const deque& Right);

template <class InputIterator>
deque(InputIterator First,  InputIterator Last);

template <class InputIterator>
deque(
   InputIterator First,
   InputIterator Last,
   const Allocator& Al);

deque(initializer_list<value_type> IList, const Allocator& Al);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Al*|Bu nesneyle kullanılacak kaynak ayırıcı sınıfı.|
|*Sayısı*|Oluşturulan deque içindeki öğe sayısı.|
|*VAL*|Oluşturulan deque öğelerin değeri.|
|*Sağ*|Deque oluşturulmuş deque kopyası olacak olduğu.|
|*ilk*|Kopyalanacak öğe aralığındaki ilk öğenin konumu.|
|*Son*|Kopyalanacak öğe aralığının dışındaki ilk öğenin konumu.|
|* IList'|Kopyalanacağı initializer_list.|

### <a name="remarks"></a>Açıklamalar

Tüm oluşturucular ayırıcı nesnesini depolar (*Al*) ve deque başlatır.

İlk iki Oluşturucu boş bir başlangıç deque belirtin. İkinci bir ayırıcı türü de belirtir (`_Al`) kullanılacak.

Üçüncü Oluşturucu, belirtilen bir tekrarını belirtir (`count`) sınıfı için varsayılan değer öğelerinin `Type`.

Dördüncü ve beşinci oluşturucular yineleneceğini belirtir (*sayısı*) değerinin öğelerinin `val`.

Altıncı Oluşturucu deque bir kopyasını belirtir *sağ*.

Yedinci ve sekizinci oluşturucular aralığını kopyalamaktadır `[First, Last)` bir deque.

Deque yedinci Oluşturucusu taşır *sağ*.

Sekizinci Oluşturucusu bir initializer_list içeriğini kopyalar.

Hiçbiri, herhangi bir geçici yapıcıların gerçekleştirin.

### <a name="example"></a>Örnek

```cpp
/ compile with: /EHsc
#include <deque>
#include <iostream>
#include <forward_list>

int main()
{
    using namespace std;

    forward_list<int> f1{ 1, 2, 3, 4 };

    f1.insert_after(f1.begin(), { 5, 6, 7, 8 });

    deque <int>::iterator c1_Iter, c2_Iter, c3_Iter, c4_Iter, c5_Iter, c6_Iter;

    // Create an empty deque c0
    deque <int> c0;

    // Create a deque c1 with 3 elements of default value 0
    deque <int> c1(3);

    // Create a deque c2 with 5 elements of value 2
    deque <int> c2(5, 2);

    // Create a deque c3 with 3 elements of value 1 and with the
    // allocator of deque c2
    deque <int> c3(3, 1, c2.get_allocator());

    // Create a copy, deque c4, of deque c2
    deque <int> c4(c2);

    // Create a deque c5 by copying the range c4[ first,  last)
    c4_Iter = c4.begin();
    c4_Iter++;
    c4_Iter++;
    deque <int> c5(c4.begin(), c4_Iter);

    // Create a deque c6 by copying the range c4[ first,  last) and
    // c2 with the allocator of deque
    c4_Iter = c4.begin();
    c4_Iter++;
    c4_Iter++;
    c4_Iter++;
    deque <int> c6(c4.begin(), c4_Iter, c2.get_allocator());

    // Create a deque c8 by copying the contents of an initializer_list
    // using brace initialization
    deque<int> c8({ 1, 2, 3, 4 });

    initializer_list<int> iList{ 5, 6, 7, 8 };
    deque<int> c9( iList);

    cout << "c1 = ";
    for (int i : c1)
        cout << i << " ";
    cout << endl;

    cout << "c2 = ";
    for (int i : c2)
        cout << i << " ";
    cout << endl;

    cout << "c3 = ";
    for (int i : c3)
        cout << i << " ";
    cout << endl;

    cout << "c4 = ";
    for (int i : c4)
        cout << i << " ";
    cout << endl;

    cout << "c5 = ";
    for (int i : c5)
        cout << i << " ";
    cout << endl;

    cout << "c6 = ";
    for (int i : c6)
        cout << i << " ";
    cout << endl;

    // Move deque c6 to deque c7
    deque <int> c7(move(c6));
    deque <int>::iterator c7_Iter;

    cout << "c7 =";
    for (int i : c7)
        cout << i << " ";
    cout << endl;

    cout << "c8 = ";
    for (int i : c8)
        cout << i << " ";
    cout << endl;

    cout << "c9 = ";
    for (int i : c9)
        cout << i << " ";
    cout << endl;

    int x = 3;
}
// deque_deque.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
    using namespace std;
   deque <int>::iterator c1_Iter, c2_Iter, c3_Iter, c4_Iter, c5_Iter, c6_Iter;

    // Create an empty deque c0
    deque <int> c0;

    // Create a deque c1 with 3 elements of default value 0
    deque <int> c1( 3 );

    // Create a deque c2 with 5 elements of value 2
    deque <int> c2( 5, 2 );

    // Create a deque c3 with 3 elements of value 1 and with the
    // allocator of deque c2
    deque <int> c3( 3, 1, c2.get_allocator( ) );

    // Create a copy, deque c4, of deque c2
    deque <int> c4( c2 );

    // Create a deque c5 by copying the range c4[ first,  last)
    c4_Iter = c4.begin( );
    c4_Iter++;
    c4_Iter++;
    deque <int> c5( c4.begin( ), c4_Iter );

    // Create a deque c6 by copying the range c4[ first,  last) and
    // c2 with the allocator of deque
    c4_Iter = c4.begin( );
   c4_Iter++;
   c4_Iter++;
   c4_Iter++;
   deque <int> c6( c4.begin( ), c4_Iter, c2.get_allocator( ) );

    // Create a deque c8 by copying the contents of an initializer_list
    // using brace initialization
    deque<int> c8({ 1, 2, 3, 4 });

        initializer_list<int> iList{ 5, 6, 7, 8 };
    deque<int> c9( iList);

    cout << "c1 = ";
    for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
        cout << *c1_Iter << " ";
    cout << endl;

    cout << "c2 = ";
    for ( c2_Iter = c2.begin( ); c2_Iter != c2.end( ); c2_Iter++ )
        cout << *c2_Iter << " ";
    cout << endl;

    cout << "c3 = ";
    for ( c3_Iter = c3.begin( ); c3_Iter != c3.end( ); c3_Iter++ )
        cout << *c3_Iter << " ";
    cout << endl;

    cout << "c4 = ";
    for ( c4_Iter = c4.begin( ); c4_Iter != c4.end( ); c4_Iter++ )
        cout << *c4_Iter << " ";
    cout << endl;

    cout << "c5 = ";
    for ( c5_Iter = c5.begin( ); c5_Iter != c5.end( ); c5_Iter++ )
        cout << *c5_Iter << " ";
    cout << endl;

    cout << "c6 = ";
    for ( c6_Iter = c6.begin( ); c6_Iter != c6.end( ); c6_Iter++ )
        cout << *c6_Iter << " ";
    cout << endl;

    // Move deque c6 to deque c7
    deque <int> c7( move(c6) );
    deque <int>::iterator c7_Iter;

    cout << "c7 =" ;
    for ( c7_Iter = c7.begin( ) ; c7_Iter != c7.end( ) ; c7_Iter++ )
        cout << " " << *c7_Iter;
    cout << endl;

    cout << "c8 = ";
    for (int i : c8)
        cout << i << " ";
    cout << endl;

    cout << "c9 = ";
    or (int i : c9)
        cout << i << " ";
    cout << endl;
}
```

## <a name="difference_type"></a>  deque::difference_type

Aynı deque içindeki öğelere başvuran iki yineleyici arasındaki farkı sağlayan bir tür.

```cpp
typedef typename Allocator::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

A `difference_type` öğelerin iki işaretçisi arasındaki bir sayı olarak açıklanabilir.

### <a name="example"></a>Örnek

```cpp
// deque_diff_type.cpp
// compile with: /EHsc
#include <iostream>
#include <deque>
#include <algorithm>

int main( )
{
   using namespace std;

   deque <int> c1;
   deque <int>::iterator c1_Iter, c2_Iter;

   c1.push_back( 30 );
   c1.push_back( 20 );
   c1.push_back( 30 );
   c1.push_back( 10 );
   c1.push_back( 30 );
   c1.push_back( 20 );

   c1_Iter = c1.begin( );
   c2_Iter = c1.end( );

   deque <int>::difference_type df_typ1, df_typ2, df_typ3;

   df_typ1 = count( c1_Iter, c2_Iter, 10 );
   df_typ2 = count( c1_Iter, c2_Iter, 20 );
   df_typ3 = count( c1_Iter, c2_Iter, 30 );
   cout << "The number '10' is in c1 collection " << df_typ1 << " times.\n";
   cout << "The number '20' is in c1 collection " << df_typ2 << " times.\n";
   cout << "The number '30' is in c1 collection " << df_typ3 << " times.\n";
}
```

```Output
The number '10' is in c1 collection 1 times.
The number '20' is in c1 collection 2 times.
The number '30' is in c1 collection 3 times.
```

## <a name="emplace"></a>  deque::emplace

Belirtilen konumda deque içine yerinde oluşturulmuş bir öğe ekler.

```cpp
iterator emplace(
    const_iterator _Where,
    Type&& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*_Where*|Konumda [deque](../standard-library/deque-class.md) ilk öğeyi burada eklenir.|
|*VAL*|İçine eklenen öğenin değerini `deque`.|

### <a name="return-value"></a>Dönüş Değeri

İşlevi burada yeni bir öğe deque eklenmiş konumu gösteren bir yineleyici döndürür.

### <a name="remarks"></a>Açıklamalar

Herhangi bir ekleme işlemi pahalı, bkz: `deque` bir irdelemesi `deque` performans.

### <a name="example"></a>Örnek

```cpp
// deque_emplace.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> v1;
   deque <int>::iterator Iter;

   v1.push_back( 10 );
   v1.push_back( 20 );
   v1.push_back( 30 );

   cout << "v1 =" ;
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )
      cout << " " << *Iter;
   cout << endl;

// initialize a deque of deques by moving v1
   deque < deque <int> > vv1;

   vv1.emplace( vv1.begin(), move( v1 ) );
   if ( vv1.size( ) != 0 && vv1[0].size( ) != 0 )
      {
      cout << "vv1[0] =";
      for (Iter = vv1[0].begin( ); Iter != vv1[0].end( ); Iter++ )
         cout << " " << *Iter;
      cout << endl;
      }
}
```

```Output
v1 = 10 20 30
vv1[0] = 10 20 30
```

## <a name="emplace_back"></a>  deque::emplace_back

Deque sonuna yerinde oluşturulmuş bir öğe ekler.

```cpp
void emplace_back(Type&& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*VAL*|Sonuna eklenen öğe [deque](../standard-library/deque-class.md).|

### <a name="example"></a>Örnek

```cpp
// deque_emplace_back.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> v1;

   v1.push_back( 1 );
   if ( v1.size( ) != 0 )
      cout << "Last element: " << v1.back( ) << endl;

   v1.push_back( 2 );
   if ( v1.size( ) != 0 )
      cout << "New last element: " << v1.back( ) << endl;

// initialize a deque of deques by moving v1
   deque < deque <int> > vv1;

   vv1.emplace_back( move( v1 ) );
   if ( vv1.size( ) != 0 && vv1[0].size( ) != 0 )
      cout << "Moved last element: " << vv1[0].back( ) << endl;
}
```

```Output
Last element: 1
New last element: 2
Moved last element: 2
```

## <a name="emplace_front"></a>  deque::emplace_front

Deque sonuna yerinde oluşturulmuş bir öğe ekler.

```cpp
void emplace_front(Type&& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*VAL*|Başlangıcına eklenen öğe [deque](../standard-library/deque-class.md).|

### <a name="example"></a>Örnek

```cpp
// deque_emplace_front.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> v1;

   v1.push_back( 1 );
   if ( v1.size( ) != 0 )
      cout << "Last element: " << v1.back( ) << endl;

   v1.push_back( 2 );
   if ( v1.size( ) != 0 )
      cout << "New last element: " << v1.back( ) << endl;

// initialize a deque of deques by moving v1
   deque < deque <int> > vv1;

   vv1.emplace_front( move( v1 ) );
   if ( vv1.size( ) != 0 && vv1[0].size( ) != 0 )
      cout << "Moved last element: " << vv1[0].back( ) << endl;
}
```

```Output
Last element: 1
New last element: 2
Moved last element: 2
```

## <a name="empty"></a>  deque::empty

İki uçlu kuyruktaki boş olup olmadığını sınar.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** deque boşsa; **false** deque boş değilse.

### <a name="example"></a>Örnek

```cpp
// deque_empty.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_back( 10 );
   if ( c1.empty( ) )
      cout << "The deque is empty." << endl;
   else
      cout << "The deque is not empty." << endl;
}
```

```Output
The deque is not empty.
```

## <a name="end"></a>  deque::End

İki uçlu kuyruktaki son öğeyi takip eden konumu adresleyen bir yineleyici döndürür.

```cpp
const_iterator end() const;

iterator end();
```

### <a name="return-value"></a>Dönüş Değeri

İki uçlu kuyruktaki son öğeyi takip eden konumu ele alan bir rastgele erişim yineleyicisi. Deque boş ve deque::end ise deque::begin ==.

### <a name="remarks"></a>Açıklamalar

`end` bir yineleyicinin kendi deque sonuna ulaştı olup olmadığını sınamak için kullanılır.

### <a name="example"></a>Örnek

```cpp
// deque_end.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;
   deque <int>::iterator c1_Iter;

   c1.push_back( 10 );
   c1.push_back( 20 );
   c1.push_back( 30 );

   c1_Iter = c1.end( );
   c1_Iter--;
   cout << "The last integer of c1 is " << *c1_Iter << endl;

   c1_Iter--;
 *c1_Iter = 400;
   cout << "The new next-to-last integer of c1 is " << *c1_Iter << endl;

   // If a const iterator had been declared instead with the line:
   // deque <int>::const_iterator c1_Iter;
   // an error would have resulted when inserting the 400

   cout << "The deque is now:";
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
      cout << " " << *c1_Iter;
}
```

```Output
The last integer of c1 is 30
The new next-to-last integer of c1 is 400
The deque is now: 10 400 30
```

## <a name="erase"></a>  deque::ERASE

Bir öğenin veya öğelerin aralığını belirtilen konumlardan iki uçlu kuyruktaki kaldırır.

```cpp
iterator erase(iterator _Where);

iterator erase(iterator first, iterator last);
```

### <a name="parameters"></a>Parametreler

*_Where* deque kaldırılacak öğenin konumu.

*İlk* ilk öğenin konumunu deque kaldırıldı.

*Son* konumu yalnızca son öğeden sonra deque kaldırıldı.

### <a name="return-value"></a>Dönüş Değeri

Kaldırılan tüm öğelerin ötesindeki ilk öğeyi belirleyen bir rastgele erişim Yineleyici, veya böyle bir öğe varsa deque sonuna bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`erase` hiçbir zaman bir özel durum oluşturur.

### <a name="example"></a>Örnek

```cpp
// deque_erase.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;
   deque <int>::iterator Iter;

   c1.push_back( 10 );
   c1.push_back( 20 );
   c1.push_back( 30 );
   c1.push_back( 40 );
   c1.push_back( 50 );
   cout << "The initial deque is: ";
   for ( Iter = c1.begin( ); Iter != c1.end( ); Iter++ )
      cout << *Iter << " ";
   cout << endl;
   c1.erase( c1.begin( ) );
   cout << "After erasing the first element, the deque becomes:  ";
   for ( Iter = c1.begin( ); Iter != c1.end( ); Iter++ )
      cout << *Iter << " ";
   cout << endl;
   Iter = c1.begin( );
   Iter++;
   c1.erase( Iter, c1.end( ) );
   cout << "After erasing all elements but the first, deque becomes: ";
   for ( Iter = c1.begin( ); Iter != c1.end( ); Iter++ )
      cout << *Iter << " ";
   cout << endl;
}
```

```Output
The initial deque is: 10 20 30 40 50
After erasing the first element, the deque becomes:  20 30 40 50
After erasing all elements but the first, deque becomes: 20
```

## <a name="front"></a>  deque::Front

İki uçlu kuyruktaki ilk öğeye bir başvuru döndürür.

```cpp
reference front();

const_reference front() const;
```

### <a name="return-value"></a>Dönüş Değeri

Deque boş ise, dönüş tanımsızdır.

### <a name="remarks"></a>Açıklamalar

Varsa dönüş değerinin `front` atanan bir `const_reference`, deque nesnesi değiştirilemez. Varsa dönüş değerinin `front` atanan bir `reference`, deque nesnesi değiştirilebilir.

Kullanılarak derlendiğinde [_ıterator_debug_level](../standard-library/iterator-debug-level.md) 1 veya 2 ' tanımlı, boş bir deque içinde bir öğeye erişmeyi denerseniz bir çalışma zamanı hatası oluşur.  Bkz: [Checked Iterators](../standard-library/checked-iterators.md) daha fazla bilgi için.

### <a name="example"></a>Örnek

```cpp
// deque_front.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_back( 10 );
   c1.push_back( 11 );

   int& i = c1.front( );
   const int& ii = c1.front( );

   cout << "The first integer of c1 is " << i << endl;
   i++;
   cout << "The second integer of c1 is " << ii << endl;
}
```

```Output
The first integer of c1 is 10
The second integer of c1 is 11
```

## <a name="get_allocator"></a>  deque::get_allocator

Deque oluşturmak için kullanılan ayırıcı nesnesinin bir kopyasını döndürür.

```cpp
Allocator get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Deque tarafından kullanılan ayırıcı.

### <a name="remarks"></a>Açıklamalar

Deque sınıfı için ayırıcılar sınıfı depolama nasıl yönettiğini belirtin. C++ Standart Kitaplığı kapsayıcı sınıfları ile sağlanan varsayılan ayırıcılar çoğu programlama ihtiyaçları için yeterli. Yazma ve kendi allocator sınıfı kullanarak bir Gelişmiş C++ konudur.

### <a name="example"></a>Örnek

```cpp
// deque_get_allocator.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   // The following lines declare objects that use the default allocator.
   deque <int> c1;
   deque <int, allocator<int> > c2 = deque <int, allocator<int> >( allocator<int>( ) );

   // c3 will use the same allocator class as c1
   deque <int> c3( c1.get_allocator( ) );

   deque <int>::allocator_type xlst = c1.get_allocator( );
   // You can now call functions on the allocator class used by c1
}
```

## <a name="insert"></a>  deque::insert

Bir öğenin veya öğelerin bir sayı veya öğe aralığını belirtilen konumda deque ekler.

```cpp
iterator insert(
    const_iterator Where,
    const Type& Val);

iterator insert(
    const_iterator Where,
    Type&& Val);

void insert(
    iterator Where,
    size_type Count,
    const Type& Val);

template <class InputIterator>
void insert(
    iterator Where,
    InputIterator First,
    InputIterator Last);

iterator insert(
    iterator Where,initializer_list<Type>
IList);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Burada*|Hedef deque içindeki ilk öğeyi burada eklenir konumu.|
|*VAL*|Deque eklenen öğe değeri.|
|*Sayısı*|Deque eklenen öğe sayısı.|
|*ilk*|İçindeki bağımsız değişken deque kopyalanacak öğe aralığındaki ilk öğenin konumu.|
|*Son*|Kopyalanacak bağımsız değişken deque içindeki öğe aralığının dışındaki ilk öğenin konumu.|
|*IList*|Eklenecek öğelerin initializer_list.|

### <a name="return-value"></a>Dönüş Değeri

İlk iki INSERT işlevler burada yeni bir öğe deque eklenmiş konumu gösteren bir yineleyici döndürür.

### <a name="remarks"></a>Açıklamalar

Herhangi bir ekleme işlemi pahalı olabilir.

## <a name="iterator"></a>  deque::iterator

Okuma veya herhangi bir öğe iki uçlu kuyruktaki değiştirebilen bir rasgele erişim yineleyicisi sağlayan bir tür.

```cpp
typedef implementation-defined iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `iterator` bir öğenin değerini değiştirmek için kullanılabilir.

### <a name="example"></a>Örnek

Örneğin bakın [başlamak](#begin).

## <a name="max_size"></a>  deque::max_size

Deque maksimum uzunluğunu döndürür.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Deque maksimum olası uzunluğu.

### <a name="example"></a>Örnek

```cpp
// deque_max_size.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;
   deque <int>::size_type i;

   i = c1.max_size( );
   cout << "The maximum possible length of the deque is " << i << "." << endl;
}
```

## <a name="op_at"></a>  deque::operator]

Deque öğesine belirtilen konumda bir başvuru döndürür.

```cpp
reference operator[](size_type pos);

const_reference operator[](size_type pos) const;
```

### <a name="parameters"></a>Parametreler

*POS* başvurulmak üzere deque öğenin konumu.

### <a name="return-value"></a>Dönüş Değeri

Konumu bağımsız değişkeninde belirtilen öğeye bir başvuru. Belirtilen konumdaki deque boyutundan büyükse, sonuç tanımsızdır.

### <a name="remarks"></a>Açıklamalar

Varsa dönüş değerinin `operator[]` atanan bir `const_reference`, deque nesnesi değiştirilemez. Varsa dönüş değerinin `operator[]` atanan bir `reference`, deque nesnesi değiştirilebilir.

Kullanılarak derlendiğinde [_ıterator_debug_level](../standard-library/iterator-debug-level.md) 1 veya 2 ' tanımlı, deque sınırları dışında bir öğeye erişmeyi denerseniz bir çalışma zamanı hatası oluşur.  Bkz: [Checked Iterators](../standard-library/checked-iterators.md) daha fazla bilgi için.

### <a name="example"></a>Örnek

```cpp
// deque_op_ref.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_back( 10 );
   c1.push_back( 20 );
   cout << "The first integer of c1 is " << c1[0] << endl;
   int& i = c1[1];
   cout << "The second integer of c1 is " << i << endl;

}
```

```Output
The first integer of c1 is 10
The second integer of c1 is 20
```

## <a name="op_eq"></a>  deque::operator =

Başka bir deque öğeleri kullanarak bu deque öğelerini değiştirir.

```cpp
deque& operator=(const deque& right);

deque& operator=(deque&& right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*sağ*|Yeni içerik sağlar deque.|

### <a name="remarks"></a>Açıklamalar

İlk geçersiz kılma öğelerini bu deque kopyalar *doğru*, atamanın kaynağı. İkinci geçersiz kılma bu deque öğeleri taşınır *doğru*.

İşleç yürütülmeden önce bu deque içinde bulunan öğeleri kaldırılır.

### <a name="example"></a>Örnek

```cpp
// deque_operator_as.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>
using namespace std;

typedef deque<int> MyDeque;

template<typename MyDeque> struct S;

template<typename MyDeque> struct S<MyDeque&> {
  static void show( MyDeque& d ) {
    MyDeque::const_iterator iter;
    for (iter = d.cbegin(); iter != d.cend(); iter++)
       cout << *iter << " ";
    cout << endl;
  }
};

template<typename MyDeque> struct S<MyDeque&&> {
  static void show( MyDeque&& d ) {
    MyDeque::const_iterator iter;
    for (iter = d.cbegin(); iter != d.cend(); iter++)
       cout << *iter << " ";
cout << " via unnamed rvalue reference " << endl;
  }
};

int main( )
{
   MyDeque d1, d2;

   d1.push_back(10);
   d1.push_back(20);
   d1.push_back(30);
   d1.push_back(40);
   d1.push_back(50);

   cout << "d1 = " ;
   S<MyDeque&>::show( d1 );

   d2 = d1;
   cout << "d2 = ";
   S<MyDeque&>::show( d2 );

   cout << "     ";
   S<MyDeque&&>::show ( move< MyDeque& > (d1) );
 }
```

## <a name="pointer"></a>  deque::pointer

Öğeye işaretçi sağlayan bir [deque](../standard-library/deque-class.md).

```unstlib
typedef typename Allocator::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `pointer` bir öğenin değerini değiştirmek için kullanılabilir. Bir [yineleyici](#iterator) genellikle sıradan çıkan bir öğeye erişmek için kullanılır.

## <a name="pop_back"></a>  deque::pop_back

Deque sonundaki öğeyi silin.

```cpp
void pop_back();
```

### <a name="remarks"></a>Açıklamalar

Son öğe boş olmamalıdır. `pop_back` hiçbir zaman bir özel durum oluşturur.

### <a name="example"></a>Örnek

```cpp
// deque_pop_back.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_back( 1 );
   c1.push_back( 2 );
   cout << "The first element is: " << c1.front( ) << endl;
   cout << "The last element is: " << c1.back( ) << endl;

   c1.pop_back( );
   cout << "After deleting the element at the end of the deque, the "
      "last element is: " << c1.back( ) << endl;
}
```

```Output
The first element is: 1
The last element is: 2
After deleting the element at the end of the deque, the last element is: 1
```

## <a name="pop_front"></a>  deque::pop_front

Deque başındaki öğeyi silin.

```cpp
void pop_front();
```

### <a name="remarks"></a>Açıklamalar

İlk öğe boş olmamalıdır. `pop_front` hiçbir zaman bir özel durum oluşturur.

### <a name="example"></a>Örnek

```cpp
// deque_pop_front.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_back( 1 );
   c1.push_back( 2 );
   cout << "The first element is: " << c1.front( ) << endl;
   cout << "The second element is: " << c1.back( ) << endl;

   c1.pop_front( );
   cout << "After deleting the element at the beginning of the "
      "deque, the first element is: " << c1.front( ) << endl;
}
```

```Output
The first element is: 1
The second element is: 2
After deleting the element at the beginning of the deque, the first element is: 2
```

## <a name="push_back"></a>  deque::push_back

Deque sonuna bir öğe ekler.

```cpp
void push_back(const Type& val);

void push_back(Type&& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*VAL*|Deque sonuna eklenen öğe.|

### <a name="remarks"></a>Açıklamalar

Bir özel durum oluşturulursa, deque bırakılır değiştirilmeden ve özel durum yeniden oluşur.

## <a name="push_front"></a>  deque::push_front

Deque başlangıcına bir öğe ekler.

```cpp
void push_front(const Type& val);
void push_front(Type&& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*VAL*|Deque başlangıcına eklenen öğe.|

### <a name="remarks"></a>Açıklamalar

Bir özel durum oluşturulursa, deque bırakılır değiştirilmeden ve özel durum yeniden oluşur.

### <a name="example"></a>Örnek

```cpp
// deque_push_front.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>
#include <string>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_front( 1 );
   if ( c1.size( ) != 0 )
      cout << "First element: " << c1.front( ) << endl;

   c1.push_front( 2 );
   if ( c1.size( ) != 0 )
      cout << "New first element: " << c1.front( ) << endl;

// move initialize a deque of strings
   deque <string> c2;
   string str("a");

   c2.push_front( move( str ) );
   cout << "Moved first element: " << c2.front( ) << endl;
}
```

```Output
First element: 1
New first element: 2
Moved first element: a
```

## <a name="rbegin"></a>  deque::rbegin

Tersine çevrilmiş deque içindeki ilk öğeye bir yineleyici döndürür.

```cpp
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen deque ilk öğeyi ele alan veya ne ters çevrilmeyen deque içindeki son öğeyi adresleyen ters rastgele erişim yineleyici.

### <a name="remarks"></a>Açıklamalar

`rbegin` ters çevrilen bir deque ile kullanılan gibi [başlamak](#begin) bir deque ile kullanılır.

Varsa dönüş değerinin `rbegin` atanan bir `const_reverse_iterator`, deque nesnesi değiştirilemez. Varsa dönüş değerinin `rbegin` atanan bir `reverse_iterator`, deque nesnesi değiştirilebilir.

`rbegin` iki uçlu kuyruktaki geriye doğru gezinmek için kullanılabilir.

### <a name="example"></a>Örnek

```cpp
// deque_rbegin.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;
   deque <int>::iterator c1_Iter;
   deque <int>::reverse_iterator c1_rIter;

   // If the following line had replaced the line above, an error
   // would have resulted in the line modifying an element
   // (commented below) because the iterator would have been const
   // deque <int>::const_reverse_iterator c1_rIter;

   c1.push_back( 10 );
   c1.push_back( 20 );
   c1.push_back( 30 );

   c1_rIter = c1.rbegin( );
   cout << "Last element in the deque is " << *c1_rIter << "." << endl;

   cout << "The deque contains the elements: ";
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
      cout << *c1_Iter << " ";
   cout << "in that order.";
   cout << endl;

   // rbegin can be used to iterate through a deque in reverse order
   cout << "The reversed deque is: ";
   for ( c1_rIter = c1.rbegin( ); c1_rIter != c1.rend( ); c1_rIter++ )
      cout << *c1_rIter << " ";
   cout << endl;

   c1_rIter = c1.rbegin( );
 *c1_rIter = 40;  // This would have caused an error if a
                    // const_reverse iterator had been declared as
                    // noted above
   cout << "Last element in deque is now " << *c1_rIter << "." << endl;
}
```

```Output
Last element in the deque is 30.
The deque contains the elements: 10 20 30 in that order.
The reversed deque is: 30 20 10
Last element in deque is now 40.
```

## <a name="reference"></a>  deque::Reference

İki uçlu kuyruktaki içinde depolanan öğeye başvuru sağlayan bir tür.

```cpp
typedef typename Allocator::reference reference;
```

### <a name="example"></a>Örnek

```cpp
// deque_reference.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_back( 10 );
   c1.push_back( 20 );

   const int &i = c1.front( );
   int &j = c1.back( );
   cout << "The first element is " << i << endl;
   cout << "The second element is " << j << endl;
}
```

```Output
The first element is 10
The second element is 20
```

## <a name="rend"></a>  deque::rend

Sonra gelen konumu adresleyen ters iki uçlu kuyruktaki son öğeyi adresleyen bir yineleyici döndürür.

```cpp
const_reverse_iterator rend() const;

reverse_iterator rend();
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir deque (ters çevrilmeyen deque ilk öğeyi önce gelen konum) içindeki son öğeden sonra gelen konumu ele ters bir rastgele erişim yineleyicisi.

### <a name="remarks"></a>Açıklamalar

`rend` ters çevrilen bir deque ile kullanılan gibi [son](#end) bir deque ile kullanılır.

Varsa dönüş değerinin `rend` atanan bir `const_reverse_iterator`, deque nesnesi değiştirilemez. Varsa dönüş değerinin `rend` atanan bir `reverse_iterator`, deque nesnesi değiştirilebilir.

`rend` Ters Yineleyici, deque sonuna ulaştı olup olmadığını test etmek için kullanılabilir.

Tarafından döndürülen değer `rend` kaldırılmamalıdır.

### <a name="example"></a>Örnek

```cpp
// deque_rend.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;

   deque <int> c1;
   deque <int>::iterator c1_Iter;
   deque <int>::reverse_iterator c1_rIter;
   // If the following line had replaced the line above, an error
   // would have resulted in the line modifying an element
   // (commented below) because the iterator would have been const
   // deque <int>::const_reverse_iterator c1_rIter;

   c1.push_back( 10 );
   c1.push_back( 20 );
   c1.push_back( 30 );

   c1_rIter = c1.rend( );
   c1_rIter --; // Decrementing a reverse iterator moves it forward
                // in the deque (to point to the first element here)
   cout << "The first element in the deque is: " << *c1_rIter << endl;

   cout << "The deque is: ";
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
      cout << *c1_Iter << " ";
   cout << endl;

   // rend can be used to test if an iteration is through all of
   // the elements of a reversed deque
   cout << "The reversed deque is: ";
   for ( c1_rIter = c1.rbegin( ); c1_rIter != c1.rend( ); c1_rIter++ )
      cout << *c1_rIter << " ";
   cout << endl;

   c1_rIter = c1.rend( );
   c1_rIter--; // Decrementing the reverse iterator moves it backward
               // in the reversed deque (to the last element here)
 *c1_rIter = 40; // This modification of the last element would
                   // have caused an error if a const_reverse
                   // iterator had been declared (as noted above)
   cout << "The modified reversed deque is: ";
   for ( c1_rIter = c1.rbegin( ); c1_rIter != c1.rend( ); c1_rIter++ )
      cout << *c1_rIter << " ";
   cout << endl;
}
```

```Output
The first element in the deque is: 10
The deque is: 10 20 30
The reversed deque is: 30 20 10
The modified reversed deque is: 30 20 40
```

## <a name="resize"></a>  deque::Resize

İki uçlu kuyruktaki için yeni bir boyut belirtir.

```cpp
void resize(size_type _Newsize);

void resize(size_type _Newsize, Type val);
```

### <a name="parameters"></a>Parametreler

*_Newsize* deque yeni boyutu.

*VAL* yeni boyutu büyükse deque için eklenecek yeni öğelerin değeri, özgün boyutu. Değer atlanırsa yeni öğeler sınıfı için varsayılan değer atanır.

### <a name="remarks"></a>Açıklamalar

Deque'nın boyutu istenen boyuttan daha küçükse *_Newsize*, istenen boyuta ulaşana kadar öğeleri için deque eklenir.

Deque'nın boyutu istenen boyuttan daha büyük ise, deque boyutuna erişene kadar deque sonuna yakın öğeler silinir *_Newsize*.

Deque mevcut boyutu istenen boyutla aynıysa hiçbir işlem yapılmaz.

[boyutu](#size) deque geçerli boyutunu yansıtır.

### <a name="example"></a>Örnek

```cpp
// deque_resize.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_back( 10 );
   c1.push_back( 20 );
   c1.push_back( 30 );

   c1.resize( 4,40 );
   cout << "The size of c1 is: " << c1.size( ) << endl;
   cout << "The value of the last element is " << c1.back( ) << endl;

   c1.resize( 5 );
   cout << "The size of c1 is now: " << c1.size( ) << endl;
   cout << "The value of the last element is now " << c1.back( ) << endl;

   c1.resize( 2 );
   cout << "The reduced size of c1 is: " << c1.size( ) << endl;
   cout << "The value of the last element is now " << c1.back( ) << endl;
}
```

```Output
The size of c1 is: 4
The value of the last element is 40
The size of c1 is now: 5
The value of the last element is now 0
The reduced size of c1 is: 2
The value of the last element is now 20
```

## <a name="reverse_iterator"></a>  deque::reverse_iterator

Okuma veya ters deque bir öğedeki değiştirebilen bir rasgele erişim yineleyicisi sağlayan bir tür.

```cpp
typedef std::reverse_iterator<iterator> reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `reverse_iterator` kullanın deque yinelemek için.

### <a name="example"></a>Örnek

Rbegin için örneğe bakın.

## <a name="shrink_to_fit"></a>  deque::shrink_to_fit

Aşırı kapasitesini atar.

```cpp
void shrink_to_fit();
```

### <a name="remarks"></a>Açıklamalar

Belirlemek için taşınabilir bir yolu yoktur `shrink_to_fit` tarafından kullanılan depolama alanı azaltır bir [deque](../standard-library/deque-class.md).

### <a name="example"></a>Örnek

```cpp
// deque_shrink_to_fit.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> v1;
   //deque <int>::iterator Iter;

   v1.push_back( 1 );
   v1.push_back( 2 );
   cout << "Current size of v1 = "
      << v1.size( ) << endl;
   v1.shrink_to_fit();
   cout << "Current size of v1 = "
      << v1.size( ) << endl;
}
```

```Output
Current size of v1 = 1
Current size of v1 = 1
```

## <a name="size"></a>  deque::size

Deque öğelerin sayısını döndürür.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Deque geçerli uzunluğu.

### <a name="example"></a>Örnek

```cpp
// deque_size.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;
   deque <int>::size_type i;

   c1.push_back( 1 );
   i = c1.size( );
   cout << "The deque length is " << i << "." << endl;

   c1.push_back( 2 );
   i = c1.size( );
   cout << "The deque length is now " << i << "." << endl;
}
```

```Output
The deque length is 1.
The deque length is now 2.
```

## <a name="size_type"></a>  deque::size_type

İki uçlu kuyruktaki öğelerin sayısını sayar türü.

```cpp
typedef typename Allocator::size_type size_type;
```

### <a name="example"></a>Örnek

Örneğin bakın [boyutu](#size).

## <a name="swap"></a>  deque::Swap

İki deques öğelerini birbiriyle değiştirir.

```cpp
void swap(deque<Type, Allocator>& right);

friend void swap(deque<Type, Allocator>& left, deque<Type, Allocator>& right) template <class Type, class Allocator>
void swap(deque<Type, Allocator>& left, deque<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*doğru* değiştirilecek öğeleri sağlayan deque veya öğeleri olan deque olanlar değiştirilecek deque `left`.

*Sol* deque olanlar değiştirilecek öğeleri olan bir deque *doğru*.

### <a name="example"></a>Örnek

```cpp
// deque_swap.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1, c2, c3;
   deque <int>::iterator c1_Iter;

   c1.push_back( 1 );
   c1.push_back( 2 );
   c1.push_back( 3 );
   c2.push_back( 10 );
   c2.push_back( 20 );
   c3.push_back( 100 );

   cout << "The original deque c1 is:";
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
      cout << " " << *c1_Iter;
   cout << endl;

   c1.swap( c2 );

   cout << "After swapping with c2, deque c1 is:";
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
      cout << " " << *c1_Iter;
   cout << endl;

   swap( c1,c3 );

   cout << "After swapping with c3, deque c1 is:";
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
      cout << " " << *c1_Iter;
   cout << endl;

   swap<>(c1, c2);
   cout << "After swapping with c2, deque c1 is:";
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
      cout << " " << *c1_Iter;
   cout << endl;
}
```

```Output
The original deque c1 is: 1 2 3
After swapping with c2, deque c1 is: 10 20
After swapping with c3, deque c1 is: 100
After swapping with c2, deque c1 is: 1 2 3
```

## <a name="value_type"></a>  deque::value_type

İki uçlu kuyruktaki içinde depolanan veri türünü temsil eden tür.

```cpp
typedef typename Allocator::value_type value_type;
```

### <a name="remarks"></a>Açıklamalar

`value_type` Şablon parametresi için bir eşanlamlı olduğu `Type`.

### <a name="example"></a>Örnek

```cpp
// deque_value_type.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>
int main( )
{
   using namespace std;
   deque<int>::value_type AnInt;
   AnInt = 44;
   cout << AnInt << endl;
}
```

```Output
44
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
