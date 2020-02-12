---
title: unsupported_feature Sınıfı
ms.date: 03/27/2019
f1_keywords:
- unsupported_feature
- AMPRT/unsupported_feature
- AMPRT/Concurrency::unsupported_feature
helpviewer_keywords:
- unsupported_feature class
ms.assetid: 6b1ab917-df13-48c7-9648-7cb2465a0ff5
ms.openlocfilehash: 561f0a258943f6d7e1c0f1b5cae716592c931fbc
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127718"
---
# <a name="unsupported_feature-class"></a>unsupported_feature Sınıfı

Desteklenmeyen bir özellik kullanıldığında oluşturulan özel durum.

## <a name="syntax"></a>Sözdizimi

```cpp
class unsupported_feature : public runtime_exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[unsupported_feature Oluşturucusu](#unsupported_feature)|`unsupported_feature` özel durumunun yeni bir örneğini oluşturur.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`runtime_exception`

`unsupported_feature`

## <a name="unsupported_feature"></a>unsupported_feature

  `unsupported_feature` özel durumunun yeni bir örneğini oluşturur.

### <a name="syntax"></a>Sözdizimi

```cpp
explicit unsupported_feature(
    const char * _Message ) throw();

unsupported_feature() throw();
```

### <a name="parameters"></a>Parametreler

*_Message*<br/>
Hatanın açıklaması.

### <a name="return-value"></a>Dönüş Değeri

`unsupported_feature` nesnesi.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** amprt. h

**Ad alanı:** Zamanlı

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
