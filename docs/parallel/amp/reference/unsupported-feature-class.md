---
title: unsupported_feature Sınıfı
ms.date: 11/04/2016
f1_keywords:
- unsupported_feature
- AMPRT/unsupported_feature
- AMPRT/Concurrency::unsupported_feature
helpviewer_keywords:
- unsupported_feature class
ms.assetid: 6b1ab917-df13-48c7-9648-7cb2465a0ff5
ms.openlocfilehash: 6a742c3fd1965882c3fa72cb1fab985cd4d981d1
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57272548"
---
# <a name="unsupportedfeature-class"></a>unsupported_feature Sınıfı

Desteklenmeyen bir özellik kullanıldığında oluşturulan özel durum.

## <a name="syntax"></a>Sözdizimi

```
class unsupported_feature : public runtime_exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[unsupported_feature Oluşturucusu](#ctor)|Yeni bir örneğini oluşturur `unsupported_feature` özel durum.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`runtime_exception`

`unsupported_feature`

## <a name="unsupported_feature__ctor"></a> unsupported_feature

  Unsupported_feature özel durumunun yeni bir örneğini oluşturur.

### <a name="syntax"></a>Sözdizimi

```
explicit unsupported_feature(
    const char * _Message ) throw();

unsupported_feature() throw();
```

### <a name="parameters"></a>Parametreler

*İl_eti*<br/>
Hatanın açıklaması.

### <a name="return-value"></a>Dönüş Değeri

`unsupported_feature` Nesne.

## <a name="requirements"></a>Gereksinimler

**Başlık:** amprt.h

**Namespace:** Eşzamanlılık

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
