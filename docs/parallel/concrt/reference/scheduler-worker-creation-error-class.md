---
title: scheduler_worker_creation_error Sınıfı
ms.date: 11/04/2016
f1_keywords:
- scheduler_worker_creation_error
- CONCRT/concurrency::scheduler_worker_creation_error
- CONCRT/concurrency::scheduler_worker_creation_error::scheduler_worker_creation_error
helpviewer_keywords:
- scheduler_worker_creation_error class
ms.assetid: 4aec1c3e-c32a-41b2-899d-2d898f23b3c7
ms.openlocfilehash: 66e7485787606c22aba2970dbe481a7d29e66621
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62337368"
---
# <a name="schedulerworkercreationerror-class"></a>scheduler_worker_creation_error Sınıfı

Bu sınıf, eşzamanlılık çalışma zamanı içinde çalışan yürütme bağlamı oluşturmak için bir hata nedeniyle verilen bir özel durumu anlatmaktadır.

## <a name="syntax"></a>Sözdizimi

```
class scheduler_worker_creation_error : public scheduler_resource_allocation_error;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[scheduler_worker_creation_error](#ctor)|Fazla Yüklendi. Oluşturur bir `scheduler_worker_creation_error` nesne.|

## <a name="remarks"></a>Açıklamalar

İşletim sistemi eşzamanlılık çalışma zamanı içinde gelen yürütme bağlamları oluşturmak için bir çağrı başarısız olduğunda bu durum genellikle oluşturulur. Yürütme bağlamları görevleri eşzamanlılık çalışma zamanı'nda yürütülen akışlardır. Normalde Win32 yöntemin çağrısından döndürülen hata kodu `GetLastError` türü bir değere dönüştürülür `HRESULT` ve taban sınıf yöntemi kullanılarak alınıp `get_error_code`.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

[scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md)

`scheduler_worker_creation_error`

## <a name="requirements"></a>Gereksinimler

**Başlık:** concrt.h

**Namespace:** eşzamanlılık

##  <a name="ctor"></a> scheduler_worker_creation_error

Oluşturur bir `scheduler_worker_creation_error` nesne.

```
scheduler_worker_creation_error(
    _In_z_ const char* _Message,
    HRESULT _Hresult) throw();

explicit _CRTIMP scheduler_worker_creation_error(
    HRESULT _Hresult) throw();
```

### <a name="parameters"></a>Parametreler

*İl_eti*<br/>
Hatanın açıklayıcı bir iletisi.

*_Hresult*<br/>
`HRESULT` Özel duruma neden olan hata değeri.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
