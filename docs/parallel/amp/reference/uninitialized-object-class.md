---
title: uninitialized_object Sınıfı
ms.date: 03/27/2019
f1_keywords:
- uninitialized_object
- AMPRT/uninitialized_object
- AMPRT/Concurrency::uninitialized_object
helpviewer_keywords:
- uninitialized_object class
ms.assetid: 6ae3c4e8-64a6-4511-a158-03be197b63af
ms.openlocfilehash: ef7ded0bf925d3430b70064c4979b75e08f9cf45
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127705"
---
# <a name="uninitialized_object-class"></a>uninitialized_object Sınıfı

Başlatılmamış bir nesne kullanıldığında oluşturulan özel durum.

## <a name="syntax"></a>Sözdizimi

```cpp
class uninitialized_object : public runtime_exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[uninitialized_object Oluşturucusu](#uninitialized_object)|`uninitialized_object` sınıfının yeni bir örneğini başlatır.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`runtime_exception`

`uninitialized_object`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** amprt. h

**Ad alanı:** Zamanlı

## <a name="uninitialized_object"></a>uninitialized_object

`uninitialized_object` özel durumunun yeni bir örneğini oluşturur.

### <a name="syntax"></a>Sözdizimi

```cpp
explicit uninitialized_object(
    const char * _Message ) throw();

uninitialized_object() throw();
```

### <a name="parameters"></a>Parametreler

*_Message*<br/>
Hatanın açıklaması.

### <a name="return-value"></a>Dönüş Değeri

`uninitialized_object` özel durum nesnesi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
