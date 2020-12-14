---
description: 'Hakkında daha fazla bilgi edinin: scheduler_resource_allocation_error sınıfı'
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
ms.openlocfilehash: 50f84cbf76d30a415e2393797baa7d6cfa1e89f9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188735"
---
# <a name="scheduler_resource_allocation_error-class"></a>scheduler_resource_allocation_error Sınıfı

Bu sınıf, Eşzamanlılık Çalışma Zamanı kritik bir kaynak alma hatası nedeniyle oluşan bir özel durumu açıklar.

## <a name="syntax"></a>Syntax

```cpp
class scheduler_resource_allocation_error : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[scheduler_resource_allocation_error](#ctor)|Fazla Yüklendi. Bir `scheduler_resource_allocation_error` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[get_error_code](#get_error_code)|Özel duruma neden olan hata kodunu döndürür.|

## <a name="remarks"></a>Açıklamalar

Bu özel durum genellikle Eşzamanlılık Çalışma Zamanı içinden işletim sistemine yapılan bir çağrı başarısız olduğunda oluşturulur. Normalde Win32 yöntemine yapılan bir çağrıdan döndürülen hata kodu, `GetLastError` türünde bir değere dönüştürülür `HRESULT` ve yöntemi kullanılarak alınabilir `get_error_code` .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`scheduler_resource_allocation_error`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="get_error_code"></a><a name="get_error_code"></a> get_error_code

Özel duruma neden olan hata kodunu döndürür.

```cpp
HRESULT get_error_code() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`HRESULT`Özel duruma neden olan hatanın değeri.

## <a name="scheduler_resource_allocation_error"></a><a name="ctor"></a> scheduler_resource_allocation_error

Bir `scheduler_resource_allocation_error` nesnesi oluşturur.

```cpp
scheduler_resource_allocation_error(
    _In_z_ const char* _Message,
    HRESULT _Hresult) throw();

explicit _CRTIMP scheduler_resource_allocation_error(
    HRESULT _Hresult) throw();
```

### <a name="parameters"></a>Parametreler

*_Message*<br/>
Hatanın açıklayıcı bir iletisi.

*_Hresult*<br/>
`HRESULT`Özel duruma neden olan hatanın değeri.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)
