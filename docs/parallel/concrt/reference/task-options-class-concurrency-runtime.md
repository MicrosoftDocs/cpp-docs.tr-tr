---
title: task_options Sınıfı (Eşzamanlılık Çalışma Zamanı)
ms.date: 11/04/2016
f1_keywords:
- ppltasks/concurrency::task_options
ms.assetid: f93d146b-70f7-46ec-8c2f-c33b8bb0af69
ms.openlocfilehash: e79dd7979b587ae807c8984a04b79be362b03758
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368603"
---
# <a name="task_options-class-concurrency-runtime"></a>task_options Sınıfı (Eşzamanlılık Çalışma Zamanı)

Görev oluşturmak için izin verilen seçenekleri temsil eder

## <a name="syntax"></a>Sözdizimi

```cpp
class task_options;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[task_options::task_options Oluşturucu (Eşzamanlı Çalışma Zamanı)](#ctor)|Fazla Yüklendi. Görev oluşturma seçeneklerinin varsayılan listesi|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[task_options::get_cancellation_token Yöntemi (Eşzamanlı Çalışma Süresi)](#get_cancellation_token)|İptal belirteci verir|
|[task_options::get_continuation_context Yöntemi (Eşzamanlı Çalışma Zamanı)](#get_continuation_context)|Devam bağlamını verir|
|[task_options::get_scheduler Yöntemi (Eşzamanlı Çalışma Zamanı)](#get_scheduler)|Zamanlayıcıyı döndürür|
|[task_options::has_cancellation_token Yöntemi (Eşzamanlı Çalışma Zamanı)](#has_cancellation_token)|Kullanıcı tarafından iptal belirteci belirtilip belirtmediğini gösterir|
|[task_options::has_scheduler Yöntemi (Eşzamanlı Çalışma Zamanı)](#has_scheduler)|Zamanlayıcı n'nin kullanıcı tarafından belirtilip belirtilmedi|
|[task_options::set_cancellation_token Yöntemi (Eşzamanlı Çalışma Zamanı)](#set_cancellation_token)|Seçeneklerde verilen belirteci ayarlar|
|[task_options::set_continuation_context Yöntemi (Eşzamanlı Çalışma Zamanı)](#set_continuation_context)|Seçeneklerde verilen devam bağlamını ayarlar|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`task_options`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** ppltasks.h

**Ad alanı:** eşzamanlılık

## <a name="task_optionsget_cancellation_token-method-concurrency-runtime"></a><a name="get_cancellation_token"></a>task_options::get_cancellation_token Yöntemi (Eşzamanlı Çalışma Süresi)

İptal belirteci verir

```cpp
cancellation_token get_cancellation_token() const;
```

### <a name="return-value"></a>Dönüş Değeri

## <a name="task_optionsget_continuation_context-method-concurrency-runtime"></a><a name="get_continuation_context"></a>task_options::get_continuation_context Yöntemi (Eşzamanlı Çalışma Zamanı)

Devam bağlamını verir

```cpp
task_continuation_context get_continuation_context() const;
```

### <a name="return-value"></a>Dönüş Değeri

## <a name="task_optionsget_scheduler-method-concurrency-runtime"></a><a name="get_scheduler"></a>task_options::get_scheduler Yöntemi (Eşzamanlı Çalışma Zamanı)

Zamanlayıcıyı döndürür

```cpp
scheduler_ptr get_scheduler() const;
```

### <a name="return-value"></a>Dönüş Değeri

## <a name="task_optionshas_cancellation_token-method-concurrency-runtime"></a><a name="has_cancellation_token"></a>task_options::has_cancellation_token Yöntemi (Eşzamanlı Çalışma Zamanı)

Kullanıcı tarafından iptal belirteci belirtilip belirtmediğini gösterir

```cpp
bool has_cancellation_token() const;
```

### <a name="return-value"></a>Dönüş Değeri

## <a name="task_optionshas_scheduler-method-concurrency-runtime"></a><a name="has_scheduler"></a>task_options::has_scheduler Yöntemi (Eşzamanlı Çalışma Zamanı)

Zamanlayıcı n'nin kullanıcı tarafından belirtilip belirtilmedi

```cpp
bool has_scheduler() const;
```

### <a name="return-value"></a>Dönüş Değeri

## <a name="task_optionsset_cancellation_token-method-concurrency-runtime"></a><a name="set_cancellation_token"></a>task_options::set_cancellation_token Yöntemi (Eşzamanlı Çalışma Zamanı)

Seçeneklerde verilen belirteci ayarlar

```cpp
void set_cancellation_token(cancellation_token _Token);
```

### <a name="parameters"></a>Parametreler

`_Token`

## <a name="task_optionsset_continuation_context-method-concurrency-runtime"></a><a name="set_continuation_context"></a>task_options::set_continuation_context Yöntemi (Eşzamanlı Çalışma Zamanı)

Seçeneklerde verilen devam bağlamını ayarlar

```cpp
void set_continuation_context(task_continuation_context _ContinuationContext);
```

### <a name="parameters"></a>Parametreler

`_ContinuationContext`

## <a name="task_optionstask_options-constructor-concurrency-runtime"></a><a name="ctor"></a>task_options::task_options Oluşturucu (Eşzamanlı Çalışma Zamanı)

Görev oluşturma seçeneklerinin varsayılan listesi

```cpp
task_options();

task_options(
    cancellation_token _Token);

task_options(
    task_continuation_context _ContinuationContext);

task_options(
    cancellation_token _Token,
    task_continuation_context _ContinuationContext);

template<typename _SchedType>
task_options(
    std::shared_ptr<_SchedType> _Scheduler);

task_options(
    scheduler_interface& _Scheduler);

task_options(
    scheduler_ptr _Scheduler);

task_options(
    const task_options& _TaskOptions);
```

### <a name="parameters"></a>Parametreler

`_SchedType`

`_Token`

`_ContinuationContext`

`_Scheduler`

`_TaskOptions`

## <a name="see-also"></a>Ayrıca bkz.

[concurrency Ad Alanı](concurrency-namespace.md)
