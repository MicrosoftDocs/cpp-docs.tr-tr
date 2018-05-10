---
title: concurrent_vector sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- concurrent_vector
- CONCURRENT_VECTOR/concurrency::concurrent_vector
- CONCURRENT_VECTOR/concurrency::concurrent_vector::concurrent_vector
- CONCURRENT_VECTOR/concurrency::concurrent_vector::assign
- CONCURRENT_VECTOR/concurrency::concurrent_vector::at
- CONCURRENT_VECTOR/concurrency::concurrent_vector::back
- CONCURRENT_VECTOR/concurrency::concurrent_vector::begin
- CONCURRENT_VECTOR/concurrency::concurrent_vector::capacity
- CONCURRENT_VECTOR/concurrency::concurrent_vector::cbegin
- CONCURRENT_VECTOR/concurrency::concurrent_vector::cend
- CONCURRENT_VECTOR/concurrency::concurrent_vector::clear
- CONCURRENT_VECTOR/concurrency::concurrent_vector::crbegin
- CONCURRENT_VECTOR/concurrency::concurrent_vector::crend
- CONCURRENT_VECTOR/concurrency::concurrent_vector::empty
- CONCURRENT_VECTOR/concurrency::concurrent_vector::end
- CONCURRENT_VECTOR/concurrency::concurrent_vector::front
- CONCURRENT_VECTOR/concurrency::concurrent_vector::get_allocator
- CONCURRENT_VECTOR/concurrency::concurrent_vector::grow_by
- CONCURRENT_VECTOR/concurrency::concurrent_vector::grow_to_at_least
- CONCURRENT_VECTOR/concurrency::concurrent_vector::max_size
- CONCURRENT_VECTOR/concurrency::concurrent_vector::push_back
- CONCURRENT_VECTOR/concurrency::concurrent_vector::rbegin
- CONCURRENT_VECTOR/concurrency::concurrent_vector::rend
- CONCURRENT_VECTOR/concurrency::concurrent_vector::reserve
- CONCURRENT_VECTOR/concurrency::concurrent_vector::resize
- CONCURRENT_VECTOR/concurrency::concurrent_vector::shrink_to_fit
- CONCURRENT_VECTOR/concurrency::concurrent_vector::size
- CONCURRENT_VECTOR/concurrency::concurrent_vector::swap
dev_langs:
- C++
helpviewer_keywords:
- concurrent_vector class
ms.assetid: a217b4ac-af2b-4d41-94eb-09a75ee28622
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e120e072fb3f56788cbf39fbbc3887f5c816f4ef
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="concurrentvector-class"></a>concurrent_vector Sınıfı
`concurrent_vector` Sınıftır herhangi bir öğeye rasgele erişim sağlayan bir dizi kapsayıcı. Eşzamanlılık güvenli etkinleştirir ekleme, öğe erişim, yineleyici erişim ve yineleyici geçişi işlemleri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<typename T, class _Ax>
class concurrent_vector: protected details::_Allocator_base<T,
    _Ax>,
 private details::_Concurrent_vector_base_v4;
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Öğeleri vektörü depolanması için veri türü.  
  
 `_Ax`  
 Ayırma ve eşzamanlı vektör bellek ayırmayı kaldırma ayrıntılarını yalıtan saklı ayırıcısı nesneyi temsil eden tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `allocator<T>`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`allocator_type`|Eşzamanlı vektör allocator sınıfı temsil eden tür.|  
|`const_iterator`|Rasgele erişim yineleyici bu can sağlayan bir türü okuma bir `const` eşzamanlı vektör öğesinde.|  
|`const_pointer`|Bir işaretçi sağlayan bir türü bir `const` eşzamanlı vektör öğesinde.|  
|`const_reference`|Bir başvuru sağlayan bir türü bir `const` okumak ve gerçekleştirmek için eş zamanlı vektör depolanan öğesi `const` işlemleri.|  
|`const_reverse_iterator`|Herhangi bir rastgele erişim yineleyici bu can sağlayan bir türü okuma `const` eşzamanlı vektör öğesinde.|  
|`difference_type`|İki eşzamanlı vektör öğelerinde arasındaki imzalı uzaklığı sağlayan türü.|  
|`iterator`|Eşzamanlı vektörü herhangi bir öğe okuyabilir rasgele erişim yineleyici sağlayan türü. Yineleyici kullanarak bir öğe değiştirilmesini eşzamanlılık uyumlu değil.|  
|`pointer`|Eşzamanlı vektör bir öğesine bir işaretçi sağlayan türü.|  
|`reference`|Bir eş zamanlı vektörü depolanan bir öğe için bir başvuru sağlar türü.|  
|`reverse_iterator`|Ters eşzamanlı vektörü herhangi bir öğe okuyabilir rasgele erişim yineleyici sağlayan türü. Yineleyici kullanarak bir öğe değiştirilmesini eşzamanlılık uyumlu değil.|  
|`size_type`|Eşzamanlı vektör öğelerinde sayar türü.|  
|`value_type`|Eşzamanlı vektör içinde depolanan veri türünü temsil eden tür.|  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[concurrent_vector](#ctor)|Fazla Yüklendi. Eşzamanlı vektörü oluşturur.|  
|[~ concurrent_vector yok Edicisi](#dtor)|Tüm öğeleri siler ve bu eşzamanlı vektör yok eder.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Ata](#assign)|Fazla Yüklendi. Eşzamanlı vektör öğelerini siler ve ya da atar `_N` birini kopyalar `_Item`, veya yineleyici aralık tarafından belirlenen değerler [ `_Begin`, `_End`). Bu yöntem eşzamanlılık uyumlu değil.|  
|[konumundaki](#at)|Fazla Yüklendi. Eşzamanlı vektör içinde belirtilen dizinindeki öğeyi erişim sağlar. Bu yöntem eşzamanlılık-güvenlidir okuma işlemleri için ve ayrıca, değer sağladıktan sürece vektör büyüyen sırasında `_Index` eşzamanlı vektör boyutu küçüktür.|  
|[Geri](#back)|Fazla Yüklendi. Bir başvuru döndürür `const` son eşzamanlı vektör öğesinde başvuru. Dönüş değerini eşzamanlı vektör boşsa, tanımlanmamıştır. Bu yöntem eşzamanlılık güvenlidir.|  
|[Başlangıç](#begin)|Fazla Yüklendi. Yineleyici türü döndürür `iterator` veya `const_iterator` eşzamanlı vektör başlangıcına. Bu yöntem eşzamanlılık güvenlidir.|  
|[Kapasite](#capacity)|Daha fazla bellek ayırmak zorunda kalmadan eşzamanlı vektör büyüyebileceği maksimum boyutu döndürür. Bu yöntem eşzamanlılık güvenlidir.|  
|[cbegin](#cbegin)|Yineleyici türü döndürür `const_iterator` eşzamanlı vektör başlangıcına. Bu yöntem eşzamanlılık güvenlidir.|  
|[cend](#cend)|Yineleyici türü döndürür `const_iterator` eşzamanlı vektör sonuna. Bu yöntem eşzamanlılık güvenlidir.|  
|[Temizle](#clear)|Eşzamanlı vektör tüm öğeler siler. Bu yöntem eşzamanlılık uyumlu değil.|  
|[crbegin](#crbegin)|Yineleyici türü döndürür `const_reverse_iterator` eşzamanlı vektör başlangıcına. Bu yöntem eşzamanlılık güvenlidir.|  
|[crend](#crend)|Yineleyici türü döndürür `const_reverse_iterator` eşzamanlı vektör sonuna. Bu yöntem eşzamanlılık güvenlidir.|  
|[boş](#empty)|Aynı anda eş zamanlı vektör boşsa, testleri, bu yöntem çağrılır. Bu yöntem eşzamanlılık güvenlidir.|  
|[Bitiş](#end)|Fazla Yüklendi. Yineleyici türü döndürür `iterator` veya `const_iterator` eşzamanlı vektör sonuna. Bu yöntem eşzamanlılık güvenlidir.|  
|[Ön](#front)|Fazla Yüklendi. Bir başvuru döndürür `const` eşzamanlı vektör ilk öğe referansı. Dönüş değerini eşzamanlı vektör boşsa, tanımlanmamıştır. Bu yöntem eşzamanlılık güvenlidir.|  
|[get_allocator](#get_allocator)|Eşzamanlı vektör oluşturmak için kullanılan ayırıcısı kopyasını döndürür. Bu yöntem eşzamanlılık güvenlidir.|  
|[grow_by](#grow_by)|Fazla Yüklendi. Bu eş zamanlı vektörü ile büyür `_Delta` öğeleri. Bu yöntem eşzamanlılık güvenlidir.|  
|[grow_to_at_least](#grow_to_at_least)|En az olana kadar bu eşzamanlı vektör büyür `_N` öğeleri. Bu yöntem eşzamanlılık güvenlidir.|  
|[max_size](#max_size)|En fazla eş zamanlı vektör tutabilir öğesi sayısını döndürür. Bu yöntem eşzamanlılık güvenlidir.|  
|[push_back](#push_back)|Fazla Yüklendi. Verilen öğe eşzamanlı vektör sonuna ekler. Bu yöntem eşzamanlılık güvenlidir.|  
|[rbegin](#rbegin)|Fazla Yüklendi. Yineleyici türü döndürür `reverse_iterator` veya `const_reverse_iterator` eşzamanlı vektör başlangıcına. Bu yöntem eşzamanlılık güvenlidir.|  
|[rend](#rend)|Fazla Yüklendi. Yineleyici türü döndürür `reverse_iterator` veya `const_reverse_iterator` eşzamanlı vektör sonuna. Bu yöntem eşzamanlılık güvenlidir.|  
|[ayırma](#reserve)|Eşzamanlı vektör boyutu büyümeye yeterli alan ayırır `_N` daha sonra daha fazla bellek ayırmak zorunda kalmadan. Bu yöntem eşzamanlılık uyumlu değil.|  
|[Yeniden boyutlandırma](#resize)|Fazla Yüklendi. İstenen boyuta silme veya gerektiği gibi öğeleri ekleme, eş zamanlı vektör boyutu değişir. Bu yöntem eşzamanlılık uyumlu değil.|  
|[shrink_to_fit](#shrink_to_fit)|Parçalanma ve bellek kullanımını en iyi duruma getirmek için eş zamanlı vektör iç gösterimini sıkıştırır. Bu yöntem eşzamanlılık uyumlu değil.|  
|[Boyutu](#size)|Eşzamanlı vektörü öğe sayısını döndürür. Bu yöntem eşzamanlılık güvenlidir.|  
|[Değiştirme](#swap)|İki eşzamanlı vektör içeriğini değiştirir. Bu yöntem eşzamanlılık uyumlu değil.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[[] işleci](#operator_at)|Fazla Yüklendi. Eşzamanlı vektör içinde belirtilen dizinindeki öğeyi erişim sağlar. Bu yöntem eşzamanlılık-güvenlidir okuma işlemleri için ve ayrıca, güvence altına sürece, değer vektör büyüyen sırasında `_Index` eşzamanlı vektör boyutu küçüktür.|  
|[operator=](#operator_eq)|Fazla Yüklendi. İçeriği başka bir atar `concurrent_vector` bu bir nesne. Bu yöntem eşzamanlılık uyumlu değil.|  
  
## <a name="remarks"></a>Açıklamalar  
 Ayrıntılı bilgi için `concurrent_vector` sınıfı için bkz: [paralel kapsayıcılar ve nesneler](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `_Concurrent_vector_base_v4`  
  
 `_Allocator_base`  
  
 `concurrent_vector`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concurrent_vector.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="assign"></a> Ata 

 Eşzamanlı vektör öğelerini siler ve ya da atar `_N` birini kopyalar `_Item`, veya yineleyici aralık tarafından belirlenen değerler [ `_Begin`, `_End`). Bu yöntem eşzamanlılık uyumlu değil.  
  
```
void assign(
    size_type _N,
    const_reference _Item);

template<class _InputIterator>
void assign(_InputIterator _Begin,
    _InputIterator _End);
```  
  
### <a name="parameters"></a>Parametreler  
 `_InputIterator`  
 Belirtilen yineleyici türü.  
  
 `_N`  
 Eşzamanlı vektör kopyalamak için öğe sayısı.  
  
 `_Item`  
 Eşzamanlı vektör doldurmak için kullanılan bir değer başvuru.  
  
 `_Begin`  
 Yineleyici kaynak aralığı ilk öğeye.  
  
 `_End`  
 Yineleyici bir kaynak aralığı son öğesinden geçti.  
  
### <a name="remarks"></a>Açıklamalar  
 `assign` Eşzamanlılık uyumlu değil. Bu yöntemi çağırdığınızda başka bir iş parçacığı eşzamanlı vektör yöntemleri çağırma emin olmalısınız.  
  
##  <a name="at"></a> konumundaki 

 Eşzamanlı vektör içinde belirtilen dizinindeki öğeyi erişim sağlar. Bu yöntem eşzamanlılık-güvenlidir okuma işlemleri için ve ayrıca, değer sağladıktan sürece vektör büyüyen sırasında `_Index` eşzamanlı vektör boyutu küçüktür.  
  
```
reference at(size_type _Index);

const_reference at(size_type _Index) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Index`  
 Alınacak öğenin dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Verilen dizindeki öğesine başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 İşlev sürümü `at` olmayan bir döndüren `const` başvurusu, aynı anda farklı iş parçacıklarından öğesine yazmak için kullanılamaz. Farklı eşitleme nesnesi eşitlemek eşzamanlı okuma ve yazma işlemleri için aynı veri öğesi için kullanılmalıdır.  
  
 Yöntem oluşturulur `out_of_range` varsa `_Index` büyük veya eşit eşzamanlı vektör boyutu ve `range_error` dizini vektör kopuk bir kısmı için ise. Nasıl bir vektör bozuk hale gelebilir hakkında daha fazla bilgi için bkz [paralel kapsayıcılar ve nesneler](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
##  <a name="back"></a> Geri 

 Bir başvuru döndürür `const` son eşzamanlı vektör öğesinde başvuru. Dönüş değerini eşzamanlı vektör boşsa, tanımlanmamıştır. Bu yöntem eşzamanlılık güvenlidir.  
  
```
reference back();

const_reference back() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başvuru veya bir `const` son eşzamanlı vektör öğesinde başvuru.  
  
##  <a name="begin"></a> Başlangıç 

 Yineleyici türü döndürür `iterator` veya `const_iterator` eşzamanlı vektör başlangıcına. Bu yöntem eşzamanlılık güvenlidir.  
  
```
iterator begin();

const_iterator begin() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yineleyici türü `iterator` veya `const_iterator` eşzamanlı vektör başlangıcına.  
  
##  <a name="capacity"></a> Kapasite 

 Daha fazla bellek ayırmak zorunda kalmadan eşzamanlı vektör büyüyebileceği maksimum boyutu döndürür. Bu yöntem eşzamanlılık güvenlidir.  
  
```
size_type capacity() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Daha fazla bellek ayırmak zorunda kalmadan eşzamanlı vektör büyüyebileceği maksimum boyutu.  
  
### <a name="remarks"></a>Açıklamalar  
 C++ Standart Kitaplığı aksine `vector`, `concurrent_vector` nesnesi değil taşırsanız varolan öğeleri daha fazla bellek ayırır.  
  
##  <a name="cbegin"></a> cbegin 

 Yineleyici türü döndürür `const_iterator` eşzamanlı vektör başlangıcına. Bu yöntem eşzamanlılık güvenlidir.  
  
```
const_iterator cbegin() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yineleyici türü `const_iterator` eşzamanlı vektör başlangıcına.  
  
##  <a name="cend"></a> cend 

 Yineleyici türü döndürür `const_iterator` eşzamanlı vektör sonuna. Bu yöntem eşzamanlılık güvenlidir.  
  
```
const_iterator cend() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yineleyici türü `const_iterator` eşzamanlı vektör sonuna.  
  
##  <a name="clear"></a> Temizle 

 Eşzamanlı vektör tüm öğeler siler. Bu yöntem eşzamanlılık uyumlu değil.  
  
```
void clear();
```  
  
### <a name="remarks"></a>Açıklamalar  
 `clear` Eşzamanlılık uyumlu değil. Bu yöntemi çağırdığınızda başka bir iş parçacığı eşzamanlı vektör yöntemleri çağırma emin olmalısınız. `clear` İç diziler boş değil. İç dizileri boşaltmak için işlev çağrısı `shrink_to_fit` sonra `clear`.  
  
##  <a name="ctor"></a> concurrent_vector 

 Eşzamanlı vektörü oluşturur.  
  
```
explicit concurrent_vector(
    const allocator_type& _Al = allocator_type());

concurrent_vector(
    const concurrent_vector& _Vector);

template<class M>
concurrent_vector(
    const concurrent_vector<T,
    M>& _Vector,
    const allocator_type& _Al = allocator_type());

concurrent_vector(
    concurrent_vector&& _Vector);

explicit concurrent_vector(
    size_type _N);

concurrent_vector(
    size_type _N,
    const_reference _Item,
    const allocator_type& _Al = allocator_type());

template<class _InputIterator>
concurrent_vector(_InputIterator _Begin,
    _InputIterator _End,
    const allocator_type& _Al = allocator_type());
```  
  
### <a name="parameters"></a>Parametreler  
 `M`  
 Kaynak vektör ayırıcı türü.  
  
 `_InputIterator`  
 Giriş yineleyici türü.  
  
 `_Al`  
 Bu nesneyle kullanılacak kaynak ayırıcı sınıfı.  
  
 `_Vector`  
 Kaynak `concurrent_vector` kopyalamak veya öğeleri taşımak için nesne.  
  
 `_N`  
 İlk kapasitesini `concurrent_vector` nesnesi.  
  
 `_Item`  
 Oluşturulan nesneye öğelerinde değeri.  
  
 `_Begin`  
 Kopyalanacak öğe aralığını ilk öğe konumu.  
  
 `_End`  
 Kopyalanacak öğeleri aralık ötesinde ilk öğe konumu.  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm oluşturucular ayırıcısı nesneyi depolamak `_Al` ve vektör başlatma.  
  
 İlk Oluşturucusu boş bir ilk vektörü belirtin ve açıkça ayırıcısı türünü belirtir. kullanılacak.  
  
 İkinci ve üçüncü oluşturucular eşzamanlı vektör kopyasını belirtin `_Vector`.  
  
 Dördüncü Oluşturucusu eşzamanlı vektör taşıma belirtir `_Vector`.  
  
 Belirtilen sayının yineleme beşinci Oluşturucusu belirtir ( `_N`) sınıfı için varsayılan değer öğelerinin `T`.  
  
 Altıncı Oluşturucusu yineleme sayısını belirtir ( `_N`) değerinin öğeleri `_Item`.  
  
 Yineleyici aralık tarafından sağlanan değerleri son Oluşturucusu belirtir [ `_Begin`, `_End`).  
  
##  <a name="dtor"></a> ~ concurrent_vector 

 Tüm öğeleri siler ve bu eşzamanlı vektör yok eder.  
  
```
~concurrent_vector();
```  
  
##  <a name="crbegin"></a> crbegin 

 Yineleyici türü döndürür `const_reverse_iterator` eşzamanlı vektör başlangıcına. Bu yöntem eşzamanlılık güvenlidir.  
  
```
const_reverse_iterator crbegin() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yineleyici türü `const_reverse_iterator` eşzamanlı vektör başlangıcına.  
  
##  <a name="crend"></a> crend 

 Yineleyici türü döndürür `const_reverse_iterator` eşzamanlı vektör sonuna. Bu yöntem eşzamanlılık güvenlidir.  
  
```
const_reverse_iterator crend() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yineleyici türü `const_reverse_iterator` eşzamanlı vektör sonuna.  
  
##  <a name="empty"></a> boş 

 Aynı anda eş zamanlı vektör boşsa, testleri, bu yöntem çağrılır. Bu yöntem eşzamanlılık güvenlidir.  
  
```
bool empty() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` vektör boşsa, işlev çağrıldı, şu anda `false` Aksi takdirde.  
  
##  <a name="end"></a> Bitiş 

 Yineleyici türü döndürür `iterator` veya `const_iterator` eşzamanlı vektör sonuna. Bu yöntem eşzamanlılık güvenlidir.  
  
```
iterator end();

const_iterator end() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yineleyici türü `iterator` veya `const_iterator` eşzamanlı vektör sonuna.  
  
##  <a name="front"></a> Ön 

 Bir başvuru döndürür `const` eşzamanlı vektör ilk öğe referansı. Dönüş değerini eşzamanlı vektör boşsa, tanımlanmamıştır. Bu yöntem eşzamanlılık güvenlidir.  
  
```
reference front();

const_reference front() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başvuru veya bir `const` eşzamanlı vektör ilk öğe referansı.  
  
##  <a name="get_allocator"></a> get_allocator 

 Eşzamanlı vektör oluşturmak için kullanılan ayırıcısı kopyasını döndürür. Bu yöntem eşzamanlılık güvenlidir.  
  
```
allocator_type get_allocator() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir kopyasını oluşturmak için kullanılan ayırıcısı `concurrent_vector` nesnesi.  
  
##  <a name="grow_by"></a> grow_by 

 Bu eş zamanlı vektörü ile büyür `_Delta` öğeleri. Bu yöntem eşzamanlılık güvenlidir.  
  
```
iterator grow_by(
    size_type _Delta);

iterator grow_by(
    size_type _Delta,
    const_reference _Item);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Delta`  
 Nesnesine eklenecek öğe sayısı.  
  
 `_Item`  
 Yeni öğelerle başlatmak için değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yineleyici ilk öğesine eklenir.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `_Item` belirtilmezse, yeni öğeler oluşturulan varsayılan bağlıdır.  
  
##  <a name="grow_to_at_least"></a> grow_to_at_least 

 En az olana kadar bu eşzamanlı vektör büyür `_N` öğeleri. Bu yöntem eşzamanlılık güvenlidir.  
  
```
iterator grow_to_at_least(size_type _N);
```  
  
### <a name="parameters"></a>Parametreler  
 `_N`  
 Yeni minimum boyutu `concurrent_vector` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Eklenen dizisi başlangıcını veya dizininde bulunan öğe işaret yineleyici `_N` öğe eklenmiş durumunda.  
  
##  <a name="max_size"></a> max_size 

 En fazla eş zamanlı vektör tutabilir öğesi sayısını döndürür. Bu yöntem eşzamanlılık güvenlidir.  
  
```
size_type max_size() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 En fazla öğe sayısı `concurrent_vector` hold nesnesi.  
  
##  <a name="operator_eq"></a> işleç = 

 İçeriği başka bir atar `concurrent_vector` bu bir nesne. Bu yöntem eşzamanlılık uyumlu değil.  
  
```
concurrent_vector& operator= (
    const concurrent_vector& _Vector);

template<class M>
concurrent_vector& operator= (
    const concurrent_vector<T, M>& _Vector);

concurrent_vector& operator= (
    concurrent_vector&& _Vector);
```  
  
### <a name="parameters"></a>Parametreler  
 `M`  
 Kaynak vektör ayırıcı türü.  
  
 `_Vector`  
 Kaynak `concurrent_vector` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu başvuru `concurrent_vector` nesnesi.  
  
##  <a name="operator_at"></a> [] işleci 

 Eşzamanlı vektör içinde belirtilen dizinindeki öğeyi erişim sağlar. Bu yöntem eşzamanlılık-güvenlidir okuma işlemleri için ve ayrıca, güvence altına sürece, değer vektör büyüyen sırasında `_Index` eşzamanlı vektör boyutu küçüktür.  
  
```
reference operator[](size_type _index);

const_reference operator[](size_type _index) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Index`  
 Alınacak öğenin dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Verilen dizindeki öğesine başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Sürümü `operator []` olmayan bir döndüren `const` başvurusu, aynı anda farklı iş parçacıklarından öğesine yazmak için kullanılamaz. Farklı eşitleme nesnesi eşitlemek eşzamanlı okuma ve yazma işlemleri için aynı veri öğesi için kullanılmalıdır.  
  
 Gerçekleştirilir emin olmak için kontrol hiçbir sınırları `_Index` eşzamanlı vektör halinde geçerli bir dizindir.  
  
##  <a name="push_back"></a> push_back 

 Verilen öğe eşzamanlı vektör sonuna ekler. Bu yöntem eşzamanlılık güvenlidir.  
  
```
iterator push_back(const_reference _Item);

iterator push_back(T&& _Item);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Item`  
 Eklenecek değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yineleyici öğesine eklenir.  
  
##  <a name="rbegin"></a> rbegin 

 Yineleyici türü döndürür `reverse_iterator` veya `const_reverse_iterator` eşzamanlı vektör başlangıcına. Bu yöntem eşzamanlılık güvenlidir.  
  
```
reverse_iterator rbegin();

const_reverse_iterator rbegin() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yineleyici türü `reverse_iterator` veya `const_reverse_iterator` eşzamanlı vektör başlangıcına.  
  
##  <a name="rend"></a> rend 

 Yineleyici türü döndürür `reverse_iterator` veya `const_reverse_iterator` eşzamanlı vektör sonuna. Bu yöntem eşzamanlılık güvenlidir.  
  
```
reverse_iterator rend();

const_reverse_iterator rend() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yineleyici türü `reverse_iterator` veya `const_reverse_iterator` eşzamanlı vektör sonuna.  
  
##  <a name="reserve"></a> ayırma 

 Eşzamanlı vektör boyutu büyümeye yeterli alan ayırır `_N` daha sonra daha fazla bellek ayırmak zorunda kalmadan. Bu yöntem eşzamanlılık uyumlu değil.  
  
```
void reserve(size_type _N);
```  
  
### <a name="parameters"></a>Parametreler  
 `_N`  
 Alan ayırmak için öğe sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 `reserve` Eşzamanlılık uyumlu değil. Bu yöntemi çağırdığınızda başka bir iş parçacığı eşzamanlı vektör yöntemleri çağırma emin olmalısınız. Metodu döndükten sonra eş zamanlı vektör kapasitesini istenen ayırma büyük olabilir.  
  
##  <a name="resize"></a> Yeniden boyutlandırma 

 İstenen boyuta silme veya gerektiği gibi öğeleri ekleme, eş zamanlı vektör boyutu değişir. Bu yöntem eşzamanlılık uyumlu değil.  
  
```
void resize(
    size_type _N);

void resize(
    size_type _N,
    const T& val);
```  
  
### <a name="parameters"></a>Parametreler  
 `_N`  
 Concurrent_vector yeni boyutu.  
  
 `val`  
 Yeni boyutu özgün boyutundan daha büyük ise vektörüne eklenen yeni öğeleri değeri. Değer belirtilmezse, yeni nesne türleri için varsayılan değer atanır.  
  
### <a name="remarks"></a>Açıklamalar  
 Kapsayıcı boyutu istenen boyuttan daha az ise, istenen boyuta ulaşana kadar öğeleri vector öğesine eklenir. Kapsayıcı boyutu istenen boyutundan daha büyükse kapsayıcı boyuta ulaşana kadar kapsayıcı sonuna kadar yakın öğeleri silinir `_N`. Kapsayıcı mevcut boyutunu istenen boyutu ile aynı olduğunda, hiçbir işlem yapılmadı.  
  
 `resize` Eşzamanlılık güvenli değil. Bu yöntemi çağırdığınızda başka bir iş parçacığı eşzamanlı vektör yöntemleri çağırma emin olmalısınız.  
  
##  <a name="shrink_to_fit"></a> shrink_to_fit 

 Parçalanma ve bellek kullanımını en iyi duruma getirmek için eş zamanlı vektör iç gösterimini sıkıştırır. Bu yöntem eşzamanlılık uyumlu değil.  
  
```
void shrink_to_fit();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem dahili olarak, geçici bellek taşıma öğeleri tüm yineleyiciler geçersiz kılmalarını yeniden ayırır. `shrink_to_fit` Eşzamanlılık uyumlu değil. Bu işlev çağırdığınızda başka bir iş parçacığı eşzamanlı vektör yöntemleri çağırma emin olmalısınız.  
  
##  <a name="size"></a> Boyutu 

 Eşzamanlı vektörü öğe sayısını döndürür. Bu yöntem eşzamanlılık güvenlidir.  
  
```
size_type size() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu öğe sayısını `concurrent_vector` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 İşlev çağrıları tarafından eklenen tüm öğeleri dahil etmek için döndürülen boyutu garanti `push_back`, ya da bu yöntemi çağırmadan önce tamamlanan işlemlerinin büyütün. Ancak, bu da ayrılan öğeleri içerebilir ancak hala büyüme yöntemlerden herhangi birini eşzamanlı çağrı tarafından aşamasında.  
  
##  <a name="swap"></a> Değiştirme 

 İki eşzamanlı vektör içeriğini değiştirir. Bu yöntem eşzamanlılık uyumlu değil.  
  
```
void swap(concurrent_vector& _Vector);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Vector`  
 `concurrent_vector` İçeriğiyle değiştirilecek nesne.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [Paralel Kapsayıcılar ve Nesneler](../../../parallel/concrt/parallel-containers-and-objects.md)



