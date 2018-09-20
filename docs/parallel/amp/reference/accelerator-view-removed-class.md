---
title: accelerator_view_removed sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- accelerator_view_removed
- AMPRT/accelerator_view_removed
- AMPRT/Concurrency::accelerator_view_removed:accelerator_view_removed
- AMPRT/Concurrency::accelerator_view_removed:get_view_removed_reason
dev_langs:
- C++
helpviewer_keywords:
- AMPRT/Concurrency::accelerator_view_removed:accelerator_view_removed Class
ms.assetid: 262446de-311c-454e-a5ed-e2aaced0d88a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e937c2f5afedf1c78a46e864ea0b081ddf18e99d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46373307"
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

**Namespace:** eşzamanlılık

## <a name="ctor"></a> accelerator_view_removed

Yeni bir örneğini başlatır [accelerator_view_removed](accelerator-view-removed-class.md) sınıfı.

### <a name="syntax"></a>Sözdizimi

```
explicit accelerator_view_removed(
    const char * _Message,
    HRESULT _View_removed_reason ) throw();

explicit accelerator_view_removed(
    HRESULT _View_removed_reason ) throw();
```

### <a name="parameters"></a>Parametreler

*İl_eti*<br/>
Hatanın açıklaması.

*_View_removed_reason*<br/>
Kaldırma nedenini belirten bir HRESULT hata kodu `accelerator_view` nesne.

### <a name="return-value"></a>Dönüş Değeri

Accelerator_view_removed sınıfı, yeni bir örneği.

## <a name="get_view_removed_reason_method"></a> get_view_removed_reason

Nedenini belirten bir HRESULT hata kodu döndürür `accelerator_view` nesnenin kaldırma.

### <a name="syntax"></a>Sözdizimi

```
HRESULT get_view_removed_reason() const throw();
```

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
