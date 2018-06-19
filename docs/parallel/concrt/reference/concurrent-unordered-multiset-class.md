---
title: concurrent_unordered_multiset sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- concurrent_unordered_multiset
- CONCURRENT_UNORDERED_SET/concurrency::concurrent_unordered_multiset
- CONCURRENT_UNORDERED_SET/concurrency::concurrent_unordered_multiset::concurrent_unordered_multiset
- CONCURRENT_UNORDERED_SET/concurrency::concurrent_unordered_multiset::hash_function
- CONCURRENT_UNORDERED_SET/concurrency::concurrent_unordered_multiset::insert
- CONCURRENT_UNORDERED_SET/concurrency::concurrent_unordered_multiset::key_eq
- CONCURRENT_UNORDERED_SET/concurrency::concurrent_unordered_multiset::swap
- CONCURRENT_UNORDERED_SET/concurrency::concurrent_unordered_multiset::unsafe_erase
dev_langs:
- C++
helpviewer_keywords:
- concurrent_unordered_multiset class
ms.assetid: 219d7d67-1ff0-45f4-9400-e9cc272991a4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fdfb187e49302f9d885c8810636f1ed638257675
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33694803"
---
# <a name="concurrentunorderedmultiset-class"></a>concurrent_unordered_multiset Sınıfı
`concurrent_unordered_multiset` Sınıfı K. türündeki öğeler değişen uzunluk dizisi denetleyen bir eşzamanlılık güvenli kapsayıcı. Sıra sağlayan eşzamanlılık güvenli bir şekilde temsil edilen ekleme, öğe erişim, yineleyici erişim ve yineleyici geçişi işlemleri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <typename K,
    typename _Hasher = std::hash<K>,
    typename key_equality = std::equal_to<K>,
    typename _Allocator_type = std::allocator<K>
>,
    typename key_equality = std::equal_to<K>,
    typename _Allocator_type = std::allocator<K>> class concurrent_unordered_multiset : public details::_Concurrent_hash<details::_Concurrent_unordered_set_traits<K,
    details::_Hash_compare<K,
 _Hasher,
    key_equality>,
 _Allocator_type,
    true>>;
```   
  
#### <a name="parameters"></a>Parametreler  
 `K`  
 Anahtar türü.  
  
 `_Hasher`  
 Karma işlev nesne türü. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `std::hash<K>`.  
  
 `key_equality`  
 Eşitlik karşılaştırma işlevi nesne türü. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `std::equal_to<K>`.  
  
 `_Allocator_type`  
 Ayırma ve eşzamanlı vektör bellek ayırmayı kaldırma ayrıntılarını yalıtan saklı ayırıcısı nesneyi temsil eden tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `std::allocator<K>`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
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
|[concurrent_unordered_multiset](#ctor)|Fazla Yüklendi. Eşzamanlı sırasız çoklu küme oluşturur.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[hash_function](#hash_function)|Depolanan karma işlev nesnesi döndürür.|  
|[Ekle](#insert)|Fazla Yüklendi. Öğelerine ekler `concurrent_unordered_multiset` nesnesi.|  
|[key_eq](#key_eq)|Saklı eşitlik karşılaştırması işlev nesnesi.|  
|[Değiştirme](#swap)|İki içeriğini değiştirir `concurrent_unordered_multiset` nesneleri. Bu yöntem eşzamanlılık uyumlu değil.|  
|[unsafe_erase](#unsafe_erase)|Fazla Yüklendi. Öğelerden kaldırır `concurrent_unordered_multiset` belirtilen konumlarda. Bu yöntem eşzamanlılık uyumlu değil.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[operator=](#operator_eq)|Fazla Yüklendi. İçeriği başka bir atar `concurrent_unordered_multiset` bu bir nesne. Bu yöntem eşzamanlılık uyumlu değil.|  
  
## <a name="remarks"></a>Açıklamalar  
 Ayrıntılı bilgi için `concurrent_unordered_multiset` sınıfı için bkz: [paralel kapsayıcılar ve nesneler](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `_Traits`  
  
 `_Concurrent_hash`  
  
 `concurrent_unordered_multiset`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concurrent_unordered_set.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="begin"></a> Başlangıç 

 Eşzamanlı kapsayıcı ilk öğe işaret eden bir yineleyici döndürür. Eşzamanlılık güvenli yöntemdir.  
  
```
iterator begin();

const_iterator begin() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yineleyici eşzamanlı kapsayıcı ilk öğe için.  
  
##  <a name="cbegin"></a> cbegin 

 Eşzamanlı kapsayıcı ilk öğe işaret eden bir const yineleyici döndürür. Eşzamanlılık güvenli yöntemdir.  
  
```
const_iterator cbegin() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Const yineleyici eşzamanlı kapsayıcı ilk öğe için.  
  
##  <a name="cend"></a> cend 

 Eşzamanlı kapsayıcı son öğesi başarılı konumuna işaret eden bir const yineleyici döndürür. Eşzamanlılık güvenli yöntemdir.  
  
```
const_iterator cend() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Const yineleyici eşzamanlı kapsayıcı son öğesi başarılı konuma.  
  
##  <a name="clear"></a> Temizle 

 Eşzamanlı kapsayıcıdaki tüm öğeleri siler. Bu işlev eşzamanlılık güvenli değil.  
  
```
void clear();
```  
  
##  <a name="ctor"></a> concurrent_unordered_multiset 

 Eşzamanlı sırasız çoklu küme oluşturur.  
  
```
explicit concurrent_unordered_multiset(
    size_type _Number_of_buckets = 8,
    const hasher& _Hasher = hasher(),
    const key_equal& key_equality = key_equal(),
    const allocator_type& _Allocator = allocator_type());

concurrent_unordered_multiset(
    const allocator_type& _Allocator);

template <typename _Iterator>
concurrent_unordered_multiset(_Iterator first,
    _Iterator last,
    size_type _Number_of_buckets = 8,
    const hasher& _Hasher = hasher(),
    const key_equal& key_equality = key_equal(),
    const allocator_type& _Allocator = allocator_type());

concurrent_unordered_multiset(
    const concurrent_unordered_multiset& _Uset);

concurrent_unordered_multiset(
    const concurrent_unordered_multiset& _Uset,
    const allocator_type& _Allocator);

concurrent_unordered_multiset(
    concurrent_unordered_multiset&& _Uset);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Iterator`  
 Giriş yineleyici türü.  
  
 `_Number_of_buckets`  
 Bu sırasız multiset aralıklarını ilk sayısı.  
  
 `_Hasher`  
 Bu sırasız multiset karma işlevi.  
  
 `key_equality`  
 Bu sırasız multiset eşitlik karşılaştırması işlevi.  
  
 `_Allocator`  
 Bu sırasız multiset ayırıcı.  
  
 `first`  
 `last`  
 `_Uset`  
 Kaynak `concurrent_unordered_multiset` öğeleri taşımak için nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm oluşturucular ayırıcısı nesneyi depolamak `_Allocator` ve sırasız multiset başlatma.  
  
 İlk Oluşturucusu boş ilk multiset ve açıkça demet sayısı karma işlevi ve eşitlik işlevi ayırıcısı yazın kullanılacak belirtir.  
  
 İkinci Oluşturucu, sırasız çoklu küme için bir ayırıcı belirtir.  
  
 Yineleyici aralık tarafından sağlanan değerleri üçüncü Oluşturucusu belirtir [ `_Begin`, `_End`).  
  
 Dördüncü ve beşinci oluşturucular eşzamanlı sırasız multiset kopyasını belirtin `_Uset`.  
  
 Son Oluşturucusu eşzamanlı sırasız multiset taşıma belirtir `_Uset`.  
  
##  <a name="count"></a> Sayısı 

 Belirtilen anahtar eşleşen öğe sayısını sayar. Eşzamanlılık güvenli işlevdir.  
  
```
size_type count(const key_type& KVal) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `KVal`  
 Aranacak anahtar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sayısı anahtar kapsayıcısında görünür sayısı zaman.  
  
##  <a name="empty"></a> boş 

 Bir öğe olup olmadığını sınar. Eşzamanlılık güvenli yöntemdir.  
  
```
bool empty() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` eşzamanlı kapsayıcı boşsa, `false` Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Eşzamanlı eklemeleri varlığında olsun veya olmasın eş zamanlı boş kapsayıcısıdır, dönüş değeri bile okumadan önce hemen bu işlev çağrıldıktan sonra değiştirebilirsiniz.  
  
##  <a name="end"></a> Bitiş 

 Eşzamanlı kapsayıcı son öğesi başarılı konumuna işaret eden bir yineleyici döndürür. Eşzamanlılık güvenli yöntemdir.  
  
```
iterator end();

const_iterator end() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yineleyici eşzamanlı kapsayıcı son öğesi başarılı konuma.  
  
##  <a name="equal_range"></a> equal_range 

 Belirtilen anahtarla eşleşen bir aralık bulur. Eşzamanlılık güvenli işlevdir.  
  
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
 A [çifti](http://msdn.microsoft.com/en-us/32e72d66-3020-4cb9-92c3-f7a5fa7998ff) burada ilk öğe başına bir yineleyici ve yineleyici aralığın sonuna ikinci öğedir.  
  
### <a name="remarks"></a>Açıklamalar  
 Begin yineleyici sonra ve son yineleyici önce eklenecek ek anahtarlar neden eşzamanlı eklemeleri mümkündür.  
  
##  <a name="find"></a> Bul 

 Belirtilen bir anahtarla eşleşen bir öğeyi bulur. Eşzamanlılık güvenli işlevdir.  
  
```
iterator find(const key_type& KVal);

const_iterator find(const key_type& KVal) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `KVal`  
 Aranacak anahtar değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yineleyici konumuna işaret eden sağlanan anahtar eşleşen ilk öğe veya yineleyici `end()` böyle bir öğe varsa.  
  
##  <a name="get_allocator"></a> get_allocator 

 Eşzamanlı bu kapsayıcı için saklı ayırıcısı nesne döndürür. Eşzamanlılık güvenli yöntemdir.  
  
```
allocator_type get_allocator() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Eşzamanlı bu kapsayıcı için saklı ayırıcısı nesnesi.  
  
##  <a name="hash_function"></a> hash_function 

 Depolanan karma işlev nesnesi döndürür.  
  
```
hasher hash_function() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Depolanan karma işlev nesnesi.  
  
##  <a name="insert"></a> Ekle 

 Öğelerine ekler `concurrent_unordered_multiset` nesnesi.  
  
```
iterator insert(
    const value_type& value);

iterator insert(
    const_iterator _Where,
    const value_type& value);

template<class _Iterator>
void insert(_Iterator first,
    _Iterator last);

template<class V>
iterator insert(
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
 Eklenen değer türü.  
  
 `value`  
 Eklenecek değer.  
  
 `_Where`  
 İçin bir ekleme noktası aramak için başlangıç konumu.  
  
 `first`  
 Eklenecek Aralık başlangıcı.  
  
 `last`  
 Eklenecek aralık sonu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ekleme konumuna işaret eden bir yineleyici.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk üye işlevi öğesi ekler `value` denetimli sırayla daha sonra eklenen öğesi atar yineleyici döndürür.  
  
 İkinci üye işlevi ekleme döndürür ( `value`) kullanarak `_Where` ekleme noktasını aramak için denetimli dizisi içindeki başlangıç noktası olarak.  
  
 Üçüncü üye işlevi bir dizi öğesi değerlerini aralıktan ekler [ `first`, `last`).  
  
 Son iki üye işlevleri hariç ilk iki olarak aynı şekilde davranır `value` eklenen değer oluşturmak için kullanılır.  
  
##  <a name="key_eq"></a> key_eq 

 Saklı eşitlik karşılaştırması işlev nesnesi.  
  
```
key_equal key_eq() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Saklı eşitlik karşılaştırması işlev nesnesi.  
  
##  <a name="load_factor"></a> load_factor 

 Hesaplar ve geçerli Yük faktörü kapsayıcısının döndürür. Demet sayısına göre bölünmüş kapsayıcı öğe sayısı yük faktördür.  
  
```
float load_factor() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kapsayıcı için Yük faktörü.  
  
##  <a name="max_load_factor"></a> max_load_factor 

 Alır veya kapsayıcının en fazla Yük faktörü ayarlar. En fazla yük öğelerin en büyük sayı kapsayıcı kendi iç tablo büyür önce tüm demet gösterilebilecek olandan faktördür.  
  
```
float max_load_factor() const;

void max_load_factor(float _Newmax);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Newmax`  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk üye işlevi depolanan en fazla Yük faktörü döndürür. İkinci üye işlevi bir değer döndürmüyor ancak oluşturur bir [out_of_range](../../../standard-library/out-of-range-class.md) sağlanan Yük faktörü geçersiz ise özel durum...  
  
##  <a name="max_size"></a> max_size 

 Ayırıcı tarafından belirlenen eşzamanlı kapsayıcı en büyük boyutu döndürür. Eşzamanlılık güvenli yöntemdir.  
  
```
size_type max_size() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 En fazla eş zamanlı bu kapsayıcıya eklenebilir öğe sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üst sınır değeri gerçekte ne kapsayıcı gerçekte tutabilir daha yüksek olabilir.  
  
##  <a name="operator_eq"></a> işleç = 

 İçeriği başka bir atar `concurrent_unordered_multiset` bu bir nesne. Bu yöntem eşzamanlılık uyumlu değil.  
  
```
concurrent_unordered_multiset& operator= (const concurrent_unordered_multiset& _Uset);

concurrent_unordered_multiset& operator= (concurrent_unordered_multiset&& _Uset);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Uset`  
 Kaynak `concurrent_unordered_multiset` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu başvuru `concurrent_unordered_multiset` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Eşzamanlı sırasız multiset içinde var olan öğeleri silindikten sonra `operator=` kopyalar ya da içeriğini taşır `_Uset` multiset sıralanmamış eşzamanlı içine.  
  
##  <a name="rehash"></a> rehash 

 Karma tabloyu yeniden oluşturur.  
  
```
void rehash(size_type _Buckets);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Buckets`  
 İstenen aralık sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini sayısı en az olacak şekilde değiştirir `_Buckets` ve karma tablosu gerektiği gibi yeniden oluşturur. Demet sayısı 2'in üssü olmalıdır. Bir güç yok, 2, 2 sonraki en büyük gücünü yuvarlanır.  
  
 Bunu oluşturur bir [out_of_range](../../../standard-library/out-of-range-class.md) demet sayısı geçersiz ise özel durum (0 veya en fazla sayısını büyük).  
  
##  <a name="size"></a> Boyutu 

 Eşzamanlı bu kapsayıcıda öğe sayısını döndürür. Eşzamanlılık güvenli yöntemdir.  
  
```
size_type size() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kapsayıcı öğelerin sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Eşzamanlı eklemeleri varlığında dönüş değeri bile okumadan önce hemen bu işlev çağrıldıktan sonra eş zamanlı kapsayıcı öğe sayısı değişebilir.  
  
##  <a name="swap"></a> Değiştirme 

 İki içeriğini değiştirir `concurrent_unordered_multiset` nesneleri. Bu yöntem eşzamanlılık uyumlu değil.  
  
```
void swap(concurrent_unordered_multiset& _Uset);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Uset`  
 `concurrent_unordered_multiset` Nesnesi ile değiştirme.  
  
##  <a name="unsafe_begin"></a> unsafe_begin 

 Bu kapsayıcı için belirli bir demet ilk öğe yineleyici döndürür.  
  
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

 Bu kapsayıcıda belirli bir anahtarın eşlendiği demet dizinini döndürür.  
  
```
size_type unsafe_bucket(const key_type& KVal) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `KVal`  
 Aranan öğe anahtarı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu kapsayıcı anahtarında demet dizini.  
  
##  <a name="unsafe_bucket_count"></a> unsafe_bucket_count 

 Bu kapsayıcıda geçerli sayısını döndürür.  
  
```
size_type unsafe_bucket_count() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu kapsayıcıda demet geçerli sayısı.  
  
##  <a name="unsafe_bucket_size"></a> unsafe_bucket_size 

 Bu kapsayıcının belirli kova öğe sayısını döndürür.  
  
```
size_type unsafe_bucket_size(size_type _Bucket);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Bucket`  
 Aranacak demet.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu kapsayıcıda demet geçerli sayısı.  
  
##  <a name="unsafe_cbegin"></a> unsafe_cbegin 

 Bu kapsayıcı için belirli bir demet ilk öğe yineleyici döndürür.  
  
```
const_local_iterator unsafe_cbegin(size_type _Bucket) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Bucket`  
 Demet dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Demet başlangıcına işaret eden bir yineleyici.  
  
##  <a name="unsafe_cend"></a> unsafe_cend 

 Belirli bir demet son öğesi başarılı konuma yineleyici döndürür.  
  
```
const_local_iterator unsafe_cend(size_type _Bucket) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Bucket`  
 Demet dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Demet başlangıcına işaret eden bir yineleyici.  
  
##  <a name="unsafe_end"></a> unsafe_end 

 Yineleyici bu kapsayıcı için belirli bir demet son öğesi döndürür.  
  
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

 Öğelerden kaldırır `concurrent_unordered_multiset` belirtilen konumlarda. Bu yöntem eşzamanlılık uyumlu değil.  
  
```
iterator unsafe_erase(
    const_iterator _Where);

iterator unsafe_erase(
    const_iterator first,
    const_iterator last);

size_type unsafe_erase(
    const key_type& KVal);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Where`  
 Gelen silme yineleyici konumu.  
  
 `first`  
 `last`  
 `KVal`  
 ERASE anahtar değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk iki üye işlevleri kaldırıldı, herhangi bir öğenin dışında kalan ilk öğe atayan bir yineleyici dönün veya [son](#end)böyle bir öğe varsa, (). Üçüncü üye işlevi kaldırır öğe sayısını döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk üye işlevi gösterdiği öğeyi kaldırır `_Where`. İkinci üye işlevi öğeleri aralığında kaldırır [ `_Begin`, `_End`).  
  
 Üçüncü üye fonksiyonu tarafından ayrılmış aralıktaki öğeleri kaldırır [equal_range](#equal_range)(KVal).  
  
##  <a name="unsafe_max_bucket_count"></a> unsafe_max_bucket_count 

 Bu kapsayıcıda maksimum sayısını döndürür.  
  
```
size_type unsafe_max_bucket_count() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu kapsayıcıda demet sayısı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [Paralel Kapsayıcılar ve Nesneler](../../../parallel/concrt/parallel-containers-and-objects.md)



