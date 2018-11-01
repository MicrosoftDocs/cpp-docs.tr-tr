---
title: task_options Sınıfı (Eşzamanlılık Çalışma Zamanı)
ms.date: 11/04/2016
f1_keywords:
- ppltasks/concurrency::task_options
ms.assetid: f93d146b-70f7-46ec-8c2f-c33b8bb0af69
ms.openlocfilehash: 78005e500e9fefae7fed6085e061af7ee4264d14
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50633109"
---
# <a name="taskoptions-class-concurrency-runtime"></a>task_options Sınıfı (Eşzamanlılık Çalışma Zamanı)

Bir görev oluşturmak için izin verilen seçenekleri temsil eder

## <a name="syntax"></a>Sözdizimi

```
class task_options;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[task_options::task_options Oluşturucusu (eşzamanlılık çalışma zamanı)](#ctor)|Fazla Yüklendi. Varsayılan görev oluşturma seçenekleri listesi|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[task_options::get_cancellation_token metodu (eşzamanlılık çalışma zamanı)](#get_cancellation_token)|İptal belirtecini döndürür|
|[task_options::get_continuation_context metodu (eşzamanlılık çalışma zamanı)](#get_continuation_context)|Devamlılık bağlamını döndürür|
|[task_options::get_scheduler metodu (eşzamanlılık çalışma zamanı)](#get_scheduler)|Zamanlayıcı döndürür|
|[task_options::has_cancellation_token metodu (eşzamanlılık çalışma zamanı)](#has_cancellation_token)|Kullanıcı tarafından bir iptal belirtecinin belirtilip belirtilmediğini gösterir.|
|[task_options::has_scheduler metodu (eşzamanlılık çalışma zamanı)](#has_scheduler)|Bir zamanlayıcı n kullanıcı tarafından belirtilip belirtilmediğini gösterir.|
|[task_options::set_cancellation_token metodu (eşzamanlılık çalışma zamanı)](#set_cancellation_token)|Seçeneklerde belirtilen belirteci ayarlar.|
|[task_options::set_continuation_context metodu (eşzamanlılık çalışma zamanı)](#set_continuation_context)|Seçeneklerde belirtilen devamlılık bağlamını ayarlar.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`task_options`

## <a name="requirements"></a>Gereksinimler

**Başlık:** ppltasks.h

**Namespace:** eşzamanlılık

##  <a name="get_cancellation_token"></a>  task_options::get_cancellation_token metodu (eşzamanlılık çalışma zamanı)

İptal belirtecini döndürür

```
cancellation_token get_cancellation_token() const;
```

### <a name="return-value"></a>Dönüş Değeri

##  <a name="get_continuation_context"></a>  task_options::get_continuation_context metodu (eşzamanlılık çalışma zamanı)

Devamlılık bağlamını döndürür

```
task_continuation_context get_continuation_context() const;
```

### <a name="return-value"></a>Dönüş Değeri

##  <a name="get_scheduler"></a>  task_options::get_scheduler metodu (eşzamanlılık çalışma zamanı)

Zamanlayıcı döndürür

```
scheduler_ptr get_scheduler() const;
```

### <a name="return-value"></a>Dönüş Değeri

##  <a name="has_cancellation_token"></a>  task_options::has_cancellation_token metodu (eşzamanlılık çalışma zamanı)

Kullanıcı tarafından bir iptal belirtecinin belirtilip belirtilmediğini gösterir.

```
bool has_cancellation_token() const;
```

### <a name="return-value"></a>Dönüş Değeri

##  <a name="has_scheduler"></a>  task_options::has_scheduler metodu (eşzamanlılık çalışma zamanı)

Bir zamanlayıcı n kullanıcı tarafından belirtilip belirtilmediğini gösterir.

```
bool has_scheduler() const;
```

### <a name="return-value"></a>Dönüş Değeri

##  <a name="set_cancellation_token"></a>  task_options::set_cancellation_token metodu (eşzamanlılık çalışma zamanı)

Seçeneklerde belirtilen belirteci ayarlar.

```
void set_cancellation_token(cancellation_token _Token);
```

### <a name="parameters"></a>Parametreler

`_Token`

##  <a name="set_continuation_context"></a>  task_options::set_continuation_context metodu (eşzamanlılık çalışma zamanı)

Seçeneklerde belirtilen devamlılık bağlamını ayarlar.

```
void set_continuation_context(task_continuation_context _ContinuationContext);
```

### <a name="parameters"></a>Parametreler

`_ContinuationContext`

##  <a name="ctor"></a>  task_options::task_options Oluşturucusu (eşzamanlılık çalışma zamanı)

Varsayılan görev oluşturma seçenekleri listesi

```
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

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
