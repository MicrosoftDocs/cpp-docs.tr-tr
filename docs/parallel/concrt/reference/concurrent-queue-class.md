---
title: "concurrent_queue sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concurrent_queue
- CONCURRENT_QUEUE/concurrency::concurrent_queue
- CONCURRENT_QUEUE/concurrency::concurrent_queue::concurrent_queue
- CONCURRENT_QUEUE/concurrency::concurrent_queue::clear
- CONCURRENT_QUEUE/concurrency::concurrent_queue::empty
- CONCURRENT_QUEUE/concurrency::concurrent_queue::get_allocator
- CONCURRENT_QUEUE/concurrency::concurrent_queue::push
- CONCURRENT_QUEUE/concurrency::concurrent_queue::try_pop
- CONCURRENT_QUEUE/concurrency::concurrent_queue::unsafe_begin
- CONCURRENT_QUEUE/concurrency::concurrent_queue::unsafe_end
- CONCURRENT_QUEUE/concurrency::concurrent_queue::unsafe_size
dev_langs: C++
helpviewer_keywords: concurrent_queue class
ms.assetid: c2218996-d0ea-40e9-b002-e9a15b085f51
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9cb1f1618f140ad9183d50d8aaacc8e9cc59c75d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="concurrentqueue-class"></a>concurrent_queue Sınıfı
`concurrent_queue` Sınıftır ilk sağlayan dizisi kapsayıcı sınıfı, öğeleri ilk erişim. Eşzamanlılık güvenli işlemler, sınırlı sayıda gibi etkinleştirir `push` ve `try_pop`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<typename T, class _Ax>
class concurrent_queue: public ::Concurrency::details::_Concurrent_queue_base_v4;
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Öğeleri sıraya depolanması için veri türü.  
  
 `_Ax`  
 Ayırma ve eşzamanlı bu sıra için bellek ayırmayı kaldırma ayrıntılarını yalıtan saklı ayırıcısı nesneyi temsil eden tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `allocator<T>`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`allocator_type`|Allocator sınıfı eşzamanlı sıranın temsil eden tür.|  
|`const_iterator`|Bir iş parçacığı güvenli olmayan temsil eden bir tür `const` yineleyici öğelerini eşzamanlı sırasındaki üzerinden.|  
|`const_reference`|Bir başvuru sağlayan bir türü bir `const` okumak ve gerçekleştirmek için eş zamanlı bir kuyrukta depolanan öğesi `const` işlemleri.|  
|`difference_type`|Eş zamanlı bir kuyrukta iki öğe arasındaki imzalı uzaklığı sağlayan türü.|  
|`iterator`|Bir iş parçacığı güvenli olmayan yineleyici öğelerini eşzamanlı bir kuyrukta üzerinden temsil eden bir tür.|  
|`reference`|Eş zamanlı bir sırada depolanan bir öğe için bir başvuru sağlar türü.|  
|`size_type`|Eşzamanlı kuyruğundaki öğelerin sayısını sayar türü.|  
|`value_type`|Eş zamanlı bir sırada depolanan veri türünü temsil eden tür.|  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[concurrent_queue](#ctor)|Fazla Yüklendi. Eş zamanlı bir kuyruk oluşturur.|  
|[~ concurrent_queue yok Edicisi](#dtor)|Eşzamanlı sıranın bozar.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Temizle](#clear)|Herhangi bir yok etme sıranın eşzamanlı temizler şu anda sıradaki öğeleri. Bu yöntem eşzamanlılık uyumlu değil.|  
|[boş](#empty)|Şu anda eş zamanlı sıranın boşsa, testleri, bu yöntem çağrılır. Bu yöntem eşzamanlılık güvenlidir.|  
|[get_allocator](#get_allocator)|Eşzamanlı kuyruk oluşturmak için kullanılan ayırıcısı kopyasını döndürür. Bu yöntem eşzamanlılık güvenlidir.|  
|[anında iletme](#push)|Fazla Yüklendi. Enqueues eşzamanlı sıranın tail sonunda bir öğe. Bu yöntem eşzamanlılık güvenlidir.|  
|[try_pop](#try_pop)|Varsa bir öğe sırasından dequeues. Bu yöntem eşzamanlılık güvenlidir.|  
|[unsafe_begin](#unsafe_begin)|Fazla Yüklendi. Yineleyici türü döndürür `iterator` veya `const_iterator` eşzamanlı sıranın başına. Bu yöntem eşzamanlılık uyumlu değil.|  
|[unsafe_end](#unsafe_end)|Fazla Yüklendi. Yineleyici türü döndürür `iterator` veya `const_iterator` eşzamanlı sıranın sonuna. Bu yöntem eşzamanlılık uyumlu değil.|  
|[unsafe_size](#unsafe_size)|Kuyrukta öğe sayısını döndürür. Bu yöntem eşzamanlılık uyumlu değil.|  
  
## <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [paralel kapsayıcılar ve nesneler](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `concurrent_queue`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concurrent_queue.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="clear"></a>Temizle 

 Herhangi bir yok etme sıranın eşzamanlı temizler şu anda sıradaki öğeleri. Bu yöntem eşzamanlılık uyumlu değil.  
  
```
void clear();
```  
  
##  <a name="ctor"></a>concurrent_queue 

 Eş zamanlı bir kuyruk oluşturur.  
  
```
explicit concurrent_queue(
    const allocator_type& _Al = allocator_type());

concurrent_queue(
    const concurrent_queue& _OtherQ,
    const allocator_type& _Al = allocator_type());

concurrent_queue(
    concurrent_queue&& _OtherQ,
    const allocator_type& _Al = allocator_type());

template<typename _InputIterator>
concurrent_queue(_InputIterator _Begin,
    _InputIterator _End);
```  
  
### <a name="parameters"></a>Parametreler  
 `_InputIterator`  
 Değer aralığını belirtir giriş yineleyici türü.  
  
 `_Al`  
 Bu nesneyle kullanılacak kaynak ayırıcı sınıfı.  
  
 `_OtherQ`  
 Kaynak `concurrent_queue` kopyalamak veya öğeleri taşımak için nesne.  
  
 `_Begin`  
 Kopyalanacak öğe aralığını ilk öğe konumu.  
  
 `_End`  
 Kopyalanacak öğeleri aralık ötesinde ilk öğe konumu.  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm oluşturucular ayırıcısı nesneyi depolamak `_Al` ve sırası başlatılamıyor.  
  
 İlk Oluşturucusu boş bir ilk sıraya ve açıkça kullanılacak ayırıcı türünü belirtir.  
  
 İkinci oluşturucu eşzamanlı sırasının bir kopyasını belirtir `_OtherQ`.  
  
 Bir taşıma eşzamanlı sırasının üçüncü Oluşturucusu belirtir `_OtherQ`.  
  
 Yineleyici aralık tarafından sağlanan değerleri dördüncü Oluşturucusu belirtir [ `_Begin`, `_End`).  
  
##  <a name="dtor"></a>~ concurrent_queue 

 Eşzamanlı sıranın bozar.  
  
```
~concurrent_queue();
```  
  
##  <a name="empty"></a>boş 

 Şu anda eş zamanlı sıranın boşsa, testleri, bu yöntem çağrılır. Bu yöntem eşzamanlılık güvenlidir.  
  
```
bool empty() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`eşzamanlı sıranın boşsa, biz Aranan, şu anda `false` Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Eşzamanlılık güvenli olsa da bu yöntem çağrıları yöntemlere göre `push`, `try_pop`, ve `empty`, onu çağıran iş parçacığı tarafından denetlenmekte zaman tarafından döndürülen değer yanlış olabilir.  
  
##  <a name="get_allocator"></a>get_allocator 

 Eşzamanlı kuyruk oluşturmak için kullanılan ayırıcısı kopyasını döndürür. Bu yöntem eşzamanlılık güvenlidir.  
  
```
allocator_type get_allocator() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Eşzamanlı kuyruk oluşturmak için kullanılan ayırıcısı kopyası.  
  
##  <a name="push"></a>anında iletme 

 Enqueues eşzamanlı sıranın tail sonunda bir öğe. Bu yöntem eşzamanlılık güvenlidir.  
  
```
void push(const T& _Src);

void push(T&& _Src);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Src`  
 Sıraya eklenecek öğe.  
  
### <a name="remarks"></a>Açıklamalar  
 `push`Eşzamanlılık uyumlu yöntemlerine göre `push`, `try_pop`, ve `empty`.  
  
##  <a name="try_pop"></a>try_pop 

 Varsa bir öğe sırasından dequeues. Bu yöntem eşzamanlılık güvenlidir.  
  
```
bool try_pop(T& _Dest);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Dest`  
 Dequeued öğesi depolamak için bir konum referansı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`bir öğe başarıyla dequeued ise `false` Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir öğe başarıyla dequeued ise parametresi `_Dest` dequeued değerini alan kuyrukta tutulan özgün değeri yok ve bu işlev döndürür `true`. Var olup olmadığını dequeue öğe yok, bu işlevi döndürür `false` engelleme ve içeriğini olmadan `_Dest` parametresi tanımlı değil.  
  
 `try_pop`Eşzamanlılık uyumlu yöntemlerine göre `push`, `try_pop`, ve `empty`.  
  
##  <a name="unsafe_begin"></a>unsafe_begin 

 Yineleyici türü döndürür `iterator` veya `const_iterator` eşzamanlı sıranın başına. Bu yöntem eşzamanlılık uyumlu değil.  
  
```
iterator unsafe_begin();

const_iterator unsafe_begin() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yineleyici türü `iterator` veya `const_iterator` başına eşzamanlı sıra nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Yineleyiciler için `concurrent_queue` sınıfı öncelikle yöneliktir hata ayıklama için yavaş ve yineleme diğer kuyruk işlemlerini göre eşzamanlılık güvenli değil.  
  
##  <a name="unsafe_end"></a>unsafe_end 

 Yineleyici türü döndürür `iterator` veya `const_iterator` eşzamanlı sıranın sonuna. Bu yöntem eşzamanlılık uyumlu değil.  
  
```
iterator unsafe_end();

const_iterator unsafe_end() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yineleyici türü `iterator` veya `const_iterator` eşzamanlı sıranın sonuna.  
  
### <a name="remarks"></a>Açıklamalar  
 Yineleyiciler için `concurrent_queue` sınıfı öncelikle yöneliktir hata ayıklama için yavaş ve yineleme diğer kuyruk işlemlerini göre eşzamanlılık güvenli değil.  
  
##  <a name="unsafe_size"></a>unsafe_size 

 Kuyrukta öğe sayısını döndürür. Bu yöntem eşzamanlılık uyumlu değil.  
  
```
size_type unsafe_size() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Eşzamanlı kuyruk boyutu.  
  
### <a name="remarks"></a>Açıklamalar  
 `unsafe_size`Eşzamanlılık uyumlu değildir ve eşzamanlı olarak yöntemlerine çağrıldıklarında hatalı sonuçlar üretebilir `push`, `try_pop`, ve `empty`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)
