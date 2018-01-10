---
title: "concurrent_unordered_multimap sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concurrent_unordered_multimap
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_multimap
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_multimap::concurrent_unordered_multimap
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_multimap::hash_function
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_multimap::insert
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_multimap::key_eq
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_multimap::swap
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_multimap::unsafe_erase
dev_langs: C++
helpviewer_keywords: concurrent_unordered_multimap class
ms.assetid: 4dada5d7-15df-4382-b9c9-348e75b2f3c1
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 41a9a5ade4f7fa704311982d57e47f15561431c9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="concurrentunorderedmultimap-class"></a>concurrent_unordered_multimap Sınıfı
`concurrent_unordered_multimap` Sınıftır türündeki öğeler değişen uzunluk dizisi denetleyen bir eşzamanlılık güvenli kapsayıcı `std::pair<const K, _Element_type>`. Sıra sağlayan eşzamanlılık güvenli bir şekilde temsil edilen ekleme, öğe erişim, yineleyici erişim ve yineleyici geçişi işlemleri.  
  
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
    _Element_type>>> class concurrent_unordered_multimap : public details::_Concurrent_hash<details::_Concurrent_unordered_map_traits<K,
    _Element_type,
 details::_Hash_compare<K,
    _Hasher,
 key_equality>,
    _Allocator_type,
 true>>;
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
 Ayırma ve eşzamanlı vektör bellek ayırmayı kaldırma ayrıntılarını yalıtan saklı ayırıcısı nesneyi temsil eden tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `std::allocator<std::pair<K`, `_Element_type>>`.  
  
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
|`mapped_type`|Her bir anahtar ile ilişkili bir eşlenen değer türü.|  
|`pointer`|Bir öğe için bir işaretçi türü.|  
|`reference`|Bir öğe için bir başvuru türü.|  
|`size_type`|İki öğe arasındaki işaretsiz bir mesafenin türü.|  
|`value_type`|Öğenin türü.|  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[concurrent_unordered_multimap](#ctor)|Fazla Yüklendi. Eşzamanlı sırasız multimap oluşturur.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[hash_function](#hash_function)|Depolanan karma işlev nesnesi döndürür.|  
|[Ekle](#insert)|Fazla Yüklendi. Öğelerine ekler `concurrent_unordered_multimap` nesnesi.|  
|[key_eq](#key_eq)|Saklı eşitlik karşılaştırması işlev nesnesi döndürür.|  
|[değiştirme](#swap)|İki içeriğini değiştirir `concurrent_unordered_multimap` nesneleri. Bu yöntem eşzamanlılık uyumlu değil.|  
|[unsafe_erase](#unsafe_erase)|Fazla Yüklendi. Öğelerden kaldırır `concurrent_unordered_multimap` belirtilen konumlarda. Bu yöntem eşzamanlılık uyumlu değil.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[işleç =](#operator_eq)|Fazla Yüklendi. İçeriği başka bir atar `concurrent_unordered_multimap` bu bir nesne. Bu yöntem eşzamanlılık uyumlu değil.|  
  
## <a name="remarks"></a>Açıklamalar  
 Ayrıntılı bilgi için `concurrent_unordered_multimap` sınıfı için bkz: [paralel kapsayıcılar ve nesneler](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `_Traits`  
  
 `_Concurrent_hash`  
  
 `concurrent_unordered_multimap`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concurrent_unordered_map.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="begin"></a>başlayın 

 Eşzamanlı kapsayıcı ilk öğe işaret eden bir yineleyici döndürür. Eşzamanlılık güvenli yöntemdir.  
  
```
iterator begin();

const_iterator begin() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yineleyici eşzamanlı kapsayıcı ilk öğe için.  
  
##  <a name="cbegin"></a>cbegin 

 Eşzamanlı kapsayıcı ilk öğe işaret eden bir const yineleyici döndürür. Eşzamanlılık güvenli yöntemdir.  
  
```
const_iterator cbegin() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Const yineleyici eşzamanlı kapsayıcı ilk öğe için.  
  
##  <a name="cend"></a>cend 

 Eşzamanlı kapsayıcı son öğesi başarılı konumuna işaret eden bir const yineleyici döndürür. Eşzamanlılık güvenli yöntemdir.  
  
```
const_iterator cend() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Const yineleyici eşzamanlı kapsayıcı son öğesi başarılı konuma.  
  
##  <a name="clear"></a>Temizle 

 Eşzamanlı kapsayıcıdaki tüm öğeleri siler. Bu işlev eşzamanlılık güvenli değil.  
  
```
void clear();
```  
  
##  <a name="ctor"></a>concurrent_unordered_multimap 

 Eşzamanlı sırasız multimap oluşturur.  
  
```
explicit concurrent_unordered_multimap(
    size_type _Number_of_buckets = 8,
    const hasher& _Hasher = hasher(),
    const key_equal& key_equality = key_equal(),
    const allocator_type& _Allocator = allocator_type());

concurrent_unordered_multimap(
    const allocator_type& _Allocator);

template <typename _Iterator>
concurrent_unordered_multimap(_Iterator _Begin,
    _Iterator _End,
    size_type _Number_of_buckets = 8,
    const hasher& _Hasher = hasher(),
    const key_equal& key_equality = key_equal(),
    const allocator_type& _Allocator = allocator_type());

concurrent_unordered_multimap(
    const concurrent_unordered_multimap& _Umap);

concurrent_unordered_multimap(
    const concurrent_unordered_multimap& _Umap,
    const allocator_type& _Allocator);

concurrent_unordered_multimap(
    concurrent_unordered_multimap&& _Umap);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Iterator`  
 Giriş yineleyici türü.  
  
 `_Number_of_buckets`  
 Bu sırasız multimap aralıklarını ilk sayısı.  
  
 `_Hasher`  
 Bu sırasız multimap karma işlevi.  
  
 `key_equality`  
 Bu sırasız multimap eşitlik karşılaştırması işlevi.  
  
 `_Allocator`  
 Bu sırasız multimap ayırıcı.  
  
 `_Begin`  
 Kopyalanacak öğe aralığını ilk öğe konumu.  
  
 `_End`  
 Kopyalanacak öğeleri aralık ötesinde ilk öğe konumu.  
  
 `_Umap`  
 Kaynak `concurrent_unordered_multimap` öğelerinden kopyalamak için nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm oluşturucular ayırıcısı nesneyi depolamak `_Allocator` ve sırasız multimap başlatma.  
  
 İlk Oluşturucusu boş bir ilk multimap ve açıkça demet sayısı karma işlevi ve eşitlik işlevi ayırıcısı yazın kullanılacak belirtir.  
  
 İkinci Oluşturucu, sırasız multimap için bir ayırıcı belirtir.  
  
 Yineleyici aralık tarafından sağlanan değerleri üçüncü Oluşturucusu belirtir [ `_Begin`, `_End`).  
  
 Dördüncü ve beşinci oluşturucular eşzamanlı sırasız multimap kopyasını belirtin `_Umap`.  
  
 Son Oluşturucusu eşzamanlı sırasız multimap taşıma belirtir `_Umap`.  
  
##  <a name="count"></a>sayısı 

 Belirtilen anahtar eşleşen öğe sayısını sayar. Eşzamanlılık güvenli işlevdir.  
  
```
size_type count(const key_type& KVal) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `KVal`  
 Aranacak anahtar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sayısı anahtar kapsayıcısında görünür sayısı zaman.  
  
##  <a name="empty"></a>boş 

 Bir öğe olup olmadığını sınar. Eşzamanlılık güvenli yöntemdir.  
  
```
bool empty() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`eşzamanlı kapsayıcı boşsa, `false` Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Eşzamanlı eklemeleri varlığında olsun veya olmasın eş zamanlı boş kapsayıcısıdır, dönüş değeri bile okumadan önce hemen bu işlev çağrıldıktan sonra değiştirebilirsiniz.  
  
##  <a name="end"></a>Bitiş 

 Eşzamanlı kapsayıcı son öğesi başarılı konumuna işaret eden bir yineleyici döndürür. Eşzamanlılık güvenli yöntemdir.  
  
```
iterator end();

const_iterator end() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yineleyici eşzamanlı kapsayıcı son öğesi başarılı konuma.  
  
##  <a name="equal_range"></a>equal_range 

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
  
##  <a name="find"></a>Bul 

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
  
##  <a name="get_allocator"></a>get_allocator 

 Eşzamanlı bu kapsayıcı için saklı ayırıcısı nesne döndürür. Eşzamanlılık güvenli yöntemdir.  
  
```
allocator_type get_allocator() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Eşzamanlı bu kapsayıcı için saklı ayırıcısı nesnesi.  
  
##  <a name="hash_function"></a>hash_function 

 Depolanan karma işlev nesnesi döndürür.  
  
```
hasher hash_function() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Depolanan karma işlev nesnesi.  
  
##  <a name="insert"></a>Ekle 

 Öğelerine ekler `concurrent_unordered_multimap` nesnesi.  
  
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
 Eşlemenin içine eklenen değerin türü.  
  
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
  
##  <a name="key_eq"></a>key_eq 

 Saklı eşitlik karşılaştırması işlev nesnesi döndürür.  
  
```
key_equal key_eq() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Saklı eşitlik karşılaştırması işlev nesnesi.  
  
##  <a name="load_factor"></a>load_factor 

 Hesaplar ve geçerli Yük faktörü kapsayıcısının döndürür. Demet sayısına göre bölünmüş kapsayıcı öğe sayısı yük faktördür.  
  
```
float load_factor() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kapsayıcı için Yük faktörü.  
  
##  <a name="max_load_factor"></a>max_load_factor 

 Alır veya kapsayıcının en fazla Yük faktörü ayarlar. En fazla yük öğelerin en büyük sayı kapsayıcı kendi iç tablo büyür önce tüm demet gösterilebilecek olandan faktördür.  
  
```
float max_load_factor() const;

void max_load_factor(float _Newmax);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Newmax`  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk üye işlevi depolanan en fazla Yük faktörü döndürür. İkinci üye işlevi bir değer döndürmüyor ancak oluşturur bir [out_of_range](../../../standard-library/out-of-range-class.md) sağlanan Yük faktörü geçersiz ise özel durum...  
  
##  <a name="max_size"></a>max_size 

 Ayırıcı tarafından belirlenen eşzamanlı kapsayıcı en büyük boyutu döndürür. Eşzamanlılık güvenli yöntemdir.  
  
```
size_type max_size() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 En fazla eş zamanlı bu kapsayıcıya eklenebilir öğe sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üst sınır değeri gerçekte ne kapsayıcı gerçekte tutabilir daha yüksek olabilir.  
  
##  <a name="operator_eq"></a>işleç = 

 İçeriği başka bir atar `concurrent_unordered_multimap` bu bir nesne. Bu yöntem eşzamanlılık uyumlu değil.  
  
```
concurrent_unordered_multimap& operator= (const concurrent_unordered_multimap& _Umap);

concurrent_unordered_multimap& operator= (concurrent_unordered_multimap&& _Umap);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Umap`  
 Kaynak `concurrent_unordered_multimap` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu başvuru `concurrent_unordered_multimap` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Eşzamanlı sırasız multimap içinde var olan öğeleri silindikten sonra `operator=` kopyalar ya da içeriğini taşır `_Umap` eşzamanlı sırasız multimap içine.  
  
##  <a name="rehash"></a>rehash 

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
  
##  <a name="size"></a>boyutu 

 Eşzamanlı bu kapsayıcıda öğe sayısını döndürür. Eşzamanlılık güvenli yöntemdir.  
  
```
size_type size() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kapsayıcı öğelerin sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Eşzamanlı eklemeleri varlığında dönüş değeri bile okumadan önce hemen bu işlev çağrıldıktan sonra eş zamanlı kapsayıcı öğe sayısı değişebilir.  
  
##  <a name="swap"></a>değiştirme 

 İki içeriğini değiştirir `concurrent_unordered_multimap` nesneleri. Bu yöntem eşzamanlılık uyumlu değil.  
  
```
void swap(concurrent_unordered_multimap& _Umap);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Umap`  
 `concurrent_unordered_multimap` Nesnesi ile değiştirme.  
  
##  <a name="unsafe_begin"></a>unsafe_begin 

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
  
##  <a name="unsafe_bucket"></a>unsafe_bucket 

 Bu kapsayıcıda belirli bir anahtarın eşlendiği demet dizinini döndürür.  
  
```
size_type unsafe_bucket(const key_type& KVal) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `KVal`  
 Aranan öğe anahtarı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu kapsayıcı anahtarında demet dizini.  
  
##  <a name="unsafe_bucket_count"></a>unsafe_bucket_count 

 Bu kapsayıcıda geçerli sayısını döndürür.  
  
```
size_type unsafe_bucket_count() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu kapsayıcıda demet geçerli sayısı.  
  
##  <a name="unsafe_bucket_size"></a>unsafe_bucket_size 

 Bu kapsayıcının belirli kova öğe sayısını döndürür.  
  
```
size_type unsafe_bucket_size(size_type _Bucket);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Bucket`  
 Aranacak demet.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu kapsayıcıda demet geçerli sayısı.  
  
##  <a name="unsafe_cbegin"></a>unsafe_cbegin 

 Bu kapsayıcı için belirli bir demet ilk öğe yineleyici döndürür.  
  
```
const_local_iterator unsafe_cbegin(size_type _Bucket) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Bucket`  
 Demet dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Demet başlangıcına işaret eden bir yineleyici.  
  
##  <a name="unsafe_cend"></a>unsafe_cend 

 Belirli bir demet son öğesi başarılı konuma yineleyici döndürür.  
  
```
const_local_iterator unsafe_cend(size_type _Bucket) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Bucket`  
 Demet dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Demet başlangıcına işaret eden bir yineleyici.  
  
##  <a name="unsafe_end"></a>unsafe_end 

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
  
##  <a name="unsafe_erase"></a>unsafe_erase 

 Öğelerden kaldırır `concurrent_unordered_multimap` belirtilen konumlarda. Bu yöntem eşzamanlılık uyumlu değil.  
  
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
 Gelen silme yineleyici konumu.  
  
 `KVal`  
 ERASE anahtar değeri.  
  
 `first`  
 `last`  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk iki üye işlevleri kaldırıldı, herhangi bir öğenin dışında kalan ilk öğe atayan bir yineleyici dönün veya `concurrent_unordered_multimap::end`böyle bir öğe varsa, (). Üçüncü üye işlevi kaldırır öğe sayısını döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk üye işlevi gösterdiği denetimli sırasının öğeyi kaldırır `_Where`. İkinci üye işlevi öğeleri aralığında kaldırır [ `_Begin`, `_End`).  
  
 Üçüncü üye fonksiyonu tarafından ayrılmış aralıktaki öğeleri kaldırır `concurrent_unordered_multimap::equal_range`(KVal).  
  
##  <a name="unsafe_max_bucket_count"></a>unsafe_max_bucket_count 

 Bu kapsayıcıda maksimum sayısını döndürür.  
  
```
size_type unsafe_max_bucket_count() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu kapsayıcıda demet sayısı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [Paralel Kapsayıcılar ve Nesneler](../../../parallel/concrt/parallel-containers-and-objects.md)



