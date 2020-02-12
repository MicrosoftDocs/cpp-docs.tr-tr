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
ms.openlocfilehash: ae8ac425f035839cdddc0b19f4f40d3b6369202a
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142582"
---
# <a name="task_continuation_context-class"></a>task_continuation_context Sınıfı

`task_continuation_context` sınıfı, bir devamlılığın nerede yürütülmesini istediğinizi belirtmenize olanak tanır. Bu sınıfı yalnızca bir Windows Çalışma Zamanı uygulamasından kullanmak faydalıdır. Windows Çalışma Zamanı olmayan uygulamalar için, görev devamlılığın yürütme bağlamı, çalışma zamanı tarafından belirlenir ve yapılandırılamaz.

## <a name="syntax"></a>Sözdizimi

```cpp
class task_continuation_context : public details::_ContextCallback;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[get_current_winrt_context](#get_current_winrt_context)|Geçerli WinRT iş parçacığı bağlamını temsil eden bir görev devamlılık bağlamı nesnesi döndürür.|
|[use_arbitrary](#use_arbitrary)|Çalışma zamanının bir devamlılık için yürütme bağlamını seçmesini sağlayan bir görev devamlılık bağlamı oluşturur.|
|[use_current](#use_current)|Geçerli yürütme bağlamını temsil eden bir görev devamlılık bağlamı nesnesi döndürür.|
|[use_default](#use_default)|Varsayılan görev devamlılık bağlamını oluşturur.|
|[use_synchronous_execution](#use_synchronous_execution)|Zaman uyumlu Yürütme bağlamını temsil eden bir görev devamlılık bağlamı nesnesi döndürür.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`_ContextCallback`

`task_continuation_context`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** ppltasks. h

**Ad alanı:** eşzamanlılık

## <a name="get_current_winrt_context"></a>get_current_winrt_context

Geçerli WinRT iş parçacığı bağlamını temsil eden bir görev devamlılık bağlamı nesnesi döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
static task_continuation_context get_current_winrt_context();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli Windows Çalışma Zamanı iş parçacığı bağlamı. Windows Çalışma Zamanı olmayan bir içerikten çağrılırsa boş bir task_continuation_context döndürür.

### <a name="remarks"></a>Açıklamalar

`get_current_winrt_context` yöntemi çağıranın Windows Çalışma Zamanı iş parçacığı bağlamını yakalar. Windows Çalışma Zamanı çağıranlar için boş bir bağlam döndürür.

`get_current_winrt_context` tarafından döndürülen değer, öncül görevin apartman uyumlu olup olmamasına bakılmaksızın devamlılığın yakalanan bağlamın (STA vs MTA) Grup modelinde yürütülmesi için çalışma zamanına işaret etmek üzere kullanılabilir. Apartment Aware görevi, bir Windows Çalışma Zamanı `IAsyncInfo` arabirimini veya bu tür bir görevden gelen bir görevi sarmalayan bir görevdir.

Bu yöntem `use_current` yönteme benzerdir, ancak Ayrıca,/CX uzantı desteği olmadan C++ C++yerel kod tarafından da kullanılabilir. Hem yerel hem de Windows Çalışma Zamanı çağıranları için/CX-agnostic kitaplık kodu yazan C++gelişmiş kullanıcılar tarafından kullanılmak üzere tasarlanmıştır. Bu işlevselliğe ihtiyacınız yoksa, yalnızca C++/CX istemcileri tarafından kullanılabilen `use_current` yöntemi önerilir.

## <a name="use_arbitrary"></a>use_arbitrary

Çalışma zamanının bir devamlılık için yürütme bağlamını seçmesini sağlayan bir görev devamlılık bağlamı oluşturur.

### <a name="syntax"></a>Sözdizimi

```cpp
static task_continuation_context use_arbitrary();
```

### <a name="return-value"></a>Dönüş Değeri

Rastgele bir konumu temsil eden bir görev devamlılık bağlamı.

### <a name="remarks"></a>Açıklamalar

Bu devamlılık bağlamı kullanıldığında, çalışma zamanının, öncül görev apartman farkında olsa bile seçtiği bir bağlamda devamlılık yürütülür.

`use_arbitrary`, bir STA 'da oluşturulan apartman duyarlı bir görevde devamlılık için varsayılan davranışı devre dışı bırakmak için kullanılabilir.

Bu yöntem yalnızca Windows Çalışma Zamanı uygulamalar tarafından kullanılabilir.

## <a name="use_current"></a>use_current

Geçerli yürütme bağlamını temsil eden bir görev devamlılık bağlamı nesnesi döndürür.

```cpp
static task_continuation_context use_current();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli yürütme bağlamı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Devamlılıkların doğru grupta yürütülebilmesi için çağıranın Windows Çalışma Zamanı bağlamını yakalar.

`use_current` tarafından döndürülen değer, öncül görevin apartman farkında olup olmamasına bakılmaksızın devamlılığın yakalanan bağlamda (STA vs MTA) yürütülmesi gerektiğini göstermek için kullanılabilir. Apartment Aware görevi, bir Windows Çalışma Zamanı `IAsyncInfo` arabirimini veya bu tür bir görevden gelen bir görevi sarmalayan bir görevdir.

Bu yöntem yalnızca Windows Çalışma Zamanı uygulamalar tarafından kullanılabilir.

## <a name="use_default"></a>use_default

Varsayılan görev devamlılık bağlamını oluşturur.

```cpp
static task_continuation_context use_default();
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan devamlılık bağlamı.

### <a name="remarks"></a>Açıklamalar

`then` yöntemini çağırdığınızda bir devamlılık bağlamı belirtmezseniz varsayılan bağlam kullanılır. Windows 7 ve sonraki Windows uygulamalarında ve Windows 8 ve üzeri sürümlerde masaüstü uygulamaları, çalışma zamanı, görev devamlılıklarının nerede yürütüleceğini belirler. Ancak, bir Windows Çalışma Zamanı uygulamasında, bir grup için bir görevde devamlılık için varsayılan devamlılık bağlamı, `then` çağrıldığı apartman olur.

Apartment Aware görevi, bir Windows Çalışma Zamanı `IAsyncInfo` arabirimini veya bu tür bir görevden gelen bir görevi sarmalayan bir görevdir. Bu nedenle, Windows Çalışma Zamanı STA 'da bir grup duyarlı görevde devamlılık zamanladıysanız, devamlılık bu STA yürütülür.

Grubu kullanmayan bir görevde devamlılık, çalışma zamanının seçtiği bir bağlamda yürütülür.

## <a name="use_synchronous_execution"></a>task_continuation_context:: use_synchronous_execution

Zaman uyumlu Yürütme bağlamını temsil eden bir görev devamlılık bağlamı nesnesi döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
static task_continuation_context use_synchronous_execution();
```

### <a name="return-value"></a>Dönüş Değeri

Zaman uyumlu yürütme bağlamı.

### <a name="remarks"></a>Açıklamalar

`use_synchronous_execution` yöntemi, devam görevini bağlam üzerinde zaman uyumlu olarak çalıştırmaya zorlar ve bu, öncül görevinin tamamlanmasına neden olur.

Devamlılık ekli olduğunda öncül görevi zaten tamamlanırsa devamlılık, devamlılığı bağlayan bağlamda zaman uyumlu olarak çalışır.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
