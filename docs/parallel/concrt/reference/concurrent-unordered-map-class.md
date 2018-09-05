---
title: concurrent_unordered_map sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- concurrent_unordered_map class
ms.assetid: b2d879dd-87ef-4af9-a266-a5443fd538b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c6fddd90eaa6259cd2552dddbeafb405d90580ac
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43684358"
---
# <a name="concurrentunorderedmap-class"></a>concurrent_unordered_map Sınıfı
`concurrent_unordered_map` Sınıfı, bir türdeki öğelerin değişen uzunluktaki dizisini denetleyen eşzamanlılığı güvenli bir kapsayıcıdır `std::pair<const K, _Element_type>`. Sıra, eşzamanlılık açısından güvenli sağlayan bir şekilde temsil edilir sona ekleme, öğe erişimi, yineleyici erişimi ve yineleyici çapraz geçiş işlemleri.  
  
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
 `K`  
 Anahtar türü.  
  
 `_Element_type`  
 Eşlenen tür.  
  
 `_Hasher`  
 Karma işlev nesne türü. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `std::hash<K>`.  
  
 `key_equality`  
 Eşitlik karşılaştırma işlevi nesne türü. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `std::equal_to<K>`.  
  
 `_Allocator_type`  
 Ayırma ve eşzamanlı sıralanmamış eşleme için bellek ayırmayı kaldırma hakkındaki ayrıntıları içeren saklı ayırıcı nesnesini gösteren tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `std::allocator<std::pair<K`, `_Element_type>>`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel Typedefler  
  
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
|`mapped_type`|Her bir anahtar ile ilişkili bir eşlenen değer türü.|  
|`pointer`|Bir öğe için bir işaretçi türü.|  
|`reference`|Bir öğe için bir başvuru türü.|  
|`size_type`|İki öğe arasındaki işaretsiz bir mesafenin türü.|  
|`value_type`|Öğenin türü.|  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[concurrent_unordered_map](#ctor)|Fazla Yüklendi. Eş zamanlı sıralanmamış bir harita oluşturur.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[konumunda](#at)|Fazla Yüklendi. Bir öğe bulur bir `concurrent_unordered_map` belirtilen anahtar değere sahip... Bu yöntem eşzamanlı güvenlidir.|  
|[hash_function](#hash_function)|Depolanan karma işlevi nesnesini alır.|  
|[Ekle](#insert)|Fazla Yüklendi. Öğeler ekler `concurrent_unordered_map` nesne.|  
|[key_eq](#key_eq)|Depolanan eşitlik karşılaştırma işlevi nesnesini alır.|  
|[değiştirme](#swap)|İki içeriğini değiştirir `concurrent_unordered_map` nesneleri. Bu yöntem eşzamanlı güvenli değil.|  
|[unsafe_erase](#unsafe_erase)|Fazla Yüklendi. Öğeleri kaldırır `concurrent_unordered_map` belirtilen konumlarda. Bu yöntem eşzamanlı güvenli değil.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[operator]](#operator_at)|Fazla Yüklendi. Belirtilen anahtarı içeren bir öğe bulur veya ekler. Bu yöntem eşzamanlı güvenlidir.|  
|[operator=](#operator_eq)|Fazla Yüklendi. Başka bir deponun içeriğini atar `concurrent_unordered_map` buna nesne. Bu yöntem eşzamanlı güvenli değil.|  
  
## <a name="remarks"></a>Açıklamalar  
 Hakkında ayrıntılı bilgi için `concurrent_unordered_map` sınıfı [paralel kapsayıcılar ve nesneler](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `_Traits`  
  
 `_Concurrent_hash`  
  
 `concurrent_unordered_map`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concurrent_unordered_map.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="at"></a> konumunda 

 Bir öğe bulur bir `concurrent_unordered_map` belirtilen anahtar değere sahip... Bu yöntem eşzamanlı güvenlidir.  
  
```
mapped_type& at(const key_type& KVal);

const mapped_type& at(const key_type& KVal) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `KVal`  
 Bulunacak anahtar değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bulunan elemanın veri değerine başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Bağımsız değişken anahtarı değeri bulunamazsa, işlev sınıfın bir nesnesi atar `out_of_range`.  
  
##  <a name="begin"></a> başlayın 

 Eş zamanlı kapsayıcıdaki ilk öğeyi gösteren bir yineleyici döndürür. Eşzamanlılık güvenli yöntemdir.  
  
```
iterator begin();

const_iterator begin() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Eş zamanlı kapsayıcıdaki ilk öğeye bir yineleyici.  
  
##  <a name="cbegin"></a> cbegin 

 Eş zamanlı kapsayıcıdaki ilk öğeyi gösteren sabit bir yineleyici döndürür. Eşzamanlılık güvenli yöntemdir.  
  
```
const_iterator cbegin() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Eş zamanlı kapsayıcıdaki ilk öğe için sabit bir yineleyici.  
  
##  <a name="cend"></a> cend 

 Eş zamanlı kapsayıcıdaki son öğeyi takip eden konumu gösteren sabit bir yineleyici döndürür. Eşzamanlılık güvenli yöntemdir.  
  
```
const_iterator cend() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Konumu eşzamanlı kapsayıcıdaki son öğeyi adresleyen bir const yineleyici.  
  
##  <a name="clear"></a> Temizle 

 Eş zamanlı kapsayıcıdaki tüm öğelerini siler. Bu işlev, eşzamanlılık güvenli değil.  
  
```
void clear();
```  
  
##  <a name="ctor"></a> concurrent_unordered_map 

 Eş zamanlı sıralanmamış bir harita oluşturur.  
  
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
 `_Iterator`  
 Giriş yineleyicisinin türü.  
  
 `_Number_of_buckets`  
 Bu sıralanmamış eşleme için demet ilk sayısı.  
  
 `_Hasher`  
 Bu sıralanmamış eşleme için karma işlevi.  
  
 `key_equality`  
 Bu sıralanmamış eşleme için eşitlik karşılaştırma işlevi.  
  
 `_Allocator`  
 Bu sıralanmamış eşleme için ayırıcı.  
  
 `_Begin`  
 Kopyalanacak öğe aralığındaki ilk öğenin konumu.  
  
 `_End`  
 Kopyalanacak öğe aralığının dışındaki ilk öğenin konumu.  
  
 `_Umap`  
 Kaynak `concurrent_unordered_map` nesneyi kopyalama veya öğeleri buradan taşımak için.  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm oluşturucular ayırıcı nesnesini depolar `_Allocator` ve sıralanmamış eşleme başlatır.  
  
 İlk Oluşturucu boş bir ilk eşleme ve açıkça demet sayısını karma işlevi, eşitlik işlevi ve ayırıcı türü kullanılmak üzere belirtir.  
  
 İkinci oluşturucu sıralanmamış eşleme için bir ayırıcısı belirtir.  
  
 Üçüncü Oluşturucu yineleyici aralığı tarafından sağlanan değerleri belirler [ `_Begin`, `_End`).  
  
 Dördüncü ve beşinci oluşturucular eşzamanlı sıralanmamış eşleme bir kopyasını belirtin `_Umap`.  
  
 Son Oluşturucu eşzamanlı sıralanmamış eşleme taşıma belirtir `_Umap`.  
  
##  <a name="count"></a> Sayısı 

 Belirtilen bir anahtarla eşleşen öğeleri sayar. Bu işlev, eşzamanlılık güvenli kullanılır.  
  
```
size_type count(const key_type& KVal) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `KVal`  
 Aranacak anahtar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Anahtar kapsayıcısında görünür sayısı çarpı.  
  
##  <a name="empty"></a> boş 

 Bir öğe olup olmadığını sınar. Eşzamanlılık güvenli yöntemdir.  
  
```
bool empty() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` eş zamanlı kapsayıcı boşsa, `false` Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Eş zamanlı ekler saklanacaktır olup olmadığını eşzamanlı kapsayıcı boşsa, dönüş değeri bile okumadan önce hemen bu işlev çağrıldıktan sonra değişebilir.  
  
##  <a name="end"></a> Son 

 Eş zamanlı kapsayıcıdaki son öğeyi takip eden konumu gösteren bir yineleyici döndürür. Eşzamanlılık güvenli yöntemdir.  
  
```
iterator end();

const_iterator end() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Konumu eşzamanlı kapsayıcıdaki son öğeyi adresleyen bir yineleyici.  
  
##  <a name="equal_range"></a> equal_range 

 Belirtilen anahtarla eşleşen aralığı bulur. Bu işlev, eşzamanlılık güvenli kullanılır.  
  
```
std::pair<iterator,
    iterator> equal_range(
    const key_type& KVal);

std::pair<const_iterator,
    const_iterator> equal_range(
    const key_type& KVal) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `KVal`  
 Aranacak anahtar değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [çifti](../../../standard-library/pair-structure.md) burada bir yineleyici başına ilk öğesidir ve aralığın sonuna bir yineleyici ikinci öğedir.  
  
### <a name="remarks"></a>Açıklamalar  
 Eş zamanlı ekler başlangıç yineleyici sonra ve end yineleyici önce eklenecek ek anahtarlar neden mümkündür.  
  
##  <a name="find"></a> Bul 

 Belirtilen bir anahtarla eşleşen bir öğeyi bulur. Bu işlev, eşzamanlılık güvenli kullanılır.  
  
```
iterator find(const key_type& KVal);

const_iterator find(const key_type& KVal) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `KVal`  
 Aranacak anahtar değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sağlanan anahtar eşleşen ilk öğenin konumu gösteren bir yineleyici veya yineleyici `end()` böyle bir öğe varsa.  
  
##  <a name="get_allocator"></a> get_allocator 

 Bu eşzamanlı kapsayıcısı için saklı ayırıcı nesnesini döndürür. Eşzamanlılık güvenli yöntemdir.  
  
```
allocator_type get_allocator() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu eşzamanlı kapsayıcısı için saklı ayırıcı nesnesini.  
  
##  <a name="hash_function"></a> hash_function 

 Depolanan karma işlevi nesnesini alır.  
  
```
hasher hash_function() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Depolanan karma işlev nesnesi.  
  
##  <a name="insert"></a> Ekle 

 Öğeler ekler `concurrent_unordered_map` nesne.  
  
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
 `_Iterator`  
 Ekleme için kullanılan yineleyici türü.  
  
 `V`  
 Eşlemeye eklenen değerin türü.  
  
 `value`  
 Eklenecek değer.  
  
 `_Where`  
 Bir ekleme noktasını aramak için başlangıç konumu.  
  
 `first`  
 Eklenecek Aralık başlangıcı.  
  
 `last`  
 Eklenecek aralık sonu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir yineleyici ve bir Boole değeri içeren bir çifti. Daha fazla ayrıntı için Açıklamalar bölümüne bakın.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk üye işlevi bir öğe X anahtarı eşdeğer olarak sıralamaya sahip sıralamadaki bulunup bulunmadığını belirler `value`. Değilse, bu tür bir öğe X oluşturur ve onu ile başlatır `value`. İşlev ardından yineleyici belirler `where` , X belirler. İşlev ekleme oluşup olmadığını döndürür `std::pair(where, true)`. Aksi halde `std::pair(where, false)`.  
  
 İkinci üye işlevi ekleme döndürür ( `value`) kullanarak `_Where` ekleme noktasını aramak için denetlenen bir dizi içinde bir başlangıç noktası olarak.  
  
 Üçüncü üye işlevi aralıktan öğe değerleri dizisi ekler [ `first`, `last`).  
  
 Son iki üye işlevleri ilk ikisi, tek fark olarak aynı şekilde davranır `value` eklenen değer oluşturmak için kullanılır.  
  
##  <a name="key_eq"></a> key_eq 

 Depolanan eşitlik karşılaştırma işlevi nesnesini alır.  
  
```
key_equal key_eq() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Depolanan eşitlik karşılaştırma işlevi nesnesi.  
  
##  <a name="load_factor"></a> load_factor 

 Hesaplar ve kapsayıcının geçerli yük faktörünü döndürür. Yük, demet sayısına göre bölünmüş kapsayıcı içindeki öğelerin sayısını faktördür.  
  
```
float load_factor() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kapsayıcının yükü faktörü.  
  
##  <a name="max_load_factor"></a> max_load_factor 

 Alır veya kapsayıcının en yüksek yük faktörünün ayarlar. En yüksek yük faktörünün en büyük öğeleri herhangi bir kovada kapsayıcı kendi iç tablo büyüdükçe önce fazla sayısıdır.  
  
```
float max_load_factor() const;

void max_load_factor(float _Newmax);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Newmax`  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk üye işlevi, depolanan en yüksek yük faktörünün döndürür. İkinci üye işlevi bir değer döndürmez ama oluşturur bir [out_of_range](../../../standard-library/out-of-range-class.md) sağlanan yük faktörünü geçersiz olduğunda özel durum...  
  
##  <a name="max_size"></a> max_size 

 Ayırıcı tarafından belirlenen eş zamanlı kapsayıcısı en büyük boyutunu döndürür. Eşzamanlılık güvenli yöntemdir.  
  
```
size_type max_size() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 En fazla eş zamanlı bu kapsayıcıya eklenen öğe sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üst sınır değeri gerçekten ne kapsayıcı gerçekten tutabilir daha yüksek olabilir.  
  
##  <a name="operator_at"></a> operator] 

 Belirtilen anahtarı içeren bir öğe bulur veya ekler. Bu yöntem eşzamanlı güvenlidir.  
  
```
mapped_type& operator[](const key_type& kval);

mapped_type& operator[](key_type&& kval);
```  
  
### <a name="parameters"></a>Parametreler  
 `KVal`  
 Anahtar değeri  
  
 bulmak veya eklemek.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bulunamadı veya eklenen öğenin veri değerine başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Bağımsız değişken anahtar değeri bulunamazsa, değer veri türünün varsayılan değeriyle birlikte eklenir.  
  
 `operator[]` öğe bir eşlemeye eklemek için kullanılabilir `m` kullanarak `m[key] = DataValue;`burada `DataValue` değeri `mapped_type` öğenin anahtar değeri ile `key`.  
  
 Kullanırken `operator[]` öğeleri eklemek için döndürülen başvuru ekleme önceden varolan bir öğeyi değiştirmek veya yeni bir tane oluşturmak anlamına gelmez. Üye işlevleri `find` ve [Ekle](#insert) belirtilen anahtara sahip bir öğe zaten bir ekleme mevcut olup olmadığını belirlemek için kullanılabilir.  
  
##  <a name="operator_eq"></a> işleç = 

 Başka bir deponun içeriğini atar `concurrent_unordered_map` buna nesne. Bu yöntem eşzamanlı güvenli değil.  
  
```
concurrent_unordered_map& operator= (const concurrent_unordered_map& _Umap);

concurrent_unordered_map& operator= (concurrent_unordered_map&& _Umap);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Umap`  
 Kaynak `concurrent_unordered_map` nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu başvuru `concurrent_unordered_map` nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Eş zamanlı vektör, var olan öğeleri silme sonra `operator=` kopyalar veya içeriğini hareket `_Umap` halinde eşzamanlı vektör.  
  
##  <a name="rehash"></a> rehash 

 Karma tabloyu yeniden oluşturur.  
  
```
void rehash(size_type _Buckets);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Buckets`  
 İstenen demet sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi en az olacak şekilde demet sayısını değiştirir `_Buckets` ve gerektiğinde karma tabloyu yeniden oluşturur. Demet sayısı 2'in üssü olmalıdır. 2'in kuvveti değil ise 2 sonraki en büyük gücünü yuvarlanır.  
  
 Atar bir [out_of_range](../../../standard-library/out-of-range-class.md) demet sayısı geçersiz özel durum (0 veya en yüksek demet sayısını büyüktür).  
  
##  <a name="size"></a> Boyutu 

 Bu eşzamanlı bir kapsayıcı içinde öğelerin sayısını döndürür. Eşzamanlılık güvenli yöntemdir.  
  
```
size_type size() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kapsayıcıdaki öğelerin sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Eş zamanlı eklemeleri varsa, dönüş değeri bile okumadan önce hemen bu işlev çağrıldıktan sonra eş zamanlı kapsayıcıdaki öğelerin sayısı değişebilir.  
  
##  <a name="swap"></a> değiştirme 

 İki içeriğini değiştirir `concurrent_unordered_map` nesneleri. Bu yöntem eşzamanlı güvenli değil.  
  
```
void swap(concurrent_unordered_map& _Umap);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Umap`  
 `concurrent_unordered_map` İle değiştirilecek nesne.  
  
##  <a name="unsafe_begin"></a> unsafe_begin 

 Belirli bir demet için bu kapsayıcıdaki ilk öğeye bir yineleyici döndürür.  
  
```
local_iterator unsafe_begin(size_type _Bucket);

const_local_iterator unsafe_begin(size_type _Bucket) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Bucket`  
 Demet dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Demet başlangıcına işaret eden bir yineleyici.  
  
##  <a name="unsafe_bucket"></a> unsafe_bucket 

 Bu kapsayıcı içinde belirli bir anahtarın eşlendiği demet dizinini döndürür.  
  
```
size_type unsafe_bucket(const key_type& KVal) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `KVal`  
 Aranan öğe anahtarı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu kapsayıcıda anahtarı için demet dizini.  
  
##  <a name="unsafe_bucket_count"></a> unsafe_bucket_count 

 Bu kapsayıcıda geçerli demet sayısını döndürür.  
  
```
size_type unsafe_bucket_count() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu kapsayıcı demet sayısı.  
  
##  <a name="unsafe_bucket_size"></a> unsafe_bucket_size 

 Bu kapsayıcının belirli bir kovada öğe sayısını döndürür.  
  
```
size_type unsafe_bucket_size(size_type _Bucket);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Bucket`  
 Aramak için demet.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu kapsayıcı demet sayısı.  
  
##  <a name="unsafe_cbegin"></a> unsafe_cbegin 

 Belirli bir demet için bu kapsayıcıdaki ilk öğeye bir yineleyici döndürür.  
  
```
const_local_iterator unsafe_cbegin(size_type _Bucket) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Bucket`  
 Demet dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Demet başlangıcına işaret eden bir yineleyici.  
  
##  <a name="unsafe_cend"></a> unsafe_cend 

 Konumu belirli bir demet içindeki son öğeyi adresleyen bir yineleyici döndürür.  
  
```
const_local_iterator unsafe_cend(size_type _Bucket) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Bucket`  
 Demet dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Demet başlangıcına işaret eden bir yineleyici.  
  
##  <a name="unsafe_end"></a> unsafe_end 

 Belirli bir demet için bu kapsayıcıdaki son öğeye bir yineleyici döndürür.  
  
```
local_iterator unsafe_end(size_type _Bucket);

const_local_iterator unsafe_end(size_type _Bucket) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Bucket`  
 Demet dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Demet sonuna işaret eden bir yineleyici.  
  
##  <a name="unsafe_erase"></a> unsafe_erase 

 Öğeleri kaldırır `concurrent_unordered_map` belirtilen konumlarda. Bu yöntem eşzamanlı güvenli değil.  
  
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
 `_Where`  
 Silmeye başlanacak yineleme konumu.  
  
 `_Begin`  
 Silinecek şekilde öğe aralığındaki ilk öğenin konumu.  
  
 `_End`  
 Silinecek şekilde öğe aralığının dışındaki ilk öğenin konumu.  
  
 `KVal`  
 Silinecek anahtar değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk iki üye işlev kaldırılan tüm öğelerin ötesindeki ilk öğeyi belirleyen bir yineleyici döndürür veya `concurrent_unordered_map::end`böyle bir öğe mevcut değil ise. Üçüncü üye işlevi, kaldırdığı öğelerin sayısını döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk üye işlevi tarafından denetlenen dizinin öğeyi kaldırır `_Where`. İkinci üye işlevi bir aralıktaki öğeleri kaldırır. [ `_Begin`, `_End`).  
  
 Üçüncü üye işlevi tarafından ayrılmış aralıktaki öğeleri kaldırır. `concurrent_unordered_map::equal_range`(KVal).  
  
##  <a name="unsafe_max_bucket_count"></a> unsafe_max_bucket_count 

 Bu kapsayıcıda en yüksek demet sayısını döndürür.  
  
```
size_type unsafe_max_bucket_count() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu kapsayıcı demet sayısı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [Paralel Kapsayıcılar ve Nesneler](../../../parallel/concrt/parallel-containers-and-objects.md)



