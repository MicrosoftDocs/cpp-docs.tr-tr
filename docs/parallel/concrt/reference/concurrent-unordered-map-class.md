---
title: concurrent_unordered_map Sınıfı
ms.date: 11/04/2016
f1_keywords:
- concurrent_unordered_map
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_map
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_map::concurrent_unordered_map
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_map::at
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_map::hash_function
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_map::insert
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_map::key_eq
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_map::swap
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_map::unsafe_erase
helpviewer_keywords:
- concurrent_unordered_map class
ms.assetid: b2d879dd-87ef-4af9-a266-a5443fd538b8
ms.openlocfilehash: a43e52edfe223dae51737d7d2cde37e3b8238f08
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75298694"
---
# <a name="concurrent_unordered_map-class"></a>concurrent_unordered_map Sınıfı

`concurrent_unordered_map` sınıfı, `std::pair<const K, _Element_type>`türündeki çeşitli uzunluktaki öğeleri denetleyen eşzamanlılık açısından güvenli bir kapsayıcıdır. Dizi eşzamanlılık açısından güvenli ekleme, öğe erişimi, yineleyici erişimi ve yineleyici çapraz geçiş işlemlerine olanak sağlayan bir şekilde temsil edilir. Burada eşzamanlılık açısından güvenli, işaretçiler veya yineleyiciler her zaman geçerlidir. Bu, öğe başlatma garantisi veya belirli bir geçiş düzeni değildir.

## <a name="syntax"></a>Sözdizimi

```
template <typename K,
    typename _Element_type,
    typename _Hasher = std::hash<K>,
    typename key_equality = std::equal_to<K>,
    typename _Allocator_type = std::allocator<std::pair<const K,
    _Element_type>>
>,
typename key_equality = std::equal_to<K>,
    typename _Allocator_type = std::allocator<std::pair<const K,
    _Element_type>>> class concurrent_unordered_map : public details::_Concurrent_hash<details::_Concurrent_unordered_map_traits<K,
    _Element_type,
details::_Hash_compare<K,
    _Hasher,
key_equality>,
    _Allocator_type,
false>>;
```

#### <a name="parameters"></a>Parametreler

*K*<br/>
Anahtar türü.

*_Element_type*<br/>
Eşlenen tür.

*_Hasher*<br/>
Karma işlev nesne türü. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `std::hash<K>`.

*key_equality*<br/>
Eşitlik karşılaştırma işlevi nesne türü. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `std::equal_to<K>`.

*_Allocator_type*<br/>
Eşzamanlı sıralanmamış eşleme için bellek ayırmayı ve ayırmayı kaldırma hakkındaki ayrıntıları kapsülleyen saklı ayırıcı nesnesini temsil eden tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `std::allocator<std::pair<K`, `_Element_type>>`.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Name|Açıklama|
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
|`mapped_type`|Her bir anahtar ile ilişkili bir eşlenen değer türü.|
|`pointer`|Bir öğe için bir işaretçi türü.|
|`reference`|Bir öğe için bir başvuru türü.|
|`size_type`|İki öğe arasındaki işaretsiz bir mesafenin türü.|
|`value_type`|Öğenin türü.|

### <a name="public-constructors"></a>Genel Oluşturucular

|Name|Açıklama|
|----------|-----------------|
|[concurrent_unordered_map](#ctor)|Aşırı yüklendi. Eşzamanlı bir sırasız eşleme oluşturur.|

### <a name="public-methods"></a>Genel Yöntemler

|Name|Açıklama|
|----------|-----------------|
|[hızı](#at)|Aşırı yüklendi. Belirtilen anahtar değerine sahip `concurrent_unordered_map` bir öğe bulur.. Bu yöntem eşzamanlılık açısından güvenlidir.|
|[hash_function](#hash_function)|Depolanan karma işlevi nesnesini alır.|
|[ekleyin](#insert)|Aşırı yüklendi. `concurrent_unordered_map` nesnesine öğe ekler.|
|[key_eq](#key_eq)|Depolanan eşitlik karşılaştırma işlevi nesnesini alır.|
|[Kur](#swap)|İki `concurrent_unordered_map` nesnesinin içeriğini değiştirir. Bu yöntem eşzamanlılık açısından güvenli değildir.|
|[unsafe_erase](#unsafe_erase)|Aşırı yüklendi. Belirtilen konumlarda `concurrent_unordered_map` öğeleri kaldırır. Bu yöntem eşzamanlılık açısından güvenli değildir.|

### <a name="public-operators"></a>Genel İşleçler

|Name|Açıklama|
|----------|-----------------|
|[işleç\[\]](#operator_at)|Aşırı yüklendi. Belirtilen anahtarı içeren bir öğe bulur veya ekler. Bu yöntem eşzamanlılık açısından güvenlidir.|
|[operator=](#operator_eq)|Aşırı yüklendi. Başka bir `concurrent_unordered_map` nesnesinin içeriğini buna atar. Bu yöntem eşzamanlılık açısından güvenli değildir.|

## <a name="remarks"></a>Açıklamalar

`concurrent_unordered_map` sınıfı hakkında ayrıntılı bilgi için bkz. [paralel kapsayıcılar ve nesneler](../../../parallel/concrt/parallel-containers-and-objects.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`_Traits`

`_Concurrent_hash`

`concurrent_unordered_map`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** concurrent_unordered_map. h

**Ad alanı:** eşzamanlılık

##  <a name="at"></a>hızı

Belirtilen anahtar değerine sahip `concurrent_unordered_map` bir öğe bulur.. Bu yöntem eşzamanlılık açısından güvenlidir.

```
mapped_type& at(const key_type& KVal);

const mapped_type& at(const key_type& KVal) const;
```

### <a name="parameters"></a>Parametreler

*KVal*<br/>
Bulunacak anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

Bulunan öğenin veri değerine başvuru.

### <a name="remarks"></a>Açıklamalar

Bağımsız değişken anahtar değeri bulunamazsa, işlev `out_of_range`sınıfından bir nesne oluşturur.

##  <a name="begin"></a>başladı

Eşzamanlı kapsayıcıdaki ilk öğeyi gösteren bir yineleyici döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.

```
iterator begin();

const_iterator begin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Eşzamanlı kapsayıcıdaki ilk öğe için bir yineleyici.

##  <a name="cbegin"></a>cbegin

Eşzamanlı kapsayıcıdaki ilk öğeyi gösteren bir const yineleyici döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.

```
const_iterator cbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Eşzamanlı kapsayıcıdaki ilk öğe için bir const yineleyici.

##  <a name="cend"></a>cend

Eşzamanlı kapsayıcıda son öğeden sonraki konuma işaret eden bir const yineleyici döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.

```
const_iterator cend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Eşzamanlı kapsayıcıda son öğeden sonraki konuma bir const yineleyici.

##  <a name="clear"></a>lediğiniz

Eş zamanlı kapsayıcıdaki tüm öğeleri siler. Bu işlev eşzamanlılık açısından güvenli değildir.

```
void clear();
```

##  <a name="ctor"></a>concurrent_unordered_map

Eşzamanlı bir sırasız eşleme oluşturur.

```
explicit concurrent_unordered_map(
    size_type _Number_of_buckets = 8,
    const hasher& _Hasher = hasher(),
    const key_equal& key_equality = key_equal(),
    const allocator_type& _Allocator = allocator_type());

concurrent_unordered_map(
    const allocator_type& _Allocator);

template <typename _Iterator>
concurrent_unordered_map(_Iterator _Begin,
    _Iterator _End,
    size_type _Number_of_buckets = 8,
    const hasher& _Hasher = hasher(),
    const key_equal& key_equality = key_equal(),
    const allocator_type& _Allocator = allocator_type());

concurrent_unordered_map(
    const concurrent_unordered_map& _Umap);

concurrent_unordered_map(
    const concurrent_unordered_map& _Umap,
    const allocator_type& _Allocator);

concurrent_unordered_map(
    concurrent_unordered_map&& _Umap);
```

### <a name="parameters"></a>Parametreler

*_Iterator*<br/>
Giriş yineleyicisinin türü.

*_Number_of_buckets*<br/>
Bu sırasız eşleme için ilk Demet sayısı.

*_Hasher*<br/>
Bu sırasız eşleme için karma işlevi.

*key_equality*<br/>
Bu sırasız eşleme için eşitlik karşılaştırma işlevi.

*_Allocator*<br/>
Bu sıralanmamış haritanın ayırıcısı.

*_Begin*<br/>
Kopyalanacak öğe aralığındaki ilk öğenin konumu.

*_End*<br/>
Kopyalanacak öğe aralığının ötesinde ilk öğenin konumu.

*_Umap*<br/>
Öğeleri kopyalamak veya taşımak için kaynak `concurrent_unordered_map` nesnesi.

### <a name="remarks"></a>Açıklamalar

Tüm oluşturucular bir ayırıcı nesne `_Allocator` depolar ve sıralanmamış eşlemeyi başlatır.

İlk Oluşturucu boş bir ilk eşleme belirtir ve kullanılacak demet sayısını, karma işlevi, eşitlik işlevini ve ayırıcı türünü belirtir.

İkinci Oluşturucu, sıralanmamış eşleme için bir ayırıcı belirtir.

Üçüncü Oluşturucu yineleyici aralığı tarafından sağlanan değerleri belirtir [`_Begin`, `_End`).

Dördüncü ve beşinci oluşturucular, eşzamanlı sıralanmamış eşlemenin `_Umap`bir kopyasını belirtir.

Son Oluşturucu, eşzamanlı sıralanmamış haritanın `_Umap`bir taşımasını belirtir.

##  <a name="count"></a>biriktirme

Belirtilen bir anahtarla eşleşen öğelerin sayısını sayar. Bu işlev eşzamanlılık açısından güvenlidir.

```
size_type count(const key_type& KVal) const;
```

### <a name="parameters"></a>Parametreler

*KVal*<br/>
Aranacak anahtar.

### <a name="return-value"></a>Dönüş Değeri

Anahtarın kapsayıcıda kaç kez göründüğüne ilişkin sayı.

##  <a name="empty"></a>olmamalıdır

Bir öğe olup olmadığını sınar. Bu yöntem eşzamanlılık açısından güvenlidir.

```
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

eşzamanlı kapsayıcı boş ise **true** , aksi takdirde **false** .

### <a name="remarks"></a>Açıklamalar

Eşzamanlı bir ekleme olması durumunda, eşzamanlı kapsayıcının boş olup olmadığı, dönüş değeri eşit bir şekilde okunmadan önce bu işlev çağrıldıktan hemen sonra değişebilir.

##  <a name="end"></a>erer

Eşzamanlı kapsayıcıda son öğeden sonraki konumu gösteren bir yineleyici döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.

```
iterator end();

const_iterator end() const;
```

### <a name="return-value"></a>Dönüş Değeri

Eşzamanlı kapsayıcıda son öğeden sonraki konuma bir yineleyici.

##  <a name="equal_range"></a>equal_range

Belirtilen anahtarla eşleşen bir Aralık bulur. Bu işlev eşzamanlılık açısından güvenlidir.

```
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

##  <a name="find"></a>bilgi

Belirtilen bir anahtarla eşleşen bir öğeyi bulur. Bu işlev eşzamanlılık açısından güvenlidir.

```
iterator find(const key_type& KVal);

const_iterator find(const key_type& KVal) const;
```

### <a name="parameters"></a>Parametreler

*KVal*<br/>
Aranacak anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen anahtarla eşleşen ilk öğenin konumunu gösteren bir yineleyici veya böyle bir öğe yoksa Yineleyici `end()`.

##  <a name="get_allocator"></a>get_allocator

Bu eşzamanlı kapsayıcı için depolanan ayırıcı nesnesini döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.

```
allocator_type get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu eşzamanlı kapsayıcı için depolanan ayırıcı nesne.

##  <a name="hash_function"></a>hash_function

Depolanan karma işlevi nesnesini alır.

```
hasher hash_function() const;
```

### <a name="return-value"></a>Dönüş Değeri

Depolanan karma işlev nesnesi.

##  <a name="insert"></a>ekleyin

`concurrent_unordered_map` nesnesine öğe ekler.

```
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
Haritaya yerleştirilen değerin türü.

*value*<br/>
Eklenecek değer.

*_Where*<br/>
Bir ekleme noktasını aramak için başlangıç konumu.

*first*<br/>
Eklenecek aralığın başlangıcı.

*last*<br/>
Eklenecek aralığın sonu.

### <a name="return-value"></a>Dönüş Değeri

Yineleyici ve Boole değeri içeren bir çift. Daha fazla bilgi için açıklamalar bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi, anahtarının, anahtarı `value`buna eşdeğer sıralamaya sahip olan dizide bulunan X öğesinin mevcut olup olmadığını belirler. Aksi takdirde, böyle bir X öğesi oluşturur ve `value`ile başlatır. Bu işlev daha sonra X öğesini atayan Yineleyici `where` belirler. Bir ekleme gerçekleştiyse, işlev `std::pair(where, true)`döndürür. Aksi takdirde, `std::pair(where, false)`döndürür.

İkinci üye işlevi, ekleme noktasını aramak için denetimli dizi içinde bir başlangıç yeri olarak `_Where` kullanarak Insert (`value`) döndürür.

Üçüncü üye işlevi öğe değerlerinin dizisini [`first`, `last`) aralığından ekler.

Son iki üye işlevi, eklenen değeri oluşturmak için `value` kullanılması dışında, ilk ikisi ile aynı şekilde davranır.

##  <a name="key_eq"></a>key_eq

Depolanan eşitlik karşılaştırma işlevi nesnesini alır.

```
key_equal key_eq() const;
```

### <a name="return-value"></a>Dönüş Değeri

Depolanan eşitlik karşılaştırma işlevi nesnesi.

##  <a name="load_factor"></a>load_factor

Kapsayıcının geçerli yük faktörünü hesaplar ve döndürür. Yük faktörü, kapsayıcıda demet sayısına bölünen öğe sayısıdır.

```
float load_factor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kapsayıcının yük faktörü.

##  <a name="max_load_factor"></a> max_load_factor

Kapsayıcının maksimum yük faktörünü alır veya ayarlar. En fazla yük faktörü, kapsayıcının iç tablosunu büyütmadan önce herhangi bir demet içinde olabilecek en fazla öğe sayısıdır.

```
float max_load_factor() const;

void max_load_factor(float _Newmax);
```

### <a name="parameters"></a>Parametreler

`_Newmax`

### <a name="return-value"></a>Dönüş Değeri

İlk üye işlevi, depolanan en fazla yük faktörünü döndürür. İkinci üye işlevi bir değer döndürmüyor, ancak sağlanan yük faktörü geçersiz ise [out_of_range](../../../standard-library/out-of-range-class.md) bir özel durum atar.

##  <a name="max_size"></a>max_size

Ayırıcı tarafından belirlenen eşzamanlı kapsayıcının maksimum boyutunu döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.

```
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu eşzamanlı kapsayıcıya eklenebilecek en fazla öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Bu üst sınır değeri, kapsayıcının gerçekten tutabileceğinden daha yüksek olabilir.

##  <a name="operator_at"></a>operator []

Belirtilen anahtarı içeren bir öğe bulur veya ekler. Bu yöntem eşzamanlılık açısından güvenlidir.

```
mapped_type& operator[](const key_type& kval);

mapped_type& operator[](key_type&& kval);
```

### <a name="parameters"></a>Parametreler

*KVal*<br/>
Anahtar değeri

bulun veya ekleyin.

### <a name="return-value"></a>Dönüş Değeri

Bulunan veya ınsertedelement veri değerine başvuru.

### <a name="remarks"></a>Açıklamalar

Bağımsız değişken anahtar değeri bulunamazsa, değer veri türünün varsayılan değeriyle birlikte eklenir.

`operator[]`, `m[key] = DataValue;`kullanarak bir harita `m` öğe eklemek için kullanılabilir; burada `DataValue`, `mapped_type` anahtar değeri olan öğenin `key`değeridir.

Öğeleri eklemek için `operator[]` kullanırken, döndürülen başvuru, bir eklentinin önceden varolan bir öğeyi değiştirip değiştirmediğini veya yeni bir tane oluşturmadığını göstermez. `find` ve [Insert](#insert) üye işlevleri, bir ekleme işleminden önce belirtilen anahtara sahip bir öğenin zaten mevcut olup olmadığını anlamak için kullanılabilir.

##  <a name="operator_eq"></a>işleç =

Başka bir `concurrent_unordered_map` nesnesinin içeriğini buna atar. Bu yöntem eşzamanlılık açısından güvenli değildir.

```
concurrent_unordered_map& operator= (const concurrent_unordered_map& _Umap);

concurrent_unordered_map& operator= (concurrent_unordered_map&& _Umap);
```

### <a name="parameters"></a>Parametreler

*_Umap*<br/>
Kaynak `concurrent_unordered_map` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Bu `concurrent_unordered_map` nesnesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

Yinelenen bir vektör olan mevcut öğeleri sildikten sonra, `operator=` `_Umap` içeriğini eşzamanlı vektöre kopyalar ya da taşıdığında.

##  <a name="rehash"></a>rehash

Karma tabloyu yeniden oluşturur.

```
void rehash(size_type _Buckets);
```

### <a name="parameters"></a>Parametreler

*_Buckets*<br/>
İstenen demet sayısı.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, demetlerin sayısını en az `_Buckets` olarak değiştirir ve gerekirse karma tabloyu yeniden oluşturur. Demetlerin sayısı 2 ' nin üssü olmalıdır. 2 ' nin üssü yoksa, 2 ' nin bir sonraki en büyük kuvvetinin yuvarlanmasını sağlar.

Demet sayısı geçersizse (0 veya maksimum demet sayısından büyükse) [out_of_range](../../../standard-library/out-of-range-class.md) bir özel durum oluşturur.

##  <a name="size"></a>boyutla

Bu eşzamanlı kapsayıcıdaki öğelerin sayısını döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.

```
size_type size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kapsayıcıdaki öğelerin sayısı.

### <a name="remarks"></a>Açıklamalar

Eşzamanlı bir ekleme durumunda, dönüş değeri eşit bir şekilde okunmadan önce, eşzamanlı kapsayıcıdaki öğelerin sayısı bu işlev çağrıldıktan hemen sonra değiştirilebilir.

##  <a name="swap"></a>Kur

İki `concurrent_unordered_map` nesnesinin içeriğini değiştirir. Bu yöntem eşzamanlılık açısından güvenli değildir.

```
void swap(concurrent_unordered_map& _Umap);
```

### <a name="parameters"></a>Parametreler

*_Umap*<br/>
İle takas edilecek `concurrent_unordered_map` nesnesi.

##  <a name="unsafe_begin"></a>unsafe_begin

Belirli bir demet için bu kapsayıcıdaki ilk öğeye bir yineleyici döndürür.

```
local_iterator unsafe_begin(size_type _Bucket);

const_local_iterator unsafe_begin(size_type _Bucket) const;
```

### <a name="parameters"></a>Parametreler

*_Bucket*<br/>
Demet dizini.

### <a name="return-value"></a>Dönüş Değeri

Demet başlangıcını işaret eden bir yineleyici.

##  <a name="unsafe_bucket"></a>unsafe_bucket

Bu kapsayıcıda, belirli bir anahtarın eşlendiği demet dizinini döndürür.

```
size_type unsafe_bucket(const key_type& KVal) const;
```

### <a name="parameters"></a>Parametreler

*KVal*<br/>
Aranan öğe anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Bu kapsayıcıdaki anahtar için demet dizini.

##  <a name="unsafe_bucket_count"></a>unsafe_bucket_count

Bu kapsayıcıdaki geçerli demet sayısını döndürür.

```
size_type unsafe_bucket_count() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu kapsayıcıdaki geçerli demet sayısı.

##  <a name="unsafe_bucket_size"></a>unsafe_bucket_size

Bu kapsayıcının belirli bir demetini içindeki öğelerin sayısını döndürür.

```
size_type unsafe_bucket_size(size_type _Bucket);
```

### <a name="parameters"></a>Parametreler

*_Bucket*<br/>
Aranacak demet.

### <a name="return-value"></a>Dönüş Değeri

Bu kapsayıcıdaki geçerli demet sayısı.

##  <a name="unsafe_cbegin"></a>unsafe_cbegin

Belirli bir demet için bu kapsayıcıdaki ilk öğeye bir yineleyici döndürür.

```
const_local_iterator unsafe_cbegin(size_type _Bucket) const;
```

### <a name="parameters"></a>Parametreler

*_Bucket*<br/>
Demet dizini.

### <a name="return-value"></a>Dönüş Değeri

Demet başlangıcını işaret eden bir yineleyici.

##  <a name="unsafe_cend"></a>unsafe_cend

Belirli bir demet içindeki son öğeden sonraki konuma bir yineleyici döndürür.

```
const_local_iterator unsafe_cend(size_type _Bucket) const;
```

### <a name="parameters"></a>Parametreler

*_Bucket*<br/>
Demet dizini.

### <a name="return-value"></a>Dönüş Değeri

Demet başlangıcını işaret eden bir yineleyici.

##  <a name="unsafe_end"></a>unsafe_end

Belirli bir demet için bu kapsayıcıdaki son öğeye bir yineleyici döndürür.

```
local_iterator unsafe_end(size_type _Bucket);

const_local_iterator unsafe_end(size_type _Bucket) const;
```

### <a name="parameters"></a>Parametreler

*_Bucket*<br/>
Demet dizini.

### <a name="return-value"></a>Dönüş Değeri

Demet sonuna işaret eden bir yineleyici.

##  <a name="unsafe_erase"></a>unsafe_erase

Belirtilen konumlarda `concurrent_unordered_map` öğeleri kaldırır. Bu yöntem eşzamanlılık açısından güvenli değildir.

```
iterator unsafe_erase(
    const_iterator _Where);

iterator unsafe_erase(
    const_iterator _Begin,
    const_iterator _End);

size_type unsafe_erase(
    const key_type& KVal);
```

### <a name="parameters"></a>Parametreler

*_Where*<br/>
Silinecek Yineleyici konumu.

*_Begin*<br/>
Silinecek öğe aralığındaki ilk öğenin konumu.

*_End*<br/>
Silinecek öğe aralığının ötesinde ilk öğenin konumu.

*KVal*<br/>
Silinecek anahtar değer.

### <a name="return-value"></a>Dönüş Değeri

İlk iki üye işlevi, kaldırılan öğelerin ötesinde kalan ilk öğeyi atayan bir yineleyici döndürür veya böyle bir öğe yoksa `concurrent_unordered_map::end`(). Üçüncü üye işlevi, kaldıran öğe sayısını döndürür.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi, `_Where`tarafından işaret edilen denetimli sıranın öğesini kaldırır. İkinci üye işlevi [`_Begin`, `_End`) aralığındaki öğeleri kaldırır.

Üçüncü üye işlevi, `concurrent_unordered_map::equal_range`(KVal) ile ayrılmış aralıktaki öğeleri kaldırır.

##  <a name="unsafe_max_bucket_count"></a>unsafe_max_bucket_count

Bu kapsayıcıdaki en fazla demet sayısını döndürür.

```
size_type unsafe_max_bucket_count() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu kapsayıcıdaki demet sayısı üst sınırı.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[Paralel Kapsayıcılar ve Nesneler](../../../parallel/concrt/parallel-containers-and-objects.md)
