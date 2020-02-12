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
ms.openlocfilehash: e7f2763d7244be9e5e5b006b31b97c08e213a4f2
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142761"
---
# <a name="scheduler_worker_creation_error-class"></a>scheduler_worker_creation_error Sınıfı

Bu sınıf, Eşzamanlılık Çalışma Zamanı bir çalışan yürütme bağlamı oluşturma hatası nedeniyle oluşan bir özel durumu açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
class scheduler_worker_creation_error : public scheduler_resource_allocation_error;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[scheduler_worker_creation_error](#ctor)|Fazla Yüklendi. `scheduler_worker_creation_error` nesnesi oluşturur.|

## <a name="remarks"></a>Açıklamalar

Bu özel durum genellikle Eşzamanlılık Çalışma Zamanı içinden Yürütme bağlamları oluşturmak üzere işletim sistemine yapılan bir çağrı başarısız olduğunda oluşturulur. Yürütme bağlamları Eşzamanlılık Çalışma Zamanı görevleri çalıştıran iş parçacılardır. Normalde Win32 yöntemine yapılan bir çağrıdan döndürülen hata kodu `GetLastError` `HRESULT` türünde bir değere dönüştürülür ve `get_error_code`temel sınıf yöntemi kullanılarak alınabilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

[scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md)

`scheduler_worker_creation_error`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="ctor"></a>scheduler_worker_creation_error

`scheduler_worker_creation_error` nesnesi oluşturur.

```cpp
scheduler_worker_creation_error(
    _In_z_ const char* _Message,
    HRESULT _Hresult) throw();

explicit _CRTIMP scheduler_worker_creation_error(
    HRESULT _Hresult) throw();
```

### <a name="parameters"></a>Parametreler

*_Message*<br/>
Hatanın açıklayıcı bir iletisi.

*_Hresult*<br/>
Özel duruma neden olan hatanın `HRESULT` değeri.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
