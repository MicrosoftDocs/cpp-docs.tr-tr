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
ms.openlocfilehash: e13242aa41cc99cdd01a6f16b607ef568195d659
ms.sourcegitcommit: 4b0928a1a497648d0d327579c8262f25ed20d02e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2019
ms.locfileid: "72890197"
---
# <a name="forward_list-class"></a>forward_list Sınıfı

Değişen uzunluklu öğe dizisini denetleyen bir nesne tanımlar. Sıra, `Type` türünde bir üye içeren düğümlerin listedir bağlantılı bir listesi olarak depolanır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type,
    class Allocator = allocator<Type>>
class forward_list
```

### <a name="parameters"></a>Parametreler

Yazın * \
Forward_list içinde depolanacak öğe veri türü.

*Ayırıcı* \
Belleğin forward_list ayırması ve ayırmayı kaldırma hakkındaki ayrıntıları kapsülleyen saklı ayırıcı nesnesi. Bu parametre isteğe bağlıdır. Varsayılan değer ayırıcı < `Type` >.

## <a name="remarks"></a>Açıklamalar

`forward_list` nesnesi, [ayırıcı sınıfına](../standard-library/allocator-class.md) dayalı bir sınıf *ayırıcı* nesnesi aracılığıyla denetlediği sıra için depolamayı ayırır ve serbest bırakır (genellikle `std::allocator)`olarak bilinir). Daha fazla bilgi için bkz. [ayırıcılar](../standard-library/allocators.md). Ayırıcı nesne, `allocator` türünde bir nesne ile aynı dış arabirime sahip olmalıdır.

> [!NOTE]
> Kapsayıcı nesne atandığında, depolanan ayırıcı nesnesi kopyalanmaz.

Denetim sırası öğeleri `forward_list`aracılığıyla silindiklerinde yineleyiciler, işaretçiler ve başvurular geçersiz hale gelebilir. `forward_list` aracılığıyla denetimli sırada gerçekleştirilen Eklenenler ve sliclalar yineleyiciler geçersiz kılmaz.

Denetlenen diziye eklemeler `Type(const  T&)`, oluşturucuyu çağıran tek üye işlevi olan [forward_list:: insert_after](#insert_after)öğesine yapılan çağrılar tarafından gerçekleşebilir. `forward_list` de taşıma oluşturucuları çağırabilir. Böyle bir ifade bir özel durum oluşturursa, kapsayıcı nesnesi yeni öğe ekler ve özel durumu yeniden atar. Bu nedenle, bu tür özel durumlar oluştuğunda `forward_list` türünde bir nesne bilinen bir durumda bırakılır.

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|||
|-|-|
|[forward_list](#forward_list)|`forward_list`türünde bir nesne oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|||
|-|-|
|[allocator_type](#allocator_type)|İleri liste nesnesi için ayırıcı sınıfını temsil eden bir tür.|
|[const_iterator](#const_iterator)|İleri listesi için sabit bir yineleyici sağlayan bir tür.|
|[const_pointer](#const_pointer)|İleri listesindeki bir **const** öğesine işaretçi sağlayan bir tür.|
|[const_reference](#const_reference)|İleri listesindeki bir öğeye sabit başvuru sağlayan bir tür.|
|[difference_type](#difference_type)|Yineleyiciler tarafından gösterilen öğeler arasındaki bir aralıktaki ileri listesinin öğelerinin sayısını temsil etmek için kullanılabilen işaretli bir tamsayı türü.|
|[iden](#iterator)|İleri listesi için Yineleyici sağlayan bir tür.|
|[çağrısı](#pointer)|İleri listesindeki bir öğeye işaretçi sağlayan bir tür.|
|[başvurunun](#reference)|İleri listesindeki bir öğeye başvuru sağlayan bir tür.|
|[size_type](#size_type)|İki öğe arasındaki işaretsiz mesafeyi temsil eden bir tür.|
|[value_type](#value_type)|İleri listesinde depolanan öğe türünü temsil eden bir tür.|

### <a name="functions"></a>İşlevler

|||
|-|-|
|[ata](#assign)|İleri listesinden öğeleri siler ve yeni bir öğe kümesini hedef ileri listesine kopyalar.|
|[before_begin](#before_begin)|İleri listesindeki ilk öğeden önceki konumu adresleyen bir yineleyici döndürür.|
|[başladı](#begin)|İleri listesindeki ilk öğeyi adresleyen bir yineleyici döndürür.|
|[cbefore_begin](#cbefore_begin)|İleri listesindeki ilk öğeden önceki konumu adresleyen bir const yineleyici döndürür.|
|[cbegin](#cbegin)|İleri listesindeki ilk öğeyi adresleyen bir const yineleyici döndürür.|
|[cend](#cend)|İleri listesindeki son öğeden sonraki konumu ele alan bir const yineleyici döndürür.|
|[lediğiniz](#clear)|İleri listesinin tüm öğelerini siler.|
|[emplace_after](#emplace_after)|Taşı belirtilen konumdan sonra yeni bir öğe oluşturur.|
|[emplace_front](#emplace_front)|Listenin başına yerinde oluşturulmuş bir öğe ekler.|
|[olmamalıdır](#empty)|Bir iletme listesinin boş olup olmadığını sınar.|
|[erer](#end)|İleri listesindeki son öğeden sonraki konumu ele alan bir yineleyici döndürür.|
|[erase_after](#erase_after)|Belirli bir konumdan sonra öğeleri ileri listesinden kaldırır.|
|[yapılan](#front)|İleri listesindeki ilk öğeye bir başvuru döndürür.|
|[get_allocator](#get_allocator)|Bir iletme listesi oluşturmak için kullanılan ayırıcı nesnesinin bir kopyasını döndürür.|
|[insert_after](#insert_after)|Belirli bir konumdan sonra ileri listesine öğe ekler.|
|[max_size](#max_size)|Bir iletme listesinin maksimum uzunluğunu döndürür.|
|[birleþtirmek](#merge)|Bağımsız değişken listesinden öğeleri kaldırır, bunları hedef iletme listesine ekler ve yeni, Birleşik öğe kümesini artan sırada veya belirli bir sıraya göre sıralar.|
|[pop_front](#pop_front)|Bir ileriye doğru listenin başındaki öğeyi siler.|
|[push_front](#push_front)|İleri listesinin başlangıcına bir öğesi ekler.|
|[remove](#remove)|İleri listesinde belirtilen bir değerle eşleşen öğeleri siler.|
|[remove_if](#remove_if)|Belirtilen koşulun karşılanmasını sağlayan ileri listesinden öğeleri siler.|
|[yeniden boyutlandırma](#resize)|İleri liste için yeni bir boyut belirtir.|
|[tersini](#reverse)|Öğelerin bir iletme listesinde oluştuğu sırayı tersine çevirir.|
|[düzenine](#sort)|Öğeleri artan düzende veya bir koşul tarafından belirtilen bir sırayla düzenler.|
|[splice_after](#splice_after)|Düğümler arasındaki bağlantıları yeniden bağlar.|
|[Kur](#swap)|İki ileri listenin öğelerini değiş tokuş eder.|
|[unique](#unique)|Belirtilen testi geçiren bitişik öğeleri kaldırır.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[işleç =](#op_eq)|İleri listesinin öğelerini başka bir iletme listesinin kopyasıyla değiştirir.|

## <a name="allocator_type"></a>allocator_type

İleri liste nesnesi için ayırıcı sınıfını temsil eden bir tür.

```cpp
typedef Allocator allocator_type;
```

### <a name="remarks"></a>Açıklamalar

`allocator_type`, şablon parametre ayırıcısı için bir eş anlamlı.

## <a name="assign"></a>ata

İleri listesinden öğeleri siler ve yeni bir öğe kümesini hedef ileri listesine kopyalar.

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

*ilk* \
Değiştirme aralığının başlangıcı.

*son* \
Değiştirme aralığının sonu.

*sayı* \
Atanacak öğe sayısı.

*val* \
Her öğe atanacak değer.

*Tür* \
Değerin türü.

*Ilist* \
Kopyalanacak initializer_list.

### <a name="remarks"></a>Açıklamalar

Forward_list bir tamsayı türü ise, ilk üye işlevi `assign((size_type)First, (Type)Last)`ile aynı şekilde davranır. Aksi halde, ilk üye işlevi, `*this` tarafından denetlenen sırayı, ilk denetlenen diziyle çakışmaması gereken [`First, Last)`dizisiyle değiştirir.

İkinci üye işlevi, `*this` tarafından denetlenen sırayı, değer `Val` `Count` öğelerinin tekrarından sonra değiştirir.

Üçüncü üye işlevi, initializer_list öğelerini forward_list içine kopyalar.

## <a name="before_begin"></a>before_begin

İleri listesindeki ilk öğeden önceki konumu adresleyen bir yineleyici döndürür.

```cpp
const_iterator before_begin() const;
iterator before_begin();
```

### <a name="return-value"></a>Dönüş Değeri

Dizinin ilk öğesinden hemen önce (veya boş bir dizinin sonundan önce) işaret eden bir ileri Yineleyici.

### <a name="remarks"></a>Açıklamalar

## <a name="begin"></a>başladı

İleri listesindeki ilk öğeyi adresleyen bir yineleyici döndürür.

```cpp
const_iterator begin() const;
iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

Dizinin ilk öğesine (veya boş bir sıranın sonuna kadar) işaret eden bir ileri Yineleyici.

### <a name="remarks"></a>Açıklamalar

## <a name="cbefore_begin"></a>cbefore_begin

İleri listesindeki ilk öğeden önceki konumu adresleyen bir const yineleyici döndürür.

```cpp
const_iterator cbefore_begin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dizinin ilk öğesinden hemen önce (veya boş bir dizinin sonundan önce) işaret eden bir ileri Yineleyici.

### <a name="remarks"></a>Açıklamalar

## <a name="cbegin"></a>cbegin

Aralıktaki ilk öğeyi ele alan bir **sabit** yineleyici döndürür.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Aralığın ilk öğesine veya boş bir aralığın sonundaki konuma (boş bir Aralık için `cbegin() == cend()`) işaret eden bir **const** ileri erişim yineleyicisi.

### <a name="remarks"></a>Açıklamalar

`cbegin`dönüş değeri ile aralıktaki öğeler değiştirilemez.

Dönüş değerinin `const_iterator`olduğunu garantilemek için `begin()` member işlevinin yerine bu üye işlevi kullanabilirsiniz. Genellikle, aşağıdaki örnekte gösterildiği gibi [Otomatik](../cpp/auto-cpp.md) tür kesintisi anahtar sözcüğüyle birlikte kullanılır. Örnekte, `begin()` ve `cbegin()` destekleyen herhangi bir türdeki değiştirilebilir ( **const**olmayan) bir kapsayıcı olarak `Container` düşünün.

```cpp
auto i1 = Container.begin();
// i1 is Container<T>::iterator
auto i2 = Container.cbegin();
// i2 is Container<T>::const_iterator
```

## <a name="cend"></a>cend

Bir aralıktaki son öğeden hemen sonra gelen konumu ele alan bir **const** yineleyici döndürür.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Aralığının hemen sonunu gösteren bir ileriye doğru erişim yineleyicisi.

### <a name="remarks"></a>Açıklamalar

`cend`, bir yineleyicinin aralığın sonunu geçtiğini test etmek için kullanılır.

Dönüş değerinin `const_iterator`olduğunu garantilemek için `end()` member işlevinin yerine bu üye işlevi kullanabilirsiniz. Genellikle, aşağıdaki örnekte gösterildiği gibi [Otomatik](../cpp/auto-cpp.md) tür kesintisi anahtar sözcüğüyle birlikte kullanılır. Örnekte, `end()` ve `cend()` destekleyen herhangi bir türdeki değiştirilebilir ( **const**olmayan) bir kapsayıcı olarak `Container` düşünün.

```cpp
auto i1 = Container.end();
// i1 is Container<T>::iterator
auto i2 = Container.cend();

// i2 is Container<T>::const_iterator
```

`cend` tarafından döndürülen değer başvurulmamalıdır.

## <a name="clear"></a>lediğiniz

İleri listesinin tüm öğelerini siler.

```cpp
void clear();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi `erase_after(before_begin(), end()).` çağırır

## <a name="const_iterator"></a>const_iterator

İleri listesi için sabit bir yineleyici sağlayan bir tür.

```cpp
typedef implementation-defined const_iterator;
```

### <a name="remarks"></a>Açıklamalar

`const_iterator` denetimli sıra için sabit bir ileri Yineleyici işlevi görebilecek bir nesne açıklar. Burada uygulama tanımlı bir tür için bir eş anlamlı olarak açıklanmaktadır.

## <a name="const_pointer"></a>const_pointer

İleri listesindeki bir **const** öğesine işaretçi sağlayan bir tür.

```cpp
typedef typename Allocator::const_pointer
    const_pointer;
```

### <a name="remarks"></a>Açıklamalar

## <a name="const_reference"></a>const_reference

İleri listesindeki bir öğeye sabit başvuru sağlayan bir tür.

```cpp
typedef typename Allocator::const_reference const_reference;
```

### <a name="remarks"></a>Açıklamalar

## <a name="difference_type"></a>difference_type

Yineleyiciler tarafından gösterilen öğeler arasındaki bir aralıktaki ileri listesinin öğelerinin sayısını temsil etmek için kullanılabilen işaretli bir tamsayı türü.

```cpp
typedef typename Allocator::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

`difference_type`, denetlenen dizideki herhangi iki öğenin adresleri arasındaki farkı temsil eden bir nesneyi tanımlar.

## <a name="emplace_after"></a>emplace_after

Taşı belirtilen konumdan sonra yeni bir öğe oluşturur.

```cpp
template <class T>
iterator emplace_after(const_iterator Where, Type&& val);
```

### <a name="parameters"></a>Parametreler

*Burada* \
Hedef iletme listesindeki, yeni öğenin oluşturulduğu konum.

*val* \
Oluşturucu bağımsız değişkeni.

### <a name="return-value"></a>Dönüş Değeri

Yeni eklenen öğeyi atayan bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, öğesinin denetimli dizide *olduğu yere* işaret eden *öğesinden hemen sonra* Oluşturucu bağımsız değişkenlerini içeren bir öğe ekler. Davranışı, [forward_list:: insert_after](#insert_after)ile aynı şekilde olur.

## <a name="emplace_front"></a>emplace_front

Listenin başına yerinde oluşturulmuş bir öğe ekler.

```cpp
template <class Type>
    void emplace_front(Type&& val);
```

### <a name="parameters"></a>Parametreler

*val* \
İleri listesinin başlangıcına eklenen öğe.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, denetlenen sıranın sonunda `_ val` Oluşturucu bağımsız değişkenlerine sahip bir öğe ekler.

Bir özel durum oluşturulursa, kapsayıcı değiştirilmemiş olarak kalır ve özel durum yeniden oluşturulur.

## <a name="empty"></a>olmamalıdır

Bir iletme listesinin boş olup olmadığını sınar.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

İleri listesi boşsa **doğru** ; Aksi takdirde, **false**.

## <a name="end"></a>erer

İleri listesindeki son öğeden sonraki konumu ele alan bir yineleyici döndürür.

```cpp
const_iterator end() const;
iterator end();
```

### <a name="return-value"></a>Dönüş Değeri

Dizinin sonunun hemen ötesinde işaret eden bir ileri Yineleyici.

## <a name="erase_after"></a>erase_after

Belirli bir konumdan sonra öğeleri ileri listesinden kaldırır.

```cpp
iterator erase_after(const_iterator Where);
iterator erase_after(const_iterator first, const_iterator last);
```

### <a name="parameters"></a>Parametreler

*Burada* \
Öğenin silinme hedefi olan hedef iletme listesindeki konum.

*ilk* \
Silinecek aralığın başlangıcı.

*son* \
Silinecek aralığın sonu.

### <a name="return-value"></a>Dönüş Değeri

Kaldırılan tüm öğelerin ötesinde kalan ilk öğeyi atayan bir yineleyici veya böyle bir öğe yoksa [forward_list:: End](#end) .

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi, denetimli dizinin öğesini *nerede*sonra kaldırır.

İkinci üye işlevi, Aralık `( first,  last)` denetlenen sıranın öğelerini kaldırır (bitiş noktası dahil değildir).

`N` öğeleri silme `N` yıkıcı çağrılarına neden olur. Yeniden [Tahsisat](../standard-library/forward-list-class.md) gerçekleşirse, yineleyiciler ve başvurular silinen öğeler için geçersiz hale gelir.

Üye işlevleri hiçbir şekilde özel durum oluşturmaz.

## <a name="forward_list"></a>forward_list

`forward_list`türünde bir nesne oluşturur.

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

*Al* \
Bu nesneyle kullanılacak kaynak ayırıcı sınıfı.

*Sayı* \
Oluşturulan listedeki öğelerin sayısı.

*Val* \
Oluşturulan listedeki öğelerin değeri.

*Sağ* \
Oluşturulan listenin bir kopya olduğu liste.

*İlk* \
Kopyalanacak öğe aralığındaki ilk öğenin konumu.

*Son* \
Kopyalanacak öğe aralığının ötesinde ilk öğenin konumu.

*Ilist* \
Kopyalanacak initializer_list.

### <a name="remarks"></a>Açıklamalar

Tüm oluşturucular bir [ayırıcıyı](../standard-library/allocator-class.md) depolar ve denetimli sırayı başlatır. Ayırıcı nesnesi varsa, *Al*bağımsız değişkenidir. Kopya Oluşturucu için ` right.get_allocator()`. Aksi takdirde, `Allocator()`.

İlk iki Oluşturucu boş bir ilk denetimli sıra belirtir.

Üçüncü Oluşturucu, `Type()` *sayı* öğelerinin bir tekrarını belirtir.

Dördüncü ve beşinci oluşturucular, değer *Val* *Count* öğelerinin bir tekrarını belirtir.

Altıncı Oluşturucu *sağ*tarafından denetlenen sıranın bir kopyasını belirtir. `InputIterator` bir tamsayı türüdür, sonraki iki Oluşturucu değer `(Type)Last``(size_type)First` öğelerinin tekrarlarını belirtir. Aksi halde, sonraki iki Oluşturucu sıra `[First, Last)`belirtir.

Dokuzuncu ve onuncu oluşturucular, altıncı ile aynı, ancak [rvalue](../cpp/rvalue-reference-declarator-amp-amp.md) başvurusuyla aynıdır.

Son Oluşturucu, `initializer_list<Type>`sınıfının bir nesnesi ile ilk denetlenen sırayı belirtir.

## <a name="front"></a>yapılan

İleri listesindeki ilk öğeye bir başvuru döndürür.

```cpp
reference front();
const_reference front() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetlenen sıranın ilk öğesine başvuru, bu, boş olmamalıdır.

## <a name="get_allocator"></a>get_allocator

Bir iletme listesi oluşturmak için kullanılan ayırıcı nesnesinin bir kopyasını döndürür.

```cpp
allocator_type get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Depolanan [ayırıcı](../standard-library/allocator-class.md) nesnesi.

## <a name="insert_after"></a>insert_after

Belirli bir konumdan sonra ileri listesine öğe ekler.

```cpp
iterator insert_after(const_iterator Where, const Type& Val);
void insert_after(const_iterator Where, size_type Count, const Type& Val);
void insert_after(const iterator Where, initializer_list<Type> IList);
iterator insert_after(const_iterator Where, Type&& Val);
template <class InputIterator>
    void insert_after(const_iterator Where, InputIterator First, InputIterator Last);
```

### <a name="parameters"></a>Parametreler

*Burada* \
İlk öğenin eklendiği hedef ileri listesindeki konum.

*Sayı* \
Eklenecek öğe sayısı.

*İlk* \
Ekleme aralığının başlangıcı.

*Son* \
Ekleme aralığının sonu.

*Val* \
İleri listesine eklenen öğe.

*Ilist* \
Eklenecek initializer_list.

### <a name="return-value"></a>Dönüş Değeri

Yeni eklenen öğeyi (yalnızca ilk ve son üye işlevlerini) atayan bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Üye işlevlerinin her biri, ' nin, kalan işlenenler tarafından belirtilen bir sıra olan denetimli sırada *olduğu* gibi, öğesinin işaret ettiği öğeden hemen sonra eklenir.

İlk üye *işlevi değer değeri* olan bir öğesi ekler ve yeni eklenen öğeyi atayan bir yineleyici döndürür.

İkinci üye işlevi, değer *Val*'in *Count* öğelerinin tekrarından birini ekler.

`InputIterator` bir tamsayı türüdür, üçüncü üye işlevi `insert(it, (size_type)First, (Type)Last)`ile aynı şekilde davranır. Aksi takdirde, ilk denetlenen dizile çakışmamalıdır `[First, Last)`diziyi ekler.

Dördüncü üye işlevi, `initializer_list<Type>`sınıfının bir nesnesi tarafından belirtilen diziyi ekler.

Son üye işlevi ilki ile aynıdır, ancak [rvalue](../cpp/rvalue-reference-declarator-amp-amp.md) başvurusu vardır.

`N` öğeleri eklemek `N` Oluşturucu çağrılarına neden olur. Yeniden [ayırma gerçekleşirse,](../standard-library/forward-list-class.md) ancak hiçbir yineleyiciye veya başvuru geçersiz olmaz.

Bir veya daha fazla öğenin eklenmesi sırasında bir özel durum oluşursa, kapsayıcı değiştirilmemiş olarak kalır ve özel durum yeniden oluşturulur.

## <a name="iterator"></a>iden

İleri listesi için Yineleyici sağlayan bir tür.

```cpp
typedef implementation-defined iterator;
```

### <a name="remarks"></a>Açıklamalar

`iterator` denetlenen sıra için ileriye doğru yineleyici olarak kullanılabilecek bir nesneyi açıklar. Burada uygulama tanımlı bir tür için bir eş anlamlı olarak açıklanmaktadır.

## <a name="max_size"></a>max_size

Bir iletme listesinin maksimum uzunluğunu döndürür.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Nesnenin denetleyecan en uzun sırasının uzunluğu.

### <a name="remarks"></a>Açıklamalar

## <a name="merge"></a>birleþtirmek

İki sıralanmış diziyi doğrusal zamanda tek bir sıralanmış sırayla birleştirir. Bağımsız değişken listesinden öğeleri kaldırır ve bu `forward_list`ekler. `merge`çağrısından önce, iki liste aynı karşılaştırma işlevi nesnesine göre sıralanmalıdır. Birleştirilmiş liste, karşılaştırma işlevi nesnesine göre sıralanır.

```cpp
void merge(forward_list& right);
template <class Predicate>
    void merge(forward_list& right, Predicate comp);
```

### <a name="parameters"></a>Parametreler

*sağ* \
Birleştirilecek ileri listesi.

*comp* \
Öğeleri sıralamak için kullanılan Compare işlevi nesnesi.

### <a name="remarks"></a>Açıklamalar

`forward_list::merge` öğeleri `forward_list` `right`kaldırır ve bu `forward_list`ekler. Her iki sıra da aşağıda açıklanan koşulla aynı koşula göre sıralanmalıdır. Birleşik sıra, bu karşılaştırma işlevi nesnesi tarafından da sıralanır.

Yineleyiciler `Pi` ve `Pj` öğeleri `i` ve `j` atamak için, ilk üye işlevi `!(*Pj < *Pi)` her seferinde sırayı uygular. (Öğeler `ascending` sırada sıralanır.) İkinci üye işlevi `i < j` her seferinde sırayı `! comp(*Pj, *Pi)` uygular.

Orijinal denetimli dizide hiçbir öğe çifti, sonuçta elde edilen denetimli sırada tersine çevrilir. Elde edilen denetimli dizide bir çift öğe eşit (`!(*Pi < *Pj) && !(*Pj < *Pi)`) karşılaştırırsa, orijinal denetimli dizideki bir öğe, `right` tarafından denetlenen sıradaki öğeden önce görünür.

Özel durum yalnızca `comp` bir özel durum oluşturursa oluşur. Bu durumda, denetlenen sıra belirtilmemiş sırayla bırakılır ve özel durum yeniden oluşturulur.

## <a name="op_eq"></a>işleç =

İleri listesinin öğelerini başka bir iletme listesinin kopyasıyla değiştirir.

```cpp
forward_list& operator=(const forward_list& right);
forward_list& operator=(initializer_list<Type> IList);
forward_list& operator=(forward_list&& right);
```

### <a name="parameters"></a>Parametreler

*sağ* \
İleri listesi, ileri listesine kopyalanıyor.

*Ilist* \
Yalnızca `Type` türünde bir dizi öğe gibi davranan, küme ayracı içine alınmış Başlatıcı listesi.

### <a name="remarks"></a>Açıklamalar

İlk üye işleci denetimli diziyi, *sağdan*denetlenen sıranın bir kopyasıyla değiştirir.

İkinci üye işleci, denetlenen sıranın `initializer_list<Type>`sınıfın bir nesnesinden yerini alır.

Üçüncü üye işleci ilki, ancak [rvalue](../cpp/rvalue-reference-declarator-amp-amp.md) başvurusuyla aynıdır.

## <a name="pointer"></a>çağrısı

İleri listesindeki bir öğeye işaretçi sağlayan bir tür.

```cpp
typedef typename Allocator::pointer pointer;
```

## <a name="pop_front"></a>pop_front

Bir ileriye doğru listenin başındaki öğeyi siler.

```cpp
void pop_front();
```

### <a name="remarks"></a>Açıklamalar

İletme listesinin ilk öğesi boş olmamalıdır.

Üye işlevi hiçbir şekilde özel durum oluşturmaz.

## <a name="push_front"></a>push_front

İleri listesinin başlangıcına bir öğesi ekler.

```cpp
void push_front(const Type& val);
void push_front(Type&& val);
```

### <a name="parameters"></a>Parametreler

*val* \
İleri listesinin başlangıcına eklenen öğe.

### <a name="remarks"></a>Açıklamalar

Bir özel durum oluşturulursa, kapsayıcı değiştirilmemiş olarak kalır ve özel durum yeniden oluşturulur.

## <a name="reference"></a>başvurunun

İleri listesindeki bir öğeye başvuru sağlayan bir tür.

```cpp
typedef typename Allocator::reference reference;
```

## <a name="remove"></a>temizlenmesine

İleri listesinde belirtilen bir değerle eşleşen öğeleri siler.

```cpp
void remove(const Type& val);
```

### <a name="parameters"></a>Parametreler

*val* \
Bir öğe tarafından tutuluyorsa, bu öğenin listeden kaldırılmasına neden olur.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, `*P ==  val` için `P` Yineleyici tarafından atanan tüm öğeler denetimli diziden kaldırılır.

Üye işlevi hiçbir şekilde özel durum oluşturmaz.

## <a name="remove_if"></a>remove_if

Belirtilen koşulun karşılanmasını sağlayan ileri listesinden öğeleri siler.

```cpp
template <class Predicate>
    void remove_if(Predicate pred);
```

### <a name="parameters"></a>Parametreler

*Pred* \
Bir öğe tarafından karşılanmadığı birli koşul, bu öğenin listeden silinmesine neden olur.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, ` pred(*P)` doğru olması için, yineleyici `P` tarafından belirlenen, denetlenen dizi tüm öğelerinden kaldırır.

Özel durum yalnızca *Pred* bir özel durum oluşturursa oluşur. Bu durumda, denetlenen sıra belirtilmemiş bir durumda bırakılır ve özel durum yeniden oluşturulur.

## <a name="resize"></a>yeniden boyutlandırma

İleri liste için yeni bir boyut belirtir.

```cpp
void resize(size_type _Newsize);
void resize(size_type _Newsize, const Type& val);
```

### <a name="parameters"></a>Parametreler

*_Newsize*\
Yeniden boyutlandırılmış ileri listesindeki öğelerin sayısı.

*val* \
Doldurma için kullanılacak değer.

### <a name="remarks"></a>Açıklamalar

Üye işlevleri her ikisi de listedeki öğe sayısının *_Newsize*olduğundan emin olur. Denetlenen diziyi daha uzun hale getirmek gerekiyorsa, ilk üye işlevi `Type()` değeri olan öğeleri ekler, ikinci üye işlevi ise değer *Val*ile öğeleri ekler. Denetimli diziyi daha kısa hale getirmek için, her iki üye işlevi `erase_after(begin() + _Newsize - 1, end())`etkin bir şekilde çağırır.

## <a name="reverse"></a>tersini

Öğelerin bir iletme listesinde oluştuğu sırayı tersine çevirir.

```cpp
void reverse();
```

## <a name="size_type"></a>size_type

İki öğe arasındaki işaretsiz mesafeyi temsil eden bir tür.

```cpp
typedef typename Allocator::size_type size_type;
```

### <a name="remarks"></a>Açıklamalar

İşaretsiz tamsayı türü, denetlenen bir dizinin uzunluğunu temsil eden bir nesneyi tanımlar.

## <a name="sort"></a>düzenine

Öğeleri artan düzende veya bir koşul tarafından belirtilen bir sırayla düzenler.

```cpp
void sort();
template <class Predicate>
void sort(Predicate pred);
```

### <a name="parameters"></a>Parametreler

*Pred* \
Sıralama koşulu.

### <a name="remarks"></a>Açıklamalar

Her iki üye işlevi, denetlenen dizideki öğeleri aşağıda açıklanan bir koşula göre sıraya koyarak.

Yineleyiciler `Pi` ve `Pj` öğeleri `i` ve `j` atamak için, ilk üye işlevi `!(*Pj < *Pi)` her seferinde sırayı uygular. (Öğeler `ascending` sırada sıralanır.) Üye şablonu işlevi `i < j` her seferinde sırayı `! pred(*Pj, *Pi)` uygular. Orijinal denetimli dizide sıralı bir öğe çifti, sonuçta elde edilen kontrollü sırada ters çevrilir. (Sıralama kararlı olur.)

Özel durum yalnızca *Pred* bir özel durum oluşturursa oluşur. Bu durumda, denetlenen sıra belirtilmemiş sırayla bırakılır ve özel durum yeniden oluşturulur.

## <a name="splice_after"></a>splice_after

Bir kaynak forward_list öğeleri kaldırır ve bir hedef forward_list içine ekler.

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

*Burada* \
Eklenecek hedef forward_list konumu.

*Kaynak* \
Hedef forward_list içine eklenecek kaynak forward_list.

*Iter* \
Kaynak forward_list eklenecek öğe.

*İlk* \
Kaynak forward_list eklenecek aralıktaki ilk öğe.

*Son* \
Kaynak forward_list eklenecek aralığın ötesindeki ilk konum.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi çifti, kaynağa göre denetlenen sıradaki öğeden hemen sonra *kaynak* tarafından denetlenen sırayı *ekler.* Ayrıca *kaynaktaki*tüm öğeleri kaldırır. (`&Source` **buna eşit olmamalı**.)

Üye işlevlerinin ikinci çifti, *kaynak* tarafından denetlenen sıranın *hemen sonrasında öğesini* kaldırır ve bunu, denetimli dizideki öğeden hemen sonra, *burada*ekler. (`Where == Iter || Where == ++Iter`, hiçbir değişiklik gerçekleşmez.)

Üçüncü üye işlevleri çifti (ranşlı Splice), *kaynak* tarafından denetlenen dizideki öğeden hemen sonra gelen `(First, Last)` tarafından belirlenen alt aralığı *ekler.* Ayrıca özgün alt aralığı *kaynağa*göre denetlenen sıraya göre kaldırır. (`&Source == this`, Aralık `(First, Last)` öğesinin *işaret ettiği öğeyi içermesi gerekir.)*

Ranşlı splice `N` öğeleri ekler ve `&Source != this`, sınıf [Yineleyici](#iterator) nesnesinin bir nesnesi `N` zaman artırılır.

Hiçbir yineleyiciye, işaretçiye veya bir şekilde, vliced öğeleri belirten başvurular geçersiz hale gelir.

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

## <a name="swap"></a>Kur

İki ileri listenin öğelerini değiş tokuş eder.

```cpp
void swap(forward_list& right);
```

### <a name="parameters"></a>Parametreler

*sağ* \
Değiş tokuş edilecek öğeleri sağlayan ileri liste.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, `*this` ve *sağ*arasındaki denetlenen dizileri değiştirir. `get_allocator() ==  right.get_allocator()`, bu durumda sabit bir zaman, özel durum oluşturmaz ve iki denetimli sırada öğeleri belirten hiçbir başvuru, işaretçi veya yineleyiciyi geçersiz kılar. Aksi takdirde, bir dizi öğe ataması ve Oluşturucu çağrısı, iki denetimli dizi içindeki öğe sayısıyla orantılı olarak gerçekleştirilir.

## <a name="unique"></a>eşi

Eşit öğelerin her ardışık grubundaki ilk öğe hariç tümünü ortadan kaldırır.

```cpp
void unique();
template <class BinaryPredicate>
void unique(BinaryPredicate comp);
```

### <a name="parameters"></a>Parametreler

*comp* \
Birbirini izleyen öğeleri karşılaştırmak için kullanılan ikili koşul.

### <a name="remarks"></a>Açıklamalar

Her benzersiz öğenin birincisini tutar ve REST 'yi kaldırır. Öğelerin, eşit değer öğeleri listede bitişik olması için sıralanmalıdır.

İlk üye işlevi, bir önceki öğesiyle eşit olarak karşılaştırıldığı her öğe denetimli diziden kaldırılır. Yineleyiciler `Pi` ve `Pj` öğeleri `i` ve `j` atamak için ikinci üye işlevi, `i + 1 == j &&  comp(*Pi, *Pj)` için her öğeyi kaldırır.

Denetlenen bir uzunluk `N` (> 0) için, koşul ` comp(*Pi, *Pj)` `N - 1` kez değerlendirilir.

Özel durum yalnızca `comp` bir özel durum oluşturursa oluşur. Bu durumda, denetlenen sıra belirtilmemiş bir durumda bırakılır ve özel durum yeniden oluşturulur.

## <a name="value_type"></a>value_type

İleri listesinde depolanan öğe türünü temsil eden bir tür.

```cpp
typedef typename Allocator::value_type value_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, `Type` şablon parametresi için bir eş anlamlı.
