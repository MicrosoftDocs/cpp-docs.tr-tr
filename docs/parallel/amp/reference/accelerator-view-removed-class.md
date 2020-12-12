---
description: 'Hakkında daha fazla bilgi edinin: accelerator_view_removed sınıfı'
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
ms.openlocfilehash: 86a5b89d3b8065bccd8eec8b10bade9ed26d6a05
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97254501"
---
# <a name="accelerator_view_removed-class"></a>accelerator_view_removed Sınıfı

Windows zaman aşımı algılama ve kurtarma mekanizması nedeniyle temeldeki bir DirectX çağrısı başarısız olduğunda oluşturulan özel durum.

## <a name="syntax"></a>Syntax

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
|[get_view_removed_reason](#get_view_removed_reason)|Nesnenin kaldırılma nedenini gösteren bir HRESULT hata kodu döndürür `accelerator_view` .|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`runtime_exception`

`out_of_memory`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** amprt. h

**Ad alanı:** Zamanlı

## <a name="accelerator_view_removed"></a><a name="ctor"></a> accelerator_view_removed

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

*İleti*<br/>
Hatanın açıklaması.

*view_removed_reason*<br/>
Nesnenin kaldırılma nedenini belirten bir HRESULT hata kodu `accelerator_view` .

### <a name="return-value"></a>Dönüş Değeri

Sınıfın yeni bir örneği `accelerator_view_removed` .

## <a name="get_view_removed_reason"></a><a name="get_view_removed_reason"></a> get_view_removed_reason

Nesnenin kaldırılma nedenini gösteren bir HRESULT hata kodu döndürür `accelerator_view` .

### <a name="syntax"></a>Syntax

```cpp
HRESULT get_view_removed_reason() const throw();
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
