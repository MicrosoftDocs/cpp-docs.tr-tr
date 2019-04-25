---
title: forward_list Sınıfı
ms.date: 11/04/2016
f1_keywords:
- forward_list/std::forward_list
- forward_list/std::forward_list::allocator_type
- forward_list/std::forward_list::const_iterator
- forward_list/std::forward_list::const_pointer
- forward_list/std::forward_list::const_reference
- forward_list/std::forward_list::difference_type
- forward_list/std::forward_list::iterator
- forward_list/std::forward_list::pointer
- forward_list/std::forward_list::reference
- forward_list/std::forward_list::size_type
- forward_list/std::forward_list::value_type
- forward_list/std::forward_list::assign
- forward_list/std::forward_list::before_begin
- forward_list/std::forward_list::begin
- forward_list/std::forward_list::cbefore_begin
- forward_list/std::forward_list::cbegin
- forward_list/std::forward_list::cend
- forward_list/std::forward_list::clear
- forward_list/std::forward_list::emplace_after
- forward_list/std::forward_list::emplace_front
- forward_list/std::forward_list::empty
- forward_list/std::forward_list::end
- forward_list/std::forward_list::erase_after
- forward_list/std::forward_list::front
- forward_list/std::forward_list::get_allocator
- forward_list/std::forward_list::insert_after
- forward_list/std::forward_list::max_size
- forward_list/std::forward_list::merge
- forward_list/std::forward_list::pop_front
- forward_list/std::forward_list::push_front
- forward_list/std::forward_list::remove
- forward_list/std::forward_list::remove_if
- forward_list/std::forward_list::resize
- forward_list/std::forward_list::reverse
- forward_list/std::forward_list::sort
- forward_list/std::forward_list::splice_after
- forward_list/std::forward_list::swap
- forward_list/std::forward_list::unique
helpviewer_keywords:
- std::forward_list
- std::forward_list::allocator_type
- std::forward_list::const_iterator
- std::forward_list::const_pointer
- std::forward_list::const_reference
- std::forward_list::difference_type
- std::forward_list::iterator
- std::forward_list::pointer
- std::forward_list::reference
- std::forward_list::size_type
- std::forward_list::value_type
- std::forward_list::assign
- std::forward_list::before_begin
- std::forward_list::begin
- std::forward_list::cbefore_begin
- std::forward_list::cbegin
- std::forward_list::cend
- std::forward_list::clear
- std::forward_list::emplace_after
- std::forward_list::emplace_front
- std::forward_list::empty
- std::forward_list::end
- std::forward_list::erase_after
- std::forward_list::front
- std::forward_list::get_allocator
- std::forward_list::insert_after
- std::forward_list::max_size
- std::forward_list::merge
- std::forward_list::pop_front
- std::forward_list::push_front
- std::forward_list::remove
- std::forward_list::remove_if
- std::forward_list::resize
- std::forward_list::reverse
- std::forward_list::sort
- std::forward_list::splice_after
- std::forward_list::swap
- std::forward_list::unique
ms.assetid: 89a3b805-ab60-4858-b772-5855130c11b1
ms.openlocfilehash: 5eaa8eba1904dc0a729fb66b280b8d3fa4bb78f1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62159788"
---
# <a name="forwardlist-class"></a>forward_list Sınıfı

Bir öğelerin değişen uzunluktaki dizisini denetleyen bir nesneyi tanımlar. Dizisi her tür üyesi içeren düğümleri listedir bağlı listesi olarak depolanan `Type`.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type,
    class Allocator = allocator<Type>>
class forward_list
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Tür*|Forward_list içinde depolanacak öğe veri türü.|
|*Ayırıcı*|Forward_list ayırma ve bellek ayırmayı kaldırma hakkındaki ayrıntıları içeren saklı ayırıcı nesnesini. Bu parametre isteğe bağlıdır. Varsayılan değer ayırıcı: < `Type`>.|

## <a name="remarks"></a>Açıklamalar

A `forward_list` nesnesi ayırır ve boşaltır sınıfın saklı nesnesi denetlediği dizi için depolama *ayırıcı* temel [allocator sınıfı](../standard-library/allocator-class.md) (genellikle olarak bilinen `std::allocator)`. Daha fazla bilgi için [ayırıcılar](../standard-library/allocators.md). Bir ayırıcı nesnenin şablon sınıfının bir nesnesiyle aynı dış arayüze sahip olması gerekir `allocator`.

> [!NOTE]
> Depolanan ayırıcı nesnenin kapsayıcı nesne atandığında kopyalanmaz.

Yineleyiciler, işaretçiler ve başvurular hale gelebilir geçersiz aracılığıyla kendi denetlenen dizideki öğelerin silinmesi, `forward_list`. Denetlenen dizi eklemeler ve splices gerçekleştirilen `forward_list` yineleyiciler geçersiz değil.

Denetlenen dizi eklemeler yapılan çağrılar tarafından oluşabilir [forward_list::insert_after](#insert_after), oluşturucuyu çağırır yalnızca üye işlev olduğu `Type(const  T&)`. `forward_list` Ayrıca arama taşıma oluşturucuları. Böyle bir ifade bir özel durum oluşturursa, kapsayıcı nesnesi herhangi bir yeni öğesi ekler ve özel durumu yeniden oluşturur. Bu nedenle, şablon sınıfın bir nesnesi `forward_list` böyle özel durumları oluştuğunda bilinen bir durumda bırakılır.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[forward_list](#forward_list)|Türünde bir nesne oluşturur `forward_list`.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[allocator_type](#allocator_type)|Bir iletme liste nesnesi için ayırıcı sınıf temsil eden tür.|
|[const_iterator](#const_iterator)|İleriye doğru listesi için sabit bir yineleyici sağlayan tür.|
|[const_pointer](#const_pointer)|Bir işaretçi sağlayan bir tür bir **const** ileriye doğru bir liste öğesi.|
|[const_reference](#const_reference)|İletme listedeki bir öğe için sabit bir başvuru sağlayan bir tür.|
|[difference_type](#difference_type)|Yineleyiciler tarafından gösterilen öğeler arasındaki bir aralıktaki ileriye doğru bir liste öğelerinin sayısını temsil etmek için kullanılabilen işaretli bir tamsayı türü.|
|[Yineleyici](#iterator)|İleriye doğru listesi için bir yineleyici sağlayan tür.|
|[İşaretçi](#pointer)|İletme listedeki bir öğeye işaretçi sağlayan bir tür.|
|[Başvuru](#reference)|İletme listedeki bir öğeye başvuru sağlayan bir tür.|
|[size_type](#size_type)|İki öğe arasındaki işaretsiz uzaklık temsil eden tür.|
|[value_type](#value_type)|Bir iletme listesinde depolanan öğenin türünü temsil eden tür.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[Ata](#assign)|İleriye doğru bir listeden öğeleri siler ve bir hedef İleri listesine yeni bir öğe kümesini kopyalar.|
|[before_begin](#before_begin)|İleriye doğru bir listedeki ilk öğeden önce konumu ele alan bir yineleyici döndürür.|
|[başlayın](#begin)|İleriye doğru bir listedeki ilk öğeyi ele alan bir yineleyici döndürür.|
|[cbefore_begin](#cbefore_begin)|İleriye doğru bir listedeki ilk öğeden önce konumu ele alan sabit bir yineleyici döndürür.|
|[cbegin](#cbegin)|İleriye doğru bir listedeki ilk öğeyi adresleyerek bir const yineleyici döndürür.|
|[cend](#cend)|İleriye doğru bir listedeki son öğeyi takip eden konumu ele alan sabit bir yineleyici döndürür.|
|[Temizle](#clear)|İleriye doğru bir listenin tüm öğelerini siler.|
|[emplace_after](#emplace_after)|Taşıma, yeni bir öğe belirtilen konuma sonra oluşturur.|
|[emplace_front](#emplace_front)|Listenin başına yerinde oluşturulmuş bir öğe ekler.|
|[boş](#empty)|İleriye doğru bir liste boş olup olmadığını sınar.|
|[Son](#end)|İleriye doğru bir listedeki son öğeden sonra gelen konumu ele alan bir yineleyici döndürür.|
|[erase_after](#erase_after)|Öğeleri sonra belirtilen konuma iletme listeden kaldırır.|
|[Ön](#front)|İleriye doğru bir listedeki ilk öğeye bir başvuru döndürür.|
|[get_allocator](#get_allocator)|İleriye doğru listesini oluşturmak için kullanılan ayırıcı nesnesinin bir kopyasını döndürür.|
|[insert_after](#insert_after)|Öğeleri İleri listeye sonra belirtilen konuma ekler.|
|[max_size](#max_size)|İleriye doğru bir listenin maksimum uzunluğunu döndürür.|
|[Birleştirme](#merge)|Bağımsız değişken listeden öğeleri kaldırır, bunları hedef İleri listesine ekler ve yeni birleşik öğeleri artan sırada veya başka bir belirtilen sırayla kümesini sıralar.|
|[pop_front](#pop_front)|İleriye doğru listesini başındaki öğeyi silin.|
|[push_front](#push_front)|İleriye doğru bir listenin başına bir öğe ekler.|
|[remove](#remove)|Belirtilen bir değerle eşleşen bir iletme listedeki öğeleri siler.|
|[remove_if](#remove_if)|Kendisi için belirtilen bir koşul sağlanırsa ileriye doğru bir listeden öğeleri siler.|
|[yeniden boyutlandırma](#resize)|İleriye doğru bir listesi için yeni bir boyut belirtir.|
|[geriye doğru](#reverse)|Öğeleri bir iletme listesinde oluşabilen sırasını tersine çevirir.|
|[Sıralama](#sort)|Öğeleri artan sırada veya bir koşula göre belirtilen bir düzende yerleştirir.|
|[splice_after](#splice_after)|Düğümler arasındaki bağlantılar restitches.|
|[değiştirme](#swap)|İletme iki listenin öğelerini değiştirir.|
|[unique](#unique)|Belirtilen testi geçmesi bitişik öğeyi kaldırır.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator=](#op_eq)|İletme listenin öğelerini başka bir ileri listesi bir kopyasını değiştirir.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<forward_list >

**Namespace:** std

## <a name="allocator_type"></a>  forward_list::allocator_type

Bir iletme liste nesnesi için ayırıcı sınıf temsil eden tür.

```cpp
typedef Allocator allocator_type;
```

### <a name="remarks"></a>Açıklamalar

`allocator_type` Şablon parametresi ayırıcı eşanlamlıdır.

## <a name="assign"></a>  forward_list::Assign

İleriye doğru bir listeden öğeleri siler ve bir hedef İleri listesine yeni bir öğe kümesini kopyalar.

```cpp
void assign(
    size_type Count,
    const Type& Val);

void assign(
    initializer_list<Type> IList);

template <class InputIterator>
void assign(InputIterator First, InputIterator Last);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*ilk*|Değiştirme aralığı başlangıcı.|
|*Son*|Değiştirme aralığın sonu.|
|*Sayısı*|Atanacak öğe sayısı.|
|*VAL*|Her öğe atanacak değer.|
|*Tür*|Değer türü.|
|* IList'| Kopyalanacağı initializer_list.|

### <a name="remarks"></a>Açıklamalar

Forward_list bir tamsayı türü ise, ilk üye işlevi aynı şekilde davranır `assign((size_type)First, (Type)Last)`. Aksi takdirde, ilk üye işlevi tarafından denetlenen dizinin değiştirir `*this` dizisiyle [ `First, Last)`, denetlenen dizideki örtüşmemelidir.

İkinci üye işlevi tarafından denetlenen dizinin değiştirir `*this` tekrarını ile `Count` değerin `Val`.

Üçüncü üye işlevi initializer_list öğelerini forward_list kopyalar.

## <a name="before_begin"></a>  forward_list::before_begin

İleriye doğru bir listedeki ilk öğeden önce konumu ele alan bir yineleyici döndürür.

```cpp
const_iterator before_begin() const;
iterator before_begin();
```

### <a name="return-value"></a>Dönüş Değeri

Dizinin ilk öğesi hemen önce (veya boş bir dizi sonuna hemen önce) gösteren bir ileriye doğru yineleyici.

### <a name="remarks"></a>Açıklamalar

## <a name="begin"></a>  forward_list::Begin

İleriye doğru bir listedeki ilk öğeyi ele alan bir yineleyici döndürür.

```cpp
const_iterator begin() const;
iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

İlk öğede dizisi (veya yalnızca boş bir dizi bitiminin ötesinde) gösteren bir ileriye doğru yineleyici.

### <a name="remarks"></a>Açıklamalar

## <a name="cbefore_begin"></a>  forward_list::cbefore_begin

İleriye doğru bir listedeki ilk öğeden önce konumu ele alan sabit bir yineleyici döndürür.

```cpp
const_iterator cbefore_begin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dizinin ilk öğesi hemen önce (veya boş bir dizi sonuna hemen önce) gösteren bir ileriye doğru yineleyici.

### <a name="remarks"></a>Açıklamalar

## <a name="cbegin"></a>  forward_list::cbegin

Döndürür bir **const** aralıktaki ilk öğeyi adresleyen bir yineleyici.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

A **const** aralığı veya konuma boş bir aralığın ilk öğesine konumundaki ileriye doğru erişim yineleyicisi (boş bir aralık için `cbegin() == cend()`).

### <a name="remarks"></a>Açıklamalar

Dönüş değeri ile `cbegin`, aralıktaki öğeler değiştirilemez.

Bu üye işlevi yerine kullanabileceğiniz `begin()` üye işlev dönüş değeri olacağını garanti etmek için `const_iterator`. Genellikle birlikte kullanılır [otomatik](../cpp/auto-cpp.md) kesinti anahtar sözcüğü, aşağıdaki örnekte gösterildiği gibi yazın. Örnekte, göz önünde bulundurun `Container` değiştirilebilir (olmayan **const**) destekleyen herhangi bir türdeki kapsayıcı `begin()` ve `cbegin()`.

```cpp
auto i1 = Container.begin();
// i1 is Container<T>::iterator
auto i2 = Container.cbegin();
// i2 is Container<T>::const_iterator
```

## <a name="cend"></a>  forward_list::cend

Döndürür bir **const** konuma bir aralıktaki son öğeyi ele alan bir yineleyici.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Aralığının hemen sonunu gösteren bir ileriye doğru erişim yineleyicisi.

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

## <a name="clear"></a>  forward_list::Clear

İleriye doğru bir listenin tüm öğelerini siler.

```cpp
void clear();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlevini çağırır. `erase_after(before_begin(), end()).`

## <a name="const_iterator"></a>  forward_list::const_iterator

İleriye doğru listesi için sabit bir yineleyici sağlayan tür.

```cpp
typedef implementation-defined const_iterator;
```

### <a name="remarks"></a>Açıklamalar

`const_iterator` Denetlenen dizi için sabit bir ileriye doğru yineleyici olarak hizmet verebilen bir nesneyi tanımlar. Açıklanmıştır bir uygulama tanımlı türünün eşanlamlısı olarak burada.

## <a name="const_pointer"></a>  forward_list::const_pointer

Bir işaretçi sağlayan bir tür bir **const** ileriye doğru bir liste öğesi.

```cpp
typedef typename Allocator::const_pointer
    const_pointer;
```

### <a name="remarks"></a>Açıklamalar

## <a name="const_reference"></a>  forward_list::const_reference

İletme listedeki bir öğe için sabit bir başvuru sağlayan bir tür.

```cpp
typedef typename Allocator::const_reference const_reference;
```

### <a name="remarks"></a>Açıklamalar

## <a name="difference_type"></a>  forward_list::difference_type

Yineleyiciler tarafından gösterilen öğeler arasındaki bir aralıktaki ileriye doğru bir liste öğelerinin sayısını temsil etmek için kullanılabilen işaretli bir tamsayı türü.

```cpp
typedef typename Allocator::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

`difference_type` adresleri denetlenen dizideki herhangi iki öğe arasındaki farkı temsil edebilen bir nesneyi tanımlar.

## <a name="emplace_after"></a>  forward_list::emplace_after

Taşıma, yeni bir öğe belirtilen konuma sonra oluşturur.

```cpp
template <class T>
iterator emplace_after(const_iterator Where, Type&& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Burada*|Burada yeni bir öğe oluşturulur hedef iletme listesindeki konumu.|
|*VAL*|Oluşturucu bağımsız değişkeni.|

### <a name="return-value"></a>Dönüş Değeri

Yeni eklenen öğeyi belirleyen bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev oluşturucu bağımsız değişkenleri olan bir öğe ekler *val* işaret ettiği öğeden sonra *burada* denetlenen dizideki. Davranışını aksi aynıdır [forward_list::insert_after](#insert_after).

## <a name="emplace_front"></a>  forward_list::emplace_front

Listenin başına yerinde oluşturulmuş bir öğe ekler.

```cpp
template <class Type>
void emplace_front(Type&& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*VAL*|Öğe iletme listenin başına eklenir.|

### <a name="remarks"></a>Açıklamalar

Bu üye işlev oluşturucu bağımsız değişkenleri olan bir öğe ekler `_ val` denetlenen dizinin sonunda.

Bir özel durum oluşturulursa, kapsayıcı bırakılır değiştirilmeden ve özel durum yeniden oluşur.

## <a name="empty"></a>  forward_list::empty

İleriye doğru bir liste boş olup olmadığını sınar.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** iletme liste boş; Aksi takdirde ise **false**.

## <a name="end"></a>  forward_list::End

İleriye doğru bir listedeki son öğeden sonra gelen konumu ele alan bir yineleyici döndürür.

```cpp
const_iterator end() const;
iterator end();
```

### <a name="return-value"></a>Dönüş Değeri

Dizinin sonunu yalnızca ileri doğru yineleyici.

## <a name="erase_after"></a>  forward_list::erase_after

Öğeleri sonra belirtilen konuma iletme listeden kaldırır.

```cpp
iterator erase_after(const_iterator Where);
iterator erase_after(const_iterator first, const_iterator last);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Burada*|Hedef iletme listesindeki öğe nerede silinir konumu.|
|*ilk*|Silme aralığını başlangıcı.|
|*Son*|Silmek için aralığın sonu.|

### <a name="return-value"></a>Dönüş Değeri

Kaldırılan tüm öğelerin ötesindeki ilk öğeyi belirleyen bir yineleyici veya [forward_list::end](#end) böyle bir öğe varsa.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi, denetimli bir öğeyi kaldırır hemen sonrasına sıra *nerede*.

İkinci üye işlevi öğeleri denetlenen dizinin aralıktaki kaldırır. `( first,  last)` (her iki bitiş noktası dahildir).

Silme `N` öğeleri nedenleri `N` yıkıcı çağrıları. [Reallocation](../standard-library/forward-list-class.md) yineleyiciler ve başvurular için silinen öğeleri geçersiz eşlenmelerine gerçekleşir.

Üye işlevleri, hiçbir zaman bir özel durum.

## <a name="forward_list"></a>  forward_list::forward_list

Türünde bir nesne oluşturur `forward_list`.

```cpp
forward_list();
explicit forward_list(const Allocator& Al);
explicit forward_list(size_type Count);
forward_list(size_type Count, const Type& Val);
forward_list(size_type Count, const Type& Val, const Allocator& Al);
forward_list(const forward_list& Right);
forward_list(const forward_list& Right, const Allocator& Al);
forward_list(forward_list&& Right);
forward_list(forward_list&& Right, const Allocator& Al);
forward_list(initializer_list<Type> IList, const Alloc& Al);
template <class InputIterator>
forward_list(InputIterator First, InputIterator Last);
template <class InputIterator>
forward_list(InputIterator First, InputIterator Last, const Allocator& Al);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Al*|Bu nesneyle kullanılacak kaynak ayırıcı sınıfı.|
|*Sayısı*|Oluşturulan listedeki öğelerin sayısı.|
|*VAL*|Oluşturulan listedeki öğelerin değeri.|
|*sağ*|Oluşturulan listenin kopyası olacak olduğu listesi.|
|*ilk*|Kopyalanacak öğe aralığındaki ilk öğenin konumu.|
|*Son*|Kopyalanacak öğe aralığının dışındaki ilk öğenin konumu.|
|*IList*|Kopyalanacağı initializer_list.|

### <a name="remarks"></a>Açıklamalar

Tüm oluşturucular depolamak bir [ayırıcı](../standard-library/allocator-class.md) ve denetlenen dizi başlatma. Bağımsız değişken ayırıcısı nesnedir *Al*, varsa. Kopya oluşturucusu için olduğu ` right.get_allocator()`. Aksi halde `Allocator()`.

İlk iki Oluşturucu boş bir başlangıç denetlenmiş dizi belirtin.

Üçüncü Oluşturucu bir tekrarını belirtir *sayısı* değerin `Type()`.

Dördüncü ve beşinci oluşturucular yineleneceğini belirtir *sayısı* değerin *Val*.

Altıncı Oluşturucu tarafından denetlenen dizinin bir kopyasını belirtir *sağ*. Varsa `InputIterator` bir tamsayı türüdür sıradaki iki Oluşturucu yineleneceğini belirtir `(size_type)First` değerin `(Type)Last`. Aksi takdirde, sıradaki iki Oluşturucu dizisini belirtin `[First, Last)`.

Dokuzuncu ve onuncu oluşturucular ile altıncı, ancak aynı olan bir [rvalue](../cpp/rvalue-reference-declarator-amp-amp.md) başvuru.

Son Oluşturucu, sınıfın bir nesnesi ilk denetlenen dizideki belirtir `initializer_list<Type>`.

## <a name="front"></a>  forward_list::Front

İleriye doğru bir listedeki ilk öğeye bir başvuru döndürür.

```cpp
reference front();
const_reference front() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetlenen dizinin boş olması gereken ilk öğeye bir başvuru.

## <a name="get_allocator"></a>  forward_list::get_allocator

İleriye doğru listesini oluşturmak için kullanılan ayırıcı nesnesinin bir kopyasını döndürür.

```cpp
allocator_type get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Depolanan [ayırıcı](../standard-library/allocator-class.md) nesne.

## <a name="insert_after"></a>  forward_list::insert_after

Öğeleri İleri listeye sonra belirtilen konuma ekler.

```cpp
iterator insert_after(const_iterator Where, const Type& Val);
void insert_after(const_iterator Where, size_type Count, const Type& Val);
void insert_after(const iterator Where, initializer_list<Type> IList);
iterator insert_after(const_iterator Where, Type&& Val);
template <class InputIterator>
void insert_after(const_iterator Where, InputIterator First, InputIterator Last);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Burada*|Hedef iletme listesindeki ilk öğe nereden eklenir konumu.|
|*Sayısı*|Eklenecek öğe sayısı.|
|*ilk*|Ekleme aralığı başlangıcı.|
|*Son*|Ekleme aralığın sonu.|
|*VAL*|İletme listeye eklenen öğe.|
|*IList*|Eklenecek initializer_list.|

### <a name="return-value"></a>Dönüş Değeri

Yeni eklenen öğeyi belirleyen bir yineleyici (ilk ve son üye işlevleri yalnızca).

### <a name="remarks"></a>Açıklamalar

Her üye bir işlev ekler — yalnızca işaret ettiği öğeden sonra *burada* denetlenen dizideki — bir dizisi, ' kalan işlenen tarafından belirtilen.

İlk üye işlevi değerine sahip bir öğe ekler *Val* ve yeni eklenen öğeyi belirleyen bir yineleyici döndürür.

İkinci üye işlevi bir tekrarını ekler *sayısı* değerin *Val*.

Varsa `InputIterator` bir tamsayı türüdür üçüncü üye işlevi gibi davranır `insert(it, (size_type)First, (Type)Last)`. Aksi takdirde, bunu dizisi ekler `[First, Last)`, denetlenen dizideki örtüşmemelidir.

Sınıfın bir nesnesi tarafından belirtilen sıra dördüncü üye işlevi ekler `initializer_list<Type>`.

Son üye işlevi ile ilk olarak, ancak aynı olan bir [rvalue](../cpp/rvalue-reference-declarator-amp-amp.md) başvuru.

Ekleme `N` öğeleri nedenleri `N` oluşturucu çağırır. [Reallocation](../standard-library/forward-list-class.md) gerçekleşir, ancak hiçbir Yineleyicilerin veya başvuruları geçersiz hale gelebilir.

Daha fazla öğe kapsayıcı bir ekleme sırasında bir özel durum veya sol değiştirilmeden ve özel durum yeniden oluşur.

## <a name="iterator"></a>  forward_list::iterator

İleriye doğru listesi için bir yineleyici sağlayan tür.

```cpp
typedef implementation-defined iterator;
```

### <a name="remarks"></a>Açıklamalar

`iterator` Denetlenen dizi için ileriye doğru yineleyici olarak hizmet verebilen bir nesneyi tanımlar. Açıklanmıştır bir uygulama tanımlı türünün eşanlamlısı olarak burada.

## <a name="max_size"></a>  forward_list::max_size

İleriye doğru bir listenin maksimum uzunluğunu döndürür.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Nesneyi de denetleyebilir kastetmek uzunluğu.

### <a name="remarks"></a>Açıklamalar

## <a name="merge"></a>  forward_list::Merge

İki sıralanmış dizileri tek bir sıralanmış dizisi doğrusal zamanda birleştirir. Bağımsız değişken listeden öğeleri kaldırır ve bu ekler `forward_list`. İki liste çağırmadan önce aynı karşılaştırma işlev nesnesi tarafından sıralanmalıdır `merge`. Birleşik listeyi tarafından karşılaştıran işlev nesnesi göre sıralanır.

```cpp
void merge(forward_list& right);
template <class Predicate>
void merge(forward_list& right, Predicate comp);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*sağ*|Şuradan Birleştir iletme liste.|
|*Comp*|Öğeleri sıralamak için kullanılan karşılaştırma işlevi nesnesi.|

### <a name="remarks"></a>Açıklamalar

`forward_list::merge` öğeleri kaldırır `forward_list` `right`ve bu ekler `forward_list`. Her iki dizileri aynı koşula göre sıralanmalıdır aşağıda açıklanmıştır. Birleşik dizisi Ayrıca, karşılaştırma işlev nesnesi tarafından düzenlenir.

Yineleyiciler için `Pi` ve `Pj` konumlarda öğeleri belirleme `i` ve `j`, ilk üye işlevi sırası uygular `!(*Pj < *Pi)` her `i < j`. (Öğeleri sıralanır `ascending` sipariş.) İkinci üye işlevi sırası uygular `! comp(*Pj, *Pi)` her `i < j`.

Özgün denetlenen dizideki öğelerin hiçbir çiftleri elde edilen denetlenen dizide ters çevrilir. Bir çift elde edilen öğelerin dizisi kontrol, eşit karşılaştırır ( `!(*Pi < *Pj) && !(*Pj < *Pi)`), özgün denetlenen dizideki öğeden önce bir öğe tarafından denetlenen dizinin görüntülenir `right`.

Yalnızca özel bir durum oluştuğunda `comp` bir özel durum oluşturur. Bu durumda, belirtilmemiş sırayla denetlenen dizideki kaldı ve özel durum yeniden oluşur.

## <a name="op_eq"></a>  forward_list::operator =

İletme listenin öğelerini başka bir ileri listesi bir kopyasını değiştirir.

```cpp
forward_list& operator=(const forward_list& right);
forward_list& operator=(initializer_list<Type> IList);
forward_list& operator=(forward_list&& right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*sağ*|İletme listeye kopyalanan iletme listesi.|
|*IList*|Yalnızca bir dizi öğe türü gibi davranan bir küme ayracı içine alınmış başlatıcı listesi `Type`.|

### <a name="remarks"></a>Açıklamalar

Denetlenen dizideki ilk üye işleci tarafından denetlenen dizinin bir kopyasını değiştirir *doğru*.

Denetlenen dizideki sınıfın bir nesnesinin ikinci üye işleci değiştirir `initializer_list<Type>`.

Üçüncü üye işleci ile ilk olarak, ancak aynı olan bir [rvalue](../cpp/rvalue-reference-declarator-amp-amp.md) başvuru.

## <a name="pointer"></a>  forward_list::pointer

İletme listedeki bir öğeye işaretçi sağlayan bir tür.

```cpp
typedef typename Allocator::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

## <a name="pop_front"></a>  forward_list::pop_front

İleriye doğru listesini başındaki öğeyi silin.

```cpp
void pop_front();
```

### <a name="remarks"></a>Açıklamalar

İletme listedeki ilk öğe boş olmalıdır.

Üye işlev hiçbir zaman bir özel durum oluşturur.

## <a name="push_front"></a>  forward_list::push_front

İleriye doğru bir listenin başına bir öğe ekler.

```cpp
void push_front(const Type& val);
void push_front(Type&& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*VAL*|Öğe iletme listenin başına eklenir.|

### <a name="remarks"></a>Açıklamalar

Bir özel durum oluşturulursa, kapsayıcı bırakılır değiştirilmeden ve özel durum yeniden oluşur.

## <a name="reference"></a>  forward_list::Reference

İletme listedeki bir öğeye başvuru sağlayan bir tür.

```cpp
typedef typename Allocator::reference reference;
```

### <a name="remarks"></a>Açıklamalar

## <a name="remove"></a>  forward_list::Remove

Belirtilen bir değerle eşleşen bir iletme listedeki öğeleri siler.

```cpp
void remove(const Type& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*VAL*|Değer, bir öğe tarafından tutulan, o öğenin listeden kaldırılmasıyla sonuçlanır.|

### <a name="remarks"></a>Açıklamalar

Üye işlevi denetlenen dizisinden yineleyici tarafından atanan tüm öğeleri kaldırır. `P`, kendisi için `*P ==  val`.

Üye işlev hiçbir zaman bir özel durum oluşturur.

## <a name="remove_if"></a>  forward_list::remove_if

Kendisi için belirtilen bir koşul sağlanırsa ileriye doğru bir listeden öğeleri siler.

```cpp
template <class Predicate>
void remove_if(Predicate pred);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Pred*|Bir öğe tarafından karşılanan, o öğenin listeden silme ile sonuçlanır, birli koşul.|

### <a name="remarks"></a>Açıklamalar

Üye işlevi denetlenen dizisinden yineleyici tarafından atanan tüm öğeleri kaldırır. `P`, kendisi için ` pred(*P)` geçerlidir.

Yalnızca özel bir durum oluştuğunda *pred* bir özel durum oluşturur. Bu durumda, denetlenen dizideki belirsiz bir durumda bırakılır ve özel durum yeniden oluşur.

## <a name="resize"></a>  forward_list::Resize

İleriye doğru bir listesi için yeni bir boyut belirtir.

```cpp
void resize(size_type _Newsize);
void resize(size_type _Newsize, const Type& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*_Newsize*|Yeniden boyutlandırılan iletme listedeki öğe sayısı.|
|*VAL*|Doldurma için kullanılacak değer.|

### <a name="remarks"></a>Açıklamalar

Her iki üye işlevleri, listedeki öğe sayısını henceforth olduğundan emin olun *_Newsize*. Denetlenen dizi uzun yapmanız gerekiyorsa, ilk üye işlevi öğeleri değerle ekler `Type()`ikinci üye işlevi öğeleri değerle ekler korurken *val*. Çağrı etkili bir şekilde her iki üye işlevleri daha kısa denetlenen dizideki yapmak `erase_after(begin() + _Newsize - 1, end())`.

## <a name="reverse"></a>  forward_list::reverse

Öğeleri bir iletme listesinde oluşabilen sırasını tersine çevirir.

```cpp
void reverse();
```

### <a name="remarks"></a>Açıklamalar

## <a name="size_type"></a>  forward_list::size_type

İki öğe arasındaki işaretsiz uzaklık temsil eden tür.

```cpp
typedef typename Allocator::size_type size_type;
```

### <a name="remarks"></a>Açıklamalar

İşaretsiz tamsayı türü, denetlenen bir dizi uzunluğunu temsil edebilen bir nesneyi tanımlar.

## <a name="sort"></a>  forward_list::sort

Öğeleri artan sırada veya bir koşula göre belirtilen bir düzende yerleştirir.

```cpp
void sort();
template <class Predicate>
void sort(Predicate pred);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Pred*|Sıralama koşul.|

### <a name="remarks"></a>Açıklamalar

Her iki üye işlevleri öğeleri denetlenen dizide bir koşula göre sıralamak aşağıda açıklanmıştır.

Yineleyiciler için `Pi` ve `Pj` konumlarda öğeleri belirleme `i` ve `j`, ilk üye işlevi sırası uygular `!(*Pj < *Pi)` her `i < j`. (Öğeleri sıralanır `ascending` sipariş.) Üye şablon işlevi sırası uygular `! pred(*Pj, *Pi)` her `i < j`. Özgün denetlenen dizideki öğelerin sıralı hiçbir çiftleri elde edilen denetlenen dizide ters çevrilir. (Sıralama, kararlı.)

Yalnızca özel bir durum oluştuğunda *pred* bir özel durum oluşturur. Bu durumda, belirtilmemiş sırayla denetlenen dizideki kaldı ve özel durum yeniden oluşur.

## <a name="splice_after"></a>  forward_list::splice_after

Bir kaynak forward_list öğeleri kaldırır ve bunları bir hedef forward_list ekler.

```cpp
// insert the entire source forward_list
void splice_after(const_iterator Where, forward_list& Source);
void splice_after(const_iterator Where, forward_list&& Source);

// insert one element of the source forward_list
void splice_after(const_iterator Where, forward_list& Source, const_iterator Iter);
void splice_after(const_iterator Where, forward_list&& Source, const_iterator Iter);

// insert a range of elements from the source forward_list
void splice_after(
    const_iterator Where,
    forward_list& Source,
    const_iterator First,
    const_iterator Last);

void splice_after(
    const_iterator Where,
    forward_list&& Source,
    const_iterator First,
    const_iterator Last);
```

### <a name="parameters"></a>Parametreler

*Burada*<br/>
Eklenecek sonra hedef forward_list konumu.

*Kaynak*<br/>
Hedef forward_list eklenecek olan kaynak forward_list.

*Iter*<br/>
Kaynak forward_list eklenecek öğe.

*ilk*<br/>
Kaynak forward_list eklenecek aralıktaki ilk öğeyi.

*Son*<br/>
Kaynak forward_list eklenecek aralığın ötesindeki ilk konumu.

### <a name="remarks"></a>Açıklamalar

İlk çift üye işlevleri tarafından denetlenen dizinin ekler *kaynak* tarafından denetlenen sıradaki öğenin hemen ardına *nerede*. Ayrıca tüm öğeleri kaldırır *kaynak*. (`&Source` değil olmalıdır **bu**.)

İkinci üye işlevleri çiftinin öğeyi kaldırır hemen sonrasına *Iter* tarafından denetlenen dizideki *kaynak* ve yalnızca denetlenen sıradaki öğenin tarafındanişaretedilensonraekler*Burada*. (Varsa `Where == Iter || Where == ++Iter`, herhangi bir değişiklik meydana gelir.)

Üçüncü çift üye işlevleri (aralıklı splice) tarafından belirlenen alt aralığı ekler `(First, Last)` tarafından denetlenen dizinin gelen *kaynak* tarafından denetlenen sıradaki öğenin hemen ardına *burada*. Bu ayrıca özgün alt aralığı tarafından denetlenen dizinin kaldırır *kaynak*. (Varsa `&Source == this`, aralığın `(First, Last)` işaret ettiği öğe içermemelidir *nerede*.)

Ranged splice ekliyorsa `N` öğeleri ve `&Source != this`, sınıfın bir nesnesi [yineleyici](#iterator) artırılır `N` kez.

Hiçbir yineleyiciler, başvuruları veya işaretçileri spliced öğeleri belirlediğiniz geçersiz olur.

### <a name="example"></a>Örnek

```cpp
// forward_list_splice_after.cpp
// compile with: /EHsc /W4
#include <forward_list>
#include <iostream>

using namespace std;

template <typename S> void print(const S& s) {
    for (const auto& p : s) {
        cout << "(" << p << ") ";
    }

    cout << endl;
}

int main()
{
    forward_list<int> c1{ 10, 11 };
    forward_list<int> c2{ 20, 21, 22 };
    forward_list<int> c3{ 30, 31 };
    forward_list<int> c4{ 40, 41, 42, 43 };

    forward_list<int>::iterator where_iter;
    forward_list<int>::iterator first_iter;
    forward_list<int>::iterator last_iter;

    cout << "Beginning state of lists:" << endl;
    cout << "c1 = ";
    print(c1);
    cout << "c2 = ";
    print(c2);
    cout << "c3 = ";
    print(c3);
    cout << "c4 = ";
    print(c4);

    where_iter = c2.begin();
    ++where_iter; // start at second element
    c2.splice_after(where_iter, c1);
    cout << "After splicing c1 into c2:" << endl;
    cout << "c1 = ";
    print(c1);
    cout << "c2 = ";
    print(c2);

    first_iter = c3.begin();
    c2.splice_after(where_iter, c3, first_iter);
    cout << "After splicing the first element of c3 into c2:" << endl;
    cout << "c3 = ";
    print(c3);
    cout << "c2 = ";
    print(c2);

    first_iter = c4.begin();
    last_iter = c4.end();
    // set up to get the middle elements
    ++first_iter;
    c2.splice_after(where_iter, c4, first_iter, last_iter);
    cout << "After splicing a range of c4 into c2:" << endl;
    cout << "c4 = ";
    print(c4);
    cout << "c2 = ";
    print(c2);
}
```

```Output
Beginning state of lists:c1 = (10) (11)c2 = (20) (21) (22)c3 = (30) (31)c4 = (40) (41) (42) (43)After splicing c1 into c2:c1 =c2 = (20) (21) (10) (11) (22)After splicing the first element of c3 into c2:c3 = (30)c2 = (20) (21) (31) (10) (11) (22)After splicing a range of c4 into c2:c4 = (40) (41)c2 = (20) (21) (42) (43) (31) (10) (11) (22)
```

## <a name="swap"></a>  forward_list::Swap

İletme iki listenin öğelerini değiştirir.

```cpp
void swap(forward_list& right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*sağ*|Değiştirilecek öğeleri sağlayan liste iletme.|

### <a name="remarks"></a>Açıklamalar

Denetlenen diziyi üye işlevi değiştirir `*this` ve *doğru*. Varsa `get_allocator() ==  right.get_allocator()`, bunu sabit sürede yapar, hiçbir özel durum oluşturur ve hiçbir başvurular, işaretçiler veya iki denetlenen dizinin öğelerini belirlemek yineleyicileri geçersiz kılar. Aksi takdirde, bir dizi öğesi atamalar ve oluşturucu çağrıları öğelerin sayısını orantılı iki denetimli sıralarında gerçekleştirir.

## <a name="unique"></a>  forward_list::Unique

Her ardışık eşit öğeleri ilk öğenin dışında tümünü ortadan kaldırır.

```cpp
void unique();
template <class BinaryPredicate>
void unique(BinaryPredicate comp);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Comp*|Ardışık öğeleri karşılaştırmak için kullanılan ikili koşul.|

### <a name="remarks"></a>Açıklamalar

Her benzersiz öğesinin ilk tutar ve rest kaldırır. Öğeleri değerine eşit öğeleri listede bitişik olacak şekilde sıralanması gerekir.

İlk üye işlevi denetlenen dizisinden, önceki öğesine eşit karşılaştıran her öğeyi kaldırır. Yineleyiciler için `Pi` ve `Pj` konumlarda öğeleri belirleme `i` ve `j`, ikinci üye işlevi her öğe için kaldıran `i + 1 == j &&  comp(*Pi, *Pj)`.

Denetlenen bir dizi uzunluğu için `N` (> 0) koşul ` comp(*Pi, *Pj)` değerlendirilir `N - 1` kez.

Yalnızca özel bir durum oluştuğunda `comp` bir özel durum oluşturur. Bu durumda, denetlenen dizideki belirsiz bir durumda bırakılır ve özel durum yeniden oluşur.

## <a name="value_type"></a>  forward_list::value_type

Bir iletme listesinde depolanan öğenin türünü temsil eden tür.

```cpp
typedef typename Allocator::value_type value_type;
```

### <a name="remarks"></a>Açıklamalar

Tür şablonu parametresi _ eşanlamlıdır `Ty`.

## <a name="see-also"></a>Ayrıca bkz.

[<forward_list>](../standard-library/forward-list.md)<br/>
