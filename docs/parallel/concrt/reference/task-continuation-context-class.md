---
title: task_continuation_context Sınıfı
ms.date: 11/04/2016
f1_keywords:
- task_continuation_context
- PPLTASKS/concurrency::task_continuation_context
- PPLTASKS/concurrency::task_continuation_context::get_current_winrt_context
- PPLTASKS/concurrency::task_continuation_context::use_arbitrary
- PPLTASKS/concurrency::task_continuation_context::use_current
- PPLTASKS/concurrency::task_continuation_context::use_default
- PPLTASKS/concurrency::task_continuation_context::use_synchronous_execution
helpviewer_keywords:
- task_continuation_context class
ms.assetid: 1fb5a76a-3682-45c2-a615-8b6b527741f0
ms.openlocfilehash: 5d7d92fcd1bb00513b9e05030afa56726e87183b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62212863"
---
# <a name="taskcontinuationcontext-class"></a>task_continuation_context Sınıfı

`task_continuation_context` Sınıfı bir devamlılığın yürütülmesini istediğiniz belirtmenize olanak verir. Yalnızca, bu sınıftan bir Windows çalışma zamanı uygulamasını kullanmak kullanışlıdır. Windows Runtime uygulamalar için görev devamlılığı yürütme içeriği, çalışma zamanı tarafından belirlenen ve yapılandırılabilir.

## <a name="syntax"></a>Sözdizimi

```
class task_continuation_context : public details::_ContextCallback;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[get_current_winrt_context](#get_current_winrt_context)|Geçerli winrt iş parçacığı bağlamını temsil eden bir görev devamlılığı bağlam nesnesi döndürür.|
|[use_arbitrary](#use_arbitrary)|Çalışma zamanı bir devamlılık için Yürütme bağlamını seçmesine izin veren bir görev devamlılığı bağlamını oluşturur.|
|[use_current](#use_current)|Geçerli Yürütme bağlamını temsil eden bir görev devamlılığı bağlam nesnesi döndürür.|
|[use_default](#use_default)|Varsayılan görev devamlılığı bağlamını oluşturur.|
|[use_synchronous_execution](#use_synchronous_execution)|Zaman uyumlu yürütme bağlamı temsil eden bir görev devamlılığı bağlam nesnesi döndürür.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`_ContextCallback`

`task_continuation_context`

## <a name="requirements"></a>Gereksinimler

**Başlık:** ppltasks.h

**Namespace:** eşzamanlılık

## <a name="get_current_winrt_context"></a> get_current_winrt_context

Geçerli WinRT iş parçacığı bağlamını temsil eden bir görev devamlılığı bağlam nesnesi döndürür.

## <a name="syntax"></a>Sözdizimi

```
static task_continuation_context get_current_winrt_context();
```

## <a name="return-value"></a>Dönüş Değeri

Geçerli Windows çalışma zamanı iş parçacığı bağlamı. Bir Windows Runtime bağlamından çağrıldığı bir boş task_continuation_context döndürür.

## <a name="remarks"></a>Açıklamalar

`get_current_winrt_context` Yöntemi çağıranın Windows çalışma zamanı iş parçacığının içeriği yakalar. Boş bir bağlamda Windows Runtime arayanlara döndürür.

Tarafından döndürülen değer `get_current_winrt_context` öncül görevin bölmeye duyarlı olup bağımsız olarak devamlılığın yakalanan bağlam (STA vs MTA), Grup modelinde yürütüleceğini çalışma zamanına belirtmek için kullanılabilir. Bir bölmeye duyarlı görev, bir Windows çalışma zamanı sarmalanmış olmaktan çıkaran görev `IAsyncInfo` arabirimi veya böyle bir görevden gelen görevdir bir görev.

Bu yöntem benzer `use_current` yöntemi, ancak kullanılabilir de için yerel C++ olmadan kod C++/CX uzantısı desteği. Yazma C + Gelişmiş kullanıcıların kullanımına için tasarlanmıştır +/ CX geçişte sorun yaşamaz kitaplık kodunu hem yerel hem de Windows çalışma zamanı arayanlar. Bu işlev gerekmedikçe öneririz `use_current` yalnızca C + için kullanılabilir olan yöntemi +/ CX istemciler.

##  <a name="use_arbitrary"></a> use_arbitrary

Çalışma zamanı bir devamlılık için Yürütme bağlamını seçmesine izin veren bir görev devamlılığı bağlamını oluşturur.

```
static task_continuation_context use_arbitrary();
```

### <a name="return-value"></a>Dönüş Değeri

Rasgele bir konumu temsil eden bir görev devamlılığı bağlamı.

### <a name="remarks"></a>Açıklamalar

Bu devamlılık içeriği kullanıldığında, devamlılık, öncül görev grubun farkında olsa bile, çalışma zamanının seçtiği bir içerikte yürütülür.

`use_arbitrary` STA'da duyarlı bir görevde devamlılık için varsayılan davranışı devre dışı bırakmak için kullanılabilir

Bu yöntem yalnızca Windows çalışma zamanı uygulamaları için kullanılabilir.

##  <a name="use_current"></a> use_current

Geçerli Yürütme bağlamını temsil eden bir görev devamlılığı bağlam nesnesi döndürür.

```
static task_continuation_context use_current();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli yürütme bağlamı.

### <a name="remarks"></a>Açıklamalar

Böylece devamlılıklar sağ apartmanda yürütülebilecek bu yöntem çağıranın Windows Çalışma Zamanı Modülü içeriği yakalar.

Tarafından döndürülen değer `use_current` devamlılık, öncül görevin bölmeye duyarlı olup olmadığını olup bağımsız olarak yakalanan bağlamda (STA vs MTA) yürütüleceğini çalışma zamanına belirtmek için kullanılabilir. Bir bölmeye duyarlı görev, bir Windows çalışma zamanı sarmalanmış olmaktan çıkaran görev `IAsyncInfo` arabirimi veya böyle bir görevden gelen görevdir bir görev.

Bu yöntem yalnızca Windows çalışma zamanı uygulamaları için kullanılabilir.

##  <a name="use_default"></a> use_default

Varsayılan görev devamlılığı bağlamını oluşturur.

```
static task_continuation_context use_default();
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan görev devamlılık bağlamı.

### <a name="remarks"></a>Açıklamalar

Çağırdığınızda kısa bir devamlılık bağlamı belirtmezseniz varsayılan bağlam kullanılır `then` yöntemi. Aşağıda ve Windows 7 için Windows uygulamaları, aynı zamanda Masaüstü uygulamalarını Windows 8 ve üzeri, görev devamlılıklarının nerede yürütüleceği çalışma zamanı belirler. Ancak, bir Windows çalışma zamanı uygulamasında duyarlı bir görevde devamlılık için varsayılan devamlılık bağlamı grup olduğu yere `then` çağrılır.

Bir bölmeye duyarlı görev, bir Windows çalışma zamanı sarmalanmış olmaktan çıkaran görev `IAsyncInfo` arabirimi veya böyle bir görevden gelen görevdir bir görev. Bu nedenle, bir devamlılık duyarlı bir görevde bir Windows çalışma zamanı STA'de içinde zamanlarsanız, devamlılık o STA içinde yürütülür

Grup olmayan kullanan bir görev bir devamlılık çalışma zamanının seçtiği bir içerikte yürütülür.

## <a name="use_synchronous_execution"></a> task_continuation_context::use_synchronous_execution

Zaman uyumlu yürütme bağlamı temsil eden bir görev devamlılığı bağlam nesnesi döndürür.

## <a name="syntax"></a>Sözdizimi

```
static task_continuation_context use_synchronous_execution();
```

## <a name="return-value"></a>Dönüş Değeri

Zaman uyumlu yürütme bağlamı.

## <a name="remarks"></a>Açıklamalar

`use_synchronous_execution` Yöntemi devamlılık görevi, öncül görevin tamamlanma neden içeriğine eşzamanlı çalışacak biçimde zorlar.

Devamlılığın iliştirildiğinde öncül görev zaten tamamlandıysa, devamlılık devamlılığın bağlayan bağlamda zaman uyumlu olarak çalışır.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
