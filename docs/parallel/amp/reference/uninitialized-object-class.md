---
title: uninitialized_object Sınıfı
ms.date: 11/04/2016
f1_keywords:
- uninitialized_object
- AMPRT/uninitialized_object
- AMPRT/Concurrency::uninitialized_object
helpviewer_keywords:
- uninitialized_object class
ms.assetid: 6ae3c4e8-64a6-4511-a158-03be197b63af
ms.openlocfilehash: 1c431364aee0f1d1e75059abdb023ae52cf92155
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57279352"
---
# <a name="uninitializedobject-class"></a>uninitialized_object Sınıfı

Başlatılmamış bir nesne kullanıldığında oluşturulan özel durum.

## <a name="syntax"></a>Sözdizimi

```
class uninitialized_object : public runtime_exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[uninitialized_object Oluşturucusu](#ctor)|Yeni bir örneğini başlatır `uninitialized_object` sınıfı.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`runtime_exception`

`uninitialized_object`

## <a name="requirements"></a>Gereksinimler

**Başlık:** amprt.h

**Namespace:** Eşzamanlılık
## <a name="uninitialized_object__ctor"></a> unsupported_feature

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

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
