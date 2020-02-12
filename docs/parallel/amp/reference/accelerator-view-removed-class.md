---
title: accelerator_view_removed Sınıfı
ms.date: 03/27/2019
f1_keywords:
- accelerator_view_removed
- AMPRT/accelerator_view_removed
- AMPRT/Concurrency::accelerator_view_removed::accelerator_view_removed
- AMPRT/Concurrency::accelerator_view_removed::get_view_removed_reason
helpviewer_keywords:
- AMPRT/Concurrency::accelerator_view_removed::accelerator_view_removed Class
ms.assetid: 262446de-311c-454e-a5ed-e2aaced0d88a
ms.openlocfilehash: 9a3f6f349fc3103893639fe209dcf23a07ffec56
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127130"
---
# <a name="accelerator_view_removed-class"></a>accelerator_view_removed Sınıfı

Windows zaman aşımı algılama ve kurtarma mekanizması nedeniyle temeldeki bir DirectX çağrısı başarısız olduğunda oluşturulan özel durum.

## <a name="syntax"></a>Sözdizimi

```cpp
class accelerator_view_removed : public runtime_exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[accelerator_view_removed Oluşturucusu](#ctor)|`accelerator_view_removed` sınıfının yeni bir örneğini başlatır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[get_view_removed_reason](#get_view_removed_reason)|`accelerator_view` nesnenin kaldırma işleminin nedenini gösteren bir HRESULT hata kodu döndürür.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`runtime_exception`

`out_of_memory`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** amprt. h

**Ad alanı:** Zamanlı

## <a name="ctor"></a>accelerator_view_removed

[Accelerator_view_removed](accelerator-view-removed-class.md) sınıfının yeni bir örneğini başlatır.

### <a name="syntax"></a>Sözdizimi

```cpp
explicit accelerator_view_removed(
    const char * message,
    HRESULT view_removed_reason ) throw();

explicit accelerator_view_removed(
    HRESULT view_removed_reason ) throw();
```

### <a name="parameters"></a>Parametreler

*message*<br/>
Hatanın açıklaması.

*view_removed_reason*<br/>
`accelerator_view` nesnesinin kaldırılma nedenini belirten bir HRESULT hata kodu.

### <a name="return-value"></a>Dönüş Değeri

`accelerator_view_removed` sınıfının yeni bir örneği.

## <a name="get_view_removed_reason"></a>get_view_removed_reason

`accelerator_view` nesnenin kaldırma işleminin nedenini gösteren bir HRESULT hata kodu döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT get_view_removed_reason() const throw();
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
