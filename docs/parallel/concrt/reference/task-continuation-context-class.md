---
title: "task_continuation_context sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- task_continuation_context
- PPLTASKS/concurrency::task_continuation_context
- PPLTASKS/concurrency::task_continuation_context::get_current_winrt_context
- PPLTASKS/concurrency::task_continuation_context::use_arbitrary
- PPLTASKS/concurrency::task_continuation_context::use_current
- PPLTASKS/concurrency::task_continuation_context::use_default
- PPLTASKS/concurrency::task_continuation_context::use_synchronous_execution
dev_langs: C++
helpviewer_keywords: task_continuation_context class
ms.assetid: 1fb5a76a-3682-45c2-a615-8b6b527741f0
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c8178ca25aaf1abe9047317673a9f47354112407
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="taskcontinuationcontext-class"></a>task_continuation_context Sınıfı
`task_continuation_context` Sınıfı yürütülecek bir devamlılık oluşturulacağı yeri belirtmenize olanak verir. Yalnızca, bu sınıftan bir Windows mağazası uygulamasını kullanmak kullanışlıdır. Windows mağazası uygulamaları için görev devamlılığı 's yürütme bağlamı çalışma zamanı tarafından belirlenen ve yapılandırılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class task_continuation_context : public details::_ContextCallback;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[get_current_winrt_context](#get_current_winrt_context)|Geçerli winrt iş parçacığı bağlamı temsil eden bir görev devamlılığı bağlam nesnesi döndürür.|  
|[use_arbitrary](#use_arbitrary)|Bir devamlılık yürütme bağlamı seçmek çalışma zamanı veren bir görev devamlılığı bağlamı oluşturur.|  
|[use_current](#use_current)|Geçerli yürütme bağlamı temsil eden bir görev devamlılığı bağlam nesnesi döndürür.|  
|[use_default](#use_default)|Varsayılan görev devamlılığı bağlamı oluşturur.|  
|[use_synchronous_execution](#use_synchronous_execution)|Zaman uyumlu yürütme bağlamı temsil eden bir görev devamlılığı bağlam nesnesi döndürür.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `_ContextCallback`  
  
 `task_continuation_context`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** ppltasks.h  
  
 **Namespace:** eşzamanlılık  

## <a name="get_current_winrt_context"></a>get_current_winrt_context
 Geçerli WinRT iş parçacığı bağlamı temsil eden bir görev devamlılığı bağlam nesnesi döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
static task_continuation_context get_current_winrt_context();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Geçerli Windows çalışma zamanı iş parçacığı bağlamı. Bir Windows Runtime bağlamından adlı boş bir task_continuation_context döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 `get_current_winrt_context` Yöntemi çağıranın Windows çalışma zamanı iş parçacığının içeriği yakalar. Bu, Windows Runtime arayanlara boş bir bağlamını döndürür.  
  
 Tarafından döndürülen değer `get_current_winrt_context` devamlılık yakalanan bağlam (STA vs MTA), Grup modelinde öncül görev grup kullanan, bağımsız olarak yürütülecek çalışma zamanına göstermek için kullanılır. Windows çalışma zamanı açar bir görev bir görevdir kullanan bir grup `IAsyncInfo` arabirimi ya da böyle bir görevden descended bir görev.  
  
 Bu yöntem benzer `use_current` yöntemi, ancak kullanılabilir ayrıca yerel C++ kodu olmadan C + +/ CX uzantısı desteği. Yazma C + deneyimli kullanıcılar tarafından kullanım için tasarlanmıştır +/ CX belirsiz kitaplık kodu hem yerel hem de Windows çalışma zamanı arayanlar. Bu işlev gerekmedikçe öneririz `use_current` yalnızca C + kullanılabilir yöntemi +/ CX istemciler.  
  
  
##  <a name="use_arbitrary"></a>use_arbitrary 

 Bir devamlılık yürütme bağlamı seçmek çalışma zamanı veren bir görev devamlılığı bağlamı oluşturur.  
  
```
static task_continuation_context use_arbitrary();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Rastgele bir konumu temsil eden bir görev devamlılığı bağlamı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu devamlılık bağlam kullanıldığında devamlılık öncül görev grup kullanan olsa bile çalışma zamanı seçer bir bağlamda yürütülür.  
  
 `use_arbitrary`Bir STA oluşturulan bir grup kullanan görevde bir devamlılık varsayılan davranışı devre dışı bırakmak için kullanılabilir  
  
 Bu yöntem yalnızca Windows mağazası uygulamaları için kullanılabilir.  
  
##  <a name="use_current"></a>use_current 

 Geçerli yürütme bağlamı temsil eden bir görev devamlılığı bağlam nesnesi döndürür.  
  
```
static task_continuation_context use_current();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli yürütme bağlamı.  
  
### <a name="remarks"></a>Açıklamalar  
 Böylece devamlılıklar doğru grupta yürütülebilir. Bu yöntem çağıranın Windows çalışma zamanı içeriği yakalar.  
  
 Tarafından döndürülen değer `use_current` devamlılık öncül görev grup farkında olsun veya olmasın, bağımsız olarak yakalanan bağlamında (STA vs MTA) yürütülecek çalışma zamanına göstermek için kullanılır. Windows çalışma zamanı açar bir görev bir görevdir kullanan bir grup `IAsyncInfo` arabirimi ya da böyle bir görevden descended bir görev.  
  
 Bu yöntem yalnızca Windows mağazası uygulamaları için kullanılabilir.  
  
##  <a name="use_default"></a>use_default 

 Varsayılan görev devamlılığı bağlamı oluşturur.  
  
```
static task_continuation_context use_default();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan devamlılık bağlamı.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan bağlam çağırdığınızda kısa bir devamlılık bağlamı yapmazsanız kullanılır `then` yöntemi. Windows uygulamaları için Windows 7 ve altında aynı zamanda Masaüstü uygulamaları Windows 8 ve üzeri, görev devamlılıklar burada yürütecek çalışma zamanı belirler. Ancak, bir Windows mağazası uygulaması varsayılan devamlılık Grup kullanan görevde devam etmesi için Grup bağlamdır nerede `then` çağrılır.  
  
 Windows çalışma zamanı açar bir görev bir görevdir kullanan bir grup `IAsyncInfo` arabirimi ya da böyle bir görevden descended bir görev. Bu nedenle, bir devamlılık Windows çalışma zamanı STA içinde bir grup kullanan görevde zamanlarsanız, o STA devamlılık yürütecek  
  
 Bir grup olmayan kullanan görevde bir devamlılık çalışma zamanı seçer bir bağlamda yürütülür.  

## <a name="use_synchronous_execution"></a>task_continuation_context::use_synchronous_execution  
Zaman uyumlu yürütme bağlamı temsil eden bir görev devamlılığı bağlam nesnesi döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
static task_continuation_context use_synchronous_execution();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Zaman uyumlu yürütme bağlamı.  
  
## <a name="remarks"></a>Açıklamalar  
 `use_synchronous_execution` Yöntemi kendi öncül görevin tamamlanma neden içeriğine eş zamanlı olarak çalıştırmak için devamlılık görevi zorlar.  
  
 Devamlılık iliştirildiğinde öncül görev zaten tamamlandı, devamlılık devamlılık iliştirir içeriğine eş zamanlı olarak çalışır.  
  
 
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Ad Alanı](concurrency-namespace.md)
