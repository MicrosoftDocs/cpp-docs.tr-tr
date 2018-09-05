---
title: concurrent_unordered_set sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- concurrent_unordered_set
- CONCURRENT_UNORDERED_SET/concurrency::concurrent_unordered_set
- CONCURRENT_UNORDERED_SET/concurrency::concurrent_unordered_set::concurrent_unordered_set
- CONCURRENT_UNORDERED_SET/concurrency::concurrent_unordered_set::hash_function
- CONCURRENT_UNORDERED_SET/concurrency::concurrent_unordered_set::insert
- CONCURRENT_UNORDERED_SET/concurrency::concurrent_unordered_set::key_eq
- CONCURRENT_UNORDERED_SET/concurrency::concurrent_unordered_set::swap
- CONCURRENT_UNORDERED_SET/concurrency::concurrent_unordered_set::unsafe_erase
dev_langs:
- C++
helpviewer_keywords:
- concurrent_unordered_set class
ms.assetid: c61f9a9a-4fd9-491a-9251-e300737ecf4b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4ffea5b097460dbed2b6d5dd4ea4e79f283cd412
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43693965"
---
# <a name="concurrentunorderedset-class"></a>concurrent_unordered_set Sınıfı
`concurrent_unordered_set` Sınıfı, bir K. türdeki öğelerin değişen uzunluktaki dizisini denetleyen eşzamanlılığı güvenli bir kapsayıcıdır Sıra, eşzamanlılık açısından güvenli sağlayan bir şekilde temsil edilir sona ekleme, öğe erişimi, yineleyici erişimi ve yineleyici çapraz geçiş işlemleri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
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
  
#### <a name="parameters"></a>Parametreler  
 `K`  
 Anahtar türü.  
  
 `_Hasher`  
 Karma işlev nesne türü. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `std::hash<K>`.  
  
 `key_equality`  
 Eşitlik karşılaştırma işlevi nesne türü. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `std::equal_to<K>`.  
  
 `_Allocator_type`  
 Ayırma ve eşzamanlı sıralanmamış için bellek ayırmayı kaldırma hakkındaki ayrıntıları içeren saklı ayırıcı nesnesini gösteren tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `std::allocator<K>`.  
  
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
|`pointer`|Bir öğe için bir işaretçi türü.|  
|`reference`|Bir öğe için bir başvuru türü.|  
|`size_type`|İki öğe arasındaki işaretsiz bir mesafenin türü.|  
|`value_type`|Öğenin türü.|  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[concurrent_unordered_set](#ctor)|Fazla Yüklendi. Eş zamanlı sıralanmamış bir küme oluşturur.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[hash_function](#hash_function)|Depolanan karma işlevi nesnesini döndürür.|  
|[Ekle](#insert)|Fazla Yüklendi. Öğeler ekler `concurrent_unordered_set` nesne.|  
|[key_eq](#key_eq)|Depolanan eşitlik karşılaştırma işlevi nesnesini döndürür.|  
|[değiştirme](#swap)|İki içeriğini değiştirir `concurrent_unordered_set` nesneleri. Bu yöntem eşzamanlı güvenli değil.|  
|[unsafe_erase](#unsafe_erase)|Fazla Yüklendi. Öğeleri kaldırır `concurrent_unordered_set` belirtilen konumlarda. Bu yöntem eşzamanlı güvenli değil.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[operator=](#operator_eq)|Fazla Yüklendi. Başka bir deponun içeriğini atar `concurrent_unordered_set` buna nesne. Bu yöntem eşzamanlı güvenli değil.|  
  
## <a name="remarks"></a>Açıklamalar  
 Hakkında ayrıntılı bilgi için `concurrent_unordered_set` sınıfı [paralel kapsayıcılar ve nesneler](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `_Traits`  
  
 `_Concurrent_hash`  
  
 `concurrent_unordered_set`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concurrent_unordered_set.h  
  
 **Namespace:** eşzamanlılık  
  
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
  
##  <a name="ctor"></a> concurrent_unordered_set 

 Eş zamanlı sıralanmamış bir küme oluşturur.  
  
```
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
 `_Iterator`  
 Giriş yineleyicisinin türü.  
  
 `_Number_of_buckets`  
 Bu sıralanmamış demetlerini ilk sayısı.  
  
 `_Hasher`  
 Bu sıralanmamış karma işlevi.  
  
 `key_equality`  
 Bu sıralanmamış için eşitlik karşılaştırma işlevi.  
  
 `_Allocator`  
 Bu sıralanmamış için ayırıcı.  
  
 `first`  
 `last`  
 `_Uset`  
 Kaynak `concurrent_unordered_set` nesneyi kopyalama veya öğeleri buradan taşımak için.  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm oluşturucular ayırıcı nesnesini depolar `_Allocator` ve sıralanmamış başlatır.  
  
 İlk Oluşturucu boş bir başlangıç kümesi ve açıkça demet sayısını karma işlevi, eşitlik işlevi ve ayırıcı türü kullanılmak üzere belirtir.  
  
 İkinci oluşturucu sıralanmamış için bir ayırıcısı belirtir.  
  
 Üçüncü Oluşturucu yineleyici aralığı tarafından sağlanan değerleri belirler [ `_Begin`, `_End`).  
  
 Dördüncü ve beşinci oluşturucular eşzamanlı sıralanmamış bir kopyasını belirtin `_Uset`.  
  
 Son Oluşturucu eşzamanlı sıralanmamış taşıma belirtir `_Uset`.  
  
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

 Depolanan karma işlevi nesnesini döndürür.  
  
```
hasher hash_function() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Depolanan karma işlev nesnesi.  
  
##  <a name="insert"></a> Ekle 

 Öğeler ekler `concurrent_unordered_set` nesne.  
  
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
 Kümesine eklenen değerin türü.  
  
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

 Depolanan eşitlik karşılaştırma işlevi nesnesini döndürür.  
  
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
  
##  <a name="operator_eq"></a> işleç = 

 Başka bir deponun içeriğini atar `concurrent_unordered_set` buna nesne. Bu yöntem eşzamanlı güvenli değil.  
  
```
concurrent_unordered_set& operator= (const concurrent_unordered_set& _Uset);

concurrent_unordered_set& operator= (concurrent_unordered_set&& _Uset);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Uset`  
 Kaynak `concurrent_unordered_set` nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu başvuru `concurrent_unordered_set` nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Eş zamanlı sıralanmamış bir küme içindeki var olan öğeleri silme sonra `operator=` kopyalar veya içeriğini hareket `_Uset` kümesi sırasız eşzamanlı olarak.  
  
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

 İki içeriğini değiştirir `concurrent_unordered_set` nesneleri. Bu yöntem eşzamanlı güvenli değil.  
  
```
void swap(concurrent_unordered_set& _Uset);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Uset`  
 `concurrent_unordered_set` İle değiştirilecek nesne.  
  
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

 Öğeleri kaldırır `concurrent_unordered_set` belirtilen konumlarda. Bu yöntem eşzamanlı güvenli değil.  
  
```
iterator unsafe_erase(
    const_iterator _Where);

size_type unsafe_erase(
    const key_type& KVal);

iterator unsafe_erase(
    const_iterator first,
    const_iterator last);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Where`  
 Silmeye başlanacak yineleme konumu.  
  
 `KVal`  
 Silinecek anahtar değer.  
  
 `first`  
 `last`  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk iki üye işlev kaldırılan tüm öğelerin ötesindeki ilk öğeyi belirleyen bir yineleyici döndürür veya [son](#end)böyle bir öğe mevcut değil ise. Üçüncü üye işlevi, kaldırdığı öğelerin sayısını döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk üye işlevi tarafından işaret edilen öğeyi kaldırır `_Where`. İkinci üye işlevi bir aralıktaki öğeleri kaldırır. [ `_Begin`, `_End`).  
  
 Üçüncü üye işlevi tarafından ayrılmış aralıktaki öğeleri kaldırır. [equal_range](#equal_range)(KVal).  
  
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



