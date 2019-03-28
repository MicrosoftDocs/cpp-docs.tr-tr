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
ms.openlocfilehash: 09f534a90f3191025c3ce99d07a462908387c676
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/28/2019
ms.locfileid: "58564959"
---
# <a name="acceleratorviewremoved-class"></a>accelerator_view_removed Sınıfı

Windows zaman aşımı algılama ve kurtarma mekanizmasına bağlı temel DirectX çağrısı başarısız olduğunda oluşturulan özel durum.

## <a name="syntax"></a>Sözdizimi

```
class accelerator_view_removed : public runtime_exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[accelerator_view_removed Oluşturucusu](#ctor)|Yeni bir örneğini başlatır `accelerator_view_removed` sınıfı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[get_view_removed_reason](#get_view_removed_reason)|Nedenini belirten bir HRESULT hata kodu döndürür `accelerator_view` nesnenin kaldırma.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`runtime_exception`

`out_of_memory`

## <a name="requirements"></a>Gereksinimler

**Başlık:** amprt.h

**Namespace:** Eşzamanlılık

## <a name="ctor"></a> accelerator_view_removed

Yeni bir örneğini başlatır [accelerator_view_removed](accelerator-view-removed-class.md) sınıfı.

### <a name="syntax"></a>Sözdizimi

```
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
Kaldırma nedenini belirten bir HRESULT hata kodu `accelerator_view` nesne.

### <a name="return-value"></a>Dönüş Değeri

Yeni bir örneğini `accelerator_view_removed` sınıfı.

## <a name="getviewremovedreason"></a>get_view_removed_reason

Nedenini belirten bir HRESULT hata kodu döndürür `accelerator_view` nesnenin kaldırma.

### <a name="syntax"></a>Sözdizimi

```
HRESULT get_view_removed_reason() const throw();
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
