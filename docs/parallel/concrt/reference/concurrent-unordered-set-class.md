---
description: 'Hakkında daha fazla bilgi edinin: concurrent_unordered_set sınıfı'
title: concurrent_unordered_set Sınıfı
ms.date: 11/04/2016
f1_keywords:
- concurrent_unordered_set
- CONCURRENT_UNORDERED_SET/concurrency::concurrent_unordered_set
- CONCURRENT_UNORDERED_SET/concurrency::concurrent_unordered_set::concurrent_unordered_set
- CONCURRENT_UNORDERED_SET/concurrency::concurrent_unordered_set::hash_function
- CONCURRENT_UNORDERED_SET/concurrency::concurrent_unordered_set::insert
- CONCURRENT_UNORDERED_SET/concurrency::concurrent_unordered_set::key_eq
- CONCURRENT_UNORDERED_SET/concurrency::concurrent_unordered_set::swap
- CONCURRENT_UNORDERED_SET/concurrency::concurrent_unordered_set::unsafe_erase
helpviewer_keywords:
- concurrent_unordered_set class
ms.assetid: c61f9a9a-4fd9-491a-9251-e300737ecf4b
ms.openlocfilehash: 5030212b5f77d04a2c4a5a63e00f4c82388c650f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97115332"
---
# <a name="concurrent_unordered_set-class"></a>concurrent_unordered_set Sınıfı

`concurrent_unordered_set`Sınıfı, K türünde bir dizi öğenin değişen uzunluklu bir dizisini denetleyen eşzamanlılık açısından güvenli bir kapsayıcıdır. Dizi eşzamanlılık açısından güvenli ekleme, öğe erişimi, yineleyici erişimi ve yineleyici çapraz geçiş işlemlerine olanak sağlayan bir şekilde temsil edilir. Burada eşzamanlılık açısından güvenli, işaretçiler veya yineleyiciler her zaman geçerlidir. Bu, öğe başlatma garantisi veya belirli bir geçiş düzeni değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename K,
    typename _Hasher = std::hash<K>,
    typename key_equality = std::equal_to<K>,
    typename _Allocator_type = std::allocator<K>
>,
    typename key_equality = std::equal_to<K>,
    typename _Allocator_type = std::allocator<K>> class concurrent_unordered_set : public details::_Concurrent_hash<details::_Concurrent_unordered_set_traits<K,
    details::_Hash_compare<K,
_Hasher,
    key_equality>,
_Allocator_type,
    false>>;
```

### <a name="parameters"></a>Parametreler

*K*<br/>
Anahtar türü.

*_Hasher*<br/>
Karma işlev nesne türü. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değerdir `std::hash<K>` .

*key_equality*<br/>
Eşitlik karşılaştırma işlevi nesne türü. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değerdir `std::equal_to<K>` .

*_Allocator_type*<br/>
Eşzamanlı Sıralanmamış küme için bellek ayırma ve ayırmayı kaldırma hakkındaki ayrıntıları kapsülleyen saklı ayırıcı nesnesini temsil eden tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değerdir `std::allocator<K>` .

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`allocator_type`|Depolamayı yönetmek için bir ayırıcı türü.|
|`const_iterator`|Denetlenen dizi için bir sabit yineleyici türü.|
|`const_local_iterator`|Denetlenen dizi için bir sabit demet yineleyici türü.|
|`const_pointer`|Bir öğe için sabit bir işaretçi türü.|
|`const_reference`|Bir öğe için sabit bir başvuru türü.|
|`difference_type`|İki öğe arasındaki işaretli mesafenin türü.|
|`hasher`|Karma işlevin türü.|
|`iterator`|Denetlenen dizi için bir yineleyici türü.|
|`key_equal`|Karşılaştırma işlevinin türü.|
|`key_type`|Bir sıralama anahtarının türü.|
|`local_iterator`|Denetlenen dizi için bir demet yineleyici türü.|
|`pointer`|Bir öğe için bir işaretçi türü.|
|`reference`|Bir öğe için bir başvuru türü.|
|`size_type`|İki öğe arasındaki işaretsiz bir mesafenin türü.|
|`value_type`|Öğenin türü.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[concurrent_unordered_set](#ctor)|Fazla Yüklendi. Eşzamanlı bir sırasız küme oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[hash_function](#hash_function)|Depolanan karma işlevi nesnesini döndürür.|
|[ekleyin](#insert)|Fazla Yüklendi. Nesneye öğe ekler `concurrent_unordered_set` .|
|[key_eq](#key_eq)|Depolanan eşitlik karşılaştırma işlevi nesnesini döndürür.|
|[Kur](#swap)|İki nesnenin içeriğini değiştirir `concurrent_unordered_set` . Bu yöntem eşzamanlılık açısından güvenli değildir.|
|[unsafe_erase](#unsafe_erase)|Fazla Yüklendi. Belirtilen konumlarda öğeleri kaldırır `concurrent_unordered_set` . Bu yöntem eşzamanlılık açısından güvenli değildir.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[işleç =](#operator_eq)|Fazla Yüklendi. Başka bir `concurrent_unordered_set` nesnenin içeriğini buna atar. Bu yöntem eşzamanlılık açısından güvenli değildir.|

## <a name="remarks"></a>Açıklamalar

Sınıfıyla ilgili ayrıntılı bilgi için `concurrent_unordered_set` bkz. [paralel kapsayıcılar ve nesneler](../../../parallel/concrt/parallel-containers-and-objects.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`_Traits`

`_Concurrent_hash`

`concurrent_unordered_set`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** concurrent_unordered_set. h

**Ad alanı:** eşzamanlılık

## <a name="begin"></a><a name="begin"></a> başladı

Eşzamanlı kapsayıcıdaki ilk öğeyi gösteren bir yineleyici döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
iterator begin();

const_iterator begin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Eşzamanlı kapsayıcıdaki ilk öğe için bir yineleyici.

## <a name="cbegin"></a><a name="cbegin"></a> cbegin

Eşzamanlı kapsayıcıdaki ilk öğeyi gösteren bir const yineleyici döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Eşzamanlı kapsayıcıdaki ilk öğe için bir const yineleyici.

## <a name="cend"></a><a name="cend"></a> cend

Eşzamanlı kapsayıcıda son öğeden sonraki konuma işaret eden bir const yineleyici döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Eşzamanlı kapsayıcıda son öğeden sonraki konuma bir const yineleyici.

## <a name="clear"></a><a name="clear"></a> lediğiniz

Eş zamanlı kapsayıcıdaki tüm öğeleri siler. Bu işlev eşzamanlılık açısından güvenli değildir.

```cpp
void clear();
```

## <a name="concurrent_unordered_set"></a><a name="ctor"></a> concurrent_unordered_set

Eşzamanlı bir sırasız küme oluşturur.

```cpp
explicit concurrent_unordered_set(
    size_type _Number_of_buckets = 8,
    const hasher& _Hasher = hasher(),
    const key_equal& key_equality = key_equal(),
    const allocator_type& _Allocator = allocator_type());

concurrent_unordered_set(
    const allocator_type& _Allocator);

template <typename _Iterator>
concurrent_unordered_set(_Iterator first,
    _Iterator last,
    size_type _Number_of_buckets = 8,
    const hasher& _Hasher = hasher(),
    const key_equal& key_equality = key_equal(),
    const allocator_type& _Allocator = allocator_type());

concurrent_unordered_set(
    const concurrent_unordered_set& _Uset);

concurrent_unordered_set(
    const concurrent_unordered_set& _Uset,
    const allocator_type& _Allocator);

concurrent_unordered_set(
    concurrent_unordered_set&& _Uset);
```

### <a name="parameters"></a>Parametreler

*_Iterator*<br/>
Giriş yineleyicisinin türü.

*_Number_of_buckets*<br/>
Bu sırasız küme için ilk Demet sayısı.

*_Hasher*<br/>
Bu sırasız küme için karma işlevi.

*key_equality*<br/>
Bu sırasız küme için eşitlik karşılaştırma işlevi.

*_Allocator*<br/>
Bu sırasız küme için ayırıcı.

*adı*<br/>
*soyadına*<br/>
*_Uset*<br/>
`concurrent_unordered_set`Öğelerin kopyalanacağı veya taşınacağı kaynak nesne.

### <a name="remarks"></a>Açıklamalar

Tüm oluşturucular bir ayırıcı nesnesi depolar `_Allocator` ve sıralanmamış kümeyi başlatır.

İlk Oluşturucu boş bir başlangıç kümesi belirtir ve açıkça kullanılacak demet sayısını, karma işlevi, eşitlik işlevini ve ayırıcı türünü belirtir.

İkinci Oluşturucu, sıralanmamış küme için bir ayırıcı belirtir.

Üçüncü Oluşturucu yineleyici aralığı [,) tarafından sağlanan değerleri belirtir `_Begin` `_End` .

Dördüncü ve beşinci oluşturucular, eşzamanlı Sıralanmamış küme 'in bir kopyasını belirtir `_Uset` .

Son Oluşturucu, eşzamanlı Sıralanmamış küme 'in bir taşımasını belirtir `_Uset` .

## <a name="count"></a><a name="count"></a> biriktirme

Belirtilen bir anahtarla eşleşen öğelerin sayısını sayar. Bu işlev eşzamanlılık açısından güvenlidir.

```cpp
size_type count(const key_type& KVal) const;
```

### <a name="parameters"></a>Parametreler

*KVal*<br/>
Aranacak anahtar.

### <a name="return-value"></a>Dönüş Değeri

Anahtarın kapsayıcıda kaç kez göründüğüne ilişkin sayı.

## <a name="empty"></a><a name="empty"></a> olmamalıdır

Bir öğe olup olmadığını sınar. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** eşzamanlı kapsayıcı boşsa, **`false`** tersi durumda.

### <a name="remarks"></a>Açıklamalar

Eşzamanlı bir ekleme olması durumunda, eşzamanlı kapsayıcının boş olup olmadığı, dönüş değeri eşit bir şekilde okunmadan önce bu işlev çağrıldıktan hemen sonra değişebilir.

## <a name="end"></a><a name="end"></a> erer

Eşzamanlı kapsayıcıda son öğeden sonraki konumu gösteren bir yineleyici döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
iterator end();

const_iterator end() const;
```

### <a name="return-value"></a>Dönüş Değeri

Eşzamanlı kapsayıcıda son öğeden sonraki konuma bir yineleyici.

## <a name="equal_range"></a><a name="equal_range"></a> equal_range

Belirtilen anahtarla eşleşen bir Aralık bulur. Bu işlev eşzamanlılık açısından güvenlidir.

```cpp
std::pair<iterator,
    iterator> equal_range(
    const key_type& KVal);

std::pair<const_iterator,
    const_iterator> equal_range(
    const key_type& KVal) const;
```

### <a name="parameters"></a>Parametreler

*KVal*<br/>
Aranacak anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

İlk öğenin bir yineleyici olduğu bir [çift](../../../standard-library/pair-structure.md) ve ikinci öğe aralığın sonundaki bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Başlangıç yineleyicisinin ve bitiş yineleyicisinin öncesinde ek anahtarların eklenmesine neden olacak şekilde, eşzamanlı ekleme yapılabilir.

## <a name="find"></a><a name="find"></a> bilgi

Belirtilen bir anahtarla eşleşen bir öğeyi bulur. Bu işlev eşzamanlılık açısından güvenlidir.

```cpp
iterator find(const key_type& KVal);

const_iterator find(const key_type& KVal) const;
```

### <a name="parameters"></a>Parametreler

*KVal*<br/>
Aranacak anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen anahtarla eşleşen ilk öğenin konumunu gösteren bir yineleyici veya böyle bir öğe yoksa Yineleyici `end()` .

## <a name="get_allocator"></a><a name="get_allocator"></a> get_allocator

Bu eşzamanlı kapsayıcı için depolanan ayırıcı nesnesini döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
allocator_type get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu eşzamanlı kapsayıcı için depolanan ayırıcı nesne.

## <a name="hash_function"></a><a name="hash_function"></a> hash_function

Depolanan karma işlevi nesnesini döndürür.

```cpp
hasher hash_function() const;
```

### <a name="return-value"></a>Dönüş Değeri

Depolanan karma işlev nesnesi.

## <a name="insert"></a><a name="insert"></a> ekleyin

Nesneye öğe ekler `concurrent_unordered_set` .

```cpp
std::pair<iterator,
    bool> insert(
    const value_type& value);

iterator insert(
    const_iterator _Where,
    const value_type& value);

template<class _Iterator>
void insert(_Iterator first,
    _Iterator last);

template<class V>
std::pair<iterator,
    bool> insert(
    V&& value);

template<class V>
typename std::enable_if<!std::is_same<const_iterator,
    typename std::remove_reference<V>::type>::value,
    iterator>::type insert(
    const_iterator _Where,
    V&& value);
```

### <a name="parameters"></a>Parametreler

*_Iterator*<br/>
Ekleme için kullanılan Yineleyici türü.

*V*<br/>
Kümesine yerleştirilen değerin türü.

*değer*<br/>
Eklenecek değer.

*_Where*<br/>
Bir ekleme noktasını aramak için başlangıç konumu.

*adı*<br/>
Eklenecek aralığın başlangıcı.

*soyadına*<br/>
Eklenecek aralığın sonu.

### <a name="return-value"></a>Dönüş Değeri

Yineleyici ve Boole değeri içeren bir çift. Daha fazla bilgi için açıklamalar bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi, anahtarı için eşdeğer sıralama değerine sahip bir öğe X öğesinin mevcut olup olmadığını belirler `value` . Aksi takdirde, böyle bir X öğesi oluşturur ve ile başlatır `value` . İşlev daha sonra X öğesini atayan yineleyiciyi belirler `where` . Bir ekleme gerçekleştiyse, işlev döndürür `std::pair(where, true)` . Aksi takdirde, döndürür `std::pair(where, false)` .

İkinci üye işlevi `value` , `_Where` ekleme noktasını aramak için denetimli dizi içinde başlangıç alanı olarak kullanılan Insert () değerini döndürür.

Üçüncü üye işlevi öğe değerlerinin dizisini [ `first` ,) aralığından ekler `last` .

Son iki üye işlevi, `value` eklenen değeri oluşturmak için kullanılması dışında, ilk ikisi ile aynı şekilde davranır.

## <a name="key_eq"></a><a name="key_eq"></a> key_eq

Depolanan eşitlik karşılaştırma işlevi nesnesini döndürür.

```cpp
key_equal key_eq() const;
```

### <a name="return-value"></a>Dönüş Değeri

Depolanan eşitlik karşılaştırma işlevi nesnesi.

## <a name="load_factor"></a><a name="load_factor"></a> load_factor

Kapsayıcının geçerli yük faktörünü hesaplar ve döndürür. Yük faktörü, kapsayıcıda demet sayısına bölünen öğe sayısıdır.

```cpp
float load_factor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kapsayıcının yük faktörü.

## <a name="max_load_factor"></a><a name="max_load_factor"></a> max_load_factor

Kapsayıcının maksimum yük faktörünü alır veya ayarlar. En fazla yük faktörü, kapsayıcının iç tablosunu büyütmadan önce herhangi bir demet içinde olabilecek en fazla öğe sayısıdır.

```cpp
float max_load_factor() const;

void max_load_factor(float _Newmax);
```

### <a name="parameters"></a>Parametreler

`_Newmax`

### <a name="return-value"></a>Dönüş Değeri

İlk üye işlevi, depolanan en fazla yük faktörünü döndürür. İkinci üye işlevi bir değer döndürmüyor, ancak sağlanan yük faktörü geçersiz ise [out_of_range](../../../standard-library/out-of-range-class.md) bir özel durum atar.

## <a name="max_size"></a><a name="max_size"></a> max_size

Ayırıcı tarafından belirlenen eşzamanlı kapsayıcının maksimum boyutunu döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu eşzamanlı kapsayıcıya eklenebilecek en fazla öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Bu üst sınır değeri, kapsayıcının gerçekten tutabileceğinden daha yüksek olabilir.

## <a name="operator"></a><a name="operator_eq"></a> işleç =

Başka bir `concurrent_unordered_set` nesnenin içeriğini buna atar. Bu yöntem eşzamanlılık açısından güvenli değildir.

```cpp
concurrent_unordered_set& operator= (const concurrent_unordered_set& _Uset);

concurrent_unordered_set& operator= (concurrent_unordered_set&& _Uset);
```

### <a name="parameters"></a>Parametreler

*_Uset*<br/>
Kaynak `concurrent_unordered_set` nesne.

### <a name="return-value"></a>Dönüş Değeri

Bu nesneye bir başvuru `concurrent_unordered_set` .

### <a name="remarks"></a>Açıklamalar

Eşzamanlı sıralanmamış bir küme içindeki var olan öğeleri sildikten sonra, `operator=` içeriğini kopyalar veya `_Uset` aynı anda sıralanmamış bir küme içine taşısın.

## <a name="rehash"></a><a name="rehash"></a> rehash

Karma tabloyu yeniden oluşturur.

```cpp
void rehash(size_type _Buckets);
```

### <a name="parameters"></a>Parametreler

*_Buckets*<br/>
İstenen demet sayısı.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, demetlerin sayısını en az olacak şekilde değiştirir `_Buckets` ve karma tabloyu gerektiği gibi yeniden derler. Demetlerin sayısı 2 ' nin üssü olmalıdır. 2 ' nin üssü yoksa, 2 ' nin bir sonraki en büyük kuvvetinin yuvarlanmasını sağlar.

Demet sayısı geçersizse (0 veya maksimum demet sayısından büyükse) [out_of_range](../../../standard-library/out-of-range-class.md) bir özel durum oluşturur.

## <a name="size"></a><a name="size"></a> boyutla

Bu eşzamanlı kapsayıcıdaki öğelerin sayısını döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kapsayıcıdaki öğelerin sayısı.

### <a name="remarks"></a>Açıklamalar

Eşzamanlı bir ekleme durumunda, dönüş değeri eşit bir şekilde okunmadan önce, eşzamanlı kapsayıcıdaki öğelerin sayısı bu işlev çağrıldıktan hemen sonra değiştirilebilir.

## <a name="swap"></a><a name="swap"></a> Kur

İki nesnenin içeriğini değiştirir `concurrent_unordered_set` . Bu yöntem eşzamanlılık açısından güvenli değildir.

```cpp
void swap(concurrent_unordered_set& _Uset);
```

### <a name="parameters"></a>Parametreler

*_Uset*<br/>
`concurrent_unordered_set`İle takas edilecek nesne.

## <a name="unsafe_begin"></a><a name="unsafe_begin"></a> unsafe_begin

Belirli bir demet için bu kapsayıcıdaki ilk öğeye bir yineleyici döndürür.

```cpp
local_iterator unsafe_begin(size_type _Bucket);

const_local_iterator unsafe_begin(size_type _Bucket) const;
```

### <a name="parameters"></a>Parametreler

*_Bucket*<br/>
Demet dizini.

### <a name="return-value"></a>Dönüş Değeri

Demet başlangıcını işaret eden bir yineleyici.

## <a name="unsafe_bucket"></a><a name="unsafe_bucket"></a> unsafe_bucket

Bu kapsayıcıda, belirli bir anahtarın eşlendiği demet dizinini döndürür.

```cpp
size_type unsafe_bucket(const key_type& KVal) const;
```

### <a name="parameters"></a>Parametreler

*KVal*<br/>
Aranan öğe anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Bu kapsayıcıdaki anahtar için demet dizini.

## <a name="unsafe_bucket_count"></a><a name="unsafe_bucket_count"></a> unsafe_bucket_count

Bu kapsayıcıdaki geçerli demet sayısını döndürür.

```cpp
size_type unsafe_bucket_count() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu kapsayıcıdaki geçerli demet sayısı.

## <a name="unsafe_bucket_size"></a><a name="unsafe_bucket_size"></a> unsafe_bucket_size

Bu kapsayıcının belirli bir demetini içindeki öğelerin sayısını döndürür.

```cpp
size_type unsafe_bucket_size(size_type _Bucket);
```

### <a name="parameters"></a>Parametreler

*_Bucket*<br/>
Aranacak demet.

### <a name="return-value"></a>Dönüş Değeri

Bu kapsayıcıdaki geçerli demet sayısı.

## <a name="unsafe_cbegin"></a><a name="unsafe_cbegin"></a> unsafe_cbegin

Belirli bir demet için bu kapsayıcıdaki ilk öğeye bir yineleyici döndürür.

```cpp
const_local_iterator unsafe_cbegin(size_type _Bucket) const;
```

### <a name="parameters"></a>Parametreler

*_Bucket*<br/>
Demet dizini.

### <a name="return-value"></a>Dönüş Değeri

Demet başlangıcını işaret eden bir yineleyici.

## <a name="unsafe_cend"></a><a name="unsafe_cend"></a> unsafe_cend

Belirli bir demet içindeki son öğeden sonraki konuma bir yineleyici döndürür.

```cpp
const_local_iterator unsafe_cend(size_type _Bucket) const;
```

### <a name="parameters"></a>Parametreler

*_Bucket*<br/>
Demet dizini.

### <a name="return-value"></a>Dönüş Değeri

Demet başlangıcını işaret eden bir yineleyici.

## <a name="unsafe_end"></a><a name="unsafe_end"></a> unsafe_end

Belirli bir demet için bu kapsayıcıdaki son öğeye bir yineleyici döndürür.

```cpp
local_iterator unsafe_end(size_type _Bucket);

const_local_iterator unsafe_end(size_type _Bucket) const;
```

### <a name="parameters"></a>Parametreler

*_Bucket*<br/>
Demet dizini.

### <a name="return-value"></a>Dönüş Değeri

Demet sonuna işaret eden bir yineleyici.

## <a name="unsafe_erase"></a><a name="unsafe_erase"></a> unsafe_erase

Belirtilen konumlarda öğeleri kaldırır `concurrent_unordered_set` . Bu yöntem eşzamanlılık açısından güvenli değildir.

```cpp
iterator unsafe_erase(
    const_iterator _Where);

size_type unsafe_erase(
    const key_type& KVal);

iterator unsafe_erase(
    const_iterator first,
    const_iterator last);
```

### <a name="parameters"></a>Parametreler

*_Where*<br/>
Silinecek Yineleyici konumu.

*KVal*<br/>
Silinecek anahtar değer.

*adı*<br/>
*soyadına*<br/>
Yineleyiciler.

### <a name="return-value"></a>Dönüş Değeri

İlk iki üye işlevi, kaldırılan tüm öğelerin ötesinde kalan ilk öğeyi atayan bir yineleyici döndürür veya böyle bir öğe yoksa [End](#end)() döndürün. Üçüncü üye işlevi, kaldıran öğe sayısını döndürür.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi tarafından işaret edilen öğeyi kaldırır `_Where` . İkinci üye işlevi [,) aralığındaki öğeleri kaldırır `_Begin` `_End` .

Üçüncü üye işlevi, [equal_range](#equal_range)(kval) ile ayrılmış aralıktaki öğeleri kaldırır.

## <a name="unsafe_max_bucket_count"></a><a name="unsafe_max_bucket_count"></a> unsafe_max_bucket_count

Bu kapsayıcıdaki en fazla demet sayısını döndürür.

```cpp
size_type unsafe_max_bucket_count() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu kapsayıcıdaki demet sayısı üst sınırı.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[Paralel Kapsayıcılar ve nesneler](../../../parallel/concrt/parallel-containers-and-objects.md)
