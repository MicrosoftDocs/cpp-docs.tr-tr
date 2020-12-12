---
description: 'Hakkında daha fazla bilgi edinin: unsupported_feature sınıfı'
title: unsupported_feature Sınıfı
ms.date: 03/27/2019
f1_keywords:
- unsupported_feature
- AMPRT/unsupported_feature
- AMPRT/Concurrency::unsupported_feature
helpviewer_keywords:
- unsupported_feature class
ms.assetid: 6b1ab917-df13-48c7-9648-7cb2465a0ff5
ms.openlocfilehash: 22cbc193de2a42e76ead4097d1e39351693ef706
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314509"
---
# <a name="unsupported_feature-class"></a>unsupported_feature Sınıfı

Desteklenmeyen bir özellik kullanıldığında oluşturulan özel durum.

## <a name="syntax"></a>Syntax

```cpp
class unsupported_feature : public runtime_exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[unsupported_feature Oluşturucusu](#unsupported_feature)|Özel durumun yeni bir örneğini oluşturur `unsupported_feature` .|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`runtime_exception`

`unsupported_feature`

## <a name="unsupported_feature"></a><a name="unsupported_feature"></a> unsupported_feature

  Özel durumun yeni bir örneğini oluşturur `unsupported_feature` .

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

[Eşzamanlılık ad alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
