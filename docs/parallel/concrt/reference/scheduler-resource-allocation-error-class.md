---
title: scheduler_resource_allocation_error Sınıfı
ms.date: 11/04/2016
f1_keywords:
- scheduler_resource_allocation_error
- CONCRT/concurrency::scheduler_resource_allocation_error
- CONCRT/concurrency::scheduler_resource_allocation_error::scheduler_resource_allocation_error
- CONCRT/concurrency::scheduler_resource_allocation_error::get_error_code
helpviewer_keywords:
- scheduler_resource_allocation_error class
ms.assetid: 8b40449a-7abb-4d0a-bb85-c0e9a495ae97
ms.openlocfilehash: 7f7254306253aabc33f46694f3da16734e6efccf
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57276500"
---
# <a name="schedulerresourceallocationerror-class"></a>scheduler_resource_allocation_error Sınıfı

Bu sınıf, eşzamanlılık çalışma zamanı içinde kritik bir kaynak almak için bir hata nedeniyle verilen bir özel durumu anlatmaktadır.

## <a name="syntax"></a>Sözdizimi

```
class scheduler_resource_allocation_error : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[scheduler_resource_allocation_error](#ctor)|Fazla Yüklendi. Oluşturur bir `scheduler_resource_allocation_error` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[get_error_code](#get_error_code)|Özel duruma neden oldu hata kodu döndürür.|

## <a name="remarks"></a>Açıklamalar

Eşzamanlılık Çalışma zamanı içinde işletim sistemi çağrısı başarısız olduğunda bu durum genellikle oluşturulur. Normalde Win32 yöntemin çağrısından döndürülen hata kodu `GetLastError` türü bir değere dönüştürülür `HRESULT` ve kullanılarak alınabilir `get_error_code` yöntemi.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`scheduler_resource_allocation_error`

## <a name="requirements"></a>Gereksinimler

**Başlık:** concrt.h

**Namespace:** eşzamanlılık

##  <a name="get_error_code"></a> get_error_code

Özel duruma neden oldu hata kodu döndürür.

```
HRESULT get_error_code() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`HRESULT` Özel duruma neden olan hata değeri.

##  <a name="ctor"></a> scheduler_resource_allocation_error

Oluşturur bir `scheduler_resource_allocation_error` nesne.

```
scheduler_resource_allocation_error(
    _In_z_ const char* _Message,
    HRESULT _Hresult) throw();

explicit _CRTIMP scheduler_resource_allocation_error(
    HRESULT _Hresult) throw();
```

### <a name="parameters"></a>Parametreler

*İl_eti*<br/>
Hatanın açıklayıcı bir iletisi.

*_Hresult*<br/>
`HRESULT` Özel duruma neden olan hata değeri.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
