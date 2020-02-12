---
title: task_options Sınıfı (Eşzamanlılık Çalışma Zamanı)
ms.date: 11/04/2016
f1_keywords:
- ppltasks/concurrency::task_options
ms.assetid: f93d146b-70f7-46ec-8c2f-c33b8bb0af69
ms.openlocfilehash: 5f60a07d709a79f3ce4845c8fbd1c40cb2ee7328
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142538"
---
# <a name="task_options-class-concurrency-runtime"></a>task_options Sınıfı (Eşzamanlılık Çalışma Zamanı)

Bir görev oluşturmak için izin verilen seçenekleri temsil eder

## <a name="syntax"></a>Sözdizimi

```cpp
class task_options;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[task_options:: task_options Oluşturucusu (Eşzamanlılık Çalışma Zamanı)](#ctor)|Fazla Yüklendi. Görev oluşturma seçeneklerinin varsayılan listesi|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[task_options:: get_cancellation_token yöntemi (Eşzamanlılık Çalışma Zamanı)](#get_cancellation_token)|İptal belirtecini döndürür|
|[task_options:: get_continuation_context yöntemi (Eşzamanlılık Çalışma Zamanı)](#get_continuation_context)|Devamlılık bağlamını döndürür|
|[task_options:: get_scheduler yöntemi (Eşzamanlılık Çalışma Zamanı)](#get_scheduler)|Zamanlayıcıyı döndürür|
|[task_options:: has_cancellation_token yöntemi (Eşzamanlılık Çalışma Zamanı)](#has_cancellation_token)|Kullanıcı tarafından bir iptal belirtecinin belirtilmiş olup olmadığını belirtir|
|[task_options:: has_scheduler yöntemi (Eşzamanlılık Çalışma Zamanı)](#has_scheduler)|Kullanıcı tarafından bir Scheduler n 'ın belirtilmiş olup olmadığını belirtir|
|[task_options:: set_cancellation_token yöntemi (Eşzamanlılık Çalışma Zamanı)](#set_cancellation_token)|Seçeneklerde verilen belirteci ayarlar|
|[task_options:: set_continuation_context yöntemi (Eşzamanlılık Çalışma Zamanı)](#set_continuation_context)|Seçeneklerde verilen devamlılık bağlamını ayarlar|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`task_options`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** ppltasks. h

**Ad alanı:** eşzamanlılık

## <a name="get_cancellation_token"></a>task_options:: get_cancellation_token yöntemi (Eşzamanlılık Çalışma Zamanı)

İptal belirtecini döndürür

```cpp
cancellation_token get_cancellation_token() const;
```

### <a name="return-value"></a>Dönüş Değeri

## <a name="get_continuation_context"></a>task_options:: get_continuation_context yöntemi (Eşzamanlılık Çalışma Zamanı)

Devamlılık bağlamını döndürür

```cpp
task_continuation_context get_continuation_context() const;
```

### <a name="return-value"></a>Dönüş Değeri

## <a name="get_scheduler"></a>task_options:: get_scheduler yöntemi (Eşzamanlılık Çalışma Zamanı)

Zamanlayıcıyı döndürür

```cpp
scheduler_ptr get_scheduler() const;
```

### <a name="return-value"></a>Dönüş Değeri

## <a name="has_cancellation_token"></a>task_options:: has_cancellation_token yöntemi (Eşzamanlılık Çalışma Zamanı)

Kullanıcı tarafından bir iptal belirtecinin belirtilmiş olup olmadığını belirtir

```cpp
bool has_cancellation_token() const;
```

### <a name="return-value"></a>Dönüş Değeri

## <a name="has_scheduler"></a>task_options:: has_scheduler yöntemi (Eşzamanlılık Çalışma Zamanı)

Kullanıcı tarafından bir Scheduler n 'ın belirtilmiş olup olmadığını belirtir

```cpp
bool has_scheduler() const;
```

### <a name="return-value"></a>Dönüş Değeri

## <a name="set_cancellation_token"></a>task_options:: set_cancellation_token yöntemi (Eşzamanlılık Çalışma Zamanı)

Seçeneklerde verilen belirteci ayarlar

```cpp
void set_cancellation_token(cancellation_token _Token);
```

### <a name="parameters"></a>Parametreler

`_Token`

## <a name="set_continuation_context"></a>task_options:: set_continuation_context yöntemi (Eşzamanlılık Çalışma Zamanı)

Seçeneklerde verilen devamlılık bağlamını ayarlar

```cpp
void set_continuation_context(task_continuation_context _ContinuationContext);
```

### <a name="parameters"></a>Parametreler

`_ContinuationContext`

## <a name="ctor"></a>task_options:: task_options Oluşturucusu (Eşzamanlılık Çalışma Zamanı)

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

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
