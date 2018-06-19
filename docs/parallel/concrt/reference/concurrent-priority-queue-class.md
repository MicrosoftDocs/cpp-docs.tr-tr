---
title: concurrent_priority_queue sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- concurrent_priority_queue
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::concurrent_priority_queue
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::clear
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::empty
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::get_allocator
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::push
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::size
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::swap
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::try_pop
dev_langs:
- C++
helpviewer_keywords:
- concurrent_priority_queue class
ms.assetid: 3e740381-0f4e-41fc-8b66-ad0bb55f17a3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ed193eea8209611640b6d125d79ffec1748a7f7f
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33693672"
---
# <a name="concurrentpriorityqueue-class"></a>concurrent_priority_queue Sınıfı
`concurrent_priority_queue` Sınıfı eş zamanlı gönderme ve pop öğeleri için birden çok iş parçacığı sağlayan bir kapsayıcıdır. Öğeleri, öncelik şablon bağımsız değişken sağlanan bir functor tarafından belirlendiği öncelik sırasına Sil'i.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <typename T,
    typename _Compare= std::less<T>,
    typename _Ax = std::allocator<T>
>,
    typename _Ax = std::allocator<T>> class concurrent_priority_queue;
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Öğeleri öncelik sırasında depolanması için veri türü.  
  
 `_Compare`  
 İki öğenin değerleri öncelik sırasına göreli sıralarına belirlemek için sıralama anahtarları olarak karşılaştırabilirsiniz işlevi nesnenin türü. Bu bağımsız değişken isteğe bağlıdır ve ikili karşılaştırma `less<T>` varsayılan değerdir.  
  
 `_Ax`  
 Ayırma ve eş zamanlı öncelik sırası bellek ayırmayı kaldırma ayrıntılarını yalıtan saklı ayırıcısı nesneyi temsil eden tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `allocator<T>`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`allocator_type`|Eş zamanlı öncelik sırası allocator sınıfı temsil eden tür.|  
|`const_reference`|Eşzamanlı öncelikli bir sırada depolanan türünde bir öğe için bir const temsil başvuru türü.|  
|`reference`|Eşzamanlı öncelikli bir sırada depolanan türünde bir öğe için bir başvuru temsil eden tür.|  
|`size_type`|Eşzamanlı öncelik sırasına öğelerin sayısını sayar türü.|  
|`value_type`|Eşzamanlı öncelikli bir sırada depolanan veri türünü temsil eden tür.|  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[concurrent_priority_queue](#ctor)|Fazla Yüklendi. Eş zamanlı öncelik sırası oluşturur.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Temizle](#clear)|Tüm öğeleri eşzamanlı öncelik siler. Bu yöntem eşzamanlılık uyumlu değil.|  
|[boş](#empty)|Eş zamanlı öncelik sırası aynı anda boşsa, testleri, bu yöntem çağrılır. Bu yöntem eşzamanlılık güvenlidir.|  
|[get_allocator](#get_allocator)|Eş zamanlı öncelik sırası oluşturmak için kullanılan ayırıcısı kopyasını döndürür. Bu yöntem eşzamanlılık güvenlidir.|  
|[push](#push)|Fazla Yüklendi. Bir öğenin eşzamanlı öncelik sırasına ekler. Bu yöntem eşzamanlılık güvenlidir.|  
|[Boyutu](#size)|Eşzamanlı öncelik sırasındaki öğe sayısını döndürür. Bu yöntem eşzamanlılık güvenlidir.|  
|[Değiştirme](#swap)|İki eşzamanlı öncelik sırası içeriğini değiştirir. Bu yöntem eşzamanlılık uyumlu değil.|  
|[try_pop](#try_pop)|Kaldırır ve sıranın boş ise sıradan en yüksek öncelik öğeyi döndürür. Bu yöntem eşzamanlılık güvenlidir.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[operator=](#operator_eq)|Fazla Yüklendi. İçeriği başka bir atar `concurrent_priority_queue` bu bir nesne. Bu yöntem eşzamanlılık uyumlu değil.|  
  
## <a name="remarks"></a>Açıklamalar  
 Ayrıntılı bilgi için `concurrent_priority_queue` sınıfı için bkz: [paralel kapsayıcılar ve nesneler](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `concurrent_priority_queue`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concurrent_priority_queue.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="clear"></a> Temizle 

 Tüm öğeleri eşzamanlı öncelik siler. Bu yöntem eşzamanlılık uyumlu değil.  
  
```
void clear();
```  
  
### <a name="remarks"></a>Açıklamalar  
 `clear` Eşzamanlılık uyumlu değil. Bu yöntemi çağırdığınızda başka bir iş parçacığı eşzamanlı öncelik sırasına yöntemleri çağırma emin olmalısınız. `clear` bellek boş değil.  
  
##  <a name="ctor"></a> concurrent_priority_queue 

 Eş zamanlı öncelik sırası oluşturur.  
  
```
explicit concurrent_priority_queue(
    const allocator_type& _Al = allocator_type());

explicit concurrent_priority_queue(
    size_type _Init_capacity,
    const allocator_type& _Al = allocator_type());

template<typename _InputIterator>
concurrent_priority_queue(_InputIterator _Begin,
    _InputIterator _End,
    const allocator_type& _Al = allocator_type());

concurrent_priority_queue(
    const concurrent_priority_queue& _Src);

concurrent_priority_queue(
    const concurrent_priority_queue& _Src,
    const allocator_type& _Al);

concurrent_priority_queue(
    concurrent_priority_queue&& _Src);

concurrent_priority_queue(
    concurrent_priority_queue&& _Src,
    const allocator_type& _Al);
```  
  
### <a name="parameters"></a>Parametreler  
 `_InputIterator`  
 Giriş yineleyici türü.  
  
 `_Al`  
 Bu nesneyle kullanılacak kaynak ayırıcı sınıfı.  
  
 `_Init_capacity`  
 İlk kapasitesini `concurrent_priority_queue` nesnesi.  
  
 `_Begin`  
 Kopyalanacak öğe aralığını ilk öğe konumu.  
  
 `_End`  
 Kopyalanacak öğeleri aralık ötesinde ilk öğe konumu.  
  
 `_Src`  
 Kaynak `concurrent_priority_queue` kopyalamak veya öğeleri taşımak için nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm oluşturucular ayırıcısı nesneyi depolamak `_Al` ve öncelik sırası başlatılamıyor.  
  
 İlk Oluşturucusu boş ilk öncelikli kuyruğa ve isteğe bağlı olarak bir ayırıcı belirtir.  
  
 İkinci oluşturucu ilk kapasiteye sahip bir öncelik sırası belirtir `_Init_capacity` ve isteğe bağlı olarak bir ayırıcı belirtir.  
  
 Yineleyici aralık tarafından sağlanan değerleri üçüncü Oluşturucusu belirtir [ `_Begin`, `_End`) ve isteğe bağlı olarak bir ayırıcı belirtir.  
  
 Dördüncü ve beşinci oluşturucular kopya bir öncelik sırası belirtin `_Src`.  
  
 Altıncı ve yedinci oluşturucular taşıma öncelik sırası belirtin `_Src`.  
  
##  <a name="empty"></a> boş 

 Eş zamanlı öncelik sırası aynı anda boşsa, testleri, bu yöntem çağrılır. Bu yöntem eşzamanlılık güvenlidir.  
  
```
bool empty() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` öncelik sırası boşsa, işlev çağrıldı, şu anda `false` Aksi takdirde.  
  
##  <a name="get_allocator"></a> get_allocator 

 Eş zamanlı öncelik sırası oluşturmak için kullanılan ayırıcısı kopyasını döndürür. Bu yöntem eşzamanlılık güvenlidir.  
  
```
allocator_type get_allocator() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir kopyasını oluşturmak için kullanılan ayırıcısı `concurrent_priority_queue` nesnesi.  
  
##  <a name="operator_eq"></a> işleç = 

 İçeriği başka bir atar `concurrent_priority_queue` bu bir nesne. Bu yöntem eşzamanlılık uyumlu değil.  
  
```
concurrent_priority_queue& operator= (const concurrent_priority_queue& _Src);

concurrent_priority_queue& operator= (concurrent_priority_queue&& _Src);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Src`  
 Kaynak `concurrent_priority_queue` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu başvuru `concurrent_priority_queue` nesnesi.  
  
##  <a name="push"></a> Anında iletme 

 Bir öğenin eşzamanlı öncelik sırasına ekler. Bu yöntem eşzamanlılık güvenlidir.  
  
```
void push(const value_type& _Elem);

void push(value_type&& _Elem);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Elem`  
 Eş zamanlı öncelik sırasına eklenecek öğe.  
  
##  <a name="size"></a> Boyutu 

 Eşzamanlı öncelik sırasındaki öğe sayısını döndürür. Bu yöntem eşzamanlılık güvenlidir.  
  
```
size_type size() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu öğe sayısını `concurrent_priority_queue` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 İşlev çağrıları tarafından eklenen tüm öğeleri dahil etmek için döndürülen boyutu garanti `push`. Ancak, sonuçlarını eşzamanlı işlem bekleyen yansıtmayabilir.  
  
##  <a name="swap"></a> Değiştirme 

 İki eşzamanlı öncelik sırası içeriğini değiştirir. Bu yöntem eşzamanlılık uyumlu değil.  
  
```
void swap(concurrent_priority_queue& _Queue);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Queue`  
 `concurrent_priority_queue` İçeriğiyle değiştirilecek nesne.  
  
##  <a name="try_pop"></a> try_pop 

 Kaldırır ve sıranın boş ise sıradan en yüksek öncelik öğeyi döndürür. Bu yöntem eşzamanlılık güvenlidir.  
  
```
bool try_pop(reference _Elem);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Elem`  
 Sıranın boş ise en yüksek öncelik öğesi ile doldurulur değişken başvuru.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` bir değer Sil'i, `false` Aksi takdirde.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [Paralel Kapsayıcılar ve Nesneler](../../../parallel/concrt/parallel-containers-and-objects.md)



