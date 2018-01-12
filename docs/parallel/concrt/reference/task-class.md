---
title: "task sınıfı (eşzamanlılık çalışma zamanı) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- task
- PPLTASKS/concurrency::task
- PPLTASKS/concurrency::task::task
- PPLTASKS/concurrency::task::get
- PPLTASKS/concurrency::task::is_apartment_aware
- PPLTASKS/concurrency::task::is_done
- PPLTASKS/concurrency::task::scheduler
- PPLTASKS/concurrency::task::then
- PPLTASKS/concurrency::task::wait
dev_langs: C++
helpviewer_keywords: task class
ms.assetid: cdc3a8c0-5cbe-45a0-b5d5-e9f81d94df1a
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4ea618ca6a5784b44666c70d79bb10b2e9f6e394
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="task-class-concurrency-runtime"></a>task Sınıfı (Eşzamanlılık Çalışma Zamanı)
Paralel Desen kitaplığı (PPL) `task` sınıfı. A `task` nesnesi paralel eşzamanlılık çalışma zamanı'nda paralel algoritmaları tarafından üretilen iş ve zaman uyumsuz olarak ve diğer görevleri ile aynı anda yürütülebilecek iş temsil eder. Bir sonuç türü üretir `_ResultType` başarıyla tamamlandığında. Tür görevleri `task<void>` hiçbir sonucu. Bir görev sırasında beklenen ve diğer görevler bağımsız olarak iptal. Ayrıca devamlılıklar kullanarak diğer görevleri ile birleştirilebilen ( `then`) ve birleştirme ( `when_all`) ve seçim ( `when_any`) desenleri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <typename T>
class task;

template <>
class task<void>;

template<typename _ReturnType>
class task;
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 `T`  
 `_ReturnType`  
 Bu görev sonuç türü.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`result_type`|Sonuç türü bu sınıfın bir nesnesi oluşturur.|  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Görev](#ctor)|Fazla Yüklendi. Oluşturan bir `task` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[get](#get)|Fazla Yüklendi. Bu görev üretilen sonuç döndürür. Görev bir terminal değilse durumunda, bir çağrı `get` görevin tamamlanmasını bekler. Bu yöntem bir görevde çağrıldığında bir değer döndürmeyen bir `result_type` , `void`.|  
|[is_apartment_aware](#is_apartment_aware)|Görev bir Windows çalışma zamanı açar olup olmadığını belirler `IAsyncInfo` arabirim ya da böyle bir görevden descended.|  
|[is_done](#is_done)|Görev tamamlandı, belirler.|  
|[Zamanlayıcı](#scheduler)|Bu Görev Zamanlayıcı'yı döndürür|  
|[ardından](#then)|Fazla Yüklendi. Devamlılık görevi için bu görev ekler.|  
|[bekleme](#wait)|Bu görev terminal durumuna ulaşmak bekler. Mümkündür `wait` tüm görevleri bağımlılıklarını karşılanır ve onu zaten yürütme için bir arka plan çalışanı tarafından çekilen değil görev satır içi yürütülecek.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[operator!=](#operator_neq)|Fazla Yüklendi. İki olup olmadığını belirleyen `task` nesneleri farklı iç görevler temsil eder.|  
|[işleç =](#operator_eq)|Fazla Yüklendi. Bir dosyanın içeriğini değiştirir `task` başka bir nesne.|  
|[operator ==](#operator_eq_eq)|Fazla Yüklendi. İki olup olmadığını belirleyen `task` nesneleri aynı iç görev temsil eder.|  
  
## <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [görev Paralelliği](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `task`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** ppltasks.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="get"></a>Al 

 Bu görev üretilen sonuç döndürür. Görev bir terminal değilse durumunda, bir çağrı `get` görevin tamamlanmasını bekler. Bu yöntem bir görevde çağrıldığında bir değer döndürmeyen bir `result_type` , `void`.  
  
```
_ReturnType get() const;

void get() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Görev sonucu.  
  
### <a name="remarks"></a>Açıklamalar  
 Görev iptal ederseniz, çağrı `get` özel durum oluşturacak bir [task_canceled](task-canceled-class.md) özel durum. Görev farklı bir özel durumla karşılaştı veya bir özel durum için bir antecedent yayıldığı görev, bir çağrı `get` bu özel durum oluşturur.  
  
> [!IMPORTANT]
>  İçinde bir [!INCLUDE[win8_appname_long](../../../build/includes/win8_appname_long_md.md)] uygulama, çağırmayın [concurrency::task::wait](#wait) veya `get` ( `wait` çağrıları `get`) STA üzerinde çalışan kod Aksi halde, çalışma zamanı oluşturur [concurrency::invalid_operation](invalid-operation-class.md) çünkü bu yöntemleri geçerli iş parçacığının engellemek ve uygulama yanıt veremez duruma neden olabilir. Ancak, çağırabilirsiniz `get` sonucu hemen kullanılabilir olduğundan, bir görev tabanlı devamlılığı öncül görev sonucu almak için yöntem.  
  
##  <a name="is_apartment_aware"></a>is_apartment_aware 

 Görev bir Windows çalışma zamanı açar olup olmadığını belirler `IAsyncInfo` arabirim ya da böyle bir görevden descended.  
  
```
bool is_apartment_aware() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`Görev açar, bir `IAsyncInfo` arabirim ya da böyle bir görevden descended `false` Aksi takdirde.  
  
##  <a name="is_done"></a>Task::is_done yöntemi (eşzamanlılık çalışma zamanı)  
 Görev tamamlandı, belirler.  
  
```
bool is_done() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Görev tamamlandı, true, false Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Görev tamamlandı ya da (ile veya kullanıcı özel olmadan) iptal işlevi true değerini döndürür.  
  
##  <a name="operator_neq"></a>operator! = 

 İki olup olmadığını belirleyen `task` nesneleri farklı iç görevler temsil eder.  
  
```
bool operator!= (const task<_ReturnType>& _Rhs) const;

bool operator!= (const task<void>& _Rhs) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Rhs`  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`nesneler farklı temel görevlere başvurursanız ve `false` Aksi takdirde.  
  
##  <a name="operator_eq"></a>işleç = 

 Bir dosyanın içeriğini değiştirir `task` başka bir nesne.  
  
```
task& operator= (const task& _Other);

task& operator= (task&& _Other);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Other`  
 Kaynak `task` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
 Olarak `task` kopya atama sonra bu akıllı bir işaretçi gibi davranır `task` nesnelerini temsil eder, aynı gerçek görev olarak `_Other` yapar.  
  
##  <a name="operator_eq_eq"></a>operator == 

 İki olup olmadığını belirleyen `task` nesneleri aynı iç görev temsil eder.  
  
```
bool operator== (const task<_ReturnType>& _Rhs) const;

bool operator== (const task<void>& _Rhs) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Rhs`  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`nesneleri aynı temel alınan görev için başvurursanız ve `false` Aksi takdirde.  
  
##  <a name="scheduler"></a>Task::Scheduler yöntemi (eşzamanlılık çalışma zamanı)  
 Bu Görev Zamanlayıcı'yı döndürür  
  
```
scheduler_ptr scheduler() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Zamanlayıcı için bir işaretçi  
  
##  <a name="ctor"></a>Görev 

 Oluşturan bir `task` nesnesi.  
  
```
task();

template<typename T>
__declspec(
    noinline) explicit task(T _Param);

template<typename T>
__declspec(
    noinline) explicit task(T _Param, const task_options& _TaskOptions);

task(
    const task& _Other);

task(
    task&& _Other);
```  
  
### <a name="parameters"></a>Parametreler  
 `T`  
 Görev oluşturulması için parametre türü.  
  
 `_Param`  
 İçinden görevi oluşturulması, parametre. Bu işlev nesnesi bir lambda olabilir bir `task_completion_event<result_type>` nesne ya da Windows mağazası uygulamanızı görevleri kullanıyorsanız Windows::Foundation::IAsyncInfo. Lambda veya işlev nesne eşdeğer bir türü olmalıdır `std::function<X(void)>`, burada X türünde bir değişken olabilir `result_type`, `task<result_type>`, veya Windows mağazası uygulamalarında Windows::Foundation::IAsyncInfo.  
  
 `_TaskOptions`  
 İptal belirteci, Zamanlayıcı vb. görev Seçenekler şunlardır:  
  
 `_Other`  
 Kaynak `task` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan Oluşturucu için bir `task` yalnızca kapsayıcılara kullanılacak görev izin vermek üzere mevcuttur. Geçerli bir görev atayana kadar oluşturulan varsayılan görev kullanılamaz. Gibi yöntemler `get`, `wait` veya `then` özel durum oluşturacak bir [invalid_argument](../../../standard-library/invalid-argument-class.md) oluşturulan varsayılan görev çağrıldığında bir özel durum.  
  
 Öğesinden oluşturulan bir görev bir `task_completion_event` tamamlayacak (ve onun devamlılıklar zamanlanmış sahip) görev tamamlama olayını ayarlandığında.  
  
 Bir iptal belirteci alan oluşturucu sürümü kullanılarak iptal bir görev oluşturur `cancellation_token_source` belirteç elde edilmiştir. Bir iptal belirteci oluşturulan görevler iptal edilebilen değildir.  
  
 Oluşturulan görevler bir `Windows::Foundation::IAsyncInfo` arabirimi veya döndüren bir lambda bir `IAsyncInfo` arabirimi ulaşmak terminal durumlarına kapalı Windows çalışma zamanı zaman uyumsuz işlem veya eylem tamamlandığında. Benzer şekilde, döndüren bir lamda oluşturulan görevler bir `task<result_type>` iç görev terminal durumuna ulaştığında ve değil lamda döndürdüğünde kendi terminal durumuna ulaşmasını.  
  
 `task`Akıllı bir işaretçi gibi davranır ve değerine göre geçici geçirmek güvenlidir. Kilitleri gerek kalmadan birden çok iş parçacığı tarafından erişilebilir.  
  
 Windows::Foundation::IAsyncInfo arabirimi veya böyle bir arabirim döndüren bir lambda alın Oluşturucusu aşırı yalnızca Windows mağazası uygulamaları için kullanılabilir.  
  
 Daha fazla bilgi için bkz: [görev Paralelliği](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
##  <a name="then"></a>ardından 

 Devamlılık görevi için bu görev ekler.  
  
```
template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func) const -> typename details::_ContinuationTypeTraits<_Function,
    _ReturnType>::_TaskOfType;

template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func,
    const task_options& _TaskOptions) const -> typename details::_ContinuationTypeTraits<_Function,
    _ReturnType>::_TaskOfType;

template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func,
    cancellation_token _CancellationToken,
    task_continuation_context _ContinuationContext) const -> typename details::_ContinuationTypeTraits<_Function,
    _ReturnType>::_TaskOfType;

template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func,
    const task_options& _TaskOptions = task_options()) const -> typename details::_ContinuationTypeTraits<_Function,
    void>::_TaskOfType;

template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func,
    cancellation_token _CancellationToken,
    task_continuation_context _ContinuationContext) const -> typename details::_ContinuationTypeTraits<_Function,
    void>::_TaskOfType;
```   
  
### <a name="parameters"></a>Parametreler  
 `_Function`  
 Bu görev tarafından çağrılan işlev nesnesi türü.  
  
 `_Func`  
 Bu görev tamamlandığında yürütmek için devamlılık işlevi. Bu devamlılık işlevi olarak almanız gerekir ya da bir değişken giriş `result_type` veya `task<result_type>`, burada `result_type` bu görevi üreten sonuç türü.  
  
 `_TaskOptions`  
 Görev seçenekleri iptal belirteci, Zamanlayıcı ve devamlılık bağlamı içerir. Varsayılan olarak önceki 3 seçenekleri öncül görevden devralınır  
  
 `_CancellationToken`  
 Devamlılık görevi ile ilişkilendirmek için iptal belirteci. Bir iptal belirteci oluşturulan bir devamlılık görevi öncül görevini belirteci devralır.  
  
 `_ContinuationContext`  
 Burada devamlılık yürütülecek belirtir değişkeni. Bu değişken, yalnızca bir Windows mağazası stili uygulamasında kullanıldığında yararlıdır. Daha fazla bilgi için bkz: [task_continuation_context](task-continuation-context-class.md)  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni oluşturulan devamlılık görevi. Döndürülen görev sonuç türü ne tarafından belirlenir `_Func` döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Aşırı `then` lambda veya Windows::Foundation::IAsyncInfo arabirimini döndürür functor alın, yalnızca Windows mağazası uygulamaları için kullanılabilir.  
  
 Zaman uyumsuz iş oluşturmak için görev devamlılıklar kullanma hakkında daha fazla bilgi için bkz: [görev Paralelliği](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
##  <a name="wait"></a>bekleme 

 Bu görev terminal durumuna ulaşmak bekler. Mümkündür `wait` tüm görevleri bağımlılıklarını karşılanır ve onu zaten yürütme için bir arka plan çalışanı tarafından çekilen değil görev satır içi yürütülecek.  
  
```
task_status wait() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `task_status` ya da olabilen değeri `completed` veya `canceled`. Görev yürütme sırasında bir özel durumla karşılaştı ya da bir özel durum için öncül bir görev yayıldığı `wait` bu özel durum oluşturur.  
  
### <a name="remarks"></a>Açıklamalar  
  
> [!IMPORTANT]
>  İçinde bir [!INCLUDE[win8_appname_long](../../../build/includes/win8_appname_long_md.md)] uygulama, çağırmayın `wait` STA üzerinde çalışan kod Aksi halde, çalışma zamanı oluşturur [concurrency::invalid_operation](invalid-operation-class.md) çünkü bu yöntem geçerli iş parçacığının engeller ve uygulama yanıt veremez duruma neden olabilir. Ancak, çağırabilirsiniz [CONCURRENCY::Task](#get) bir görev tabanlı devamlılığı öncül görev sonucu almak için yöntem.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Ad Alanı](concurrency-namespace.md)
